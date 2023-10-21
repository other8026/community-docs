+++
title = "Link to Other Articles in .md File"
description = "How to link to other pages correctly using Zola"

[extra]
related = ["meta/list_related_articles.md"]

+++
When writing articles in `.md` format, you will want to add links to other parts of the site.

Zola helps keep track of links, so we don't need to write full links, nor do we want to in case something breaks.

So, all links should be written like this: `[link text](@/section/filename.md)`.

You can consider the `@` as being an alias for `/content`.