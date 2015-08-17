
Android NfcProvisioning Sample
===================================

This sample demonstrates how to use NFC to provision a new device with a device owner. Device owner
is a specialized type of device administrator that can control device security and configuration.
This sample itself is not a device owner, but it is a programming app that sends NFC message to an
unprovisioned peer device and tells it to set up the specified device owner app.

Introduction
------------

NFC Provisioning app is nothing but an ordinary Android Beam app that just sends out provisioning
values to the peer device. This sample uses the values below.

* [EXTRA_PROVISIONING_DEVICE_ADMIN_PACKAGE_NAME] - The package name of the mobile device management
  application that will be set as the profile owner or device owner.
* [EXTRA_PROVISIONING_LOCALE] - The Locale that the device will be set to.
* [EXTRA_PROVISIONING_TIME_ZONE] - The time zone AlarmManager that the device will be set to.
* [EXTRA_PROVISIONING_WIFI_SSID] - The ssid of the wifi network that should be used during nfc
  device owner provisioning for downloading the mobile device management application.
* [EXTRA_PROVISIONING_WIFI_PASSWORD] - The password of the wifi network in
  EXTRA_PROVISIONING_WIFI_SSID.

Store values in an instance of Properties. Get a byte array representation of the Properties using
ByteArrayOutputStream. Create an NdefRecord with the MIME type of
[DevicePolicyManager.MIME_TYPE_PROVISIONING_NFC][1]. Use [NfcAdapter#setNdefPushMessage][2] to set
the NdefMessage as the message to be sent.

[1]: https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#MIME_TYPE_PROVISIONING_NFC
[2]: http://developer.android.com/reference/android/nfc/NfcAdapter.html#setNdefPushMessage(android.nfc.NdefMessage, android.app.Activity, android.app.Activity...)

Pre-requisites
--------------

- Android SDK v23
- Android Build Tools v23.0.0
- Android Support Repository

Screenshots
-------------

<img src="screenshots/1-main.png" height="400" alt="Screenshot"/> 

Getting Started
---------------

This sample uses the Gradle build system. To build this project, use the
"gradlew build" command or use "Import Project" in Android Studio.

Support
-------

- Google+ Community: https://plus.google.com/communities/105153134372062985968
- Stack Overflow: http://stackoverflow.com/questions/tagged/android

If you've found an error in this sample, please file an issue:
https://github.com/googlesamples/android-NfcProvisioning

Patches are encouraged, and may be submitted by forking this project and
submitting a pull request through GitHub. Please see CONTRIBUTING.md for more details.

License
-------

Copyright 2014 The Android Open Source Project, Inc.

Licensed to the Apache Software Foundation (ASF) under one or more contributor
license agreements.  See the NOTICE file distributed with this work for
additional information regarding copyright ownership.  The ASF licenses this
file to you under the Apache License, Version 2.0 (the "License"); you may not
use this file except in compliance with the License.  You may obtain a copy of
the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.  See the
License for the specific language governing permissions and limitations under
the License.
