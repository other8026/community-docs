+++
title = "Wireless Emergency Alerts"
description = "Many in the community have issues with WEA and think it's a backdoor. Here I try to explain that it's not."

[extra]
related = []

+++
## Source
The Wireless Emergency Alerts (WEA) app is open source, like the rest of GrapheneOS. You can find all of GrapheneOS's repositories listed [here](https://grapheneos.org/source).

Wireless Emergency Alerts' package name is `com.android.cellbroadcastreceiver`, and here's the [GitHub repo](https://github.com/GrapheneOS/platform_packages_apps_CellBroadcastReceiver/).

## What it does
WEA is a system app/service. Its purpose is to receive emergency alerts from the carrier and display them to the phone owner. There are varying levels of alerts and some alerts may behave differently depending on their severity or settings from the carrier.

## Code
I skimmed through the code fairly quickly. It's not very exciting. It's exactly what it says it is. There's just tons of code about checking stuff, changing permissions, checking if the messages are formatted correctly, saving them, etc. It's all very boring.

## Changes by GrapheneOS
In AOSP, some alerts can be disabled, but the most "important" cannot. GrapheneOS enables users to disable all alerts.

## Permissions
One of the things that worries users most about WEA is the permissions granted to it. While the permissions may seem excessive, they're necessary for the functioning of the app.

The permissions are as follows:

- `android.permission.BROADCAST_CLOSE_SYSTEM_DIALOGS` - Allows an application to broadcast the intent `android.content.Intent#ACTION_CLOSE_SYSTEM_DIALOGS`.
- `android.permission.RECEIVE_SMS` - Allows an application to receive SMS messages. ([link](https://developer.android.com/reference/android/Manifest.permission#RECEIVE_SMS))
- `android.permission.RECEIVE_EMERGENCY_BROADCAST` - Allows an application to receive emergency cell broadcast messages, to record or display them to the user.
- `android.permission.READ_PRIVILEGED_PHONE_STATE` - Allows read access to privileged phone state.
- `android.permission.MODIFY_PHONE_STATE` - Allows modification of the telephony state - power on, mmi, etc. Does not include placing calls. ([link](https://developer.android.com/reference/android/Manifest.permission#MODIFY_PHONE_STATE))
- `android.permission.MODIFY_CELL_BROADCASTS` - Allows an application to modify the cell broadcasts configuration (i.e. enable or disable channels).
- `android.permission.DISABLE_KEYGUARD` - Allows applications to disable the keyguard if it is not secure. ([link](https://developer.android.com/reference/android/Manifest.permission#DISABLE_KEYGUARD))
- `android.permission.STATUS_BAR` - Allows an application to open, close, or disable the status bar and its icons. ([link](https://developer.android.com/reference/android/Manifest.permission#STATUS_BAR))
- `android.permission.VIBRATE` - Allows access to the vibrator. ([link](https://developer.android.com/reference/android/Manifest.permission#VIBRATE))
- `android.permission.INTERACT_ACROSS_USERS` - Allows an application to call APIs that allow it to do interactions across the users on the device, using singleton services and user-targeted broadcasts.
- `android.permission.MANAGE_USERS` - Allows an application to call APIs that allow it to query and manage users on the device.
- `android.permission.DEVICE_POWER` - Allows low-level access to power management.
- `android.permission.START_ACTIVITIES_FROM_BACKGROUND` - Allows an application to start activities from background
- `android.permission.READ_CELL_BROADCASTS` - Allows an application to read previously received cell broadcast messages and to register a content observer to get notifications when a cell broadcast has been received and added to the database. For emergency alerts, the database is updated immediately after the alert dialog and notification sound/vibration/speech are presented. The "read" column is then updated after the user dismisses the alert. This enables supplementary emergency assistance apps to start loading additional emergency information (if Internet access is available) when the alert is first received, and to delay presenting the info to the user until after the initial alert dialog is dismissed.
- `android.permission.READ_SMS` - Allows an application to read SMS messages. ([link](https://developer.android.com/reference/android/Manifest.permission#READ_SMS))
- `android.permission.HIDE_NON_SYSTEM_OVERLAY_WINDOW` - Allows an application to use `android.view.WindowManager.LayoutsParams#SYSTEM_FLAG_HIDE_NON_SYSTEM_OVERLAY_WINDOWS` to hide non-system-overlay windows.
- `com.android.cellbroadcastservice.FULL_ACCESS_CELL_BROADCAST_HISTORY` - [...][a]llows the CellBroadcastReceiver app to have full access to the database inside CellBroadcastService. ([link](https://source.android.com/docs/core/ota/modular-system/cellbroadcast#permission-config))
- `android.permission.RECEIVE_BOOT_COMPLETED` - Allows an application to receive the `Intent.ACTION_BOOT_COMPLETED` that is broadcast after the system finishes booting. ([link](https://developer.android.com/reference/android/Manifest.permission#RECEIVE_BOOT_COMPLETED))
- `android.permission.BLUETOOTH` - Allows applications to connect to paired bluetooth devices. ([link](https://developer.android.com/reference/android/Manifest.permission#BLUETOOTH))
- `android.permission.BLUETOOTH_CONNECT` - Required to be able to advertise to nearby Bluetooth devices. ([link](https://developer.android.com/reference/android/Manifest.permission#BLUETOOTH_CONNECT))
- `android.permission.POST_NOTIFICATIONS` - Allows an app to post notifications ([link](https://developer.android.com/reference/android/Manifest.permission#POST_NOTIFICATIONS))
- `android.permission.WAKE_LOCK` - Allows using PowerManager WakeLocks to keep processor from sleeping or screen from dimming. ([link](https://developer.android.com/reference/android/Manifest.permission#WAKE_LOCK))

Any permissions listed without a link were found [here](https://github.com/GrapheneOS/platform_frameworks_base/blob/14/core/res/AndroidManifest.xml).

## Why does WEA need these permissions?
Again, I didn't read through all of the code, so I may have missed some things and this list may be incomplete, but here are some reasons I found:

- *SMS* - Some alerts can be saved to the messages store. SMS permissions allow it to do that.
- *Interact across users and manage users* - The only thing I could find was a check to see which user is active to avoid saving the message multiple times (since the SMS message store is global). It checks if the logged in user is the admin user to restrict changing settings if not. It also checks if the user is logged in.
- *Bluetooth* - Checks if phone is connected to audio device. Checks if phone is connected to a "companion" device, and sends to companion device if necessary.
- *Keyguard* - Display over the keyguard when the device is locked.
- *Read (privileged) phone state* - Check if the user is in a call, get carrier config, get carrier ID (to reset settings if/when a new one is used), 

I think it's pretty obvious why the rest are there.

## Conclusion
Hopefully after reading about this boring service/app, you agree that Wireless Emergency Alerts is not a "backdoor" or even worth worrying about. It's just a boring app that bothers you if it receives an alert to do so.