# veritas-infoscale

## Configuring Two node cluster.

```
[root@verclus01 rhel7_x86_64]# ./installer

                                    Veritas InfoScale Storage and Availability Solutions 7.4.2 Install Program

Copyright (c) 2020 Veritas Technologies LLC.  All rights reserved.  Veritas and the Veritas Logo are trademarks or registered trademarks of
Veritas Technologies LLC or its affiliates in the U.S. and other countries. Other names may be trademarks of their respective owners.

The Licensed Software and Documentation are deemed to be "commercial computer software" and "commercial computer software documentation" as
defined in FAR Sections 12.212 and DFARS Section 227.7202.

Logs are being written to /opt/VRTStmp/installer-202210140638Mmm while installer is in progress.


                                    Veritas InfoScale Storage and Availability Solutions 7.4.2 Install Program


Task Menu:

    P) Perform a Pre-Installation Check     I) Install a Product
    C) Configure a Product Component        G) Upgrade a Product
    O) Perform a Post-Installation Check    U) Uninstall a Product
    L) License a Product                    S) Start a Product
    D) View Product Descriptions            X) Stop a Product
    R) View Product Requirements            ?) Help

Enter a Task: [P,I,C,G,O,U,L,S,D,X,R,?] P


                                   Veritas InfoScale Storage and Availability Solutions 7.4.2 Precheck Program

     1)  Veritas InfoScale Foundation
     2)  Veritas InfoScale Availability
     3)  Veritas InfoScale Storage
     4)  Veritas InfoScale Enterprise
     b)  Back to previous menu

Select a product to perform pre-installation check for: [1-4,b,q] 4

     1)  Cluster Server (VCS)
     2)  Storage Foundation (SF)
     3)  Storage Foundation and High Availability (SFHA)
     4)  Storage Foundation Cluster File System HA (SFCFSHA)
     5)  Storage Foundation for Oracle RAC (SF Oracle RAC)

Select a component to perform pre-installation check for: [1-5,q] 3

Enter the system names separated by spaces: [q,?] verclus01 verclus02

                                               Veritas InfoScale Enterprise 7.4.2 Precheck Program
                                                                verclus01 verclus02

Logs are being written to /opt/VRTStmp/installer-202210140638Mmm while installer is in progress

    Verifying systems: 12%               _____________________________________________________________________________________________________

    Estimated time remaining: (mm:ss) 0:10                                                                                              1 of 8

    Checking system communication ............................................................................................. Partially Done
Either ssh or rsh needs to be set up between the local system and verclus02 for communication

Would you like the installer to setup ssh or rsh communication automatically between the systems?
Superuser passwords for the systems will be asked. [y,n,q,?] (y) y

Enter the superuser password for system verclus02:

     1)  Setup ssh between the systems
     2)  Setup rsh between the systems
     b)  Back to previous menu

Select the communication method [1-2,b,q,?] (1) 1

Would you like to use the path '/var/tmp' on the remote system(s) to copy the ssh public key? [y,n,q] (y) y

Setting up communication between systems. Please wait.
Re-verifying systems.


                                               Veritas InfoScale Enterprise 7.4.2 Precheck Program
                                                                verclus01 verclus02

Logs are being written to /opt/VRTStmp/installer-202210140638Mmm while installer is in progress

    Verifying systems: 100%

    Estimated time remaining: (mm:ss) 0:00                                                                                              8 of 8

    Checking system communication ....................................................................................................... Done
    Checking release compatibility ...................................................................................................... Done
    Checking installed product .......................................................................................................... Done
    Checking platform version ........................................................................................................... Done
    Checking prerequisite patches and rpms ............................................................................................ Failed
    Checking file system free space ..................................................................................................... Done
    Checking configured component ....................................................................................................... Done
    Performing product prechecks ........................................................................................................ Done

The following required OS rpms were not found on verclus01:
        perl.x86_64 libhbalinux.x86_64 ed.x86_64 ksh.x86_64 perl-Socket.x86_64 perl-Exporter.noarch libhbaapi.x86_64

The following required OS rpms were not found on verclus02:
        perl.x86_64 libhbalinux.x86_64 ed.x86_64 ksh.x86_64 perl-Socket.x86_64 perl-Exporter.noarch libhbaapi.x86_64

The installer provides some guidance about how to install OS rpms using native methods, like yum, or how to manually install the required OS rpms.

     1)  Install the missing required OS rpms with yum, if yum is configured on the systems
     2)  Install the missing required OS rpms manually, (detailed steps are provided)
     3)  Do not install the missing required OS rpms

How would you like to install the missing required OS rpms? [1-3,q,?] (1) 1

The installation may take a few minutes, be patient.

    Install the missing OS rpms with yum on verclus01
................................................................................... Done
    Install the missing OS rpms with yum on verclus02
................................................................................... Done

Press [Enter] to continue:

                                               Veritas InfoScale Enterprise 7.4.2 Precheck Program
                                                                verclus01 verclus02

Logs are being written to /opt/VRTStmp/installer-202210140638Mmm while installer is in progress

    Verifying systems: 100%

    Estimated time remaining: (mm:ss) 0:00                                                                                              8 of 8

    Checking system communication ....................................................................................................... Done
    Checking release compatibility ...................................................................................................... Done
    Checking installed product .......................................................................................................... Done
    Checking platform version ........................................................................................................... Done
    Checking prerequisite patches and rpms .............................................................................................. Done
    Checking file system free space ..................................................................................................... Done
    Checking configured component ....................................................................................................... Done
    Performing product prechecks ........................................................................................................ Done

Precheck report completed

System verification checks completed

The following notes were discovered on the systems:

CPI NOTE V-9-30-1021 The system information on verclus01:
        Operating system: Linux CentOS 7.9 x86_64
        CPU number: 1
        CPU speed: 2712 MHz
        Memory size: 3789 MB
        Swap size: 8191 MB

CPI NOTE V-9-30-1021 The system information on verclus02:
        Operating system: Linux CentOS 7.9 x86_64
        CPU number: 1
        CPU speed: 2712 MHz
        Memory size: 3789 MB
        Swap size: 8191 MB

The following warnings were discovered on the systems:

CPI WARNING V-9-40-1418 Kernel Release 3.10.0-1160.76.1.el7.x86_64 is detected on verclus01, which is not recognizable by the installer. It is
strongly recommended to check it on SORT (https://sort.veritas.com) before continue.

CPI WARNING V-9-40-1418 Kernel Release 3.10.0-1160.76.1.el7.x86_64 is detected on verclus02, which is not recognizable by the installer. It is
strongly recommended to check it on SORT (https://sort.veritas.com) before continue.

Would you like to install InfoScale Enterprise on verclus01 verclus02? [y,n,q] (n)

ssh is configured in password-less mode on verclus02

Do you want to cleanup the communication for the systems verclus02? [y,n,q] (n)

installer log files, summary file, and response file are saved at:

        /opt/VRTS/install/logs/installer-202210140638Mmm

Would you like to view the summary file? [y,n,q] (n)

[root@verclus01 rhel7_x86_64]#
[root@verclus01 rhel7_x86_64]#
[root@verclus01 rhel7_x86_64]# ./installer

                                    Veritas InfoScale Storage and Availability Solutions 7.4.2 Install Program

Copyright (c) 2020 Veritas Technologies LLC.  All rights reserved.  Veritas and the Veritas Logo are trademarks or registered trademarks of
Veritas Technologies LLC or its affiliates in the U.S. and other countries. Other names may be trademarks of their respective owners.

The Licensed Software and Documentation are deemed to be "commercial computer software" and "commercial computer software documentation" as
defined in FAR Sections 12.212 and DFARS Section 227.7202.

Logs are being written to /opt/VRTStmp/installer-202210140647HON while installer is in progress.


                                    Veritas InfoScale Storage and Availability Solutions 7.4.2 Install Program


Task Menu:

    P) Perform a Pre-Installation Check     I) Install a Product
    C) Configure a Product Component        G) Upgrade a Product
    O) Perform a Post-Installation Check    U) Uninstall a Product
    L) License a Product                    S) Start a Product
    D) View Product Descriptions            X) Stop a Product
    R) View Product Requirements            ?) Help

Enter a Task: [P,I,C,G,O,U,L,S,D,X,R,?] I


                                    Veritas InfoScale Storage and Availability Solutions 7.4.2 Install Program

     1)  Veritas InfoScale Foundation
     2)  Veritas InfoScale Availability
     3)  Veritas InfoScale Storage
     4)  Veritas InfoScale Enterprise
     b)  Back to previous menu

Select a product to install: [1-4,b,q,?] 4

Would you like to configure InfoScale Enterprise after installation? [y,n,q] (n) n

This product may contain open source and other third party materials that are subject to a separate license. See the applicable Third-Party Notice
at https://www.veritas.com/about/legal/license-agreements

Do you agree with the terms of the End User License Agreement as specified in the EULA/en/EULA.pdf file present on media? [y,n,q,?] y

Enter the system names separated by spaces: [q,?] verclus01 verclus02

                                                Veritas InfoScale Enterprise 7.4.2 Install Program
                                                                verclus01 verclus02

Logs are being written to /opt/VRTStmp/installer-202210140647HON while installer is in progress

    Verifying systems: 100%

    Estimated time remaining: (mm:ss) 0:00                                                                                              8 of 8

    Checking system communication ....................................................................................................... Done
    Checking release compatibility ...................................................................................................... Done
    Checking installed product .......................................................................................................... Done
    Checking platform version ........................................................................................................... Done
    Checking prerequisite patches and rpms .............................................................................................. Done
    Checking file system free space ..................................................................................................... Done
    Checking configured component ....................................................................................................... Done
    Performing product prechecks ........................................................................................................ Done

System verification checks completed

The following warnings were discovered on the systems:

CPI WARNING V-9-40-1418 Kernel Release 3.10.0-1160.76.1.el7.x86_64 is detected on verclus01, which is not recognizable by the installer. It is
strongly recommended to check it on SORT (https://sort.veritas.com) before continue.

CPI WARNING V-9-40-1418 Kernel Release 3.10.0-1160.76.1.el7.x86_64 is detected on verclus02, which is not recognizable by the installer. It is
strongly recommended to check it on SORT (https://sort.veritas.com) before continue.

Do you want to continue? [y,n,q] (y) y


                                                Veritas InfoScale Enterprise 7.4.2 Install Program
                                                                verclus01 verclus02

Logs are being written to /opt/VRTStmp/installer-202210140647HON while installer is in progress

    Installing InfoScale Enterprise: 100%

    Estimated time remaining: (mm:ss) 0:00                                                                                            29 of 29

    Installing VRTSvxfs rpm ............................................................................................................. Done
    Installing VRTSfsadv rpm ............................................................................................................ Done
    Installing VRTSllt rpm .............................................................................................................. Done
    Installing VRTSgab rpm .............................................................................................................. Done
    Installing VRTSvxfen rpm ............................................................................................................ Done
    Installing VRTSamf rpm .............................................................................................................. Done
    Installing VRTSvcs rpm .............................................................................................................. Done
    Installing VRTScps rpm .............................................................................................................. Done
    Installing VRTSvcsag rpm ............................................................................................................ Done
    Installing VRTSvcsea rpm ............................................................................................................ Done
    Installing VRTSdbed rpm ............................................................................................................. Done
    Installing VRTSglm rpm .............................................................................................................. Done
    Installing VRTScavf rpm ............................................................................................................. Done
    Installing VRTSgms rpm .............................................................................................................. Done
    Installing VRTSodm rpm .............................................................................................................. Done
    Installing VRTSdbac rpm ............................................................................................................. Done
    Installing VRTSsfmh rpm ............................................................................................................. Done
    Installing VRTSvbs rpm .............................................................................................................. Done
    Installing VRTSsfcpi rpm ............................................................................................................ Done
    Installing VRTSvcswiz rpm ........................................................................................................... Done
    Performing InfoScale Enterprise postinstall tasks ................................................................................... Done

Veritas InfoScale Enterprise Install completed successfully


                                                Veritas InfoScale Enterprise 7.4.2 Install Program
                                                                verclus01 verclus02

To comply with the terms of our End User License Agreement, you have 60 days to either:

 * Enter a valid license key matching the functionality in use on the systems
 * Enable keyless licensing and manage the systems with a Management Server. For more details visit
http://www.veritas.com/community/blogs/introducing-keyless-feature-enablement-storage-foundation-ha-51. The product is fully functional during
these 60 days.

     1)  Enter a valid license key(Key file path needed)
     2)  Enable keyless licensing and complete system licensing later

How would you like to license the systems? [1-2,q] (2) 2

     1)  Veritas InfoScale Foundation
     2)  Veritas InfoScale Availability
     3)  Veritas InfoScale Storage
     4)  Veritas InfoScale Enterprise
     b)  Back to previous menu

Which product would you like to register? [1-4,b,q] (4) 4
Registering keyless key ENTERPRISE on Veritas InfoScale Enterprise
Successfully registered ENTERPRISE keyless key on verclus01
Successfully registered ENTERPRISE keyless key on verclus02

The updates to VRTSaslapm package are released via the SORT web page: https://sort.veritas.com/asl. To make sure you have the latest version of
VRTSaslapm (for up to date ASLs and APMs), download and install the latest package from the SORT web page.

You are running this virtual machine under a VMware environment. You may access the cluster view for this virtual machine using the vSphere
client. To access the cluster view for the virtual machine using the vSphere client, log on to the vCenter Server through the vSphere client,
navigate to the virtual machine in the inventory view and click on the 'High Availability' tab.
You may also access the cluster view from a browser. To access the cluster view through a browser, open the URL below in a browser:

https://<VM_IP_or_Hostname>:5634/vcs/admin/application_health.html

Veritas InfoScale Enterprise cannot be started without configuration.

Run the '/opt/VRTS/install/installer -configure' command when you are ready to configure Veritas InfoScale Enterprise.

Checking online updates for Veritas InfoScale Enterprise 7.4.2

        No updates available for Veritas InfoScale Enterprise 7.4.2

        Visit https://sort.veritas.com for more information.

installer log files, summary file, and response file are saved at:

        /opt/VRTS/install/logs/installer-202210140647HON

Would you like to view the summary file? [y,n,q] (n) n

[root@verclus01 rhel7_x86_64]# ha
halt      hardlink  hash
[root@verclus01 rhel7_x86_64]# ls
copyright  docs  EULA  installer  perl  rpms  scripts  tools
[root@verclus01 rhel7_x86_64]#
[root@verclus01 rhel7_x86_64]# ./installer
^C
CPI WARNING V-9-20-1183 Interrupt Received--installer terminated

[root@verclus01 rhel7_x86_64]# ./installer -configure

                                   Veritas InfoScale Storage and Availability Solutions 7.4.2 Configure Program

Copyright (c) 2020 Veritas Technologies LLC.  All rights reserved.  Veritas and the Veritas Logo are trademarks or registered trademarks of
Veritas Technologies LLC or its affiliates in the U.S. and other countries. Other names may be trademarks of their respective owners.

The Licensed Software and Documentation are deemed to be "commercial computer software" and "commercial computer software documentation" as
defined in FAR Sections 12.212 and DFARS Section 227.7202.

Logs are being written to /opt/VRTStmp/installer-202210140725LhZ while installer is in progress.


                                   Veritas InfoScale Storage and Availability Solutions 7.4.2 Configure Program

     1)  Veritas InfoScale Foundation
     2)  Veritas InfoScale Availability
     3)  Veritas InfoScale Storage
     4)  Veritas InfoScale Enterprise

Select a product to configure: [1-4,q] 4

     1)  Cluster Server (VCS)
     2)  Storage Foundation (SF)
     3)  Storage Foundation and High Availability (SFHA)
     4)  Storage Foundation Cluster File System HA (SFCFSHA)
     5)  Storage Foundation for Oracle RAC (SF Oracle RAC)

Select a component to configure: [1-5,q] 3

Enter the system names separated by spaces: [q,?] verclus01 verclus02

                                               Veritas InfoScale Enterprise 7.4.2 Configure Program
                                                                verclus01 verclus02

Logs are being written to /opt/VRTStmp/installer-202210140725LhZ while installer is in progress

    Verifying systems: 100%

    Estimated time remaining: (mm:ss) 0:00                                                                                              7 of 7

    Checking system communication ....................................................................................................... Done
    Checking release compatibility ...................................................................................................... Done
    Checking installed product .......................................................................................................... Done
    Checking platform version ........................................................................................................... Done
    Checking configured component ....................................................................................................... Done
    Checking product licensing .......................................................................................................... Done
    Performing product prechecks ........................................................................................................ Done

System verification checks completed successfully

I/O Fencing

It needs to be determined at this time if you plan to configure I/O Fencing in enabled or disabled mode, as well as help in determining the number
of network interconnects (NICS) required on your systems. If you configure I/O Fencing in enabled mode, only a single NIC is required, though at
least two are recommended.

A split brain can occur if servers within the cluster become unable to communicate for any number of reasons. If I/O Fencing is not enabled, you
run the risk of data corruption should a split brain occur. Therefore, to avoid data corruption due to split brain in CFS environments, I/O
Fencing has to be enabled.

If you do not enable I/O Fencing, you do so at your own risk

See the Administrator's Guide for more information on I/O Fencing

Do you want to configure I/O Fencing in enabled mode? [y,n,q,?] (y) y


                                               Veritas InfoScale Enterprise 7.4.2 Configure Program
                                                                verclus01 verclus02

To configure VCS, answer the set of questions on the next screen.

When [b] is presented after a question, 'b' may be entered to go back to the first question of the configuration set.

When [?] is presented after a question, '?' may be entered for help or additional information about the question.

Following each set of questions, the information you have entered will be presented for confirmation.  To repeat the set of questions and correct
any previous errors, enter 'n' at the confirmation prompt.

No configuration changes are made to the systems until all configuration questions are completed and confirmed.

Press [Enter] to continue:

                                               Veritas InfoScale Enterprise 7.4.2 Configure Program
                                                                verclus01 verclus02

To configure VCS for InfoScale Enterprise the following information is required:

        A unique cluster name
        One or more NICs per system used for heartbeat links
        A unique cluster ID number between 0-65535

        One or more heartbeat links are configured as private links
        You can configure one heartbeat link as a low-priority link

All systems are being configured to create one cluster.

Enter the unique cluster name: [q,?] vcs-cluster

                                               Veritas InfoScale Enterprise 7.4.2 Configure Program
                                                                verclus01 verclus02

     1)  Configure the heartbeat links using LLT over Ethernet
     2)  Configure the heartbeat links using LLT over UDP
     3)  Configure the heartbeat links using LLT over TCP
     4)  Configure the heartbeat links using LLT over RDMA
     5)  Automatically detect configuration for LLT over Ethernet
     b)  Back to previous menu

How would you like to configure heartbeat links? [1-5,b,q,?] (5) 5

On Linux systems, only activated NICs can be detected and configured automatically.

Press [Enter] to continue:

                                               Veritas InfoScale Enterprise 7.4.2 Configure Program
                                                                verclus01 verclus02

Logs are being written to /opt/VRTStmp/installer-202210140725LhZ while installer is in progress

    Configuring LLT links: 100%

    Estimated time remaining: (mm:ss) 0:00                                                                                              4 of 4

    Checking system NICs on verclus01 ........................................................................................... 3 NICs found
    Checking system NICs on verclus02 ........................................................................................... 3 NICs found
    Checking network links ..................................................................................................... 3 links found
    Setting link priority ............................................................................................................... Done

Enter a unique cluster ID number between 0-65535: [b,q,?] (2946)

The cluster cannot be configured if the cluster ID 2946 is in use by another cluster. Installer can perform a check to determine if the cluster ID
is duplicate. The check will take less than a minute to complete.

Would you like to check if the cluster ID is in use by another cluster? [y,n,q] (y)

    Checking cluster ID
................................................................................................................. Done

Duplicated cluster ID detection passed. The cluster ID 2946 can be used for the cluster.

Press [Enter] to continue:
                                               Veritas InfoScale Enterprise 7.4.2 Configure Program
                                                                verclus01 verclus02

Cluster information verification:

        Cluster Name:      vcs-cluster
        Cluster ID Number: 2946

        Private Heartbeat NICs for verclus01:
                link1=enp0s8
                link2=enp0s9
        Low-Priority Heartbeat NIC for verclus01:
                link-lowpri1=enp0s3

        Private Heartbeat NICs for verclus02:
                link1=enp0s8
                link2=enp0s9
        Low-Priority Heartbeat NIC for verclus02:
                link-lowpri1=enp0s3

Is this information correct? [y,n,q,?] (y) y

                                               Veritas InfoScale Enterprise 7.4.2 Configure Program
                                                                verclus01 verclus02

The following data is required to configure the Virtual IP of the Cluster:

        A public NIC used by each system in the cluster
        A Virtual IP address and netmask

Do you want to configure the Virtual IP? [y,n,q,?] (n) y

Active NIC devices discovered on verclus01: enp0s3 enp0s8 enp0s9

Enter the NIC for Virtual IP of the Cluster to use on verclus01: [b,q,?] (enp0s3)
Is enp0s3 to be the public NIC used by all systems? [y,n,q,b,?] (y)
Enter the Virtual IP address for the Cluster: [b,q,?] 192.168.9.150
Enter the NetMask for IP 192.168.9.150: [b,q,?] (255.255.255.0)

                                               Veritas InfoScale Enterprise 7.4.2 Configure Program
                                                                verclus01 verclus02

Cluster Virtual IP verification:

        NIC: enp0s3
        IP: 192.168.9.150
        NetMask: 255.255.255.0

Is this information correct? [y,n,q] (y) y

                                               Veritas InfoScale Enterprise 7.4.2 Configure Program
                                                                verclus01 verclus02

We recommend that you run Cluster Server in secure mode.

Running VCS in Secure Mode guarantees that all inter-system communication is encrypted, and users are verified with security credentials.

When running VCS in Secure Mode, NIS and system usernames and passwords are used to verify identity. VCS usernames and passwords are no longer
utilized when a cluster is running in Secure Mode.

Would you like to configure the VCS cluster in secure mode? [y,n,q,?] (y) n

CPI WARNING V-9-40-3390 We recommend that you install the cluster in secure mode. This ensures that communication between cluster components is
encrypted and cluster information is visible to specified users only.


Are you sure that you want to proceed with non-secure installation? [y,n,q] (n) y

                                               Veritas InfoScale Enterprise 7.4.2 Configure Program
                                                                verclus01 verclus02

The following information is required to add VCS users:

        A user name
        A password for the user
        User privileges (Administrator, Operator, or Guest)

Do you wish to accept the default cluster credentials of 'admin/password'? [y,n,q] (y) y

Do you want to add another user to the cluster? [y,n,q] (n) n

                                               Veritas InfoScale Enterprise 7.4.2 Configure Program
                                                                verclus01 verclus02

VCS User verification:

        User: admin     Privilege: Administrator

        Passwords are not displayed

Is this information correct? [y,n,q] (y) y

                                               Veritas InfoScale Enterprise 7.4.2 Configure Program
                                                                verclus01 verclus02

The following information is required to configure SMTP notification:

        The domain-based hostname of the SMTP server
        The email address of each SMTP recipient
        A minimum severity level of messages to send to each recipient

Do you want to configure SMTP notification? [y,n,q,?] (n)

                                               Veritas InfoScale Enterprise 7.4.2 Configure Program
                                                                verclus01 verclus02

The following information is required to configure SNMP notification:

        System names of SNMP consoles to receive VCS trap messages
        SNMP trap daemon port numbers for each console
        A minimum severity level of messages to send to each console

Do you want to configure SNMP notification? [y,n,q,?] (n)


                                               Veritas InfoScale Enterprise 7.4.2 Configure Program
                                                                verclus01 verclus02

The following data is required to configure the Global Cluster Option:

        A public NIC used by each system in the cluster
        A Virtual IP address and netmask

Do you want to configure the Global Cluster Option? [y,n,q,?] (n) n

All InfoScale Enterprise processes that are currently running must be stopped

Do you want to stop InfoScale Enterprise processes now? [y,n,q,?] (y) y


                                               Veritas InfoScale Enterprise 7.4.2 Configure Program
                                                                verclus01 verclus02

Logs are being written to /opt/VRTStmp/installer-202210140725LhZ while installer is in progress

    Stopping InfoScale Enterprise: 100%

    Estimated time remaining: (mm:ss) 0:00                                                                                            11 of 11

    Performing InfoScale Enterprise prestop tasks ....................................................................................... Done
    Stopping vcsmm ...................................................................................................................... Done
    Stopping vxgms ...................................................................................................................... Done
    Stopping vxglm ...................................................................................................................... Done
    Stopping vxcpserv ................................................................................................................... Done
    Stopping had ........................................................................................................................ Done
    Stopping amf ........................................................................................................................ Done
    Stopping vxfen ...................................................................................................................... Done
    Stopping gab ........................................................................................................................ Done
    Stopping llt ........................................................................................................................ Done
    Performing InfoScale Enterprise poststop tasks ...................................................................................... Done

Veritas InfoScale Enterprise Shutdown completed successfully


                                               Veritas InfoScale Enterprise 7.4.2 Configure Program
                                                                verclus01 verclus02

Logs are being written to /opt/VRTStmp/installer-202210140725LhZ while installer is in progress

    Starting SFHA: 100%

    Estimated time remaining: (mm:ss) 0:00                                                                                            22 of 22

    Starting CollectorService ........................................................................................................... Done
    Starting veki ....................................................................................................................... Done
    Starting vxdmp ...................................................................................................................... Done
    Starting vxio ....................................................................................................................... Done
    Starting vxspec ..................................................................................................................... Done
    Starting vxconfigd .................................................................................................................. Done
    Starting vxvm-recover ............................................................................................................... Done
    Starting vxencryptd ................................................................................................................. Done
    Starting vvr ........................................................................................................................ Done
    Starting vxcloud .................................................................................................................... Done
    Starting xprtld ..................................................................................................................... Done
    Starting vxfs ....................................................................................................................... Done
    Starting vxportal ................................................................................................................... Done
    Starting fdd ........................................................................................................................ Done
    Starting vxcafs ..................................................................................................................... Done
    Starting llt ........................................................................................................................ Done
    Starting gab ........................................................................................................................ Done
    Starting amf ........................................................................................................................ Done
    Starting had ........................................................................................................................ Done
    Starting vxodm ...................................................................................................................... Done
    Performing SFHA poststart tasks ..................................................................................................... Done

Storage Foundation and High Availability Startup completed successfully


                                               Veritas InfoScale Enterprise 7.4.2 Configure Program
                                                                verclus01 verclus02

Fencing configuration
     1)  Configure Coordination Point client based fencing
     2)  Configure disk based fencing
     3)  Configure majority based fencing

Select the fencing mechanism to be configured in this Application Cluster: [1-3,q,?] 3

Majority-based I/O fencing has limited functionality. In case of a split brain, where none of the sub-clusters have a majority or where the
sub-cluster having majority is hung, all nodes in the cluster may panic. Refer to VCS Administrator's Guide for more details.

Do you want to continue? [y,n,q] (n) y

Does your storage environment support SCSI3 PR? [y,n,q,?] n

Installer will stop VCS before applying fencing configuration. To make sure VCS shuts down successfully, unfreeze any frozen service group and
unmount the mounted file systems in the cluster.

HAD and all the applications will be stopped. Do you want to stop VCS and all its applications and apply fencing configuration on all nodes at
this point? [y,n,q] (y) y
    Stopping VCS on verclus01 ........................................................................................................... Done
    Stopping vxodm on verclus01 ......................................................................................................... Done
    Stopping gab on verclus01 ........................................................................................................... Done
    Stopping VCS on verclus02 ........................................................................................................... Done
    Stopping vxodm on verclus02 ......................................................................................................... Done
    Stopping gab on verclus02 ........................................................................................................... Done
    Updating /etc/vxfenmode file on verclus01 ........................................................................................... Done
    Updating /etc/vxenviron file on verclus01 ........................................................................................... Done
    Updating /etc/sysconfig/vxfen file on verclus01 ..................................................................................... Done
    Updating /etc/llttab file on verclus01 .............................................................................................. Done
    Updating /etc/vxfenmode file on verclus02 ........................................................................................... Done
    Updating /etc/vxenviron file on verclus02 ........................................................................................... Done
    Updating /etc/sysconfig/vxfen file on verclus02 ..................................................................................... Done
    Updating /etc/llttab file on verclus02 .............................................................................................. Done
    Starting gab on verclus01 ........................................................................................................... Done
    Starting gab on verclus02 ........................................................................................................... Done
    Starting vxfen on verclus01 ......................................................................................................... Done
    Starting vxfen on verclus02 ......................................................................................................... Done
    Starting vxodm on verclus01 ......................................................................................................... Done
    Starting vxodm on verclus02 ......................................................................................................... Done
    Updating main.cf with fencing ....................................................................................................... Done
    Starting VCS on verclus01 ........................................................................................................... Done
    Starting VCS on verclus02 ........................................................................................................... Done
    I/O Fencing configuration ........................................................................................................... Done

I/O Fencing configuration completed successfully

The updates to VRTSaslapm package are released via the SORT web page: https://sort.veritas.com/asl. To make sure you have the latest version of
VRTSaslapm (for up to date ASLs and APMs), download and install the latest package from the SORT web page.

You are running this virtual machine under a VMware environment. You may access the cluster view for this virtual machine using the vSphere
client. To access the cluster view for the virtual machine using the vSphere client, log on to the vCenter Server through the vSphere client,
navigate to the virtual machine in the inventory view and click on the 'High Availability' tab.
You may also access the cluster view from a browser. To access the cluster view through a browser, open the URL below in a browser:

https://<VM_IP_or_Hostname>:5634/vcs/admin/application_health.html

Installation procedures and diagnostic information are saved in the log files under directory /opt/VRTStmp/installer-202210140725LhZ. This
information helps us identify and resolve failed operations performed by the installer. Would you like to send the information to us to help
improve installation in the future? [y,n,q,?] (y) n

installer log files, summary file, and response file are saved at:

        /opt/VRTS/install/logs/installer-202210140725LhZ

Would you like to view the summary file? [y,n,q] (n)

[root@verclus01 rhel7_x86_64]#
[root@verclus01 rhel7_x86_64]# ha
halt      hardlink  hash
[root@verclus01 rhel7_x86_64]# ps -ef | grep -i h

```
