---
slug: smlm-managing-linux-distros
id: xwbbkru4elci
type: challenge
title: Managing different Linux distributions
tabs:
- id: nejibmsfonuc
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: uc3opgllyk50
  title: Ubuntu 2404 LTS
  type: terminal
  hostname: ubuntu2404lts
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Managing different Linux distributions
===================================

<style type="text/css">
  * {
    font-family: suse;
    src: url('https://fonts.google.com/specimen/SUSE');
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
  .smls {
    color: #2453ff;
  }
  .smlsext {
    color: #2453ff;
  }
  .companyname {
    color: #008657;
  }
  .liberty {
    color: #efefef;
  }
  .sles {
    color: #90ebcd;
  }

  .bottoms {
    vertical-align: middle;
    height: 50%;
    width: 50%;
    margin: 0px;
    padding: 0px;
    object-fit: contain;
  }

  img.animatedgif {
    --borderthickness: 5pt;
    --colors: #0000 25%,#30ba78 0;
    padding: 10px;
    background:
      conic-gradient(from 90deg  at top    var(--borderthickness) left  var(--borderthickness),var(--colors)) 0    0,
      conic-gradient(from 180deg at top    var(--borderthickness) right var(--borderthickness),var(--colors)) 100% 0,
      conic-gradient(from 0deg   at bottom var(--borderthickness) left  var(--borderthickness),var(--colors)) 0    100%,
      conic-gradient(from -90deg at bottom var(--borderthickness) right var(--borderthickness),var(--colors)) 100% 100%;
    background-size: 50px 50px;
    background-repeat: no-repeat;
    transition: 1s;
  }

  img.animatedgif:hover {
    background-size: 51% 51%;
  }

  img.logos {
    border-radius: 10px;
  }

</style>

<img class="logos" alt="Welcome!" src="../assets/logos/02-managing_linux_distros.jpeg"/>

Here at [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]], <b class="smlmext">SUSE Multi-Linux Manager</b>  is the key to managing our diverse fleet of Linux distributions and architectures from a single pane of glass. This has helped us avoid the extra customizations that used to complicate our jobs as engineers, which in turn increased the cost and time required to maintain and implement our system policies.

With this tool, we are not locked into a single vendor, architecture, or automation platform. We are free to choose what we need for our environment and manage them all in the same way. Imagine if for every type of aircraft in our fleet, we needed a different air traffic control tower with its own language and procedures. The operational complexity would be unmanageable, and the costs would be prohibitive.

We all know a certain aircraft model is better for a specific route; flying a jumbo jet for a half-hour flight is not cost-effective. The same applies to our Linux distributions. While SUSE’s own distributions are excellent, some of our applications have specific requirements. <b class="smlm">SMLM</b> ensures we are never locked in and can always integrate the best solution for the task at hand.


## <b class="hovereffect">Your Objectives:</b>

- Onboard an Ubuntu 24.04 LTS system, a specialized system required for our marketing team.

- Demonstrate how we manage this new, different system using the same tools and patching procedures as the rest of our fleet.



Lab details
===========

Username:
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```

Password:
```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

<b class="smlm">SMLM</b> URL: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>


Onboarding Ubuntu
=================

A new service request has come in from our marketing department. Their graphic designers rely on a specific creative suite that is only supported on Ubuntu. We are going to onboard their system so that we can manage and ensure it meets our security and compliance standards, in the same way as we do with the others.

Let's begin.
<br/>

- Access the system terminal from the tab [button label="Ubuntu 2404 LTS" variant="success"](tab-1)

  Before we make any changes let's check where it is sourcing the packages from:

```bash,run
grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```

This workstation is pulling software directly from public Ubuntu repositories. This presents two issues: first, we have no control over the patches being applied, which is a security concern. Second, as the marketing team reported, every time these workstations fetch updates, they can slow down the office internet connection, causing frustration for other employees.


Let's bring this system under our management. This will solve both problems by connecting it to our internal <b class="smlmext">SUSE Multi-Linux Manager</b> instance for all software needs.

We are going to use the [button label="web UI" variant="success"](tab-0) to do so:

- Under `Home` ✈ `Overview`, let's click on `Register Systems`

- Fill in the following details:

  - **Host:**

  ```txt
  ubuntu2404lts
  ```

  - **User:**

  ```txt
  root
  ```

  - **Password:**

  ```txt
  [[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
  ```

  - **Activation Key:**

  ```txt
  1-ubuntu2404
  ```

- Leave the rest as it is and click on

<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-bootstrap.png"/>


- The registration process may take a couple of minutes to complete, let's go to the [button label="terminal" variant="success"](tab-1) and run the first command one more time to see what has changed:


```bash,run
echo 'Waiting for the registration to complete' ;while [[ ! -f /etc/apt/sources.list.d/susemanager_bootstrap.sources ]] || [[ ! -f /etc/apt/sources.list.d/susemanager:channels.sources ]]; do echo -n '.'; sleep 5; done ; grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```


We can see new files appeared:

**/etc/apt/sources.list.d/susemanager:***

They point to the system to our centrally managed and controlled channels in <b class="smlm">SMLM</b>.


We can also see the original file, **/etc/apt/sources.list.d/ubuntu.sources**, has been modified to disable all the public respositories but has not been eliminated, this would allow us to roll back easily if we needed so.


> [!NOTE]
> Using root via SSH with password authentication for registering is just for demonstration purposes and not recommended for production.


> [!NOTE]
> By default we have to approve the registration of each system through the UI or via command line < salt-key -A -y >, here <b class="smlm">SMLM</b> has been configured to auto approve.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-register_ubuntu.gif"/>
  </div>

<br/>



Now let's switch to the [button label="SMLM UI" variant="success"](tab-0) tab


- We navigate to `Systems` ✈ `System List` ✈ `All`

  We can see the system we just registered `Ubuntu2404lts`, note by default it will be registered under the hostname.

  Let's click on it, we will go directly to `Details` - `Overview` where we can see amongst other information:

  - The system status.
  - All the information such as hostname, IP address, type of virtualization, Kernel used and installed products.
  - The channels it is subscribed to.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_overview.gif"/>
  </div>


<br/>

Managing multiple Linux distributions
=====================================


As mentioned earlier, at <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b> we use different Linux distributions, like we use different airplane models and companies. This helps us to stay ahead of the competition by using the most suitable product for each of our needs.

With <b class="smlmext">SUSE Multi-Linux Manager</b> we can manage all of them with the same procedures, same schedules, etc.. using the same interface and mechanisms.

Below we will explore how to perform different tasks on your systems, following the same process independently of which OS our systems are running, without having to create unecessary customizations.


## <b class="hovereffect">Add extra information</b>


Let's continue with the system we just registered, we are going to add a few settings and information to it:

- Let's click in `Properties`, where we will add extra information about the system and change some settings.


  - Enable Automatic application of patches:

  <img style='vertical-align: middle; height: 60%; width: 60%; object-fit: contain' src="../assets/SMLM5.1/option-auto_patch_update-enabled.png"/>

    This will automatically patch the system when there are relevant patches.



  - Add the following details for the system:


| Field | Content                                                  |
| ---: | :-----                                                    |
| **Description** | Multimedia workstation for graphics designers. |
| **Facility Address** | Candy eye street, 1 |
| **City** | Aeolia |
| **Building** | Belem Tower 4 |
| **Room** | Sierra nevada |


<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-Update_Properties.png"/>



- Let's look at what hardware it is running on:

  - Click on `Details` ✈ `Hardware`


<br/>

> [!NOTE]
> All this can be automated through the API.

<br/>

Now we are going to add some extra information to the system using custom keys, this information can be easily consumed in your automation scripts later on.


- Click on `Details` ✈ `Custom Info`

<img style='vertical-align: top; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Create_Value.png"/>

- Click `application` and fill **value** with the following:

```text
Logo Wings designer pro
```

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Update_Key.png"/>


<br/>

> [!NOTE]
> We have already create the custom key **application** for you, if you want to create you own keys it is as simple as going to: `Systems` ✈ `Custom System Info` ✈ `Create key`

<br/><br/>

Let's go back to the Systems list

`Systems` ✈ `System List` ✈ `All`


Let's click on any of the systems and go to `Details` ✈ `Custom Info`.

We have already populated each system with a value,

<br/>

Now go to `Details` ✈ `Overview` and notice **Installed Products** and **Subscribed Channels**, these are different than the ones in your Ubuntu system because they are running a different operating system.



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_properties.gif"/>
  </div>

<br/>


## <b class="hovereffect">Run commands on multiple systems at once</b>


Let's do something on all the systems we have, go back to `Systems` ✈ `System List` ✈ `All` and select all:

<img style='vertical-align: middle; margin: 2px; height: 50%; width: 50%; object-fit: contain' src="../assets/SMLM5.1/select_all_systems.png"/>

Notice the **Base Channel** column, we have systems running three different OS.

<br/>

Having selected all the systems we want to operate let's go to perform a group action:

`Systems` ✈ `System Set Manager`

Let's run a command on all of them, for that we can go to:

`Misc` ✈ `Remote Command`

then fill in the following details and leave the rest with the default values:


Script:

```bash,run
cat /etc/os-release
```

Don't modify the schedule, we want it to run as soon as possible, click on:

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Schedule.png"/>


<br/>


<br/><br/>

You will see a blue notice on the top indicating that the task has been scheduled.

Let's go to see the results, for that we will go to:

`Schedule` ✈ `Completed Actions`

We will see a list of actions, in **Filter by Action** field type:

```text
Run
```
Click on the top entry that appears on the list, should be similar to this:

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/Select_complete_action_run.png"/>


There we can go to **Completed Systems** and examine the result by clicking on the system name.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-multiple_systems_at_once.gif"/>
  </div>

<br/>


<br/><br/>

With this we complete this part, we will see more examples of how we can manage multiple Linux systems along the workshop.



Why is it important for [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- No vendor lock-in, keep the freedom of choice and flexibility to react fast to changing markets.

- Simplify and save time avoiding extra work on customizations.

- A single UI to manage all reduces the complexity and will make future troubleshooting, scaling, patching and automation much more agile and less time consuming.



More information
================

For a list of supported distributions please visit:

[SMLM - Supported Clients and Features](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/client-configuration/supported-features.html)



