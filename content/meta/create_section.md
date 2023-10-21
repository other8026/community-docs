+++
title = "Create a Section"
description = "Instructions on how to create a new section"

[extra]
related = ["meta/create_article.md"]

+++
Creating a section is very easy. The steps are as follows:

- Create a new folder in the `content/` folder (be sure to use underscores, not hyphens or spaces, in the filename).
- Create a new file called `_index.md`. This file is used to configure the section.
- Populate the `_index.md` file with the following content:

```
+++
title = "Section Title"
description = "Short Section Description"
sort_by = "title"

# for weight info, see below
weight = 10

+++
A short little tidbit to explain what's in this section.
This shows up in the section pages for mobile users.
```

That's it. You're finished.

Now, you're ready to [add an article](@/meta/create_article.md) to this new section.

---

# Some configuration things:

## `sort_by`

`sort_by` has many possible values, which are explained in [Zola's documentation](https://www.getzola.org/documentation/content/section/), but I'd expect any contributors would use one of the following: `date`, `title`, or `weight`

If set to `title`, all pages in a section will be sorted alphabetically by their title.

If set to `date`, like if we wanted a kind of blog-like section, all articles should follow a filename convention. They should be named `YYYY-MM-DD_title.md`, for example `2023-12-31_happy_new_year.md`.

Setting to `weight` is a bit more of a pain to manage. If using `weight` to sort, each page has to have a `weight` set. A `weight` of 0 will be displayed higher when pages are listed together, like in the sidebar.

## `weight`

`weight` in this file tells Zola the order in which to sort sections. The `weight` variable isn't required, but not setting it means sections will be sorted (maybe?) randomly every time the site is rebuilt. So, it's probably better to include `weight`.

A `weight` of 0 is displayed highest.