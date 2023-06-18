---
layout: post
title: HTTPS on a Squarespace Custom Domain
categories:
- https
- squarespace
tags: []
---

*They say it can’t be done.*

While they are true, full end-to-end encryption with a Squarespace custom domain is not supported, we can at least get a green https in the url.

Surprisingly, this is very easy with CloudFlare free flexible SSL.

<hr>

## How to get the green https:

First sign up at cloudflare.com and follow the automated setup.

Log into your registar (where you registered the domain), ensure all DNS host records were copied from here to Cloudflare, then add the CloudFlare nameservers.

Back to CloudFlare, go to Page Rules, and add the following rules:

- mydomain.com Forwarding to https://mydomain.com
- http://mydomain.com/ always use https
- http://www.mydomain.com/ always use https

**Note: CloudFlare uses somewhat weak encryption and this setup is not completely encrypted. That said, this should suffice for landing pages.**
