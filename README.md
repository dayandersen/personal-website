# Personal website

Static homepage and engineering résumé for https://dandersen.net/.

## Files

- `index.html`: homepage and Person/ProfilePage structured data.
- `resume.html`: printable engineering résumé, served at `/resume` by Cloudflare Pages.
- `styles.css`: responsive layout, light/dark colors, keyboard focus, and print styles.
- `robots.txt`, `sitemap.xml`: crawl discovery for canonical public pages.
- `404.html`: actual not-found responses instead of the homepage fallback.
- `_headers`: excludes Pages aliases and repository support files from search, without blocking the custom domain.
- `blog/blog.html`: Blogger XML theme installed separately through Blogger.

## Preview and publishing

Run `python3 -m http.server 8000` locally. Python's simple server uses `/resume.html`; Cloudflare Pages serves the canonical clean URL `/resume`.
There is no build step or executable JavaScript dependency. The JSON-LD script contains data only.

The existing Cloudflare Pages Git integration deploys this repository. Publish the HTML, CSS, robots, sitemap, and headers together. The Blogger theme has a separate publishing process.

## Search verification after deployment

- Verify Google Search Console and Bing Webmaster Tools ownership, submit the sitemap, and inspect the production URLs.
- Check production robots and WAF/AI Crawl Control settings; source robots rules cannot override edge blocking.
- Verify that the custom domain has no noindex header, Pages aliases do, and unknown paths return 404.
- Public email links use Cloudflare's documented email_off comments so contact works without JavaScript.
- Search crawler access is separate from model training preferences. Do not change account-wide permissions as part of routine content edits.
- Profile data must describe visible facts. Job-location preferences are not a claim of residence.
- Track qualified inquiries and interview progression separately from pageviews and automated traffic. No analytics account or event collector is configured in this repository.
