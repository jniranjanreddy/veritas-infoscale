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

[root@verclus01 ~]# haconf -makerw
[root@verclus01 ~]# hastatu s-sum
-bash: hastatu: command not found
[root@verclus01 ~]# hastatus -sum

-- SYSTEM STATE
-- System               State                Frozen

A  verclus01            RUNNING              0
A  verclus02            RUNNING              0

-- GROUP STATE
-- Group           System               Probed     AutoDisabled    State

B  SG1             verclus01            Y          N               ONLINE
B  SG1             verclus02            Y          N               OFFLINE
[root@verclus01 ~]# vxdiks list
-bash: vxdiks: command not found
[root@verclus01 ~]# vxdisk list
DEVICE          TYPE            DISK         GROUP        STATUS
verclus01_disk_0 auto:cdsdisk    disk1        DG1          online
verclus01_disk_1 auto:LVM        -            -            LVM
verclus01_disk_2 auto:cdsdisk    -            -            online
verclus01_disk_3 auto:cdsdisk    -            -            online
[root@verclus01 ~]#
[root@verclus01 ~]# hares -add DG1 DiskGroup SG1
VCS NOTICE V-16-1-10242 Resource added. Enabled attribute must be set before agent monitors
[root@verclus01 ~]# hares -modify DG1 DiskGroup DG1
[root@verclus01 ~]# hares -add testvcsfs_lv Mount SG1
VCS NOTICE V-16-1-10242 Resource added. Enabled attribute must be set before agent monitors
[root@verclus01 ~]# hares -modify testvcsfs_lv BlockDevice /dev/vx/dsk/DG1/testvcsfs_lv
[root@verclus01 ~]# hares -modify testvcsfs_lv FSType vxfs
[root@verclus01 ~]# hares -modify testvcsfs_lv FsckOpt "%-y"
[root@verclus01 ~]# hares -modify testvcsfs_lv MountPoint /testvcsfs
[root@verclus01 ~]# hares -link testvcsfs_lv DG1
[root@verclus01 ~]# hagrp -enableresources SG1
[root@verclus01 ~]# haconf -dump -makero
[root@verclus01 ~]# hares -online testvcsfs_lv -sys verclus01
[root@verclus01 ~]# hastatus -sum

-- SYSTEM STATE
-- System               State                Frozen

A  verclus01            RUNNING              0
A  verclus02            RUNNING              0

-- GROUP STATE
-- Group           System               Probed     AutoDisabled    State

B  SG1             verclus01            Y          N               ONLINE
B  SG1             verclus02            Y          N               OFFLINE
[root@verclus01 ~]# hastatus -sum

-- SYSTEM STATE
-- System               State                Frozen

A  verclus01            RUNNING              0
A  verclus02            RUNNING              0

-- GROUP STATE
-- Group           System               Probed     AutoDisabled    State

B  SG1             verclus01            Y          N               ONLINE
B  SG1             verclus02            Y          N               OFFLINE
[root@verclus01 ~]# hastatus -sum

-- SYSTEM STATE
-- System               State                Frozen

A  verclus01            RUNNING              0
A  verclus02            RUNNING              0

-- GROUP STATE
-- Group           System               Probed     AutoDisabled    State

B  SG1             verclus01            Y          N               ONLINE
B  SG1             verclus02            Y          N               OFFLINE
[root@verclus01 ~]# hastatus -sum

-- SYSTEM STATE
-- System               State                Frozen

A  verclus01            RUNNING              0
A  verclus02            RUNNING              0

-- GROUP STATE
-- Group           System               Probed     AutoDisabled    State

B  SG1             verclus01            Y          N               ONLINE
B  SG1             verclus02            Y          N               OFFLINE
[root@verclus01 ~]#

```
