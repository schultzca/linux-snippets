# Create Bootable USB

1. Install usb stick.

2. Find device name using `lsblk`

```
lsblk

loop15                  7:15   0  89.1M  1 loop /snap/core/7917
loop1                   7:1    0 218.9M  1 loop /snap/gimp/165
loop13                  7:13   0 124.8M  1 loop /snap/vscode/87
sdd                     8:48   1   3.9G  0 disk 
└─sdd1                  8:49   1   3.9G  0 part <----------- USB DEVICE
loop11                  7:11   0  54.5M  1 loop /snap/core18/1192
sdb                     8:16   0 465.8G  0 disk 
└─sdb1                  8:17   0 465.8G  0 part 
loop8                   7:8    0  42.8M  1 loop /snap/gtk-common-themes/1313
loop6                   7:6    0 376.2M  1 loop /snap/pycharm-professional/136
loop4                   7:4    0 421.2M  1 loop /snap/pycharm-professional/159
loop2                   7:2    0   124M  1 loop /snap/vscode/89
loop14                  7:14   0  54.4M  1 loop /snap/core18/1144
loop0                   7:0    0 219.1M  1 loop /snap/gimp/189
loop12                  7:12   0 146.8M  1 loop /snap/slack/18
sdc                     8:32   0   1.8T  0 disk 
└─sdc1                  8:33   0   1.8T  0 part 
loop9                   7:9    0    89M  1 loop /snap/core/7713
loop10                  7:10   0 181.1M  1 loop /snap/spotify/36
sda                     8:0    0 223.6G  0 disk 
├─sda2                  8:2    0     1K  0 part 
├─sda5                  8:5    0 223.1G  0 part 
│ ├─ubuntu--vg-swap_1 253:1    0    16G  0 lvm  [SWAP]
│ └─ubuntu--vg-root   253:0    0 207.1G  0 lvm  /
└─sda1                  8:1    0   487M  0 part /boot
loop7                   7:7    0  44.2M  1 loop /snap/gtk-common-themes/1353
loop5                   7:5    0 124.3M  1 loop /snap/vscode/93
loop3                   7:3    0 146.6M  1 loop /snap/slack/17
```
3. Unmount the device.

`sudo umount /dev/sdd1`

4. Load ISO onto flash drive.

`sudo dd bs=4M if=<path to iso> of=/dev/sd<id> conv=fdatasync status=progress`
