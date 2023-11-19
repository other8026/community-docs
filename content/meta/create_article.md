+++
title = "Create an Article"
description = "Instructions on how to create a new article"

[extra]
related = ["meta/list_related_articles.md", "meta/create_section.md"]

+++

Creating an article is very easy. All you need to do is create an `.md` file in the correct place and the site will generate the page for you.

For example, if I want to add a page to the "meta" section about creating a page, you'd just do the following:

- Go to the folder `content/meta/`
- Create a file called `create_article.md`. (The filename will be the article's slug, so pick wisely. Also, use underscores, not hyphens or spaces.)
- Write what you want the article content to be
- Add the following to the top of the file so that Zola can build the page:

```
+++
title = "Create an Article"
description = "Instructions on how to create a new article"

[extra]
related = []

+++
```

That's it. You're done.

If you want to add *optional* related pages, please refer to this [article](@/meta/list_related_articles.md).