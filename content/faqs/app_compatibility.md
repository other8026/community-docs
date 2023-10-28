+++
title = "App Compatibility with GrapheneOS"
description = "A comprehensive list of suggestions on how to troubleshoot apps that don't work on GrapheneOS"
draft = true

[extra]
related = []

+++
_Note that this was originally [posted](https://discuss.grapheneos.org/d/8330-app-compatibility-with-grapheneos) on the official GrapheneOS Discussion Forum by [akc3n](https://discuss.grapheneos.org/u/akc3n)_

---

Purpose: Utilize as a reference permalink for consistent citing on duplicates across platforms. [E.g.](https://github.com/GrapheneOS/os-issue-tracker/issues/2578#issuecomment-1772174718),

---

For banking app compatibility with GrapheneOS, please use this [issue-tracker](https://github.com/PrivSec-dev/banking-apps-compat-report).

> A 3rd party community-sourced effort containing [banking app compatibility](https://privsec.dev/posts/android/banking-applications-compatibility-with-grapheneos/) information is maintained by PrivSec.dev. GrapheneOS does not make any guarantees regarding the list's validity.

---

# Possible workaround solutions for problematic applications

1 — By default, [native code debugging](https://grapheneos.org/usage#banking-apps) is enabled. If you disabled it, try enabling it again. Launch app. If unsuccessful, proceed to step 2.

`Settings ➔ Security ➔ Enable native code debugging`

---

2 — Enable the per-app [exploit protection compatibility mode](https://grapheneos.org/usage#bugs-uncovered-by-security-features). Launch app. If unsuccessful, proceed to step 3 for testing only.

`Settings ➔ Apps ➔ AppName ➔ Advanced ➔ Exploit protection compatibility mode`

Turning off the exploit protection compatibility toggle reduces system security but may allow this application to run without crashing. The app crashed because GrapheneOS detected a memory corruption bug that may be exploitable by an attacker.

---

3 — Temporarily disable [secure app spawning](https://grapheneos.org/usage#exec-spawning).

`Setting ➔ Security ➔ Enable secure app spawning`

---

4 — Restart device. Launch app to see if this GrapheneOS feature caused the compatibility issue. The app may be refusing to run if it detects a different spawning mechanism.

[Significant security loss and directly affecting some privacy using Zygote](https://old.reddit.com/r/GrapheneOS/comments/tq0k7q/comment/i2ex547/)

- Disabling exec-based spawning reverts to using the traditional Zygote spawning model AOSP's app processes
- Spawned as a clone of the Zygote
- Each app process has the same random secrets for ASLR, SSP, memory tagging, pointer authentication, setjmp canaries, and heap randomization
- Half of the userspace is made of app processes
- Applies across all profiles
- App in profile A and profile B have same random values, which they can see

---

5 — Revert to secure spawning by enabling it again and restart device. See step 3 above.

---

6 — Potential use of an unofficial/alternative Google Play Store frontend client may be [problematic](https://akc3n.page/posts/banking-app-issues/#auroraoss-is-problematic) for misguided apps:

- That can check if they were installed from the Play Store and can choose to refuse to work if they were not installed from the Play Store.
- Some forbid usage on non-stock OS (most OSes are insecure)
- May cause your Google Account to be disabled/blocked/blacklisted by Google.
- [Anonymous account](https://twitter.com/GrapheneOS/status/1661989816584511489) usage may have negative consequences and have a less secure connection to the Play Store servers.

General recommendation: [Install Sandboxed Google Play](https://grapheneos.org/usage#sandboxed-google-play). Optionally use a [throwaway](https://twitter.com/search?q=throwaway%20%28from%3Agrapheneos%29&src=typed_query) account.

---

7 — Search the [forum](https://discuss.grapheneos.org/), [os-issue-tracker](https://github.com/GrapheneOS/os-issue-tracker/issues), and/or within the [community](https://grapheneos.org/contact#community) for keyword(s) specific to the app name. _If unsuccessful with finding a solution, only than proceed to step 8._

---

8 — Attempt to reproduce the issue by capturing a 'Bug report' using the feature in Developer options if you still run into the [app aborting](https://grapheneos.org/usage#banking-apps:~:text=if%20you%20run%20into%20an%20application%20aborting) at launch.

- Enable Developer option by tapping the 'Build number' 7 times
`Settings ➔ About ➔ Device identifiers ➔ Build number`

- Capture a bug report
`Settings ➔ System ➔ Developer options ➔Bug Report ➔ Interactive report ➔ REPORT`

---

9 — Open a [new issue](https://github.com/GrapheneOS/os-issue-tracker/issues/new), provide a description and make contact via the appropriate channels with a similar message like "[Bug report capture for issue #104](https://grapheneos.org/usage#banking-apps:~:text=bug%20report%20capture%20for%20issue%20%23104)". in order to submit the bug report capture zip privately. (Replace the issue # number).

- [Contacting the project](https://grapheneos.org/contact#contacting-the-project)
- [Reporting issues](https://grapheneos.org/contact#reporting-issues)
- _Friendly reminder: [instructions for getting support](https://github.com/GrapheneOS/.github/blob/main/SUPPORT.md) via [chat](https://grapheneos.org/contact#community) and when to avoid using the os-issue-tracker: ask questions + request support_

---

10 — Disable the developer options.

`Settings ➔ System ➔ Developer options ➔ Use developer options`

We recommend disabling developer options as a whole for a device that's not being used for app or OS development.

---

11 — It's plausible that this is app-related, rather than a compatibility issue with GrapheneOS - acknowledging this factor must be considered. _If so, in Step #12, share the attestation compatibility guide with the app developer._

---

12 — Please see the [Attestation compatibility guide](https://grapheneos.org/articles/attestation-compatibility-guide) on using remote attestation in a way that's compatible with GrapheneOS and how you can help.

> GrapheneOS users are strongly encouraged to share this documentation with app developers enforcing only being able to use the stock OS. Send an email to the developers and leave a review of the app with a link to this information. Share it with other users and create pressure to support GrapheneOS rather than locking users into the stock OS without a valid security reason. GrapheneOS not only upholds the app security model but substantially reinforces it, so it cannot be justified with reasoning based on security, anti-fraud, etc.