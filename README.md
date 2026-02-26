# Attaching Frida tutorial
This tutorial explains how to attach a Frida script to Brawl Stars. Frida is a dynamic instrumentation toolkit that lets you inject scripts into running processes.

Steps:

Copy the Frida script

Place your Frida script into the /lib/armeabi-v7a/ directory within your Android application's files.

Name the script libXXX.js, where XXX is a descriptive name (e.g., libdebug.js).

Create a configuration file:

In the same directory (/lib/armeabi-v7a/), create a configuration file named libXXX.config.so (e.g., libdebug.config.so).

This file should contain the following JSON content, which tells Frida how to interact with the script: [Click](https://raw.githubusercontent.com/thecoolestfali/attachfrida/refs/heads/main/lib/armeabi-v7a/libXXX.config.so)

Add frida gadget:

Download Frida gadget: [Click](https://github.com/frida/frida/releases/latest)

Place it inside of libXXX.so (same name as Frida script but instead of .js extension use .so).

Modify the application's Smali code:

Open the smali/com/supercell/titan/GameApp.smali file.

Locate a line containing the character "g".

Move three lines down from that line.

Insert the following Smali code to load your Frida script: [Click](https://raw.githubusercontent.com/thecoolestfali/attachfrida/refs/heads/main/smali/com/supercell/titan/GameApp.smali)

Replace "XXX" with the name you used in step 1 (e.g., "debug"). This code instructs the app to load your script as a native library.

8hacc guided me and ai wrote this.
