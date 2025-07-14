---
slug: smlms-intro
id: wb6ybu9mjctz
type: challenge
title: RC - Welcome to SUSE Multi-Linux Hands-on Workshop!
teaser: Welcome to SUSE Multi-Linux Hands-on Workshop! in this section we will introduce
  you to the workshop and to its main components.
notes:
- type: text
  contents: |
    # Welcome to the SMLM/S
    Please wait while we setup your lab environment.
tabs:
- id: vuahsyyxgrd0
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: ""
enhanced_loading: null
---




# Welcome to <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">SUSE</b> Multi-Linux Hands-on Workshop
![Welcome](../assets/logos/01-welcome.jpeg)

In this workshop you will explore some of the magic that <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #fe7c3f">SUSE Multi-Linux Manager</b> (<b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #fe7c3f">SMLM</b>) can do, it is <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">SUSE</b>'s solution to manage multiple Linux distributions at scale from a unified interface. And also will discover how can you keep your legacy production servers supported with <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #2453ff">SUSE Multi-Linux Support</b> (<b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #2453ff">SMLS</b>), our professional and reliable support solution for Linux systems.

&emsp;&emsp; You will adopt the role of an **engineer** at <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b>, an airline where every plane has a Linux server onboard.

&emsp;&emsp; As with any airplane component, it is critical that those servers remain stable and reliable, no matter if they are located on the ground in some datacenter or flying above the clouds ☁ ☁ ☁


&emsp;&emsp; Some plane models will require a different Linux flavor, or a different CPU arquitecture. This is not an issue for <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #fe7c3f">SMLM</b>, you are free to choose the Linux distribution and CPU arquitecture that better suits your needs without having to give up on easy standardization and management.


&emsp;&emsp; As an engineer responsible for managing the Linux landscape you will go through some of the solutions <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #fe7c3f">SMLM</b> and <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #2453ff">SMLS</b> offers you to ease and automate systems management and resolve exceptional problems that may occur.


Along the different challenges you will have the following tools available:

 ✈ **SUSE Multi-Linux Manager**:
   The single pane of glass for managing all of your Linux stack.

 ✈ **Centos 7**:
   A legacy distribution still in use on some older planes and datacenters.

 ✈ **Ubuntu 24**: A Linux distribution required to run some of your graphics design applications.

 ✈ **SLES 15**: <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">SUSE</b>'s super reliable, stable and secure Linux distribution used for most of your systems.




## <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">SUSE Multi-Linux Manager</b>

It is a best-in-class open source infrastructure management solution for your software-defined infrastructure.

&emsp;&emsp; <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #fe7c3f">SUSE Multi-Linux Manager</b> was designed to help your enterprise DevOps and IT Operations teams reduce complexity and regain control of your IT assets, a single but very powerful tool to manage Linux systems across a variety of hardware architectures, hypervisors as well as container, IoT and cloud platforms.

&emsp;&emsp; It automates Linux server and IoT device provisioning, patching and configuration for faster, consistent and repeatable server deployment helping to optimize operations and reduce costs. And with automated monitoring, tracking, auditing and reporting of your systems, VMs, and containers across your development, test and production environments, you can ensure compliance with internal security policies and external regulations.


## <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">SUSE Multi-Linux Support</b>


It is a comprehensive service offering technical assistance and maintenance for various Linux distributions, including your existing Red Hat Enterprise Linux (RHEL), CentOS, <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #efefef">SUSE Liberty Linux</b>, and <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #90ebcd">SUSE Linux Enterprise Server</b> (<b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #90ebcd">SLES</b>), depending on the offering.

&emsp;&emsp; It enables organizations to manage mixed Linux environments efficiently under a single support framework.
Depending on the package purchased, <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #2453ff">SUSE Multi-Linux Support</b> may also include <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #fe7c3f">SUSE Multi-Linux Manager</b>, a multi-Linux management tool to manage these distributions.



 🌅 Explore the Instruqt UI
=======================
Before you start your new job, Let's take a minute to look at Instruqt UI.

+ The right side of the screen provides you with instructions for the Lab and navigation control

+ The left side give you access to the various machines and services that make up the labs.

Within the Instruqt UI we can jump between the [button label="SMLM UI" variant="success"](tab-0) and the available [button label="terminals" variant="success"](tab-1) by clicking on tabs.


🛫 Logging into <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">SUSE Multi-Linux Manager</b> 🛫
========================================

Let's get you familiarized with the environment. Open SUSE Multi-Linux Manager inside the lab from the [button label="SMLM UI" variant="success"](tab-0)


Login with the following credentials:

  - Username:

```txt
[[ Instruqt-Var key="SMLM_ADMIN_USERNAME" hostname="zbastion" ]]
```

  - Password:

```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

If everything went ok, you should see the Overview page in the SUSE Multi-Linux Manager UI and be logged in as `[[ Instruqt-Var key="SMLM_ADMIN_USERNAME" hostname="zbastion" ]]` user.

> [!NOTE]
> It could be that the browser tab needs to be refreshed after the environment is started.


🗺 Explore <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">SUSE Multi-Linux Manager</b> 🗺
======================================

We are going to explore some of the things that SUSE Multi-Linux Manager can do, this is not meant to be exhaustive list and is not going depth on any particular topic, we will see some of them in more details later during the workshop.


Here we just need to read, imagine be curious.

Let's start.


On the left hand side panel click on `systems`, here you can see the list of systems already registered, there are not many now, we will increase the list as we go through the exercises.


- **Systems menu** <img  style='vertical-align: middle; height: 40%; width: 40%; object-fit: contain' src="../assets/SMLM5.1/left_column_-_systems.png"/>

   - **System Lists**

     The `System List` section provides convenient, pre-filtered views, like `Out of Date`, that allows you to instantly see and select relevant systems without needing to perform a manual search each time. </p>


  - **System Groups**

    To organize systems according to your logic we have `System Groups`, you can categorize them based on your criteria, by doing so you can save time when applying actions or defining policies. Once created you can automatically attach systems to one or multiple groups, for example using `activation keys`.


    Try creating your own system groups just by clicking `+ Create Group` on the top-right corner of the frame.


  - **Batch operations**
    `System Set Manager` provides a powerful way to perform actions on multiple systems simultaneously.


    Instead of applying changes one by one, you can select a collection of systems, either individually from the System List or by leveraging existing System Groups, and then execute tasks across all of them in a single operation.


  - **Provisioning**

    SUSE Manager provides comprehensive tools for provisioning new systems and reprovisioning existing ones. This capability helps you establish a standardized and repeatable process for system deployment.


    For example, within `Autoinstallation` section you can define distributions and Kickstart/AutoYaST profiles which allows you to specify how your systems should be deployed, what software they will have installed, how the storage space will be distributed and more.


    All these simple to setup automation mechanisms can be combined with complex but more powerful automation solutions like Salt or Ansible, maintaining your freedom to choose the best solution for each challenge.



- **Patches menu** <img  style='vertical-align: middle; height: 40%; width: 40%; object-fit: contain' src="../assets/SMLM5.1/left_column_-_patches.png"/>

  - **Patching**

    One of the most common tasks in IT is to keep systems up-to-date and from time to time apply security patches in a rush!
    Wish SMLM we can easily see a list of **relevant** pacthes, classified by type, and provided with all the information you may need to know including all the systems and packages they affect.

    Beyond the vendor-supplied patches we can also create our own patches. Later on we will explore the different options we have to manage patching and regular updates accross all our systems or a subset of them.


- **Software channels** <img  style='vertical-align: middle; height: 40%; width: 40%; object-fit: contain' src="../assets/SMLM5.1/left_column_-_software.png"/>

  On `Channel List` we can see all the package channels/repositories/streams available for consumption, you can also create new software channels to organize your software or upload your own packages.

  All the channels you currently see have been retrieved by SMLM from the official sources and they can be kept in sync easily.

  In `Package Search` we are able to search for specific packages and inspect their content and metadata.


- **Configuration** <img  style='vertical-align: middle; height: 40%; width: 40%; object-fit: contain' src="../assets/SMLM5.1/left_column_-_configuration.png"/>

  It is also possible to manage and apply specific configurations to systems, upon registration or afterwards, for that we can inspect `Configuration` section.

  SMLM provides an easy way to easily manage revisions, deploy and compare configuration files across systems. And all can be easily grouped into configuration channels.

- **Scheduling** <img  style='vertical-align: middle; height: 40%; width: 40%; object-fit: contain' src="../assets/SMLM5.1/left_column_-_schedule.png"/>

  In `Schedule` we can observe and manage scheduled actions, define specific maintenance windows. This is specially useful to automate regular operations or perform canary deployments when managing many systems. We will see this in action later on during the workshop.



SUSE Multi-Linux Manager offers many posibilities to manage your systems, we cannot cover all of them in this workshop but always feel free to ask questions and explore, your user has full admin privileges so we recommend to make changes only after having finished the exercises.

