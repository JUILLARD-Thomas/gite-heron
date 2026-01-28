# Gite du Heron

Static website for the Gite du Heron (Lorleau, France), designed to be hosted on GitHub Pages
under `/gite-heron/`. The site is plain HTML/CSS/JS with no build step.

## Structure

- `index.html` : Home
- `gite/`, `tarifs/`, `acces/`, `activites/`, `contact/`, `mentions-legales/` : Section pages
- `css/` : Global styles
- `images/` : Images used across the site
- `vendor/glightbox/` : Local GLightbox assets (no CDN)

## Local preview

Open `index.html` in a browser, or serve the folder with a simple static server:

```bash
python3 -m http.server
```

Then visit `http://localhost:8000/`.

## GitHub Pages paths

The site is published at `/gite-heron/`, so all links and assets use **relative paths**.
Avoid leading slashes like `/css/...` in HTML.

Examples:

```html
<!-- Root page -->
<link rel="stylesheet" href="css/styles.css">

<!-- Section page (e.g. /gite/) -->
<link rel="stylesheet" href="../css/styles.css">
```

## GLightbox (gallery)

Lightbox for the "En images" section on `gite/index.html` is powered by GLightbox.
Assets are stored locally for static hosting:

- `vendor/glightbox/glightbox.min.css`
- `vendor/glightbox/glightbox.min.js`

### Add a new image to the gallery

1. Put the image in `images/` (e.g. `images/nouvelle_photo.jpg`).
2. Add a new item in `gite/index.html` inside `.gallery-grid`:

```html
<figure class="gallery-item">
  <a href="../images/nouvelle_photo.jpg" class="glightbox" data-gallery="gite" data-title="Short caption">
    <img src="../images/nouvelle_photo.jpg" alt="Clear image description">
  </a>
</figure>
```

If you have no thumbnails, use the same file for `href` and `src`.

## Contact page

The contact page (`contact/index.html`) favors direct email contact and includes copy-to-clipboard
buttons powered by a small vanilla JS script (no external dependencies).

## License

See `LICENSE`.
