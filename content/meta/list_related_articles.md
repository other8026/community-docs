+++
title = "List Related Articles"
description = "How to list related articles at the bottom of an article"

[extra]
related = ["meta/create_article.md", "meta/edit_front_page_featured_articles.md"]

+++
In order to add related articles to the bottom of an article, all you have to do is add articles to the `related` field at the top of the `.md` file for the article in question.

The `related` field is an array of strings, for example `["section_name/article1.md", "section_name/article2.md"]`. Links are listed in order, so the first link in the `related` field is the first link printed on the resulting page.

For example, this is the "front-matter" for this article:

```
+++
title = "List Related Articles"
description = "How to list related articles at the bottom of an article"

[extra]
related = ["meta/create_article.md", "meta/edit_front_page_featured_articles.md"]

+++
```