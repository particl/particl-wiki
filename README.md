# Particl.wiki

Hugo-based knowledge base for @particl Project


## Development

1. Clone repo
2. Install [Hugo](gohugo.io)
3. To run Hugo dev server: `hugo server -D`
4. To compile assets: `gulp` (one-time) or `gulp devel` (continuous)
5. To check production version locally: `hugo` and then check the result in `/public` folder


## Formatting

- Table of Contents: `{{< toc >}}`
- Buttons: `{{< button relref="/" [class="..."] >}}Text{{< /button >}}`
- For features - check (yes) `{{< yes >}}`, cross (no) `{{< no >}}`, n/a `{{< na >}}`

### Tables

```markdown
| head | head |
| ---- | ---- |
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

### Images

To include static media, either put them in `/static` folder first (only applies for global site assets) OR create a [page bundle](https://gohugo.io/content-management/page-bundles/) (in short: convert `.md` file to folder of the same name + it's content into `index.md` + put all assets to be inluded in the same folder - you can then reference them relatively to the `index.md` file).

```
{{< image src="image.png" [class="something"] [alt="desc"] [caption="caption"] >}}
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
{{< tab "macOS" >}} # macOS Content {{< /tab >}}
{{< tab "Linux" >}} # Linux Content {{< /tab >}}
{{< tab "Windows" >}} # Windows Content {{< /tab >}}
{{< /tabs >}}
```


## Notes

### Menus

Menus are defined in `data/menu/main.yml` and `../more.yml`

### TODO

- [ ] image galleries/lightboxes (Learn > Privacy > TX types)
- [ ] fix taxonomy pages (tag lists)
- [ ] link to missing/unfinished pages in footer (http://localhost:1313/tags/TODO/)
- [ ] highlight important pages (w/ "important" tag) in lists - bold? star icon?


## Credits

Based on [@xoxys/hugo-geekdoc](https://github.com/xoxys/hugo-geekdoc)
