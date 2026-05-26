---
slug: smlms-intro
id: czegcbnwbsst
type: challenge
title: Welcome to SUSE Multi-Linux Hands-on Workshop!
teaser: Welcome to SUSE Multi-Linux Hands-on Workshop! in this section we will introduce
  you to the workshop and to its main components.
notes:
- type: text
  contents: |
    # Welcome to the SUSE Multi-Linux Hands-on Workshop!
    Please wait while we setup your lab environment.
    <img class="logos" src="../assets/logos/suse_logo.svg"/>
tabs:
- id: anmg573mysnu
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: ""
enhanced_loading: null
---

Welcome to <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">SUSE</b> Multi-Linux Hands-on Workshop
==================================================================

<link  rel="stylesheet" href="https://raw.githubusercontent.com/SUSE-Technical-Marketing/lab-setup/refs/heads/develop/web/css/instruqt.css" type="text/css" crossorigin="anonymous" fetchpriority="high" />

<style type="text/css">

  @import url("https://raw.githubusercontent.com/SUSE-Technical-Marketing/lab-setup/refs/heads/develop/web/css/instruqt.css");
  @import "https://raw.githubusercontent.com/SUSE-Technical-Marketing/lab-setup/refs/heads/develop/web/css/instruqt.css";

  * {
    font-family: suse;
    src: url('https://fonts.google.com/specimen/SUSE');
/*    background-color: #30ba78; */
  }
  .hovereffect {
    border-radius: 25px 25px 25px 25px;
    background: linear-gradient(#30ba78 0 0) var(--hundredpercent, 0) / var(--hundredpercent, 0) no-repeat;
    transition: 0.5s, background-position 0s;
    padding: 5px;
  }
  .hovereffect:hover {
    --hundredpercent: 100%;
    color: white;
    border-radius: 10px 25px 10px 25px;
  }
  .smlmext {
    color: #fe7c3f;
  }
  .smlm {
    color: #fe7c3f;
  }
  .suse {
    color: #30ba78;
  }
  .highlightcopy {
    color: white;
    font-weight: bold;
    padding: 0 10px;
  }


</style>



<img class="logos" alt="Welcome!" src="../assets/logos/01-welcome.jpeg"/>

In this workshop you will explore some of the magic that <b class="smlmext">SUSE Multi-Linux Manager</b> (<b class="smlm">SMLM</b>) can do, it is <b class="suse">SUSE</b>'s solution to manage multiple Linux distributions at scale from a unified interface. And also will discover how can you keep your legacy production servers supported with <b class="smlsext">SUSE Multi-Linux Support</b> (<b class="smls">SMLS</b>), our professional and reliable support solution for Linux systems.

&emsp;&emsp; You will adopt the role of an **engineer** at <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b>, an airline where every plane has a Linux server onboard.

&emsp;&emsp; As with any airplane component, it is critical that those servers remain stable and reliable, no matter if they are located on the ground in some datacenter or flying above the clouds ☁ ☁ ☁

&emsp;&emsp; Some plane models will require a different Linux flavor, or a different CPU architecture. This is not an issue for <b class="smlm">SMLM</b>, you are free to choose the Linux distribution and CPU architecture that better suits your needs without having to give up on easy standardization and management.

&emsp;&emsp; As an engineer responsible for managing the Linux landscape you will go through some of the solutions <b class="smlm">SMLM</b> and <b class="smls">SMLS</b> offers you to ease and automate systems management and resolve exceptional problems that may occur.


Along the different challenges you will have the following tools available:

 ✈ **SUSE Multi-Linux Manager**:
   The single pane of glass for managing your entire Linux stack.

 ✈ **Centos 7**:
   A legacy distribution still in use on some older aircrafts and ground systems.

 ✈ **Ubuntu 24**: A specific Linux distribution required by our marketing department to run their graphic design applications.

 ✈ **SLES 15**: <b class="suse">SUSE</b>'s highly reliable, stable and secure Linux distribution that forms the backbone of our most critical systems.




## <b class="smlmext hovereffect">SUSE Multi-Linux Manager</b>

It is a best-in-class open source infrastructure management solution for your software-defined infrastructure.

&emsp;&emsp; <b class="smlmext">SUSE Multi-Linux Manager</b> was designed to help your enterprise DevOps and IT Operations teams reduce complexity and regain control of your IT assets, a single but very powerful tool to manage Linux systems across a variety of hardware architectures, hypervisors as well as container, IoT and cloud platforms.

&emsp;&emsp; It automates Linux server and IoT device provisioning, patching and configuration for faster, consistent and repeatable server deployment helping to optimize operations and reduce costs. And with automated monitoring, tracking, auditing and reporting of your systems, VMs, and containers across your development, test and production environments, you can ensure compliance with internal security policies and external regulations.


## <b class="smlsext hovereffect">SUSE Multi-Linux Support</b>


It is a comprehensive service offering technical assistance and maintenance for various Linux distributions, including your existing Red Hat Enterprise Linux (RHEL), CentOS, <b class="liberty">SUSE Liberty Linux</b>, and <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>), depending on the offering.

&emsp;&emsp; It enables organizations to manage mixed Linux environments efficiently under a single support framework.
Depending on the package purchased, <b class="smlsext">SUSE Multi-Linux Support</b> may also include <b class="smlmext">SUSE Multi-Linux Manager</b>, a multi-Linux management tool to manage these distributions.



 🌅 Explore the Instruqt UI
=======================
Before we begin our first task, let's take a moment to look at Instruqt UI.

+ The **left side** of the screen provides you with these instructions and navigation controls.

+ The **right side** give you access to the various machines and services that make up our lab environment.

Within the Instruqt UI you can jump between the [button label="SMLM UI" variant="success"](tab-0) and the available [button label="terminals" variant="success"](tab-1) by clicking on tabs at the top of the left-side panel.


> [!NOTE]
> No automatic reloading happens on the web UI, in some cases you may have to reload Instruqt's internal web browser to see updates.


🛫 Logging into <b class="smlmext">SUSE Multi-Linux Manager</b> 🛫
========================================

Let's get you familiarized with the environment.

- Open <b class="smlmext">SUSE Multi-Linux Manager</b> inside the lab from the [button label="SMLM UI" variant="success"](tab-0)


- Log in with the following credentials:

  - Username:
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```
  - Password:

```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

If everything went well, you should see the **Overview** page in the <b class="smlmext">SUSE Multi-Linux Manager</b> UI logged in as `[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]` user.

> [!NOTE]
> If you wish to access <b class="smlmext">SUSE Multi-Linux Manager</b> UI directly through your browser you can do too:

<b class="smlm">SMLM</b> URL: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>


> [!NOTE]
> If the page doesn't load correctly, you may need to refresh the browser tab after the lab environment has finished starting up.


🗺 Explore <b class="smlmext">SUSE Multi-Linux Manager</b> 🗺
======================================

Before we take off, let's get familiar with the controls. This is not meant to be an exhaustive tour, but a brief overview of the key instruments we will use throughout the workshop. We encourage you to be curious and explore.


Let's begin.


- **Systems menu** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_systems.png"/>

  On the left-hand panel, click on `systems`. This is our fleet overview, showing every registered server. The list is small now, but it will grow as we complete our exercises.

   - **System Lists**

     This section provides convenient, pre-filtered views. For example, the `Out of Date`list instantly shows you which servers require updates, saving you from performing a manual search. </p>

  <br/>

  - **System Groups**

    To organize our fleet logically, we use `System Groups`, you can categorize them based on any criteria, by doing so you can save time when applying actions or defining policies. Once created you can automatically attach systems to one or multiple groups, e.g. using `activation keys`.


    Feel free to try creating one now by clicking `+ Create Group`.

  <br/>

  - **Batch operations**

    `System Set Manager` provides a powerful way to perform actions on multiple systems simultaneously.


    Instead of applying changes one by one, you can select a collection of systems, either individually from the System List or by leveraging existing System Groups, and then execute tasks across all of them in a single operation.

  <br/>

  - **Provisioning**

    <b class="smlmext">SUSE Multi-Linux Manager</b> provides comprehensive tools for provisioning new systems and reprovisioning existing ones. This capability helps you establish a standardized and repeatable process for systems deployment.


    For example, within `Autoinstallation` section you can define distributions and Kickstart/AutoYaST profiles which allows you to specify how your systems should be deployed, what software they will have installed, how the storage space will be distributed and more.


    All these simple to setup automation mechanisms can be combined with complex but more powerful automation solutions like Salt or Ansible, maintaining your freedom to choose the best solution for each challenge.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_systems.gif"/>
  </div>

<br/>



- **Patches menu** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_patches.png"/>

  - **Patching**

    One of the most common tasks in IT is to keep systems up-to-date and from time to time apply security patches in a rush!
    With SMLM we can easily see a list of **relevant** pacthes, classified by type, and provided with all the information you may need to know including all the systems and packages they affect.

    Beyond the vendor-supplied patches we can also create our own patches. Later on we will explore the different options we have to manage patching and regular updates accross all our fleet.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_patches.gif"/>
  </div>

<br/>


- **Software channels** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_software.png"/>

  On `Channel List` we can see all the package channels/repositories/streams available for consumption, you can also create new software channels to organize your software or upload your own packages.

  All the channels you currently see have been retrieved by SMLM from the official sources and they can be kept in sync easily.

  In `Package Search` we are able to search for specific packages and inspect their content and metadata.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_software.gif"/>
  </div>

<br/>

- **Configuration** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_configuration.png"/>

  It is also possible to manage and apply specific configurations to systems, upon registration or afterwards, for that we can inspect `Configuration` section.

  SMLM provides an easy way to easily manage revisions, deploy and compare configuration files across systems. And all can be easily grouped into configuration channels.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_configuration.gif"/>
  </div>

<br/>

- **Scheduling** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_schedule.png"/>

  In `Schedule` we can observe and manage scheduled actions, define specific maintenance windows. This is specially useful to automate regular operations or perform canary deployments when managing many systems. We will see this in action later on during the workshop.

<br/>
<br/>

SUSE Multi-Linux Manager offers many posibilities to manage your systems, we cannot cover all of them in this workshop but, as always, feel free to ask questions and explore.

> [!NOTE]
> Your user has full admin privileges so we recommend to make changes only after having finished the exercises.




