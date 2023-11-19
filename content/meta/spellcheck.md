+++
title = "Spellcheck"
description = "About this site's automatic spell check"

[extra]
related = []
+++

One of the things that's done when the site is generated for GitHub Pages and when a new pull request is submitted is every `.md` file is checked for spelling errors using [this workflow](https://github.com/rojopolis/spellcheck-github-actions).

When submitting a pull request, all checks should pass before the pull request can be accepted. So, when the spellchecker finds a word that it mistakenly finds to be misspelled, then the word should be added to a list of words to be ignored by the spellchecker. The word list is located in the repository root, saved as {{ github_link( text = ".wordlist.txt", path = "/blob/main/.wordlist.txt" )}}. Once the word is added and the pull request is updated, then all checks should pass and the pull request can be approved.