---
title: External Shortcode
author: Iacopo Moles
date: 2020-10-22T13:49:04.000Z
tags:
  - Hugo
  - shortcode
  - tutorial
banner: ""
math: false
toc: true
latex: false
---
Hugo supports custom elements to incorporate snippets from other services.

<!--more-->

## Instagram

```markdown
{{</* instagram BWNjjyYFxVx */>}}
```
{{<info "Instagram problems" >}}In [October 2020](https://www.searchenginejournal.com/facebook-instagram-drop-support-for-wordpress-embeds/383847/) Instagram changed the API that Hugo used to create the embedded content causing failed builds all across the Internet, this shortcode will probably be deprecated in the future.{{</info>}}

## Twitter

```markdown
{{</* tweet 877500564405444608 */>}}
```

Renders as:

{{< tweet GoHugoIO 877500564405444608 >}}

## Vimeo

```markdown
{{</* vimeo 146022717 */>}}
```

Renders as:

{{< vimeo 146022717 >}}

## Gist

```markdown
{{</* gist spf13 7896402 */>}}
```

Renders as:

{{< gist spf13 7896402 >}}

## YouTube

```markdown
{{</* youtube w7Ft2ymGmfc */>}}
```

Renders as:

{{< youtube w7Ft2ymGmfc >}}