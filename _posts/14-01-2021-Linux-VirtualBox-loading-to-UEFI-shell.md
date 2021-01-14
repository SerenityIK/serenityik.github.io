---
layout: post
title: "Guest Linux system loading to UEFI-shell on VirtualBox with turned on UEFI"
date: 2021-01-14 22:15:00 +0300
categories: guest linux, virtualbox, uefi, uefi-shell, linux not loading
---
If your guest Linux system loading only to UEFI-shell you can copy your grubx64.efi file to `\EFI\boot\bootx64.EFI` (i don't recommend this, cause you will need to copy grubx64.efi each time after updating) or make start script.

To make start script:
1.   Type `fs0:` and press enter
2.   Check location of grubx64.EFI file with `ls` command. Example: `ls \EFI\debian\`. Yes, you just need to find it by hands
3.   Enter command `EDIT startup.nsh`
4.   Write `FSO:\EFI\debian\grubx64.efi`, press Ctrl + s, enter and Ctrl + q to exit editor
5.   Reboot your virtual machine

To copy:
1.    ...
2.    ...
3.    Enter command `mkdir \EFI\boot`
4.    Enter command `cp \EFI\debian\grubx64.efi \EFI\boot\bootx64.EFI`
5.    Reboot your virtual machine

If something not working just check that VirtualBox UEFI-shell using dos-style slashes, not Unix-one.
