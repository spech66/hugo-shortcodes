# hugo-shortcodes

A collection of my [Hugo](https://gohugo.io/) shortcodes.

Additional information on each module might be found in the readme folder in that directory.

## optfigure

Create a figure with title and image from the page bundle.
The image will be resized if it is larger than 600x* (you might want to match this to your maximum page width).
Optfigure will search for NAME.png or NAME.jpg automatically. Only the filename without extension is required.

```html
{{< optfigure src="logo" title="Page Logo" >}}
```