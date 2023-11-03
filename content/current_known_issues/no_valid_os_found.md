+++
title = "No Valid OS found"
description = "Some Android devices running Android 14 are reporting they cannot find a valid OS"

[extra]
related = ["os_updates/update_failed.md"]
+++

A very small number of users have been reporting that when booting up their phones they see an error message saying the phone cannot find a valid OS to boot to. This seems to be a result of an [upstream problem](https://issuetracker.google.com/issues/277984765) with the bootloader, which can only be fixed by Google.

People experiencing this problem can simply restart their phone multiple times (some have reported restarting 10+ times) until the phone starts working again. Others have fixed the problem by [sideloading](https://grapheneos.org/usage#updates-sideloading) updates.