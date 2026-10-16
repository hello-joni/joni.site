# Microsite: Website-Secific Code

This site is built using Hugo, a fast and efficient static site generator. The
design is optimized for hosting on an ESP32-S3 microcontroller, which has
limited processing power and storage. CSS is inlined into each page at build
time, and media files are served from page bundles alongside the content.

## Design Constraints & Philosophy

- Each page inlines its CSS at build time.
- No external dependencies – No external CSS or JavaScript; media files live in
  page bundles next to the content.
- Optimized for bandwidth and storage – Pages are minified and structured for
  low-power devices.
- Minimalist yet functional – No unnecessary features; content and efficiency
  take priority.

## Features

### Blog System (`/blog/`)

- All posts are listed with automatic tag filtering.
- RSS feed available at `/blog/index.xml`.
- Previous/Next article navigation for improved reading flow.

### Media Handling

- Images and videos are referenced with standard Markdown syntax.
- A Goldmark render hook wraps media in `<figure>` and `<figcaption>`.
- Media files live in page bundles next to each post's `index.md`.

### Performance Enhancements

- Minified inline CSS for reduced page size.
- Scrollable tables for mobile-friendly display.
- Consistent visited/unvisited link colors, excluding navigation.

## Media Handling

Images and videos use standard Markdown syntax, with files stored in each
post's page bundle:

```md
![Example Circuit Board](media/circuit-board.webp)
![Demo Video](media/beach.webm)
```

A Goldmark render hook (`layouts/_default/_markup/render-image.html`) converts
each Markdown image into a `<figure>` with a `<figcaption>`, using the alt
text as the caption. Destinations ending in `.webm`, `.mp4`, `.ogv`, or
`.ogg` render as a `<video>` element.

Standalone images accept an attribute list for sizing and positioning:

```md
![A close-up of a PCB](media/circuit-board.webp) {style="max-width:30%;float:right;"}
```

## Running the Site Locally

To preview the site: `sh hugo server` Access it at `http://localhost:1313/`.

To generate a production build: `sh hugo --minify `

## Credits

This site was adapted from Hugo XMin, a minimalist theme by Yihui Xie, which
aligned well with the goal of creating a lightweight, fully static site.

- Original theme repository: [Hugo XMin](https://github.com/yihui/hugo-xmin)
- Author: Yihui Xie ([Website](https://yihui.org))
