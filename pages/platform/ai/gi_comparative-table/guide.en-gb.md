---
title: Comparative tables between AI Notebooks, AI Training, AI Apps
slug: ai-comparative-tables
excerpt: Discover the main differences between each of the OVHcloud AI tools' bricks
section: General information
order: 100
---

**Last updated January 5th, 2022.**

## Objective

OVHcloud provides a set of managed tools designed for building your machine learning projects. 
This guide explains the main differences between our AI tools, commonly called AI Notebooks, AI Training and AI Apps.

## Overview

OVHcloud AI tools work inside our Public Cloud ecosystem. Once logged in to your Public Cloud project, you have access to AI tools including:

- **AI Notebooks**
- **AI Training**
- **AI Apps**

Each of them are autonomous tools, billed per minute and with shared elements, such as security tokens, etc.

All AI Tools have access to OVHcloud Object Storage as a central point, allowing you to work with your data securely and easily.

We schematize our AI offers this way:

![OVHcloud AI tools](images/AI_tools_overview.png){.thumbnail}

## Comparative tables

| Product offers              | AI Notebooks                                                                                 | AI Training                                                                                                                   | AI Apps                                                                                                             |
|-------------------|----------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| Description       | Managed Jupyter or VSCode notebook, linked to compute resources (CPU or GPU) and storage.    | Automate your trainings, deploy your own Docker container, linked to compute resources (CPU of GPU), and attached storage.    | Deploy with high-availability your own AI application and models via Docker containers or select one from our catalog |
| Billing Resources | per minute                                                                                   | per minute                                                                                                                    | per minute                                                                                                          |


| AI Features                                                                                                        | AI Notebooks               | AI Training                | AI Apps                    |
|--------------------------------------------------------------------------------------------------------------------|----------------------------|----------------------------|----------------------------|
| Managed Jupyter Notebook with preinstalled libraries                                                               | X                          |                            |                            |
| Managed VSCode Notebook with preinstalled libraries                                                                | X                          |                            |                            |
| Automate Training phases (timeout, grid computing, ...)                                                            |                            | X                          |                            |
| Bring your own Docker image (with notebooks inside, models, whatever) and connect to compute and storage resources |                            | X                          | X                          |
| Deploy your managed applications and models with high-availability                                                 |                            |                            | X                          |
| Deploy AI applications from a catalog made with partners                                                           |                            |                            | X                          |


| Management                                                                                                         | AI Notebooks               | AI Training                | AI Apps                    |
|--------------------------------------------------------------------------------------------------------------------|----------------------------|----------------------------|----------------------------|
| Control panel                                                                                                      | X                          | X                          | X                          |
| API                                                                                                                | X                          | X                          | X                          |
| CLI                                                                                                                | X                          | X                          | X                          |


| Resources                                                                                                          | AI Notebooks                | AI Training                 | AI Apps                     |
|--------------------------------------------------------------------------------------------------------------------|-----------------------------|-----------------------------|-----------------------------|
| CPU resources                                                                                                      | X                           | X                           | X                           |
| CPU flavors available                                                                                              | ai1-1-CPU                   | ai1-1-CPU                   | ai1-1-CPU                   |
| GPU resources                                                                                                      | X                           | X                           | X                           |
| GPU flavors available                                                                                              | ai1-1-GPU                   | ai1-1-GPU                   | ai1-1-GPU                   |
| RAM Memory                                                                                                         | X                           | X                           | X                           |
| Dask computing                                                                                                     |                             | X                           |                             |
| Cold-patch resources (adjust gpu/cpu/, attached storage)                                                           | X                           |                             |                             |
| Local SSD-NVMe storage                                                                                             | X                           | X                           | X                           |
| Local SSD-NVMe storage size                                                                                        | depends on selected flavors | depends on selected flavors | depends on selected flavors |
| Ability to attach a remote storage (Object Storage)                                                                | X                           | X                           | X                           |
| Pull Storage Sync (from object storage)                                                                            | X                           | X                           | X                           |
| Push Storage sync (to object storage)                                                                              | X                           | X                           |                             |
| Maximum runtime                                                                                                    | unlimited                   | unlimited                   | unlimited                   |
| Ability to add a runtime timeout (via CLI)                                                                         |                             | X                           |                             |


| Security                                                                                                           | AI Notebooks               | AI Training                | AI Apps                    |
|--------------------------------------------------------------------------------------------------------------------|----------------------------|----------------------------|----------------------------|
| ACL via Openstack user                                                                                             | X                          | X                          | X                          |
| ACL via tokens                                                                                                     | X                          | X                          | X                          |
| Backups and resiliency                                                                                             |                            |                            |                            |
| Automatic backup                                                                                                   |                            |                            |                            |
| Backup when you stop                                                                                               | X                          |                            |                            |
| High availability                                                                                                  |                            |                            | X (when replicas > 1)      |
| Auto scaling                                                                                                       |                            |                            | Planned                    |


| Advanced features and parameters                                                                                   | AI Notebooks               | AI Training                | AI Apps                    |
|--------------------------------------------------------------------------------------------------------------------|----------------------------|----------------------------|----------------------------|
| Labels                                                                                                             | X                          | X                          | X                          |
| Start / Stop / Resume                                                                                              | X                          |                            | X                          |
| Easily import data from Git/* via UI                                                                               | X                          |                            |                            |
| Unchanging endpoint URL                                                                                            |                            |                            | X                          |

## Feedback

Please feel free to send us your questions, feedback and suggestions to help our team improve the service on the OVHcloud [Discord server](https://discord.com/invite/vXVurFfwe9) 
