# Static blog migration plan

## Recommendation

Create a small, dedicated Git-backed blog project for `blog.dandersen.net`, using Markdown posts and a lightweight static generator such as Eleventy. Keep the existing URL shape (`/YYYY/MM/slug.html`) so current links continue to work after the DNS cutover. Keep the portfolio in its existing Pages project and share the same visual tokens rather than coupling the two build pipelines.

## Phase 1 — Make the Blogger version a safe bridge

1. Publish the updated Blogger theme from `../blog.html`.
2. Take a Blogger XML/Google Takeout backup of posts, pages, comments, and the theme.
3. Confirm the public post list, individual posts, search, mobile layout, RSS/Atom feed, and the one historical comment.
4. Decide whether email subscription is worth retaining; do not carry the current third-party follow.it block into the static site by default.

## Phase 2 — Build the replacement without touching production

1. Create a dedicated GitHub repository and Cloudflare Pages project.
2. Add the extracted Markdown posts from `../content/` as initial content.
3. Localize the diagram image and add explicit dimensions and descriptive alt text.
4. Build the shared shell: `dayne /`, Home, Work, Projects, Contact, responsive navigation, skip link, focus states, dark/light behavior, RSS, sitemap, canonical URLs, and 404 handling.
5. Generate the original dated/slugged paths and verify every old Blogger URL against the Pages preview URL.
6. Add editorial review before republishing older technical claims, especially the mini-split electrical, refrigerant, and EPA guidance.

## Phase 3 — Cut over and close the loop

1. Deploy and smoke-test the Pages preview on desktop and mobile.
2. Add the Pages project, custom domain, and DNS record to the Pulumi-managed infrastructure.
3. Change only `blog.dandersen.net` from Blogger's Google CNAME to the Pages custom-domain target; leave the portfolio and other sites untouched.
4. Verify HTTPS, old paths, feed discovery, robots, sitemap, images, and external links.
5. Keep the Blogger blog and backup for a cooling-off period. If desired, retain the Blogspot address as an archival fallback before retiring the custom-domain mapping.

## Acceptance criteria

- All three posts render with their current canonical paths and readable typography.
- The historical comment is either preserved in the rendered archive or intentionally documented as archive-only.
- No Blogger/follow.it branding remains in the primary reading path unless deliberately chosen.
- The blog and portfolio feel like one system while retaining distinct reading and portfolio layouts.
- A Git commit, Pages deployment, and Pulumi preview provide the complete change record.
