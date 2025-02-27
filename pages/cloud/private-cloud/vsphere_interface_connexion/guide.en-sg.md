---
title: Logging in to the vSphere interface
slug: login-vsphere-interface
excerpt: Find out about the different ways you can log in to vSphere
section: 'Getting started'
order: 2
---

**Last updated 28th December 2021**

## Objective

**This guide explains the different ways to connect to the vSphere client.**

## Requirements

- Being an administrative contact of your [Hosted Private Cloud infrastructure](https://www.ovhcloud.com/en-sg/enterprise/products/hosted-private-cloud/) to receive login credentials
- A user account with access to vSphere (created in the [OVHcloud Control Panel](https://ca.ovh.com/auth/?action=gotomanager&from=https://www.ovh.com/sg/&ovhSubsidiary=sg))

## Instructions

### Retrieving credentials

Login credentials are sent out by email when the Private Cloud service is created, when a password is changed or when a user profile is created.

```
Name/IP address: pcc-xxx-xxx-xxx-xxx.ovh.com Username: admin password: xxxxxx
```

To ensure access, please refer to the VMware documentation, in which the different ports to be opened in your firewall are listed: [Client access](https://kb.vmware.com/kb/1012382){.external}.


### Using the HTML5 web client

The HTML5 web client is available on the Private Cloud web interface at this URL: <https://pcc-xxx-xxx-xxx-xxx.ovh.com/ui> (replace pcc-xxx-xxx-xxx-xxx.ovh.com with your Private Cloud address).

![Connecting to vSphere HTML5](images/connection_interface_w_html5.png){.thumbnail}

You will arrive at this interface:

![Connecting to vSphere HTML5](images/vsphere-client-html5.png){.thumbnail}

The `Home`{.action} page provides accces to the main menus of your vCenter.

### Using the Flash web client

The Flash web client is available on the Private Cloud web interface at this URL: <https://pcc-xxx-xxx-xxx-xxx.ovh.com/vsphere-client> (replace pcc-xxx-xxx-xxx-xxx.ovh.com with your Private Cloud address).

Log in using the credentials that were sent to you:

![vSphere client](images/vsphere-client.png){.thumbnail}

You can then access this interface:

![Connecting to the vSphere interface](images/connection_interface_w.png){.thumbnail}

On the `Home`{.action} page you can find your vCenter main menus.

## Go further

Join our community of users on <https://community.ovh.com/en/>.
