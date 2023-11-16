+++
title = "OS Update Failed"
description = "Information on what's going on or what to do in the rare event that a GrapheneOS update fails"

[extra]
related = ["current_known_issues/no_valid_os_found.md"]
+++
In very rare cases, GrapheneOS OS updates fail. This can be concerning for users when it happens, but the chances of a phone being "bricked" is very low.

GrapheneOS, as well as some other OSes, have changed or are changing updates to [A/B (seamless) system updates](https://source.android.com/docs/core/ota/ab). In a nutshell, A/B system updates was designed to accomplish two things: less downtime for phone users and fault resistance.

The update process looks roughly like this:
- The updater app checks for updates, finds one, then starts a download
- The updater app tells the `update_engine` to update using the downloaded file
- After the update is complete, the `update_engine` changes the boot slot
- When the phone restarts it attempts to boot to the updated slot
- If unsuccessful, the phone will revert back to the old slot

Due to how phones with GrapheneOS installed perform updates, bricking a phone during updates is extremely unlikely. Restarting a phone or a phone dying during an update will not brick the phone. However, if a phone fails to successfully boot after an update multiple times, then that can be an indicator of failing hardware.

As of version [2023102300](https://grapheneos.org/releases#2023102300), users can now require the updater wait until the phone is charging to install updates. That can be set up in the Owner profile by toggling it on here: `Settings > System > System update > Require device be charging`.