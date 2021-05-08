# Particl.wiki

Hugo-based knowledge base for @particl Project


## Development

1. Clone repo
2. Install [Hugo](https://gohugo.io/getting-started/installing/), [Yarn](https://yarnpkg.com/getting-started/install) and do `yarn install` to fetch dependenciesnvm 
3. To run Hugo dev server: `yarn hugo`
4. To compile assets: `yarn dev` (continuous) or just `gulp` (one-time)
5. To check production version locally: `yarn build` and then check the result in `/public` folder


## Formatting

- Table of Contents: `{{< toc >}}`
- Tree ToC (list all child pages with hierarchy): `{{< tree-toc >}}`
- Buttons
  - Internal: `{{< button relref="/" [class="..."] >}}Text{{< /button >}}`
  - External: `{{< button href="/" [class="..."] >}}Text{{< /button >}}`
- Icons: `{{< ico NAME >}}` - names correspond to icon file names in `/static/media/icons/`, e.g. `{{< ico yes >}}`
- Youtube: `{{< youtube PRxmGh24ILU >}}` (`PRxmGh24ILU` stands for video ID found in it's URL)
- Vimeo: `{{< vimeo 330290302 >}}` (`330290302` stands for video ID found in it's URL)
- Labels: `{{< label primary|warning|alert|info">Label{{< /label >}}`

### Tables

```markdown
| head | head |
| ---- | ---- |
| data | data |
| data | data |
```

### Hints/Callouts

```go
{{< hint [info|warning|alert] >}}
**Markdown content**\
Dolor sit, sumo unique argument um no. Gracie nominal id xiv. Romanesque acclimates investiture.
 Ornateness bland it ex enc, est yeti am bongo detract re.
{{< /hint >}}
```

### Images & video

To include static media, either put them in `/static` folder first (only applies for global site assets) OR create a [page bundle](https://gohugo.io/content-management/page-bundles/) (in short: convert `.md` file to folder of the same name + it's content into `index.md` + put all assets to be inluded in the same folder - you can then reference them relatively to the `index.md` file).

```
{{< image src="image.png" class="side-thumb" [alt="desc"] [caption="caption"] >}}

{{< video webm="video.webm" mp4="video.mp4" [alt="desc"] [caption="caption"] >}}
```

### List tagged articles

To get a list of articles tagged with e.g. "important" use:

```
{{< list-articles important >}}
```

### Columns

```
{{< columns >}}
  # first column
<--->
  # second column
{{< /columns >}}
```

### Tabs

```go
{{< tabs "uniqueid" >}}
{{< tab "Windows" >}} # Windows Content {{< /tab >}}
{{< tab "macOS" >}} # macOS Content {{< /tab >}}
{{< tab "Linux" >}} # Linux Content {{< /tab >}}
{{< /tabs >}}
```


## Notes

- since this Hugo-based wiki has slightly different file/folder and link structure than the former Dokuwiki, links to pages that didn't match are solved via `aliases` parameter in articles' frontmatter

### Menus

Menus are defined in `data/menu/main.yml` and `../more.yml`

### TODO

- [ ] image galleries/lightboxes (Learn > Privacy > TX types)
- [ ] Matomo analytics?

## Credits

Based on [@xoxys/hugo-geekdoc](https://github.com/xoxys/hugo-geekdoc)
