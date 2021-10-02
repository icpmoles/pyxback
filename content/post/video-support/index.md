---
title: "How to add native videos"
date: 2021-05-09T17:42:32+02:00
draft: false
author: "Iacopo Moles"
latex: false
tags:  [ "video", "hugo_component", "hugo-video" ]
toc: true
latex: false
---

In case you want to host your videos directly in your website without relying on Youtube or other third parties this is how to do it.

<!--more-->

## The Hugo Video component

You can use [this guide](https://github.com/martignoni/hugo-video)

To summarize

1. Add the `hugo-video` as a submodule to be able to get upstream changes later
   {{< highlight bash "linenos=false">}} git submodule add https://github.com/martignoni/hugo-video.git themes/hugo-video{{< / highlight>}}
2. Add `hugo-video` as the left-most element of the `theme` list variable in your site's or theme's configuration file `config.yaml` or `config.toml`. Example, with `config.yaml`:
    {{< highlight yaml "linenos=false">}} theme: ["hugo-video", "my-theme"] {{< / highlight>}}
    or, with `config.toml`,
    {{< highlight toml "linenos=false">}} theme = ["hugo-video", "my-theme"] {{< / highlight>}}
3. Place your video file(s) in the [page bundle](https://gohugo.io/content-management/page-bundles/) of your post.
4. In your site, use the shortcode, this way, indicating the video filename __without its extension__. If your video file is `my-beautiful-screencast.mp4`, type this:
    {{< highlight go "linenos=false">}} {{</*  video src="my-beautiful-screencast" */>}} {{< / highlight>}}
   

## Config

### Poster

If you want to use a [poster](https://www.w3schools.com/TAgs/att_video_poster.asp) you just need to place an image with an image extension in the same page folder using the same filename of the video. Continuing the example from before you will place a file called `my-beautiful-screencast.jpeg` or `my-beautiful-screencast.png` and it will show up as a video preview instead of the first frame of the video

## Multiple Video Types

The component will include various video sources to improve browser compatibility. You just need to provide the videos with different extensions and keeping the same filename.


To summarize your folder should look like this:

{{< highlight bash "linenos=false">}}$ tree post-folder
post-folder
├── index.md
└── my-beautiful-screencast.mp4 {{< / highlight>}}

But if you want to add poster and multiple video types you just need to:

{{< highlight bash "linenos=false">}}$ tree post-folder
post-folder
├── index.md
├── my-beautiful-screencast.jpeg
├── my-beautiful-screencast.hevc.mp4
├── my-beautiful-screencast.mp4
├── my-beautiful-screencast.av1.webm
└── my-beautiful-screencast.webm {{< / highlight>}}

{{< video src="input" >}}


### Width

 {{< highlight go "linenos=false">}} {{</*  video src="my-beautiful-screencast" width="600px" */>}} {{< / highlight>}}
 

{{<warning "Mobile incompatibility" >}} Be aware that a width too big may break the visualization on small size devices {{</warning>}}

{{<  video src="input" width="600px" >}} 

### Height

 {{< highlight go "linenos=false">}} {{</*  video src="my-beautiful-screencast" height="200px" */>}} {{< / highlight>}}

 {{<  video src="input" height="200px" >}} 


 {{<info "Mobile incompatibility" >}}For a better looking videoplayer:

 {{< highlight go "linenos=false">}} {{</*  video src="my-beautiful-screencast"  width=auto height="200px" */>}} {{< / highlight>}} 
 {{</info>}}



{{<  video src="input" width=auto height="200px" >}}

### Muted

 {{< highlight go "linenos=false">}} {{</*  video src="my-beautiful-screencast" muted="true" */>}} {{< / highlight>}}


{{<  video src="input" muted="true" >}} 

### Controls

 {{< highlight go "linenos=false">}} {{</*  video src="my-beautiful-screencast" controls="false" */>}} {{< / highlight>}}

{{<  video src="input" controls="false" >}} 

### Autoplay

{{<warning "Autoplay annoyance" >}} To avoid unwanted data usage and annoying sounds playing at the page opening it's better to use small videos and the muted tag {{</warning>}}


 {{< highlight go "linenos=false">}} {{</*  video src="my-beautiful-screencast" autoplay="true" */>}} {{< / highlight>}}


{{<  video src="input" autoplay="true" >}} 


### Loop

 {{< highlight go "linenos=false">}} {{</*  video src="my-beautiful-screencast" loop="true" */>}} {{< / highlight>}}

 {{<  video src="input" loop="true" >}} 

### GIF mode

By using loop, autoplay, no controls and mute we can use our video like a GIF

 {{< highlight go "linenos=false">}} {{</*  video src="my-beautiful-screencast" loop="true" autoplay="true" controls="false"  muted="true"  */>}} {{< / highlight>}}

 {{<  video src="input" loop="true" autoplay="true" controls="false"  muted="true" >}} 

We can also use the faster `gif` shortcode

 {{< highlight go "linenos=false">}} {{</*  gif "my-beautiful-screencast"  */>}} {{< / highlight>}}

 {{<  gif "input"  >}} 

{{<warning "Autoplay annoyance" >}} To avoid unwanted data usage it's better to use small compressed videos {{</warning>}}


### Preload

The `preload` tag will default to `metadata` unless specified otherwise. The other values are `none` and `auto`.

{{< highlight go "linenos=false">}} {{</*  video src="my-beautiful-screencast" preload="auto" */>}} {{< / highlight>}}
{{<  video src="input" preload="auto" >}} 


{{< highlight go "linenos=false">}} {{</*  video src="my-beautiful-screencast" preload="none" */>}} {{< / highlight>}}
{{<  video src="input" preload="none" >}} 

