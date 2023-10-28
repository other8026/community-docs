+++
title = "Running This Site Locally"
description = "How to run this site locally"

[extra]
related = []
+++
In order to run this site locally, whether it's to play around with it or to help contribute, you first need to download the website's files.

You can either use `git pull` to download, or download a `.zip` file from the {{ github_link( text = "GitHub") }} page by clicking the green `Code` button then `Download ZIP`, and then unzip somewhere.

After downloading the source files, install Zola following instructions on their [website](https://www.getzola.org/documentation/getting-started/installation/).

If you're just running locally in a "development" environment, just use your computer's terminal application (i.e. Windows PowerShell, MacOS Terminal, gnome-terminal, etc.) to `cd` into the folder downloaded earlier, then run `zola serve`

If you want to build the site and host it elsewhere, it's better to learn how on [Zola's website](https://www.getzola.org/documentation/getting-started/overview/).