---
title: "Self Hosting Your Blog"
date: "2025-05-04T14:37:00-07:00"
updated: "2025-05-04T14:44:14-07:00"
source: "Blogger"
source_url: "https://blog.dandersen.net/2025/05/self-hosting-your-blog.html"
blogger_post_id: "5259312541006854246"
comments: 0
migration_status: "extracted"
---

There have been so many things cooking for the past year that choosing the topic for a first post is incredibly difficult.

But! I think the easiest option is to describe how we arrived at today's blogpost itself, what the setup looks like for replication purposes, and what the long-term purpose of this site will be.

This is a simple Ghost website, a well known opensource WordPress alternative, self hosted on a Raspberry Pi 4 sitting on my desk, running as a docker container.

The domain is managed by porkbun for its registrar, and was transferred to me by the lovely friend DJ. The nameservers are pointed to some Cloudflare provided options to allow management via Cloudflare.

Access to the site itself, along with TLS cert management and termination, is handled by a Cloudflare tunnel pointed at the Ghost process. The magic of these interactions are continually impressive, so much value provided for free that its turning me into a Cloudflare shill.... which leads me into some additional Cloudflare shilling!

Access to the Admin panel (`/ghost*` routes) is also managed by a Cloudflare product! Originally I was given quite the scare by a friend (Brong) about potential escalation of privilege, but after consulting my local Cloudflare expert (aolkin) I was learned in the ways of Cloudflare Access. Using that access to all of the admin paths is now blocked by 2FA using my personal email, which hopefully means we're safe 😄

The docker compose file for setting up Ghost and its associated MySQL instance + the Cloudflare tunnel will be uploaded to a GitHub repo for sharing at some point in the near future, and I'll edit this to include it.

Until then, I hope you enjoyed this simple little writeup of the process of self hosting a blog! Next posts to hopefully be less specifically technical, more monthly, and to have a note on how I setup backups to R2 🙏

Peace,

Dayne
