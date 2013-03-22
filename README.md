## Fork of Meize's Realtek RTL8111 Network Driver by RehabMan


### How to Install:

First you must remove any other Realtek driver you may have installed.  

Common ones are:
RealtekRTL81xx.kext
RealtekRTL8000SL.kext
AppleRTL8169Ethernet.kext

It is possible that these kexts are installed under directly in /System/Library/Extensions or under /S/L/E/IONetworkingFamily.kext/Contents/PlugIns, so be sure to check both locations.

Next, install the kext using Kext Wizard or your favorite kext installer.

Special note for Snow Leopard users:  There is a conflict between the RTL8169 driver that is part of Snow Leopard and this driver.  The RTL8169 driver, during its probe method, puts the hardware into a bad state where it cannot be detected properly by this driver.  As a result, you must remove it:

sudo rm -rf /System/Library/Extensions/IONetworkingFamily.kext/Contents/PlugIns/AppleRTL8169Ethernet.kext


### Downloads:

Downloads are available on Google Code:

https://code.google.com/p/os-x-realtek-network/downloads/list


### Build Environment

My build environment is currently Xcode 4.61, using SDK 10.8, targeting OS X 10.6.

This kext can be built with any of the following SDKs: 10.8, 10.7, or 10.6.
In addition, it can be built supporting any of these OS X targets: 10.8, 10.7, or 10.6.

For greatest compatibility, the provided build is SDK 10.8 targeting 10.6.


### 32-bit Builds

This project does not support 32-bit builds.  It is coded for 64-bit only.


### Source Code:

The source code is maintained at the following sites:

https://code.google.com/p/os-x-realtek-network/

https://github.com/RehabMan/OS-X-Realtek-Network


### Feedback:

Please use the following thread on tonymacx86.com for feedback, questions, and help:

TODO: provide link


### Known issues:


### Change Log:

2013-03-22 (RehabMan)

- Modified for single binary to work on ML, Lion, and SL.

- Optimize build to reduce code size and exported symbols.


2013-03-17 (Meize)

- Initial build provided by Meize on insanelymac.com


### History

This repository contains a modified version of Meize's Ethernet driver for Realtek RTL8111 series chips.  All credits to Meize for the original code and probably further enhancements/bug fixes.

Original sources came from this post on Insanely Mac:

http://www.insanelymac.com/forum/topic/287161-new-driver-for-realtek-rtl8111/

My goal in creating this repository was just to create a single binary that could be used on 10.8, 10.7, and 10.6 for use in the Probook Installer.
