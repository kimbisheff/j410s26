# Multimedia Story Template

A self-contained HTML/CSS/JS template for building a multimedia journalism story page. Drop in your content and media files — no build tools or frameworks required.

## Features

- Fixed navigation bar with mobile hamburger menu
- Full-screen hero section with background image
- Story text section with pull quote support
- Photo slideshow gallery with prev/next controls
- Audio section with clickable speaker images (GIF/JPG rollover, click to play)
- Video player with poster image
- Optional infographic/embed section (commented out by default)
- Parallax divider images between sections
- Back-to-top button
- Responsive — mobile-friendly at 768px breakpoint

## File Structure

```
template_S26/
├── index.html
├── style.css
├── script.js
├── img/
│   ├── hero.jpg          # Hero section background
│   ├── poster.jpg        # Video thumbnail
│   ├── parallax1.jpg     # First parallax divider
│   ├── parallax2.jpg     # Second parallax divider
│   ├── parallax3.jpg     # Third parallax divider
│   ├── 1.jpg             # Slideshow photos
│   ├── 2.jpg
│   ├── 3.jpg
│   └── rollover/
│       ├── 1.gif         # Animated speaker image (default)
│       ├── 1.jpg         # Still speaker image (on hover)
│       ├── 2.gif
│       ├── 2.jpg
│       ├── 3.gif
│       └── 3.jpg
├── audio/
│   ├── 1.mp3
│   ├── 2.mp3
│   └── 3.mp3
└── video/
    └── video.mp4
```

## Customization

### Text content
Edit `index.html` directly. Each section has comments explaining what to change.

### Fonts
The template uses [Raleway](https://fonts.google.com/specimen/Raleway) (headings) and [Lora](https://fonts.google.com/specimen/Lora) (body) from Google Fonts. To swap fonts, update the `<link>` in `index.html` and the font variables in `style.css`:

```css
:root {
    --primary-font: 'Lora', Georgia, serif;
    --heading-font: 'Raleway', Arial, sans-serif;
}
```

### Colors
Edit the CSS variables at the top of `style.css`:

```css
:root {
    --accent-color: #c41e3a;   /* Red — used for borders, hover states */
    --primary-color: #1a1a1a;  /* Near-black — nav, footer, buttons */
}
```

### Background images
- **Hero:** `.hero { background-image: url('img/hero.jpg') }` in `style.css`
- **Parallax dividers:** `.parallax-1`, `.parallax-2`, `.parallax-3` in `style.css`

### Adding/removing slides
Add or remove `<div class="slide">` blocks inside `.slideshow` in `index.html`. The slide counter updates automatically on page load.

### Audio speakers
Each speaker needs:
1. An animated GIF at `img/rollover/N.gif` (shown by default)
2. A still JPG at `img/rollover/N.jpg` (shown on hover)
3. An audio file at `audio/N.mp3`

Only one audio clip plays at a time — others pause automatically.

### Optional infographic section
In `index.html`, find the commented-out `<section id="infographic">` block and remove the surrounding `<!--` / `-->` tags. Paste your Datawrapper, Flourish, or Infogram embed code where indicated.

## Usage

Open `index.html` in a browser. No server required for most features; however, some browsers block local audio/video autoplay or GIF loading from the filesystem. Use a local server (e.g. VS Code Live Server) if you encounter issues.
