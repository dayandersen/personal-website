# Blogger migration workspace

This directory is a normalized, public-content extraction for planning the move away from Blogger. It is not a full Google Takeout backup and does not replace Blogger's own XML/theme backup.

## Capture

- Source blog: <https://blog.dandersen.net/>
- Posts feed: <https://blog.dandersen.net/feeds/posts/default?alt=atom&max-results=50>
- Captured: 2026-09-13
- Posts found: 3
- Comments found: 1
- External image assets found: 1

The Markdown in `../content/` preserves the post wording while removing Blogger editor markup and splitting hard-break paragraphs into readable paragraphs. The image is still referenced at its original Blogger-hosted URL until the static-site migration localizes it.

Before cutover, take the authenticated Blogger backup of posts, pages, comments, and the theme through Blogger/Google Takeout. Keep that archive outside Git if it contains account metadata or private material.
