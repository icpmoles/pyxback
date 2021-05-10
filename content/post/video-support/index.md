---
title: "How to add native videos"
date: 2021-05-09T17:42:32+02:00
draft: false
author: "Iacopo Moles"
latex: false
tags:  [ fill me ]
toc: true
latex: false
---

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

If you want to use a [poster](https://www.w3schools.com/TAgs/att_video_poster.asp) you just need to place an image with an image extensionin the same page folder with the same name of the video. Continuing the example from before you will place a file called `my-beautiful-screencast.jpeg` or `my-beautiful-screencast.png` and it will show up as a video preview instead of the first frame of the video


### Width

 {{< highlight go "linenos=false">}} {{</*  video src="my-beautiful-screencast" width="600px" */>}} {{< / highlight>}}

### Height

 {{< highlight go "linenos=false">}} {{</*  video src="my-beautiful-screencast" height="200px" */>}} {{< / highlight>}}


### Muted

 {{< highlight go "linenos=false">}} {{</*  video src="my-beautiful-screencast" muted="true" */>}} {{< / highlight>}}


### Controls

 {{< highlight go "linenos=false">}} {{</*  video src="my-beautiful-screencast" controls="false" */>}} {{< / highlight>}}


### Autoplay

 {{< highlight go "linenos=false">}} {{</*  video src="my-beautiful-screencast" autoplay="true" */>}} {{< / highlight>}}

### Loop

 {{< highlight go "linenos=false">}} {{</*  video src="my-beautiful-screencast" loop="true" */>}} {{< / highlight>}}

## Result

### Vanilla

{{< video src="input" >}}

### Width

{{<  video src="input" width="600px" >}} 

### Height

{{<  video src="input" height="200px" >}} 

### Muted

{{<  video src="input" muted="true" >}} 

### Controls

{{<  video src="input" controls="false" >}} 

### Autoplay

{{<  video src="input" autoplay="true" >}} 

### Loop

{{<  video src="input" loop="true" >}} 
