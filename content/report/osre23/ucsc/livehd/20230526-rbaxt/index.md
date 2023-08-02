---
title: "Highlighting and Formatting Pyrope HDL"
subtitle: ""
summary:
authors: 
  - rbaxt
tags: ["osre23", uc]
categories: []
date: 2023-06-22
lastmod: 2023-06-26
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
As part of [Micro Architecture Santa Cruz (MASC)](/project/osre23/ucsc/livehd) my [proposal](https://drive.google.com/file/d/1aJIF-geNoN49zjkFS1W7yur2-rYCxhrt/view?usp=sharing) under the mentorship of Jose Renau aims to develop syntax highlighting and a vertical alignment tool for Pyrope. Pyrope is a modern hardware description language under development by MASC. Code is parsed with the [tree-sitter grammar for Pyrope](https://github.com/masc-ucsc/tree-sitter-pyrope/tree/main). I am working on developing a query file for the nvim-treesitter plugin. This gives neovim users Pyrope syntax highlighting based on the parse tree. In addition to syntax highlighting, I am working on a vertical alignment tool to improve code readability. These features will improve the usability and convenience of Pyrope.
