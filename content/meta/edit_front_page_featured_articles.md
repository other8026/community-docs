+++
title = "Edit Front Page's Featured Articles"
description = "How to edit the featured articles list"

[extra]
related = ["meta/list_related_articles.md"]

+++
The steps to edit the featured articles on the front page is very similar to the steps to add/edit suggested articles on other articles.

To do this, open the file `content/_index.md`, then add links like this:

```
[extra]
related = ["section/article1.md", "section/article2.md", "section/article3.md"]
```