---
title: Contribute to Wiki
subtitle: How to add your updates and new articles
slug:
weight: 0
tags:
  - Contribute
---

{{< toc >}}

## List of incomplete articles

These articles are either completely missing or just unfinished. Since other articles are linking to them, these should be written ASAP:

{{< list-articles TODO >}}

{{< hint info >}}
**To mark an article as incomplete**\
simply add a "TODO" tag in article's frontmatter (section between `---`'s on top)
{{< /hint >}}


## How to contribute

Hello contributor and thanks for your initiative!

To contribute to this Wiki, you will need just a couple of things:

1. a free **GitHub** account
2. basic knowledge of **Markdown** syntax/formatting (don't worry, it's very easy)
3. at least some familiarity with Wiki Shortcodes

Let's get through these one by one:

### Registering on GitHub

Head over to [GitHub](https://github.com) and sign up if you haven't already. GitHub is one of the most popular open source hubs, so your new account will come in handy in the future. Even our new [Particl Community Crowdfunding](https://ccs.particl.io) relies on GitHub!

### Markdown syntax

There are many Markdown tutorials online (e.g. [basic syntax](https://www.markdownguide.org/cheat-sheet) and [in-depth one](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)), so we'll skip that - refer to the linked articles instead.

Besides Markdown, we're making use of Shortcodes. For a reference on what they are and how to use them, check [Shortcode section below](#useful-shortcodes).

When in doubt about some of the formatting, check other similar pages on the Wiki how they are structured, formatted etc. No need to reinvent the wheel.

### Submitting your changes

OK, you have your GitHub account ready, you have your changes ready - what now?

{{< todo >}}


## Useful Shortcodes

Shortcodes are handy pieces of code, wrapped in special brackets, that can create more advanced elements. Here's a quick overview of available Shortcodes on this Wiki - feel free to consult this list whenever you need:

### Table of Contents

Very useful for long, structured articles. Usually added right on the top of your document:

```
{{</* toc */>}}
```


### Buttons

Useful for highlighting external links (downloads, official site/documentation etc.)

{{< button href="https://particl.io" >}}Official Particl website{{< /button >}}

```
{{</* button href="https://particl.io" */>}}Official Particl website{{</* /button */>}}
```


### Images and video

To include static media, create a [page bundle](https://gohugo.io/content-management/page-bundles/) like so:

Create a folder in the current path with the name of your article/file, move the `.md` file in it and rename it to `index.md`. So if you had an article called `example.md`, you should end up with `example/index.md`. When this is done, you can put your images/video in the `example/` folder and reference it simply via `image.png`:

```
example/
├── index.md
├── image.png
├── video.mp4
└── video.webm
```

**Images**

```
{{</* image src="<path to image>" [class="side-thumb"] [alt="desc"] [caption="caption"] */>}}

{{</* image src="image.png" class="side-thumb" alt="Send dialog in Particl Desktop" */>}}
{{</* image src="image2.png" alt="Infographic describing Particl Market orders" caption="Particl Marketplace orders" */>}}
```

- `class="side-thumb"` transforms the image into thumbnail pinned to the side (without it, image takes full width of the page)
- optional, but recommended `alt=""` attribute is used to describe what's happening in the image in text (great for accessibility, SEO)
- optional `caption=""` defines the caption of the image underneath it (if it's not provided, `alt` text is used instead)


**Video**

```
{{</* video webm="<path to webm source>" mp4="<path to mp4 source>" [alt="desc"] [caption="caption"] */>}}

{{</* video webm="video.webm" mp4="video.mp4" alt="How to install Particl Desktop" */>}}
```

- define sources to local video file via `webm=""` and `mp4=""` attributes
- `alt` and `caption` work the same as for images (see above)


### YouTube / Vimeo

Self-explanatory shortcode for including videos from either YouTube or Vimeo.

Look for the video ID in URL (the part after `?v=`), e.g.: this video's ID `https://www.youtube.com/watch?v=PRxmGh24ILU` would be `PRxmGh24ILU`.

{{< columns >}}
{{< youtube PRxmGh24ILU >}}
```
{{</* youtube PRxmGh24ILU */>}}
```
<--->
{{< vimeo 330290302 >}}
```
{{</* vimeo 330290302 */>}}
```
{{< /columns >}}


### Icons

For inserting icons from [`/static/media/icons/`](https://github.com/AllienWorks/particl-wiki/tree/master/static/media/icons) folder (second word equals to file name of the icon) e.g.:

{{< ico yes >}}
{{< ico no >}}
{{< ico linux >}}

```
{{</* ico yes */>}}
{{</* ico no */>}}
{{</* ico linux */>}}
```


### Labels

Labels are a bit of exception for the time being, but they will be eventually converted to shortcode as well:

<label type="primary">Primary label</label>
<label type="warning">Warning</label>
<label type="alert">Alert</label>
<label type="info">Info</label>

```
<label type="primary">Primary label</label>
<label type="warning">Warning</label>
<label type="alert">Alert</label>
<label type="info">Info</label>
```


### Hints

Great for highlighting some important or dangerous information - can take `info`, `warning` or `alert` parameters. You can further emphasize the first sentence/line by making it bold, followed by `\` for a line break:

{{< hint info >}}
Useful info: Dolor sit, sumo unique argument um no.
{{< /hint >}}

{{< hint alert >}}
**Dangerous info**\
Ornateness bland it ex enc, est yeti am bongo detract re!
{{< /hint >}}

```
{{</* hint info */>}}
Useful info: Dolor sit, sumo unique argument um no.
{{</* /hint */>}}

{{</* hint alert */>}}
**Dangerous info**\
Ornateness bland it ex enc, est yeti am bongo detract re!
{{</* /hint */>}}
```


### Columns

Used for splitting content into same-width columns. `<--->` is a separator placed between columns - the more of these are used, the more columns are created.

```
{{</* columns */>}}

first column

<--->

second column

{{</* /columns */>}}
```


### Tabs

{{< tabs "uniqueid" >}}

{{< tab "First" >}}
First tab
{{< /tab >}}

{{< tab "Second" >}}
Second tab
{{< /tab >}}

{{< /tabs >}}

- if multiple tab groups are present on the same page, you need to differentiate them via different `uniqueid`'s - it's best to always name the `uniqueid` semantically, e.g. "installing-particl-desktop":

```
{{</* tabs "uniqueid" */>}}

{{</* tab "First" */>}}
First tab
{{</* /tab */>}}

{{</* tab "Second" */>}}
Second tab
{{</* /tab */>}}

{{</* /tabs */>}}
```