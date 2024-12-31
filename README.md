# fedora-setup
let's start rolling with fedora

## Delete all partitions on a drive during live session with terminal
```bash
wipefs -a /dev/sdX
```
- [Deleting All Partitions From the Command Line](https://serverfault.com/questions/250839/deleting-all-partitions-from-the-command-line)

## Update BIOS (and other firmware) with terminal

```bash
fwupdmgr get-updates ; fwupdmgr update
```
- [I want to update BIOS in a complete Linux(Fedora Workstation 36) environment](https://www.reddit.com/r/Fedora/comments/yot62i/i_want_to_update_bios_in_a_complete_linuxfedora/)
