# Personal website

Static homepage for https://dandersen.net/.

## Files

- `index.html`: homepage content and semantic markup.
- `styles.css`: responsive layout, system light/dark colors, keyboard focus, and print styles.
- `blog/blog.html`: Blogger XML theme. It must be installed through Blogger; it is not a standalone article page. Blog posts live outside this repository.

## Local preview

From this directory, run `python3 -m http.server 8000`, then open http://localhost:8000/.

The homepage requires no build step, JavaScript, third-party stylesheets, or web fonts.

## Publishing

Publish `index.html` and `styles.css` together at the web root using the site's existing hosting process. This repository does not currently define that process. Changes to the Blogger theme are a separate publishing step.

## Editing

Keep career dates and impact metrics accurate when updating the copy. Link writing entries to individual published posts. Check narrow and wide screens, system light/dark appearance, keyboard navigation, enlarged text, and print output after layout changes.

