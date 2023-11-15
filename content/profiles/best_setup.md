+++
title = "Best User Profile Setup"
description = "One of the most common questions we get is about profile setups. Here are some thoughts."

[extra]
related = []
+++
One of the most common questions posed by new (and even sometimes not so new) community members is about the perfect profile setup.

Profiles are probably one of GrapheneOS's most commonly used features. Although the profile feature is added by AOSP, GrapheneOS has [improved them](https://grapheneos.org/features#improved-user-profiles).

The answer to the question of what is the best profile setup is that there is no answer. Each individual person has their own specific needs and use their phones in their own way. It's impossible for anyone to say their profile setup is the best and all others are inferior because the "best" setup is purely subjective.

It is important to remember that all apps on Android are sandboxed, regardless of which profile they're installed in. For most use-cases, using profiles to further isolate apps is unnecessary. However, isolating apps to different profiles does have a few advantages, some of which are listed below:

- Apps within profiles can communicate with each other via inter-process communication (IPC) (though control of IPC is an upcoming feature according to the GrapheneOS Twitter account's post on [App Scopes](https://twitter.com/GrapheneOS/status/1721270069412376933)).
- Apps can list other installed apps within the same profile without needing special permission.
- Some apps don't allow multiple users to be logged in, so profiles can be used to get around this kind of limitation.

---

## Some Common Setups

Some of the most common setups are as follows:

### Isolated Google Apps

One of the most common profile setups people in the community talk about is one where the user sets up two profiles: one with FOSS apps, and one with Google apps, or apps that rely on Google Play to operate, including Google Maps or certain bank apps.

### Empty Owner Profile

Many GrapheneOS users choose to keep their Owner profile completely empty, then use a secondary profile as their main profile.

This setup has a huge advantage in that Owner can set many global settings (like enabling ADB, for example), so if the Owner profile is protected by a strong password, these kinds of sensitive settings are protected.

Another advantage to this setup is that if a personal profile needs to be deleted for any reason, it's easy to do so from the Owner profile. No need to do a factory reset, and any other profiles that might be on the phone won't be affected.

### Owner as an app pusher

Some users who tend to use profiles a lot like to set up their Owner profile to push apps to other profiles. Some install Sandboxed Google Play in their Owner profile, but not in other profiles so they can push apps to profiles without Sandboxed Google Play installed. And since GrapheneOS allows users to [disable user installed apps](https://grapheneos.org/features#user-installed-apps-can-be-disabled), users can disable Google Play and Google Play Services when not in use.

### No Profiles

One option that many never even consider is not using profiles at all. Using profiles can add some unnecessary annoyances for some people because of how notifications work or switching between profiles is annoying, or PINs / passwords are too long or annoying. For some, no profiles is the best fit.

---

## Final Thoughts

Don't worry too much about setting up user profiles perfectly the first time. Many in the community have said that they've gone through multiple setups before finally settling on what they think works for them.