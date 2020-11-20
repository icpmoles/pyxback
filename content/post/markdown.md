---
title: Markdown
author: Iacopo Moles
date: 2020-10-22T05:31:59.000Z
tags:
  - pyxill2
  - code block
  - highlight
  - code
  - quote
  - syntax
  - markdown
  - guide
  - manual
banner: /uploads/gohugoio-card.png
math: false
toc: true
latex: false
---
Example of markdown supported by HUGO CMS:

<!--more-->

## Text type

**Bold text**

{{< highlight markdown >}}**Bold text**{{< / highlight>}}

*Italic Text*
{{< highlight markdown>}}
*Italic Text*
{{< / highlight>}}

`Inline code section`
{{< highlight markdown>}}
`Inline code section`
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

- - -

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

was produced by: [^markdown escape]

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

To use footnotes[^wiki]

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

{{< highlight markdown >}}

> Example of quoteblock
>
> > Nested Block

{{< /highlight>}}

{{<quote green>}} Quote with green accent {{</quote>}}

{{< highlight markdown >}}

{{</* quote green */>}} Quote with green accent {{</* /quote */>}}

{{< /highlight>}}

The custom quote shortcode supports 6 colors:

1. red
2. green
3. yellow
4. orange
5. purple
6. blue

You can iterate through them

{{<quote green>}} Quote with green accent 

{{<quote red>}} Subquote with red accent
 
{{<quote purple>}} Keep in mind to not rely too much on color to avoid difficulties to colorblind people {{</quote>}}
{{<quote orange >}} You can use this for conversation or various graphs {{</quote>}}
{{<quote yellow >}} To create warning signs or other alert there are custom shortcodes for that
{{<quote blue >}} Blue {{</quote>}}
 {{</quote>}}

 {{</quote>}}


{{<quote yellow >}} Subquote with yellow accent {{</quote>}}

{{<quote orange >}} Subquote with orange accent {{</quote>}}

{{</quote>}}


## Alerts

There are various way to mark some important infromation for your readers, one way is to use alert messages. To describe the type of alert this theme uses a syntax similar to [Bootstrap](https://www.w3schools.com/bootstrap/bootstrap_alerts.asp) to differentiate between them:

- Danger
- Warning
- Info
- Success



### Danger

{{<danger "Danger Title" >}} This alert box indicates a dangerous or potentially negative action {{</danger>}}

{{< highlight markdown >}}

{{</* danger "Danger Title" */>}}
 This alert box indicates a dangerous or potentially negative action
{{</* / danger */>}}


{{< /highlight>}}

### Warning


{{<warning "Warning title" >}} This alert box indicates a warning that might need attention.{{</warning>}}

{{< highlight markdown >}}

{{</* warning "Warning Title" */>}}
This alert box indicates a warning that might need attention.
{{</* / warning */>}}


{{< /highlight>}}

### Info

{{<info "Info title" >}} This alert box indicates a neutral informative change or action. {{</info>}}

{{< highlight markdown >}}

{{</* info "Info Title" */>}}
 This alert box indicates a neutral informative change or action.
{{</* / info */>}}


{{< /highlight>}}

### Success

{{<success "Success title" >}}  This alert box indicates a successful or positive action. {{</success>}}

{{< highlight markdown >}}

{{</* success "Success title" */>}}
 This alert box indicates a successful or positive action.
{{</* / success */>}}


{{< /highlight>}}

### Configuration

You can edit the default symbols displayed on every type of alert by editing your config file

{{< highlight toml >}}

[params]
  [params.alert]
    warning="⚠️"
    error="❗"
    success="✔"
    info="ℹ️"

{{< /highlight>}}