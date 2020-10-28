+++
author = "Iacopo Moles"
banner = "/uploads/1_-_hero_image_xmab9m.jpg"
date = 2020-10-22T06:40:05Z
math = true
tags = ["MathJax", "configuration", "syntax", "latex", "Katex"]
title = "Math rendering in Pyxill 2 use"
toc = true

+++
Syntax and configuration to render math elements with the theme

<!--more-->

## Enable Math Rendering

In your FrontMatter for the page set

{{< highlight C "linenos=true">}}

math=true

{{< / highlight>}}


## Choose your math library

In your configuration file you can switch between `mathjax` or `katex` as your favourite math rendering library by changing the string value of `math_library` in the `params` section.
 
## Insert math code in your post

You can use the standard Latex syntax for inline mode and display mode:

This code:
{{< highlight  latex "linenos=false">}}
When \\(a \\ne 0\\), there are two solutions to \\(ax^2 + bx + c = 0\\) and they are:
{{< / highlight>}}

renders as: 

> When \\(a \\ne 0\\), there are two solutions to \\(ax^2 + bx + c = 0\\) and they are:

While this:

{{< highlight  latex "linenos=false">}}
...and they are: $$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$
{{< / highlight>}}

renders as: 

> ...and they are: $$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$