# automated-monkey-testing-with-adb

## Monkey Testing Commands for com.foodi.userdev
This repository contains a set of commands for conducting Monkey Testing on the Android application package com.foodi.userdev. Monkey Testing is a stress test that generates a large number of random events to simulate user interactions with the app, helping to identify crashes or unexpected behavior.

## Prerequisites
- Android Debug Bridge (ADB): Ensure ADB is installed and added to the system's PATH.
- Android Device: A connected Android device or emulator with USB Debugging enabled.
- Application Package: The com.foodi.userdev APK must be installed on the device.

## Commands
1. List Connected Devices
Use the following command to list all devices or emulators currently connected to the system:

`adb devices`

2. List Installed Packages
This command lists all installed packages on the connected device. This can help confirm whether com.foodi.userdev is installed:

`adb shell pm list packages`

3. Run Monkey Test with 10,000 Events
Run the Monkey test on com.foodi.userdev with 10,000 random events using the command below:

`adb shell monkey -p com.foodi.userdev -v 10000`

4. Run Monkey Test with 500 Events and Save Log
Execute this command to run the Monkey test with 500 random events and save the output to a specified log file:

`adb shell monkey -p com.foodi.userdev -v 500 > C:\Users\TN-99286\Desktop\Report\monkey_log.txt`

5. Capture Logcat Output
To capture the logcat output during testing, use this command. It logs all system messages, including stack traces if the app crashes:

`adb logcat > C:\Users\TN-99286\Desktop\New_folder\monkey_test.log`

## Notes
- Ensure the device is properly connected and recognized by ADB before running these commands.
- The number of events specified in the Monkey command (-v 10000 or -v 500) can be adjusted based on testing needs.
- Logs captured during the test can be reviewed to identify any crashes or unexpected behavior in the app.
