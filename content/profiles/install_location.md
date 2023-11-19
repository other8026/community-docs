+++
title = "App Install Location"
description = "When using multiple profiles, some GrapheneOS users are curious about how the OS deals with apps, while others sometimes run into issues with apps being incompatible when installing."

[extra]
related = []
+++

One common misconception about Android and its user profiles feature is about apps and where they're installed. Many people think that apps are installed in a profile, so installs and updates in one profile cannot affect another profile. This is not the case.

In short, apps are installed _globally_, meaning if an app is installed in any profile, that app is installed in a location on the phone that is accessible to all profiles.

For example:

- Profile A installs an app called `Awesome App`, version 1. The app is not installed in any other profile, so the phone's package manager installs the app, and Profile A can see that `Awesome App` is an installed app.
- Profile B installs `Awesome App`, version 1. It's already installed, so the same app basically just becomes visible to Profile B.
- Profile C later installs a newer version of `Awesome App`, version 2. The app is updated and becomes visible to Profile C.
- Profile D tries to install an earlier version of `Awesome App`, version 1. The Package Manager cannot downgrade apps, so an error is displayed and the app doesn't show up in Profile D.

## Is data kept private between profiles?

Yes. The location where apps are installed is basically available to all profiles, however, apps don't store their data in the same location as where the app is installed. App data can be installed in any number of folders, but all within the profile running the app. This means that even though profiles share the same apps, all data is kept private within the profiles.

## Can apps see what apps are installed in other profiles?

No. Even though apps are installed in a location that all profiles can access, it's not possible for user installed apps to scan the folder to figure out which apps are installed in other profiles.