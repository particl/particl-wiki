# Particl.wiki

Hugo-based knowledge base for @particl Project


## Development

1. Clone repo
2. Install [Hugo](gohugo.io)
3. To run Hugo dev server: `hugo server -D`
4. To compile assets: `gulp`
5. To check production version locally: `hugo` and then check the result in `/public` folder


## Formatting

- Table of Contents: `{{< toc >}}`
- Buttons: `{{< button relref="/" [class="..."] >}}Text{{< /button >}}`


### Tables

```markdown
| head | head |
| ---- | ---- |
| data | data |
```

### Hints/Callouts

```go
{{< hint [info|warning|danger] >}}
**Markdown content**\
Dolor sit, sumo unique argument um no. Gracie nominal id xiv. Romanesque acclimates investiture.
 Ornateness bland it ex enc, est yeti am bongo detract re.
{{< /hint >}}
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


## Credits

Based on [@xoxys/hugo-geekdoc](https://github.com/xoxys/hugo-geekdoc)
