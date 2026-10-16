# joni.site

Personal site and blog, built with Hugo.

## Content structure

- Blog posts: `content/blog/<name>/index.md`.
- Project pages: `content/projects/<name>/index.md`.

## Media

Images and videos use standard Markdown syntax:

```md
![Example Circuit Board](media/circuit-board.webp)
![Demo Video](media/beach.webm)
```

Optional caption text:

```md
![Close-up of a printed circuit board](media/circuit-board.webp "The first Microsite prototype")
```

renders as:

```html
<figure>
  <img
    src="media/circuit-board.webp"
    alt="Close-up of a printed circuit board"
  />
  <figcaption>The first Microsite prototype</figcaption>
</figure>
```

Video extensions render as a `<video>` element.

Standalone images accept an attribute list:

```md
![A close-up of a PCB](media/circuit-board.webp)
{style="max-width:30%;float:right;"}
```

A standalone image with the `bare` class renders without a box:

```md
![A simple loading animation](media/loading-animation.gif)
{.bare style="max-width:15%;float:right;"}
```
