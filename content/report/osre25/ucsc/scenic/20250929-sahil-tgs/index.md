---
title: "Scenic-RoboSuite Integration: Building the First Working Prototype"
subtitle: "A functional bridge enabling declarative manipulation scenarios with physics"
summary: "Progress update on Scenic-RoboSuite integration prototype. Status: Core interface functional, MJCF XML injection working, basic behaviors implemented, multi-robot support operational. The first working prototype bridging probabilistic scenario specification with robotic manipulation is ready for testing."
authors: 
  - sahil-tgs
tags: ["osre25", "scenic", "robosuite", "robotics", "probabilistic programming", "manipulation", "mujoco", "simulation", "gsoc", "uc", "xml", "mjcf", "prototype"]
categories: ["GSoC 2025", "Robotics", "Open Source"]
date: 2025-09-29
lastmod: 2025-09-29
featured: true
draft: false

image:
  caption: "Scenic-RoboSuite Bridge: First Working Prototype"
  focal_point: ""
  preview_only: false
---


I'm [Sahil](https://sahiltgs.super.site/), presenting the first working prototype of the Scenic-RoboSuite integration. This [project](https://sahiltgs.super.site/gsoc/uc-ospo-proposal) is being mentored by [Daniel Fremont](https://ucsc-ospo.github.io/author/daniel-fremont/) and [Eric Vin](https://ucsc-ospo.github.io/author/eric-vin/).

After months of development, we have achieved a functional prototype of the [Scenic](https://scenic-lang.org/)-[RoboSuite](https://robosuite.ai/) interface. Researchers can now write basic declarative robotic manipulation scenarios in Scenic that execute with physics simulation in RoboSuite. While still in development, the prototype demonstrates the feasibility and potential of bridging probabilistic scenario generation with detailed robot control.

## Major Achievements

### MJCF XML Injection
The interface introduces direct MJCF XML support, allowing Scenic to build RoboSuite-native manipulable objects from raw XML definitions. Users can define custom objects with complex mesh geometries, textures, and physics properties directly in their Scenic scenarios:

```scenic
dragon_xml = '''
<mujoco>
  <asset>
    <mesh file="dragon.stl" scale="0.01 0.01 0.01"/>
    <texture file="dragon_texture.png"/>
  </asset>
  <worldbody>
    <body name="object">
      <geom mesh="dragon_mesh" type="mesh"/>
    </body>
  </worldbody>
</mujoco>
'''

dragon = new CustomObject with mjcfXml dragon_xml
```

The system automatically handles collision geometry generation, joint creation for physics, and asset file resolution.

### Complex Mesh Object Support
Import and manipulate arbitrary 3D models (STL, OBJ) with automatic mesh repair and texture mapping. The interface resolves file paths relative to Scenic files, copies assets to temporary directories for MuJoCo, and converts textures (JPG to PNG) when needed. This enables using custom robotic tools, industrial parts, or any 3D model in manipulation scenarios.

### Custom Arena Definition
Define complete custom environments using MJCF XML, extending beyond RoboSuite's built-in arenas:

```scenic
custom_arena = new CustomArena with arenaXml localPath("warehouse.xml")
```

This allows creating specialized workspaces, factory floors, or research-specific environments while maintaining full physics simulation.

### Multi-Robot Support
The interface handles multiple robots operating in the same workspace:

```scenic
robot1 = new Panda at (-0.5, 0, 0)
robot2 = new UR5e at (0.5, 0, 0)
table = new Table at (0, 0, 0.425)
```

Each robot maintains independent control and can execute coordinated or individual behaviors.

### Built-in Manipulation Behaviors
Ready-to-use behaviors for immediate testing and development:

- `MoveToPosition` - Precise end-effector positioning
- `PickObject` - Automated grasping with approach and closure
- `LiftToHeight` - Controlled lifting to target heights
- `PickAndLift` - Complete pick-and-place sequence

These behaviors use Operational Space Control (OSC) for intuitive 3D movement commands.

### Extended Environment Configuration
The interface extends RoboSuite's configurability through Scenic's parameter system:

```scenic
param controller_config = {'type': 'OSC_POSITION', 'impedance': 'low'}
param camera_view = 'robot0_eye_in_hand'
param lite_physics = True  # Faster simulation for testing
```


## Example: Probabilistic Pick-and-Place

```scenic
model scenic.simulators.robosuite.model

# Randomly position cube on table
table = new Table at (0.6, 0, 0.425)
cube = new Box on table,
    with color (1, 0, 0, 1),
    with position (Uniform(-0.2, 0.2), Uniform(-0.2, 0.2), _)

# Robot adapts to random cube position
behavior AdaptivePickup():
    do PickAndLift(cube, height=1.1)

ego = new Panda at (0, 0, 0),
    with behavior AdaptivePickup()
```

Each scenario run generates a different cube position, testing the robot's adaptive capabilities.

## Challenges Overcome

### Understanding Dual Architecture Paradigms
RoboSuite and Scenic operate on fundamentally different principles. RoboSuite builds environments imperatively through MuJoCo XML composition, expecting complete scene specification upfront. Scenic generates scenes probabilistically through constraint solving, requiring geometric knowledge before simulation. Bridging these required developing a two-pass system where we first extract geometry from a temporary RoboSuite environment, update Scenic's understanding, then create the final simulation. This architectural mismatch touched every aspect of the integration, from object creation to property updates.

### Discovering and Extending ManipulationEnv
RoboSuite's documentation focuses on using pre-built tasks, not creating custom environments. Through extensive source code analysis, we discovered that `ManipulationEnv` was the key - it accepts robots as configuration while allowing customizable arenas and objects as components. This class became our foundation, but required significant extension. We implemented `ScenicManipulationEnv` to intercept Scenic's object configurations, handle dynamic arena selection (EmptyArena vs MultiTableArena based on scene content), and manage the complex initialization sequence where robots, arenas, and objects must be assembled in specific order for MuJoCo compilation.

### XML to 3D Mesh Pipeline
Converting MJCF XML to usable 3D meshes proved complex. MuJoCo uses XML to describe geometry, but Scenic needs actual mesh data for collision checking. We built a multi-stage pipeline: First, `ElementTree` parses the XML to extract mesh references and primitive definitions. Then, we handle two paths - for mesh files, we load STL/OBJ files with trimesh and apply XML-specified transformations; for primitives (boxes, cylinders), we generate meshes programmatically. The challenge intensified with composite objects - a table might have a box tabletop and four cylinder legs. We developed `ComponentExtractor` to analyze the MuJoCo scene graph, identify related geometries through naming patterns and hierarchy, and export each component as a separate GLB file with proper world transforms preserved.

### File Path Resolution Discrepancies
Scenic and RoboSuite handle file paths completely differently. Scenic uses `localPath()` for paths relative to the scenario file, while RoboSuite expects paths relative to its package structure or absolute paths. MJCF XML compounds this - mesh references can be relative to the XML file location, not the calling code. We implemented a sophisticated path resolution system: detect whether paths come from embedded XML (relative to Scenic file) or external XML files (relative to XML location), copy all referenced assets (meshes, textures) to temporary directories accessible to MuJoCo, and handle texture format conversion (JPG to PNG) when needed. This system transparently manages assets whether they're in the Scenic project, RoboSuite package, or absolute paths, making the interface truly portable.

## Impact and Applications

This bridge enables:

- **Research**: Generate diverse manipulation scenarios for robot learning algorithms
- **Testing**: Validate robotic systems against probabilistic task variations
- **Development**: Rapid prototyping of manipulation tasks without manual scene setup
- **Education**: Teach robotics concepts through declarative scenario specification

The integration makes complex robotic simulations accessible through Scenic's intuitive language while preserving RoboSuite's detailed physics and control capabilities.

## Documentation and Resources

The project includes:
- **example scenarios** demonstrating all features
- **Comprehensive STATUS.md** tracking working features and known issues
- **Technical documentation** in `docs/` covering architecture and troubleshooting
- **Mesh extraction utilities** for pre-processing and caching

## Current Status and Future Work

This prototype demonstrates that the Scenic-RoboSuite bridge is viable and functional. Basic features are working reliably:
- Single-robot manipulation scenarios execute successfully
- MJCF XML injection creates custom objects
- Pick-and-place behaviors operate consistently
- Multi-robot support functions in controlled scenarios

However, significant work remains:
- **Stability improvements**: Some features work intermittently and need refinement
- **Velocity tracking**: Full implementation awaits framework updates
- **Multi-robot coordination**: Advanced synchronization primitives needed
- **Performance optimization**: Mesh extraction and caching can be streamlined
- **Extended testing**: More diverse scenarios and edge cases need validation

The prototype serves as a proof of concept, showing that probabilistic scenario specification can successfully drive physics-based robot simulation. The architecture is sound, the core features function, and the path forward is clear.

## Conclusion

This working prototype of the Scenic-RoboSuite integration represents significant progress toward bridging probabilistic programming with robotic simulation. We've successfully demonstrated that declarative scenario specification can control detailed physics simulation, opening new possibilities for robotic system development and testing.

While not yet production-ready, the prototype provides a solid foundation for future development. Researchers can begin experimenting with basic manipulation scenarios, developers can test the interface with their use cases, and the community can contribute to making this bridge more robust and feature-complete.

The challenges overcome - from understanding dual architectures to implementing XML-to-mesh pipelines - have resulted in a functional system that validates our approach. This prototype proves that Scenic's elegant scenario language and RoboSuite's detailed physics can work together, setting the stage for a powerful new tool in robotics research and development.