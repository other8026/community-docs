+++
title = "Site's Software"
description = "A brief description of the software that builds this site"

[extra]
related = []

+++
This site was built using [Zola](https://www.getzola.org/), and this site's source code is on {{ github_link( text = "GitHub") }}.

This site does not store cookies or use any browser local storage, nor does it use any kind of tracking or analytics libraries. The site also doesn't fetch any external fonts, scripts, or stylesheets.

The site is automatically built and updated on GitHub when the repository's `main` branch is updated. It is then automatically deployed to GitHub Pages as a completely static site.

There are three files that are generated when the site is built, so they're not in the GitHub repository. One is the CSS that the site uses for styling. The `styles.css` file is built using the `.scss` files in the folder `sass`. The other two are called `elasticlunr.min.js`, which helps power the local search function, and `search_index.en.json`, which is the index used for searching.

The search function relies on JavaScript to work. This site should otherwise function normally even with JavaScript disabled.