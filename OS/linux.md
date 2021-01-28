# Working on Linux

[How to know about disks usage](#how-to-know-about-disks-usage)

[View system information](#view-system-information)

[View, which process uses the TCP port](#view-which-process-uses-the-TCP-port)

[Vim](#vim)

&nbsp;&nbsp;&nbsp;&nbsp;[Settings for Vim](#settings-for-vim)

[Tmux](#tmux)

&nbsp;&nbsp;&nbsp;&nbsp;[Turn on mouse](#turn-on-mouse)

[Genisoimage](#genisoimage)

[How to write iso-image to flash with dd](#how-to-write-iso-image-to-flash-with-dd)


## How to know about disks usage

Summarize info about partitions and their free/is used space:

    df -h

Info about folders'/files' size:

    du -h --max-depth=1

How to print files/folders are sorted by size (in megabytes):

    du -BM --max-depth=1 | sort -r -n

## View system information

    sudo dmidecode | more

or:

    sudo lshw | more

## View, which process uses the TCP port

    sudo lsof -i :<port-number>


## Vim

### Settings for Vim

[Miguel Grinberg's .vimrc](https://gist.github.com/miguelgrinberg/527bb5a400791f89b3c4da4bd61222e4)

[Alexei Goloburdin's .vimrc](https://gist.github.com/alexey-goloburdin/62d5b1b5ec19275d33497b7f3c0b6eec)

## tmux

### Turn on mouse

In file `~/.tmux.conf` add string:

    set -g mouse on


## genisoimage 

Ubuntu: creating bootable ISO-image from directiry

```bash
genisoimage -r -V "ISO-LABEL" -cache-inodes -J -l \
-b isolinux/isolinux.bin -c isolinux/boot.cat -no-emul-boot \
-boot-load-size 4 -boot-info-table -o NAME-OF-ISO.iso ISOTMP
```

## How to write iso image to flash with dd

```bash
sudo dd if=/path/to/image.iso of=/dev/sdb1
```
