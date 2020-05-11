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
