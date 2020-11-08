+++
author = "Iacopo Moles"
banner = "/uploads/gohugoio-card.png"
date = 2020-10-22T05:31:59Z
latex = false
tags = ["syntax", "markdown", "guide", "manual"]
title = "Markdown"
toc = true

+++
Example of markdown supported by HUGO CMS:

<!--more-->

## Text type

**Bold text**

{{< highlight markdown >}}**Bold text**{{< / highlight>}}

_Italic Text_
{{< highlight markdown>}}
_Italic Text_
{{< / highlight>}}

> Quotation section
>
> > With subsection

{{< highlight markdown>}}

> Quotation section
>
> > With subsection

{{< / highlight>}}

## Headings

#### Various

###### Headings

### Sizes

{{< highlight markdown >}}

#### Various

###### Headings

### Sizes

{{< / highlight>}}

## Image

![Hugo Banner](/uploads/gohugoio-card-1.png)
{{< highlight markdown >}}![File Description](path/to/file/gohugoio-card-1.png){{< / highlight>}}

## Link

[Homepage for the CMS](https://gohugo.io/ "Hugo CMS")

{{< highlight markdown>}}[Homepage for the CMS](https://gohugo.io/ "Link description"){{< / highlight>}}

## List

* Unordered
* list
  * with
  * sublists

{{< highlight markdown>}}

* Unordered
* list
  * with
  * sublists

{{< / highlight>}}

***

1. Ordered
2. sublist
   1. with
   2. sublists

{{< highlight markdown>}}

1. Ordered
2. sublist
   1. with
   2. sublists

{{< / highlight>}}

## Code blocks

{{< highlight go "linenos=table">}}

package main

import "fmt"

func main() {
fmt.Println("hello world")
}

{{< /highlight>}}

was produced by: \[^markdown escape\]

{{< highlight markdown "linenos=table">}}

{{</*  highlight your_language "linenos=table" */>}}

package main

import "fmt"

func main() {
fmt.Println("hello world")
}
{{</*  /highlight */>}}

{{< /highlight>}}

## Footnotes

To use footnotes\[^wiki\]

{{< highlight markdown "linenos=table">}}

your text [^name of your footnote] ... your other text

.

.

.

(everywhere in your page)

[^name of your footnote]: description of your footnote

{{< / highlight>}}

[^markdown escape]: To avoid Hugo CMS from rendering your shortcodes use [this guide](https://liatas.com/posts/escaping-hugo-shortcodes/)

[^wiki]: The number things you see on every boring book or in Wikipedia

## Quote blocks

> Example of quoteblock
>
> > Nested Block

{{< highlight markdown "linenos=table">}}

> Example of quoteblock
>
> > Nested Block

{{< /highlight>}}

{{<quote green>}} Quote with green accent {{</quote>}}

{{< highlight markdown "linenos=table">}}

{{</* quote green */>}} Quote with green accent {{</* /quote */>}}

{{< /highlight>}}

The custom quote shortcode supports 5 colors:

1. red
2. green
3. yellow
4. orange
5. purple