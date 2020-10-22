+++
author = "Iacopo Moles"
banner = "/uploads/1_-_hero_image_xmab9m.jpg"
date = 2020-10-22T06:40:05Z
latex = true
tags = ["MathJax", "configuration", "syntax", "latex"]
title = "MathJax use"
toc = true

+++
Syntax and configuration to render math elements with the theme

<!--more-->

## Enable MathJax

In your FrontMatter for the page set

{{< highlight C "linenos=true">}}

latex=true

{{< / highlight>}}

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