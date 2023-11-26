+++
title = "Apps With Known Compatibility Issues"
description = "Apps With Known Compatibility Issues with GrapheneOS"

aliases = ["bad-apps"]

[extra]

related = []
+++
When doing research about GrapheneOS, some people may find inaccurate information suggesting that
many apps don't work on GrapheneOS. This just isn't true. The truth is the vast majority of apps work
great with GrapheneOS.

The emojis below mean the following:

- ✅ - The app works in general or works without listed restrictions
- ⚠️ - The app works, but only if the app is configured to run using Exploit Protection Compatibility Mode
- ❌ - The app doesn't work at all on GrapheneOS, or it has a listed restriction
- ❓ - It's unknown whether the app works as listed

If any information on this list is incorrect, please open an issue on this site's
{{ github_issues_link( text = "GitHub Issue Tracker") }}, or submit a pull request for the affected app.

---

{{ raw_html( html = "<div class='toc'>") }}
[A](#a) | [G](#g)
{{ raw_html( html = "</div>") }}

# A

{{ raw_html( html = "<div class='app-compat-list-section'>") }}
{{ app_compat_card( app_name = "AP News", package_name = "mnn.Android", version = "5.50", repo_or_download_link = "", link_host = "", description = "", works = true, general_status_icon = "✅", works_without_gms = "❌", works_installed_by_any_source = "❓", other_compatibility_comment = "" ) }}
{{ raw_html( html = "</div>") }}

# G

{{ raw_html( html = "<div class='app-compat-list-section'>") }}
{{ app_compat_card( app_name = "Google Camera", package_name = "com.google.android.GoogleCamera", version = "9.0.115.561695573.37", repo_or_download_link = "", link_host = "", description = "", works = true, general_status_icon = "⚠️", works_without_gms = "✅", works_installed_by_any_source = "✅", other_compatibility_comment = "" ) }}
{{ app_compat_card( app_name = "Google Docs", package_name = "com.google.android.apps.docs.editors.docs", version = "1.23.452.03.90", repo_or_download_link = "", link_host = "", description = "", works = true, general_status_icon = "✅", works_without_gms = "❌", works_installed_by_any_source = "❓", other_compatibility_comment = "" ) }}
{{ app_compat_card( app_name = "Google Drive", package_name = "com.google.android.apps.docs", version = "2.23.447.3.all.alldpi", repo_or_download_link = "", link_host = "", description = "", works = true, general_status_icon = "✅", works_without_gms = "❌", works_installed_by_any_source = "❓", other_compatibility_comment = "" ) }}
{{ app_compat_card( app_name = "Google Home", package_name = "com.google.android.apps.chromecast.app", version = "3.9.1.6", repo_or_download_link = "", link_host = "", description = "", works = true, general_status_icon = "✅", works_without_gms = "❌", works_installed_by_any_source = "❓", other_compatibility_comment = "" ) }}
{{ app_compat_card( app_name = "Google Sheets", package_name = "com.google.android.apps.docs.editors.sheets", version = "1.23.452.03.90", repo_or_download_link = "", link_host = "", description = "", works = true, general_status_icon = "✅", works_without_gms = "❌", works_installed_by_any_source = "❓", other_compatibility_comment = "" ) }}
{{ raw_html( html = "</div>") }}

