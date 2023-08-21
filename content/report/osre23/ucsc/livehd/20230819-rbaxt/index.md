---
title: "Grammar, Parsers, and Queries"
subtitle: ""
summary:
authors: 
  - rbaxt
tags: ["osre23", uc]
categories: []
date: 2023-08-12
lastmod: 2023-08-12
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false
---
## Update on tree-sitter-pyrope
The pyrope hardware description language now has syntax highlighting available for neovim users. 
The [repository](https://github.com/masc-ucsc/tree-sitter-pyrope) includes a guide to installing the parser, and activating highlights.
After we have tested the syntax highlighting, a pull request will be made to the [nvim-treesitter repository](https://github.com/nvim-treesitter/nvim-treesitter).
In this post, I will outline the highlighting process and reflect on a useful feature of neovim.

### Syntax Trees
The pyrope language is described by a grammar. A grammar is a set of rules that describes the allowed structure of a language.
A parser uses the grammar to generate a syntax tree. For example, consider this line of pyrope code.
```shell
var a:u32 = 0
```
Using the pyrope parser, we can get a syntax tree for this statement.
The command `tree-sitter parse file.prp` gives us the following output.
```shell
(statement [1, 0] - [1, 13]
    (assignment_or_declaration_statement [1, 0] - [1, 13]
      decl: (var_or_let_or_reg [1, 0] - [1, 3])
      lvalue: (complex_identifier [1, 4] - [1, 5]
        (identifier [1, 4] - [1, 5]))
      type: (type_cast [1, 5] - [1, 9]
        type: (primitive_type [1, 6] - [1, 9]
          (sized_integer_type [1, 6] - [1, 9])))
      operator: (assignment_operator [1, 10] - [1, 11])
      rvalue: (constant [1, 12] - [1, 13])))
```
The nvim-treesitter syntax highlighting is based on this tree structure.

### Queries
A query is an expression that selects nodes from the tree. 
For example, 
```shell
(complex_identifier (identifier))
```
matches any identifier that is the child of a complex_identifier.
Color schemes in neovim assign colors to different highlight groups. 
So, we can assign highlight groups to tree queries.
```shell
(constant) @number
```
Now, when a constant shows up in the syntax tree, it will highlight according to the @number group.
Most of the work I did on this project involved studying the pyrope grammar, and writing queries based on it. 

## neovim
The text editor [neovim](https://neovim.io/) is a popular choice among programmers. It allows advanced user control with configuration files.
It also has an active community working on plugins to extend its functionality. 
Tools such as lazyvim allow for features like code completion and file management that give neovim the same functionality as IDEs.
However, because neovim configuration is unique to each user, this may make it difficult to reproduce neovim instructions.
For example, Professor Renau was going to test pyrope syntax highlighting in neovim.
However, I did not know what configuration was necessary for him to see highlights in neovim. 
While I knew that syntax highlighting worked on my setup, I have lots of configuration files that may have contributed to that success.
There is no guarantee that Professor Renau, or other potential users, have the same neovim configuration that I do.

### NVIM_APPNAME
So, Professor Renau suggested I use the `$NVIM_APPNAME` variable to test the process on a fresh configuration.
This feature allows the user to specify the configuration files used to launch neovim.
For example, I installed [lazyvim](https://www.lazyvim.org/) to the folder `~/.config/lazy`. Then, I launched neovim with `NVIM_APPNAME=lazy nvim`.
So instead of using my default configuration from `~/.config/nvim`, the lazyvim configuration was used. 
This allowed me to use a neovim instance that was unaffected by my configuration files.
I was able to preview the process of setting up syntax highlighting from the perspective of a lazyvim user.
Similarly, the process can be done with an empty folder to mimic a brand new neovim installation
The point is, configuration files can impact reproducibility in neovim.
However, this feature allows us to bypass our individual configurations, and create reproducible guidelines.

### Conclusion
In conclusion, most of my work involved writing queries for the pyrope tree-sitter grammar.
This was for the purpose of syntax highlighting in neovim.
However, an important part of any open source project is communicating the results and providing documentation.
The NVIM_APPNAME feature helps view neovim from the perspective of different users, which helps for writing useful documentation.
