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

Articles tagged with "TODO" are either completely missing or just unfinished. Since other articles are linking to them, these should be written ASAP. Contributing to these is highly appreciated!

{{< button relref="/tags/TODO" >}}List of incomplete articles{{< /button >}}

{{< hint info >}}
**To mark an article as incomplete**\
simply add a "TODO" tag in article's frontmatter (section between `---`'s on top)
{{< /hint >}}


## How to contribute

Hello contributor and thanks for your initiative!

To contribute to this Wiki, you will need just a couple of things:

1. a free **GitHub** account
2. basic knowledge of **Markdown** syntax/formatting (don't worry, it's very easy)
3. at least some familiarity with Wiki [Shortcodes](#useful-shortcodes)

Let's get through these one by one:

**Registering on GitHub**

Head over to [GitHub](https://github.com) and sign up if you haven't already. GitHub is one of the most popular open source hubs, so your new account will come in handy in the future. Even our new [Particl Community Crowdfunding](https://ccs.particl.io) relies on GitHub!

**Markdown syntax**

There are many Markdown tutorials online (e.g. [basic syntax](https://www.markdownguide.org/cheat-sheet) and [in-depth one](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)), so we'll skip that - refer to the linked articles instead.

Besides Markdown, we're making use of Shortcodes. For a reference on what they are and how to use them, check [Shortcode section below](#useful-shortcodes).

When in doubt about some of the formatting, check other similar pages on the Wiki how they are structured, formatted etc. No need to reinvent the wheel.

### Editing/creating pages

This section covers editing Wiki directly from Github's built-in text editor.

{{< hint info >}}
**If you're more tech-savvy and adventurous**, you can run the Wiki locally on your system -- in that case, please refer to Wiki's [`README`]({{< repo-url >}}/blob/master/README.md) on how to run Hugo and compile everything.
{{< /hint >}}

{{< tabs "how-to-edit" >}}
{{< tab "Editing existing pages" >}}

#### Editing existing pages

1. Locate the page you would like to update directly on the Wiki
2. Click the <kbd>Edit this page</kbd> link in the upper right corner
3. This will redirect you to the [Wiki repository on GitHub]({{< repo-url >}}) and ask you to _fork the repository_ (if you haven't done that already) - click <kbd>Fork this repository</kbd> button
4. After forking, text editor will appear with the contents of the page you chose to edit
5. Now it's time to make your changes!
6. When you're done with edits, fill in the form below the editor - add some meaningful summary of your changes in the first field (if you need some more space, feel free to add longer description in the second field as well) - finish up by clicking <kbd>Propose changes</kbd> button
7. You'll be taken to the overview of your changes, click the <kbd>Create pull request</kbd> to send your changes for approval

{{< /tab >}}
{{< tab "Creating new pages" >}}

#### Creating new pages

1. If you haven't forked the Wiki repository yet, visit [Wiki's repo]({{< repo-url >}}) and click the <kbd>Fork</kbd> button in the upper right corner
2. Locate the file, where you want to create a new page -- all written content is in [`/content`]({{< repo-url >}}/tree/master/content) folder

{{< hint warning >}}
**Files are organized regarding to the Wiki structure**\
`dev` for developer docs, `learn` for informative articles, `support` for troubleshooting guides and `tutorial` for howtos and guides -- please respect this structure and choose a place for your new page accordingly!
{{< /hint >}}

3. When you have found the ideal place for your page, click the <kbd>Add file</kbd> dropdown in the top right and select <kbd>Create new file</kbd>
4. Start with name of your page (in _Name your file..._ field at the top) -- choose short, descriptive file name (use dashes `-` instead of spaces if needed)
5. Write your content in the text area below -- start by adding the frontmatter and your content -- here's a template to get you started:

```
---
title: Staking PART on your smartwatch
subtitle: Stake your coins with every step taken
slug:
weight: 5
tags:
  - staking
  - smartwatch
---

{{</* toc */>}}

Write your Markdown-formatted content here..
```

Let's go through the frontmatter here:

- it must begin and end with `---`s
- `title:` article's title shown as level 1 heading
- `subtitle:` summary of the article (shown below the heading, in Article lists and Related pages)
- `slug:` (optional, not needed in 90% of cases) used to overwrite the page's URL (URL is normally derived from file name)
- `weight:` defines position of the page in article lists and menus -- higher number = lower position
- `tags:` tags used to mark topics of the page (e.g. "staking", "Particl Desktop" etc.) -- see [list of available tags](/tags)

If you're not sure about any of these and how to fill them up, see some other existing pages -- feel free to copy-paste.

6. When you're done with edits, fill in the form below the editor - add some meaningful summary of your changes in the first field (if you need some more space, feel free to add longer description in the second field as well) - finish up by clicking <kbd>Propose changes</kbd> button
7. You'll be taken to the overview of your changes, click the <kbd>Create pull request</kbd> to send your changes for approval

{{< /tab >}}
{{< /tabs >}}

Now it's up to the Wiki maintainers to approve your PR and "merge" your changes. This will make them live on the Wiki for the general public -- great, you've made your first contribution to open source!

In case there are some issues (incorrect info submitted, broken formatting or something like that), you might be asked by Wiki maintainers to update your changes accordingly and fix what's broken. If that's the case, repeat steps 5-6 to submit additional edits, until your changes are approved and merged.


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

{{< label primary >}}Primary{{< /label >}}
{{< label warning >}}Warning{{< /label >}}
{{< label alert >}}Alert{{< /label >}}
{{< label info >}}Info{{< /label >}}

```
{{</* label primary */>}}Primary{{</* /label */>}}
{{</* label warning */>}}Warning{{</* /label */>}}
{{</* label alert */>}}Alert{{</* /label */>}}
{{</* label info */>}}Info{{</* /label */>}}
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