+++
title = "App Compatibility Page"
description = "This page goes over some details of how the App Compatibility List page is generated and how to add to it."

[extra]
related = ["app-compatibility/app-compat-list.md"]
+++
The App Compatibility List is automatically generated every time the page is built by GitHub Actions. The page is not manually created or edited because even markup is annoying to edit and formatting mistakes can just cause the page to look messed up or unprofessional. Editing configuration files is cleaner and easier. Additionally, using config files can make collaboration easier since multiple people can create pull requests with a much lower risk of there being merge conflicts.

The configuration files are found in the folder `app-compat-files` in the root of the repository and follow this format:

```
app_name: App Name
package_name: com.app.name
works: true
works_without_compat_mode: true
works_without_gms: true
works_installed_by_any_source: true
comment: Optional comment.
```

When this repository is updated, GitHub Actions automatically triggers a workflow. One of the steps is a [command line program](https://github.com/other8026/create_md_pages), which is called `create_md_pages`, is built and run to parse the config files and a new page is added to this site's `content` directory. This way any collaborators don't have to download and run `create_md_pages` themselves if they don't wish to.

`create_md_pages` has an option of creating new config files, but it's probably easier to copy the `_template.yaml` [file](https://github.com/other8026/community-docs/blob/main/app-compat-files/_template.yaml). The template file has comments, explaining the fields and what values are supported.