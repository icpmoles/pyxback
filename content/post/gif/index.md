---
title: "Modern web GIF"
date: 2021-10-01T17:42:32+02:00
draft: false
author: "Iacopo Moles"
latex: false
tags:  [ "video", "hugo_component", "hugo-video" , "gif"]
toc: true
latex: false
---

The `hugo-video` component has a `gif` shortcode that helps supporting modern web formats to play animated images.

<!--more-->

## The Hugo Video component

You can use [this guide](https://github.com/martignoni/hugo-video) and simply putting my repo `https://github.com/icpmoles/hugo-video`.

To summarize

1. Add the `hugo-video` as a submodule to be able to get upstream changes later
   {{< highlight bash "linenos=false">}} git submodule add https://github.com/icpmoles/hugo-video.git themes/hugo-video{{< / highlight>}}
2. Add `hugo-video` as the left-most element of the `theme` list variable in your site's or theme's configuration file `config.yaml` or `config.toml`. Example, with `config.yaml`:
    {{< highlight yaml "linenos=false">}} theme: ["hugo-video", "my-theme"] {{< / highlight>}}
    or, with `config.toml`,
    {{< highlight toml "linenos=false">}} theme = ["hugo-video", "my-theme"] {{< / highlight>}}
3. Place your video file(s) in the [page bundle](https://gohugo.io/content-management/page-bundles/) of your post.
4. In your site, use the shortcode, this way, indicating the video filename __without its extension__. If your video file is `my-beautiful-loop.gif`, type this:
    {{< highlight go "linenos=false">}} {{</*  gif "my-beautiful-loop" */>}} {{< / highlight>}}
   

## Multiple Animated Picture Types

The component will include various video sources to improve browser compatibility. You just need to provide the gif with different extensions and keeping the same filename.


To summarize your folder should look like this:

{{< highlight bash "linenos=false">}}$ tree post-folder
post-folder
├── index.md
└── my-beautiful-loop.gif {{< / highlight>}}

But if you want to add poster and multiple video types you just need to:

{{< highlight bash "linenos=false">}}$ tree post-folder
post-folder
├── index.md
├── my-beautiful-loop.gif
├── my-beautiful-loop.hevc.mp4
├── my-beautiful-loop.mp4
├── my-beautiful-loop.av1.webm
└── my-beautiful-loop.webm {{< / highlight>}}



Once you prepared the file(s) you can simply use the `gif` shortcode.

 {{< highlight go "linenos=false">}} {{</*  gif "my-beautiful-loop"  */>}} {{< / highlight>}}

 {{<  gif "input"  >}} 

## Gotchas

Unfortunately hugo doesn't have ways to convert gifs to the various other formats and viceversa so you need to provide the files by yourself.

For now the only alternative format supported are the video formats from the `video` shortcode. No webp, APNG or JPEG-XL are supported for now.

To reduce the video file size remenber to remove the audio track.

Since converting for every format can be cumbersome I recommend to only convert the gifs to webm since it's a good compromise between size and [device support](https://caniuse.com/webm). A good collection of quality sizes for the variuos resolutions can be found on the [Google VP9 Guide](https://developers.google.com/media/vp9/settings/vod#ffmpeg_command_lines). Remenber to add `-an` to the command when coming from a video.

