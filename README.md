# fedora-setup
let's start rolling with fedora

## Delete all partitions on a drive during live session with terminal
```bash
wipefs -a /dev/sdX
```
- [Deleting All Partitions From the Command Line](https://serverfault.com/questions/250839/deleting-all-partitions-from-the-command-line)

## Video tutorial for Fedora installation
- [Tutorial: Fedora Workstation installieren (und dazu Windows partitionieren)](https://www.youtube.com/watch?v=cRIeogbzET4&t=1010s)
- Keyboard bug in installer
  - Even when selecting German layout, English qwerty layout is still being used
  - Be careful when setting passphrase for encryption blindly
- Select third party software after first reboot after installation
- First tutorial after finishing user and passord is about GNOME features (overview explanation, touchpad swiping)

## Update BIOS (and other firmware) with terminal

```bash
fwupdmgr get-updates ; fwupdmgr update
```
- [I want to update BIOS in a complete Linux(Fedora Workstation 36) environment](https://www.reddit.com/r/Fedora/comments/yot62i/i_want_to_update_bios_in_a_complete_linuxfedora/)
