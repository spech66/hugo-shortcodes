# hugo-shortcodes

A collection of my [Hugo](https://gohugo.io/) shortcodes.

Additional information on each module might be found in the readme folder in that directory.

## render-link

Starting with Hugo 0.60 and the *Goldmark* parser external **links** won't open in a **new window**. The `hrefTargetBlank` from *Blackfriday* is not supported in *Goldmark*.
The render `render-link.html` shortcode will fix the problem. Put the file in `\layouts\_default\_markup` and alls urls starting with http(s) will get the `target="_blank" rel="noopener noreferrer"` properties.

Additionally this shortcode adds icons to *amazon* and *github* links to provide an example how to enhance the functionality of the shortcode even more.

## optfigure

Create a figure with title and image from the page bundle.
The image will be resized if it is larger than 600x* (you might want to match this to your maximum page width).
Optfigure will search for NAME.png or NAME.jpg automatically. Only the filename without extension is required.

```html
{{< optfigure src="logo" title="Page Logo" >}}
```

## MermaidJS

Add [Mermaid](https://mermaid-js.github.io/mermaid/#/) graph support.

The MermaidJS script is required for the shortcode to work. This should be included in the footer or end of body from the active theme. Adding a parameter to toggle this for every page is advised.
The following snippet includes the script. To active this include `mermaid: true` in the frontmatter of a page.

```
{{ if (.Params.mermaid) }}
<script async src="https://unpkg.com/mermaid@8.4.8/dist/mermaid.min.js"></script>
{{ end }}
```

Add the graph markdown by surrounding it using hugos shortcode syntax.

```
{{<mermaid>}}
graph LR
    A --> B
    B --> C
    A --> C
{{</mermaid>}}
```
