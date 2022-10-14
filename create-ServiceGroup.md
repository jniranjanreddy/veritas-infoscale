## How to create ServiceGroup
```
How to configure a new ServiceGroup.
[root@verclus01 ~]# haconf -makerw
[root@verclus01 ~]# hagrp -add SG1
VCS NOTICE V-16-1-10136 Group added; populating SystemList and setting the Parallel attribute recommended before adding resources
[root@verclus01 ~]# hagrp -modify SG1 SystemList verclus01 0 verclus02 1
[root@verclus01 ~]# hagrp -modify SG1 AutoStartList verclus01 verclus02
[root@verclus01 ~]# haconf -dump -makero
[root@verclus01 ~]# hastatus -sum

-- SYSTEM STATE
-- System               State                Frozen

A  verclus01            RUNNING              0
A  verclus02            RUNNING              0

-- GROUP STATE
-- Group           System               Probed     AutoDisabled    State

B  SG1             verclus01            Y          N               OFFLINE
B  SG1             verclus02            Y          N               OFFLINE

[root@verclus01 ~]# hares -add SG-ip IP SG1
VCS NOTICE V-16-1-10242 Resource added. Enabled attribute must be set before agent monitors
[root@verclus01 ~]# hares -modify SG-ip Enabled 1
[root@verclus01 ~]# hares -modify SG-ip Device enp0s3
[root@verclus01 ~]# hares -modify SG-ip Address "192.168.9.150"
[root@verclus01 ~]# hares -modify SG-ip NetMask "255.255.255.0"
[root@verclus01 ~]# hares -add SG-nic NIC SG1
VCS NOTICE V-16-1-10242 Resource added. Enabled attribute must be set before agent monitors
[root@verclus01 ~]# hares -modify SG-nic Device enp0s3
[root@verclus01 ~]# hares -modify SG-nic Enabled 1
[root@verclus01 ~]# hares -link SG-ip SG-nic
[root@verclus01 ~]# haconf -dump -makero

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

# Part of main.cf
group SG1 (
        SystemList = { verclus01 = 0, verclus02 = 1 }
        AutoStartList = { verclus01, verclus02 }
        )

        IP SG-ip (
                Device = enp0s3
                Address = "192.168.9.150"
                NetMask = "255.255.255.0"
                )

        NIC SG-nic (
                Device = enp0s3
                )

        SG-ip requires SG-nic


        // resource dependency tree
        //
        //      group SG1
        //      {
        //      IP SG-ip
        //          {
        //          NIC SG-nic
        //          }
        //      }

```
