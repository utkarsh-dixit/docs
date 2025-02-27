---
title: Use High Performance with rClone
slug: s3/rclone
excerpt: Learn how to set up Rclone to synchronize your files to and from High Performance.
section: Object Storage S3 High Performance
order: 110
---

**Last updated on 3rd January 2022**

## Objective

Rclone is a backup tool that can sync to and from various storage backends, and can be used on Windows, macOS and Linux.

**This guide explains how to set up Rclone to synchronize your files to and from High Performance.**

## Requirements

- A bucket
- A user and defined the required access rights on the bucket
- Your S3 credentials (access_key and secret_access_key)

See our [Getting started with S3 High Performance](https://docs.ovh.com/ca/en/storage/s3/getting-started-with-s3) guide.

## Instructions

To configure Rclone, edit or create the `~/.config/rclone/rclone.conf` file and add this:

```bash
[<remote_name>]
type = s3
provider = Other
env_auth = false
access_key_id = <access_key>
secret_access_key = <secret_key>
endpoint = https://s3.<region>.perf.cloud.ovh.net
acl = private
region = <region>
location_constraint = <region>
```

Rclone is now ready for use.

**Command examples**

List all buckets:

```bash
$ rclone lsd <remote_name>:
```

Create a new bucket:

```bash
$ rclone mkdir <remote_name>:mybucket
```

List the contents of a bucket:

```bash
$ rclone ls <remote_name>:mybucket
```

Synchronise `/home/user/documents` to a bucket:

```bash
$ rclone sync /home/user/documents <remote_name>:mybucket
```

Copy a file `/home/user/file.txt` into a bucket:

```bash
$ rclone copy /home/user/file.txt <remote_name>:mybucket
```

Download a file `file.txt` from a bucket:

```bash
$ rclone copy <remote_name>:mybucket/file.txt fichier.txt
```

You will find on the official rClone website a detailed documentation of the possible actions: [Official rClone documentation](https://rclone.org/docs/){.external}.

## Go further

Join our community of users on [https://community.ovh.com/en](https://community.ovh.com/en){.external}.
