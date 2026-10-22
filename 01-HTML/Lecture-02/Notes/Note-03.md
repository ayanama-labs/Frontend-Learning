# 13. Media Elements

HTML5 provides native elements for embedding **audio, video, and captions** without requiring plugins such as Flash.

---

## 13.1 `<audio>`

Used to embed audio content.

```html
<audio controls src="song.mp3"></audio>
```

### `controls`

Displays browser-provided controls such as:

- Play/pause
- Volume
- Progress
- Audio settings

Without `controls`, the user generally has no built-in way to interact with the audio.

### Common attributes

| Attribute  | Purpose                  |
| ---------- | ------------------------ |
| `controls` | Show playback controls   |
| `autoplay` | Start automatically      |
| `loop`     | Repeat continuously      |
| `muted`    | Start muted              |
| `preload`  | Hint how much to preload |

Example:

```html
<audio controls loop>
  <source src="song.mp3" type="audio/mpeg" />
</audio>
```

### `autoplay`

```html
<audio autoplay></audio>
```

Browsers commonly restrict **autoplay with sound** because it can be intrusive.

---

# 13.2 `<video>`

Used to embed video.

```html
<video controls src="movie.mp4"></video>
```

Common attributes:

```html
<video controls width="640" height="360" poster="thumbnail.jpg"></video>
```

### Important attributes

| Attribute  | Purpose                         |
| ---------- | ------------------------------- |
| `controls` | Playback controls               |
| `autoplay` | Automatically play              |
| `loop`     | Repeat                          |
| `muted`    | Start muted                     |
| `poster`   | Image displayed before playback |
| `width`    | Display width                   |
| `height`   | Display height                  |
| `preload`  | Loading hint                    |

### `poster`

```html
<video controls poster="thumbnail.jpg"></video>
```

The poster is displayed before the video starts playing.

---

# 13.3 `<source>`

`<source>` allows you to provide **multiple media formats**.

```html
<video controls>
  <source src="movie.mp4" type="video/mp4" />
  <source src="movie.webm" type="video/webm" />
</video>
```

The browser chooses a source it supports.

Similarly:

```html
<audio controls>
  <source src="song.mp3" type="audio/mpeg" />
  <source src="song.ogg" type="audio/ogg" />
</audio>
```

### Why use multiple sources?

Different browsers/platforms may support different codecs and formats.

### Important

`<source>` is generally used **inside `<audio>` or `<video>`**.

---

# 13.4 Fallback Content

You can provide fallback content for browsers that don't support the media element.

```html
<video controls>
  <source src="movie.mp4" type="video/mp4" />

  Your browser does not support video.
</video>
```

The text is fallback content.

---

# 13.5 `<track>`

`<track>` adds **text tracks** to video/audio, most commonly captions or subtitles.

```html
<video controls>
  <source src="movie.mp4" type="video/mp4" />

  <track
    kind="captions"
    src="captions.vtt"
    srclang="en"
    label="English"
    default
  />
</video>
```

### Important attributes

| Attribute | Purpose                   |
| --------- | ------------------------- |
| `kind`    | Type of text track        |
| `src`     | Location of `.vtt` file   |
| `srclang` | Track language            |
| `label`   | Human-readable track name |
| `default` | Default selected track    |

### Common `kind` values

```text
captions
subtitles
descriptions
chapters
metadata
```

---

## 13.6 WebVTT

`<track>` commonly uses **WebVTT (`.vtt`)** files.

Example:

```text
WEBVTT

00:00:01.000 --> 00:00:04.000
Welcome to the course.

00:00:05.000 --> 00:00:08.000
Today we are learning HTML.
```

### Captions vs subtitles

**Subtitles** → primarily translate or represent spoken dialogue.

**Captions** → include dialogue plus relevant audio information, e.g. `[door closes]`.

Captions are particularly important for **accessibility**.

---

# 14. Embedded Content

Embedded content allows external or graphical content to be included inside an HTML document.

Major technologies:

- `<iframe>`
- `<object>`
- `<embed>`
- SVG
- Canvas

---

# 14.1 `<iframe>`

`<iframe>` embeds another HTML document inside the current page.

```html
<iframe src="https://example.com" width="600" height="400"></iframe>
```

Common uses:

- Maps
- Videos
- External webpages
- Documents
- Widgets

For example, YouTube videos are commonly embedded using an iframe.

### Important attributes

| Attribute        | Purpose                          |
| ---------------- | -------------------------------- |
| `src`            | URL of embedded resource         |
| `width`          | Width                            |
| `height`         | Height                           |
| `title`          | Accessible description           |
| `loading="lazy"` | Delay loading until needed       |
| `allow`          | Permissions for certain features |
| `sandbox`        | Restricts iframe capabilities    |

### Accessibility

Give an iframe a meaningful `title`:

```html
<iframe src="..." title="Company location map"></iframe>
```

---

# 14.2 `<object>`

Embeds an external resource.

```html
<object
  data="document.pdf"
  type="application/pdf"
  width="600"
  height="500"
></object>
```

Historically used for:

- PDFs
- Images
- Other external resources

It can also contain fallback content.

```html
<object data="file.pdf" type="application/pdf">
  Unable to display the PDF.
</object>
```

---

# 14.3 `<embed>`

Embeds external content.

```html
<embed src="file.pdf" type="application/pdf" />
```

`<embed>` is a more direct embedding mechanism and historically had strong ties to browser plugins.

### `<object>` vs `<embed>`

For modern development, you will encounter both, but the appropriate element depends on the resource and browser support. For common modern use cases, dedicated elements such as `<img>`, `<video>`, `<audio>`, or `<iframe>` are generally preferable when applicable.

---

# 14.4 SVG Basics

**SVG = Scalable Vector Graphics**

SVG describes graphics using XML-based markup.

Unlike raster images such as JPEG/PNG, SVG graphics are **vector-based**, so they can scale without becoming pixelated.

Basic SVG:

```html
<svg width="200" height="100">
  <circle cx="50" cy="50" r="40" fill="blue" />
</svg>
```

Common SVG elements:

| Element    | Purpose        |
| ---------- | -------------- |
| `<svg>`    | SVG container  |
| `<circle>` | Circle         |
| `<rect>`   | Rectangle      |
| `<line>`   | Line           |
| `<path>`   | Complex shapes |
| `<text>`   | Text           |

### SVG advantages

- Scales without losing quality
- Great for icons and logos
- Can be styled with CSS
- Can be manipulated with JavaScript
- Usually works well for responsive graphics

SVG can also be loaded as an image:

```html
<img src="logo.svg" alt="Company logo" />
```

---

# 14.5 Canvas Introduction

`<canvas>` provides a **drawing surface** that JavaScript can manipulate.

```html
<canvas id="myCanvas" width="500" height="300"> </canvas>
```

JavaScript:

```js
const canvas = document.getElementById("myCanvas");
const ctx = canvas.getContext("2d");

ctx.fillRect(50, 50, 100, 100);
```

The browser provides a bitmap-like drawing surface, and JavaScript performs the drawing.

### Common Canvas uses

- Games
- Data visualization
- Image manipulation
- Drawing applications
- Animations
- Graphical effects

---

# 14.6 Canvas vs SVG

This distinction is important.

| Canvas                                | SVG                           |
| ------------------------------------- | ----------------------------- |
| Raster/bitmap-style drawing surface   | Vector graphics               |
| Drawing controlled mainly through JS  | Elements exist in the DOM     |
| Good for many rapidly changing pixels | Good for structured graphics  |
| Often useful for games                | Often useful for icons/charts |
| Individual shapes aren't DOM elements | Shapes are DOM elements       |
| Resolution-dependent drawing surface  | Resolution-independent        |

### Simple mental model

```text
SVG
↓
"Create shapes/elements"

Canvas
↓
"Draw pixels/graphics onto a surface"
```

---

# Quick Revision

## Media

```text
<audio>   → audio
<video>   → video
<source>  → alternative media sources
<track>   → captions/subtitles/text tracks
```

### Typical video

```html
<video controls poster="thumbnail.jpg">
  <source src="video.mp4" type="video/mp4" />

  <track
    kind="captions"
    src="captions.vtt"
    srclang="en"
    label="English"
    default
  />
</video>
```

---

## Embedded Content

```text
<iframe>  → another HTML document/page
<object>  → external resource
<embed>   → external embedded resource
<svg>     → scalable vector graphics
<canvas>  → JavaScript drawing surface
```

### Most important distinctions

```text
<iframe> → embeds another document

<svg>    → vector graphics made from elements/shapes

<canvas> → drawing surface manipulated by JavaScript

<track>  → captions/subtitles/text tracks

<source> → gives browser alternative media files
```

**One practical rule:** use the most semantic/dedicated element available. For example, use `<video>` for video, `<audio>` for audio, `<img>` for ordinary images, and `<iframe>` when you genuinely need to embed another document.
