# Disk, disk, sleuth! II

## Challenge Description

All we know is the file with the flag is named `down-at-the-bottom.txt`... Disk image: dds2-alpine.flag.img.gz

## Hints

- The sleuthkit has some great tools for this challenge as well.
- Sleuthkit docs here are so helpful: TSK Tool Overview
- This disk can also be booted with qemu!
  
## Solution

I started by analyzing the disk structure

```bash
$ mmls dds2-alpine.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000262143   0000260096   Linux (0x83)
```

I noticed that the Linux partition started at sector 2048 

From the challenge description it's clear that I need to find the file `down-at-the-bottom.txt` for which I referred [this](https://www.lmgsecurity.com/sleuth-kit/?srsltid=AfmBOooMTKAsZUu9nc3oD44X4ER5HqwMNizhNHZ4wJ-luvelr5FMB7eY). I figured that if I search the output of `fls -r -p -o 2048 dds2-alpine.flag.img ` for the filename, I'll get its inode number and then I can just use `icat` to list its contents 

```bash
$ fls -r -p -o 2048 dds2-alpine.flag.img | grep down-at-the-bottom.txt
r/r 18291:      root/down-at-the-bottom.txt
$ icat -o 2048 dds2-alpine.flag.img 18291
   _     _     _     _     _     _     _     _     _     _     _     _     _
  / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \
 ( p ) ( i ) ( c ) ( o ) ( C ) ( T ) ( F ) ( { ) ( f ) ( 0 ) ( r ) ( 3 ) ( n )
  \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/
   _     _     _     _     _     _     _     _     _     _     _     _     _
  / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \
 ( s ) ( 1 ) ( c ) ( 4 ) ( t ) ( 0 ) ( r ) ( _ ) ( n ) ( 0 ) ( v ) ( 1 ) ( c )
  \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/
   _     _     _     _     _     _     _     _     _     _     _
  / \   / \   / \   / \   / \   / \   / \   / \   / \   / \   / \
 ( 3 ) ( _ ) ( 0 ) ( b ) ( a ) ( 8 ) ( d ) ( 0 ) ( 2 ) ( d ) ( } )
  \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/   \_/
```

Thus the flag for this challenge `picoCTF{f0r3ns1c4t0r_n0v1c3_0ba8d02d}`
