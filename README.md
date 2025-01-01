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

## Problematic flatpak version of Signal
Flatpak installation of Signal with security warning:

```bash
Signal is being launched with the plaintext password store by
default due to database corruption bugs when using the encrypted backends.
This will leave your keys unencrypted on disk as it did in all previous versions.

If you wish to experiment with the encrypted backend, set the environment variable
SIGNAL_PASSWORD_STORE to gnome-libsecret, kwallet,
kwallet5 or kwallet6 depending on your desktop environment using
Flatseal or the following command:

flatpak override --env=SIGNAL_PASSWORD_STORE=gnome-libsecret org.signal.Signal

Note that the encrypted backends are experimental and may cause data loss on some systems.

Press Yes to proceed with plaintext password store or
No to exit.
```

Recommended installation method is via additional repo

```bash
user@fedora:~$ sudo dnf config-manager addrepo --from-repofile=https://download.opensuse.org/repositories/network:im:signal/Fedora_41/network:im:signal.repo
user@fedora:~$ sudo dnf install signal-desktop
```

- [Accurate way to install signal in fedora](https://discussion.fedoraproject.org/t/accurate-way-to-install-signal-in-fedora/117236)
- [Does anyone know what's up with Signal on Fedora currently?](https://www.reddit.com/r/Fedora/comments/1fsrzyi/does_anyone_know_whats_up_with_signal_on_fedora/)

## Different flatpak remotes available for OBS Studio installation
There are two flatpak remotes available for OBS installation ('fedora' and 'flatpak')

Main differences:
- 'fedora'
  - Newest version
  - Does not install additional packages for hardware encoding, only OpenH264 available as software encoder
  - hardware encoding one might be fixed/added with rpm packages?
- 'flatpak'
  - slightly older version
  - ships with relevant packages for hardware encoding
  - HEVC and H.264 can be selected with harddware acceleration e.g. Intel Quick Sync
  - Hardware acceleration can be observed with intel_gpu_top
