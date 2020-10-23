---
title: External Shortcode
author: Iacopo Moles
date: 2020-10-22T13:49:04.000Z
tags:
  - Hugo
  - shortcode
  - tutorial
banner: ""
latex: false
toc: true
---
Hugo supports custom elements to incorporate snippets from other services.

<!--more-->

## Instagram

```markdown
{{</* instagram BWNjjyYFxVx */>}}
```



## Twitter

```markdown
{{</* tweet 877500564405444608 */>}}
```

Renders as:

{{< tweet 877500564405444608 >}}



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
