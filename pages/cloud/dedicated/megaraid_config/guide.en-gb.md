---
title: 'Configuring MegaRAID for RAID Level 0'
slug: using-the-maximum-amount-of-disk-space
excerpt: 'This guide will help you to configure your server’s disks with RAID 0, which will allow you to use all of the usable space.'
section: 'RAID and disks'
---

**Last updated 2nd August 2018**
 
## Objective

Redundant Array of Independent Disks (RAID) is a utility that mitigates data loss on a server by replicating data across two or more disks.

The default RAID level for OVH server installations is RAID 1, which doubles the space taken up by your data, effectively halving the usable disk space.

**This guide will help you to configure your server’s disks with RAID 0, which will allow you to use all your disks' usable space.**

> [!warning]
> 
> Please note: RAID 0 provides **NO FAULT TOLERANCE** and **NO DATA REDUNDANCY**, making data loss in the event of disk failure highly likely.
> 

## Requirements

- a [dedicated server](https://www.ovhcloud.com/en-gb/bare-metal/){.external} with hardware RAID
- administrative (root) access to the server via SSH

## Instructions

### Using the OVHcloud Control Panel

In the [OVHcloud Control Panel](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.co.uk/&ovhSubsidiary=GB){.external}, click on the `Bare Metal Cloud`{.action} menu and then select your server by going to `Dedicated Servers`{.action} in the left-hand sidebar. 

Next, on the `Server status`{.action} tab, click the `Reinstall`{.action} button to install a new operating system with your custom RAID 0 configuration.

Now select **Install from an OVH template** and then click `Next`{.action}.

![megaraid](images/server_installation_raid0_1.png){.thumbnail}

Select the operating system you want to install and then click `Next`{.action}.

Tick the boxes for **Customise the hardware RAID configuration** and **Customise the partition configuration**, then click `Next`{.action}.

![megaraid](images/server_installation_raid0_2.png){.thumbnail}

Select raid0 from the RAID drop-down list and click `Next`{.action}.

![megaraid](images/server_installation_raid0_3.png){.thumbnail}

Configure the partitions as you see fit and then click `Next`{.action}.

![megaraid](images/server_installation_raid0_4.png){.thumbnail}

Finally, click `Confirm`{.action}.

![megaraid](images/server_installation_raid0_5.png){.thumbnail}

After your server has been installed, check the partition sizes by logging on to the server via SSH and running the following command:

```sh
df -h
```

### Using rescue mode

In the [OVH Control Panel](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.co.uk/&ovhSubsidiary=GB){.external}, click on the `Bare Metal Cloud`{.action} menu and then select your server by going to `Dedicated Servers`{.action} in the left-hand sidebar. 

On the `Server status`{.action} tab, click the `Edit`{.action} button to change the boot system.

![megaraid](images/rescue_mode_raid0_1.png){.thumbnail}

Next, select `Boot in rescue mode`{.action} then select `rescue64-pro`{.action} from the drop-down list.

In the field "Send new login details to the following email address:", specify an alternative email address if you do not want the login credentials sent to your customer account’s primary address.

![megaraid](images/rescue_mode_raid0_2.png){.thumbnail}

Click `Next`{.action} and then click `Confirm`{.action} on the following screen.

![megaraid](images/rescue_mode_raid0_3.png){.thumbnail}

Once the change is completed, click on `...`{.action} next to “Status” in the box labelled **Service status**. Select `Restart`{.action} and the server will restart into rescue mode.

![megaraid](images/server_installation_raid0_6.png){.thumbnail}

When your server reboots, log in to it via SSH using the rescue mode credentials that were emailed to you.

From the command line, type the following commands to delete the existing RAID settings. All data in the RAID will be deleted:

```sh
MegaCli -CfgLdDel -L0 -a0
MegaCli -CfgLdDel -Lall -aAll
```

Type the following command to retrieve the slot device IDs of your disks:

```sh
MegaCli -PdList -aALL | egrep "Slot|Device ID"
```

Type the following commands to configure RAID level 0:

```sh
MegaCli -CfgLDAdd -R0[252:0,252:1] -a0
```

In this example, 252 is the ID of the drive enclosure.

After setting the new RAID level you can check the settings with the following command:

```sh
MegaCli -LDInfo -Lall -a0 |grep -i size
```

## Go further

[Hot Swap – Hardware RAID](https://docs.ovh.com/gb/en/dedicated/hotswap-raid-hard/){.external}

[Hot Swap – Software RAID](https://docs.ovh.com/gb/en/dedicated/hotswap-raid-soft/){.external}

[Hardware RAID](https://docs.ovh.com/gb/en/dedicated/raid-hard/){.external} 

Join our community of users on <https://community.ovh.com/en/>
