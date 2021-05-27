---
title: "How to add native videos with subs"
date: 2021-05-09T17:42:32+02:00
draft: false
author: "Iacopo Moles"
latex: false
tags:   [ "video", "hugo_component", "hugo-video" ]
toc: false
latex: false
---

A modificaton of the [hugo-video](https://github.com/martignoni/hugo-video) component to support automatic video subtitles

<!--more-->

The component will add various subtitles automatically as long as you name them as `[video-filename].[language_code].vtt`. The subtitle should follow the [VTT format](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API) and the language code must be 2 letters.


To summarize your basic video plus subtitle folder should look like this:

{{< highlight bash "linenos=false">}}$ tree post-folder
post-folder
├── index.md
├── my-beautiful-screencast.en.vtt
└── my-beautiful-screencast.mp4 {{< / highlight>}}

If you want to add poster, multiple video types and multiple languages subtitles you just need to:

{{< highlight bash "linenos=false">}}$ tree post-folder
post-folder
├── index.md
├── my-beautiful-screencast.jpeg
├── my-beautiful-screencast.mp4
├── my-beautiful-screencast.jpeg
├── my-beautiful-screencast.en.vtt
└── my-beautiful-screencast.es.vtt {{< / highlight>}}


### Example

 {{< highlight go "linenos=false">}} {{</*  video src="my-beautiful-screencast"  */>}} {{< / highlight>}}


### Vanilla

{{< video src="input" >}}


Video credits go to the Blender Foundation for [Elephants Dream](https://orange.blender.org/)
