---
title: About
codehl: false

---


# Pixyll

Pixyll is a simple, beautiful theme for [Hugo](http://gohugo.io/).
Based on [Pixyll for Jekyll](https://github.com/johnotander/pixyll)


<a href="https://app.netlify.com/sites/pixtest/deploys"><img src="https://api.netlify.com/api/v1/badges/a971bc37-c8f3-40d0-ab1b-b28300b4a8d9/deploy-status" alt="Netlify Status"></a>
<a href="https://app.netlify.com/start/deploy?repository=https://github.com/IcpMoles/pyxback&stack=hugo"><img src="https://www.netlify.com/img/deploy/button.svg" alt="Deploy to Netlify"></a>
<a href="https://app.forestry.io/quick-start?repo=icpmoles/pyxback&engine=hugo&version=0.88.1"><img src="https://assets.forestry.io/import-to-forestry.svg" alt="Import this project into Forestry"></a>



## How to

Head to the tutorial from the [main blog](https://pyxill2.netlify.app/post/setup-guide/) to discover more.

## Features

- High Lighthouse score.
- No external dependencies.
- Minimal JS use (for the Web Share API, the AMP website and the caching in the PWA).
- Basic tag support.
- Comments powered by Staticman.
- Powerful sharing widget.
- Social links (currently only for twitter).
- Pagination support.
- AMP support.
- MathJax support.
- Homepage under 20KiB.

## Changes from Pixyll

- No more search support.
- No more internalization (i18n) support.
- Automatic dark mode with the `prefers-color-scheme` CSS media feature.
- Removed fonts hosted on Google Fonts, now they are included in the theme as a fallback if the web safe fonts are not available.
- Added Archive page.
- Comment support.
- Share page widget.
- Table of contents support.
- Basic support for Twitter Cards.
- Fixed color contrast to follow WebAIM's minimum AA guidelines.

### Example config:

```toml
baseURL = "https://example.com/"
absURL= "https://example.com"
languageCode = "en-en"
title = "Pyxill 2"

contentdir = "content"
publishdir = "public"
builddrafts = false
theme = "pyxill2"
ignoreFiles = [ "\\.db$","\\.css$"]
pygmentsUseClassic=false
pygmentsStyle="dracula"
pygmentsCodefences=true
#pygmentsOptions="linenos=table"
Paginate= 10
relativeURLs = false
canonifyURLs= true
[indexes]
  category = "categories"
  tag = "tags"

[params]
  math_library = "katex"
  toc= true
  absURL= "https://example.com"
  mainSections = ["post"]
  bg_color= "#3b4252"
  theme_color= "#4c566a"
  twitter_username = "twittersupport"
  paginate = 10
  description = "for the web scraping"
  author = "Author"
  banner= "/banner.png"
# staticman_api = "http://your-staticman-url/v2/connect/GITHUB-USERNAME/GITHUB-REPOSITORY"  Add staticman API URL to enable staticman comments https://pyxill2.netlify.app/post/staticman/ for more information
# RssUrl = "https://feeds.feedburner.com/feed for analytics" 
# google_analytics_id = "oVaXKQsxNsPoOo6UNrGbQrBTdxEOBP0qJBRMTScdg8U" (for Google Search Console ownership)
# flattr_id = "e0v7jk"  (for Flattr ownership https://flattr.com/settings/connect/domain?redirect=%2Fsettings%2Fprofile%23connections)
# payment_pointer = "$ilp.uphold.com/kk3ZPeDi34nP" (for Coil.com monetization)
# google_analytics_js = false  (to enable the JS analytics )
  js_privacy = true #uses locally hosted libraries instead of using their CDN
  footer_links = false #enables a footer navigation bar
  custom_navbar = false #makes the main navbar editable
  custom_footbar = false #maked the footbare editable 
  


[author]
  name = "The Author"
	
[outputs]
  home = ["HTML", "AMP", "RSS"]
  page = ["HTML", "AMP", "RSS"]

  
[privacy]
  [privacy.instagram]
    disable = false
    simple = true
  [privacy.twitter]
    disable = false
    enableDNT = true
    simple = true
  [privacy.vimeo]
    disable = false
    simple = true
  [privacy.youtube]
    disable = false
    privacyEnhanced = true 
    
[build]
  writeStats = true
  

[markup]
  [markup.goldmark]
    [markup.goldmark.extensions]
      definitionList = true
      footnote = true
      linkify = true
      strikethrough = true
      table = true
      taskList = true
      typographer = true
    [markup.goldmark.parser]
      attribute = true
      autoHeadingID = true
      autoHeadingIDType = "github"
    [markup.goldmark.renderer]
      hardWraps = false
      unsafe = false
      xhtml = false

[menu]

  [[menu.main]]
    name = "About"
    url = "/about/"
    weight = -90

  [[menu.main]]
    name = "Archive"
    url = "/archives/"
    weight = -100

  [[menu.main]]
    name = "Contact"
    url = "/contact/"
    weight = -110

  [[menu.main]]
    name = "Tags"
    url = "/tags/"
    weight = -120

  [[menu.footer]]
    name = "Privacy Policy"
    url = "/privacy-policy/"
    weight = -90

  [[menu.footer]]
    name = " | "
    weight = -95

  [[menu.footer]]
    name = "Credits"
    url = "/credits/"
    weight = -100

  [[menu.footer]]
    name = "  | "
    weight = -105

  [[menu.footer]]
    name = "Admin"
    url = "/netlify/"
    weight = -110


      

```
## Screenshots



{{<gallery>}}
{{<ge "mobile_light">}}
{{<ge "mobile_dark">}}
{{<ge "desktop_light.png">}}
{{<ge "desktop_dark">}}
{{</gallery>}}

## Lighthouse Score
![Lighthouse of 100](lighthouse.png)

