# Commands

> npx react-native-asset
for linking assets with react native project.

> npm run android -- --deviceId __deviceID__  or npm run android -- --device __deviceID__
for running 

> emulator -avd __emulated_device_name__ -gpu off
for running emulated device while it's gpu is off

> emulator -avd New_Device_2 -gpu off -no-snapshot -no-boot-anim
for running emulated device while it's gpu is off and without boot animation.

> [emulator -avd Pixel_6a -gpu off -no-snapshot -no-boot-anim](emulator -avd Pixel_6a -gpu off -no-snapshot -no-boot-anim)

> getVisibleProductsNumInCart

> npm start -- --reset-cache
for resetting cache of the app.

> adb-396374202667616254-oiypvx._adb-tls-connect._tcp --> Handshow Device
saving hanshow device name in the.

> adb shell pm list packages
Showing the names of the installed packages in the connected device.

> adb uninstall __package_name__
For uninstalling the package with the provided name



To fix the no permissions (missing udev rules?) error, you need to configure udev rules on your Linux system. This tells Linux to grant your user account permission to interact with your specific Android phone via USB.
Here is how to fix this in under two minutes:
## 1. Find Your Phone's Vendor ID
First, find the specific hardware ID of your connected phone. Run this command in your terminal:

lsusb

Look for your phone in the list. It will look something like this:

Bus 001 Device 005: ID 18d1:4ee7 Google Inc. Nexus/Pixel Device

The 4-character code before the colon (in this example, 18d1) is your Vendor ID. Note yours down.
## 2. Create the Udev Rule
Create a new rule file using your terminal's text editor (like nano):

sudo nano /etc/udev/rules.d/51-android.rules

Paste the following line into the file. Replace 18d1 with the actual Vendor ID you found in the step above:

SUBSYSTEM=="usb", ATTR{idVendor}=="18d1", MODE="0666", GROUP="plugdev"

To save and exit Nano: Press Ctrl + O, then Enter, then Ctrl + X.
## 3. Apply the Changes
Reload the Linux udev rules to activate the new configuration:

sudo udevadm control --reload-rules
sudo systemctl restart udev

## 4. Restart the ADB Server
Unplug the USB cable from your phone, then run these commands to restart ADB with proper permissions:

adb kill-server
adb start-server

Plug your USB cable back in. Look at your phone's screen and accept the "Allow USB Debugging?" prompt if it appears. Finally, verify it works:

adb devices

Your device should now say device instead of no permissions, allowing you to run gnirehtet and your development apps perfectly.
Did your device successfully switch to showing device in the terminal, or are you still getting a permission error?

