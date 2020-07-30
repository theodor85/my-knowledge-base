## Working on Linux

### How to know about disks usage

Summarize info about partitions and their free/is used space:

    df -h

Info about folders'/files' size:

    du -h --max-depth=1

How to print files/folders are sorted by size (in megabytes):

    du -BM --max-depth=1 | sort -r -n

### View system information

    sudo dmidecode | more

or:

    sudo lshw | more

### View, which process uses the TCP port

    sudo lsof -i :<port-number>


## Vim

### Settings for Vim

    [Miguel Grinberg](https://gist.github.com/miguelgrinberg/527bb5a400791f89b3c4da4bd61222e4)

    [Alexei Goloburdin](https://gist.github.com/alexey-goloburdin/62d5b1b5ec19275d33497b7f3c0b6eec)

## tmux

### Turn On mouse

I file `~/.tmux.conf` add string:

    set -g mouse on
