# EZAC The ***FASTEST*** Auto Clicker for Minecraft Bedrock

# UPDATES PAST VERSION 1.26.21 ARE NOT SUPPORTED AND WILL TAKE A WHILE TO UPDATE.

## What is EZAC?

EZAC is a free internal based Minecraft Bedrock auto clicker. The latest version is available on the release tap of this repo.

## What does EZAC stand for?

EZAC stands for **EZ Auto Clicker** or **Easy Auto Clicker**.

## How does it work?

EZAC works by injecting a DLL in to Minecraft. This DLL then allocates a console window to the Minecraft process where it displays all of the debug messages and information on how to use the program. After reading the instructions, you are prompted to press a button to continue, and after doing so, the program will install hooks in to your Minecraft process ready to be used for Auto Clicking. This project originally started as a simple Cheat Engine script that would set a value to a certain integer, which would trick Minecraft in to thinking it is clicking high amounts of clicks per second. Then, I just converted it in to a C++ hook ready for a DLL to be compiled with CMake and injected in to Minecraft.

## How does the injector download and inject the DLL?

The injector simply connects a http server to this repo and finds the DLL from there, downloads it as a temporary file, then converts back to a regular DLL once complete. After this, the injector opens Minecraft using a command with shell execute. (minecraft:) After this, it waits around 2 - 5 seconds before running a command that interacts with a separate file called "EZAC-CmdLineInjector.exe" which passes the DLL file path and Minecraft's file name (Minecraft.Windows.exe) which then runs logic inside another C++ application to inject the DLL in to Minecraft via LoadLibrary for Kernel32.

## How does the injector updater work?

The injector updater is most likely the most complicated part of this project because of how many tasks it has to do.
Firstly, it downloads both the injector executable file and DLL file - both available on this repo - and then changes the file names to "EZAC-Injector.exe.tmp" and "EZAC-Injector.dll.tmp". After that, it runs a cmd script. Inside of this script, it force closes the injector using "taskkill" and then renames the files back to their original, then just tries to open a file called "EZAC-Injector.exe". If all of this succeeds, then your injector will open up the latest version and you'll be good to go!

---

At the current time of this project being published, this code **is** open source.

The source code is in the repo below:
[EZ Auto Clicker - OSS](https://github.com/Shardzzexe/EZ-Auto-Clicker/)

## 🤔 How do I use this utility?

Head on over to the release tab right [here.](https://github.com/Shardzzexe/EZAC-API/releases/)
Download the ZIP file and follow the instructions on the dedicated release description.
