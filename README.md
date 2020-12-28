# deno_website2

[![Build Status](https://github.com/denoland/deno_website2/workflows/ci/badge.svg?branch=master&event=push)](https://github.com/denoland/deno_website2/actions)

Voici le code du site https://deno.land/

Il consiste en deux parties :

1. Un Cloudflare Worker
2. Une application Next.js hébergée sur Vercel

Nous voulons fournir des URLs jolies et explicites pour les modules qui seront utilisés par Deno.
Par example : https://deno.land/std/http/server.ts

When we request this file inside of Deno, we need to receive back the raw
content of the file. However, when we visit that URL in the browser we want to
see a pretty HTML file with syntax highlighting.

To accomplish this the Cloudflare Worker looks at the "Accept:" HTTP header to
see if the client wants HTML or not. If it does want HTML, we simply proxy the
request to Vercel. (We use Vercel because of their nice GitHub integration.)

## History

This is a rewrite of the Deno website it will combine the code in
https://github.com/denoland/deno/tree/f96aaa802b245c8b3aeb5d57b031f8a55bb07de2/website
and https://github.com/denoland/registry and have faster deployment.

This is written in React / TailwindCSS / Vercel / CloudFlare Workers. Not in
Deno. Ideally this could be ported to Deno at some point but we are in need of a
new website and dogfooding takes too long. We hope to see this code ported to
Deno with minimal developer flow interrupted (in particular, we need the ability
to listen for FS events and reload the web server).

## Image License

These Deno images are distributed under the MIT license (public domain and free
for use).

- [A graphic for the v1 blog post by @hashrock](https://deno.land/v1.jpg)
