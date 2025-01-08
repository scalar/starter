# Introduction

Welcome to your new documentation site!

Here's a little bit about how to format your markdown to get the most out of your Scalar docs.

## Headings, Titles and Front Matter

It's expected that each file only contains one `h1` heading. This will be used as the page title.
If an h1 heading is not found, the title from the front matter will be used.

```md
---
# Note: title will be overridden with the first h1 if it exists
title: Front matter Title
description: "This page was parsed using all markdown!"
---
```

## Text Decoration

Standard git markdown is supported with text decorations like **bold**, _italic_, and `code`.

> You can also provide quotes  
> ...on multiple lines

## Components

Scalar also supports a number of extended components to help you format your content.

### Buttons

::scalar-button[My Button]{href=https://scalar.com icon=solid/mail-send-envelope }

### Callouts

:::scalar-callout{ type=info }
Callouts can be used **highlight** important information
:::

### Code Blocks

Const blocks are supported with syntax highlighting.

```c++ Some Title
int b = 10;
```

### Lists

- One
- Two
- Three

1. Apples
2. Oranges
3. Bananas
   1. Are
   2. Yellow
      Asdasd

- [x] First
- [ ] Task
- [ ] Todo

### Images

![My Image](https://mdg.imgix.net/assets/images/san-juan-mountains.jpg "The Image Title")

### Embeds

::scalar-embed[Some Caption]{src=https://www.youtube.com/embed/jfKfPfyJRdk caption='Overridden Caption'}

### Fineprint

::scalar-fineprint[Some fine text in a block]{}

### Math

::scalar-math[y =\sum_{a}^{b}\int_{1}^{2}x + \Delta d \beta \models \ncong \bowtie \frac{\partial }{\partial y}]{caption='Some Caption'}
