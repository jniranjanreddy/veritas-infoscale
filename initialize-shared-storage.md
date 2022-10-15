## How to initialie shared storage.

```
[root@verclus01 ~]# vxdisk list
DEVICE          TYPE            DISK         GROUP        STATUS
verclus01_disk_0 auto:none       -            -            online invalid
verclus01_disk_1 auto:LVM        -            -            LVM
verclus01_disk_2 auto:none       -            -            online invalid
verclus01_disk_3 auto:none       -            -            online invalid
[root@verclus01 ~]#
```
## vxdctl enable # enable on other node.
```
[root@verclus01 ~]# vxdisk list
DEVICE          TYPE            DISK         GROUP        STATUS
verclus01_disk_0 auto:cdsdisk    -            -            online
verclus01_disk_1 auto:LVM        -            -            LVM
verclus01_disk_2 auto:cdsdisk    -            -            online
verclus01_disk_3 auto:cdsdisk    -            -            online
[root@verclus01 ~]# vxdg init DG1 disk1=verclus01_disk_0
[root@verclus01 ~]# vxdisk list
DEVICE          TYPE            DISK         GROUP        STATUS
verclus01_disk_0 auto:cdsdisk    disk1        DG1          online
verclus01_disk_1 auto:LVM        -            -            LVM
verclus01_disk_2 auto:cdsdisk    -            -            online
verclus01_disk_3 auto:cdsdisk    -            -            online

[root@verclus01 ~]# mkdir /testvcsfs

[root@verclus01 ~]# vxassist -g DG1 make testvcsfs_lv 100M
[root@verclus01 ~]# mkfs -t vxfs /dev/vx/rdsk/DG1/testvcsfs_lv
    version 16 layout
    204800 sectors, 102400 blocks of size 1024, log size 1024 blocks
    rcq size 1024 blocks
    largefiles supported
    maxlink supported
    WORM not supported
[root@verclus01 ~]#

```
