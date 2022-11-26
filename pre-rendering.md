---
title: 'Two Forms of Pre-rendering in NextJS'
date: '2022-11-26'
---

Next.js has two forms of pre-rendering: **Static Generation** and **Server-side Rendering**. The difference is in **when** it generates the HTML for a page.

- **Static Generation** is the pre-rendering method that generates the HTML at **build time**. The pre-rendered HTML is then _reused_ on each request.
- **Server-side Rendering** is the pre-rendering method that generates the HTML on **each request**.

Importantly, Next.js let's you **choose** which pre-rendering form to use for each page. You can create a "hybrid" Next.js app by using Static Generation for most pages and using Server-side Rendering for others.

This makes it possible for your application to perform much better with much faster loading through pre-renders.

It's recommended using **Static Generation** (with and without data) whenever possible because your page can be built once and served by CDN, which makes it much faster than having a server render the page on every request, because it will cost much more time.

You can use Static Generation for many types of pages, including:

- Marketing pages
- Blog posts
- E-commerce product listings
- Help and documentation

If the answer of the question: "Can I pre-render this page **ahead** of a user's request?" is yes, then you should choose Static Generation.

On the other hand, Static Generation is **not** a good idea if you cannot pre-render a page ahead of a user's request. Maybe your page shows frequently updated data, and the page content changes on every request.

In that case, you can use **Server-Side Rendering**. It will be slower, but the pre-rendered page will always be up-to-date. In this case, NextJS allows you to control the cache for this dynamic responses and avoid too much re-renders if the cached value is still fresh.

You also can skip pre-rendering and use client-side JavaScript to populate data.

You can found more information about this in the NextJS documentation an tutorials here [NextJS Tutorial](https://nextjs.org/learn/foundations/about-nextjs?utm_source=next-site&utm_medium=nav-cta&utm_campaign=next-website)