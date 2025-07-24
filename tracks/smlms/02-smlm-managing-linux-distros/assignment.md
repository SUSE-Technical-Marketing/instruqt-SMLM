---
slug: smlm-managing-linux-distros
id: xwbbkru4elci
type: challenge
title: RC - Managing different Linux distributions
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

![Welcome](../assets/logos/02-managing_linux_distros.jpeg)

Here at [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]], <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">SUSE Multi-Linux Manager</b> allows us to manage our different Linux distributions and architectures from a single pane of glass. This has helped us avoid the extra customizations that used to complicate our jobs as engineers, which in turn increased the cost and time required to maintain and implement our system policies.

With this tool, we are not locked into a single vendor, architecture, or automation platform. We are free to choose what we need for our environment and manage it all in the same way. Imagine if for every type of aircraft in our fleet, we needed a different air traffic control tower with its own language and procedures. It wouldn't make sense, and the costs would be prohibitive.

We all know a certain aircraft model is better for a specific route; flying a jumbo jet for a half-hour flight is not cost-effective. The same applies to our Linux distributions. While SUSE’s own distributions are excellent, some of our applications have specific requirements, and this tool ensures we are never locked in.


### Your Objectives:

- Onboard an Ubuntu 24.04 LTS system.

- Examine how to manage multiple Linux distributions



Lab details
===========

Username:
```txt
[[ Instruqt-Var key="SMLM_ADMIN_USERNAME" hostname="zbastion" ]]
```

Password:
```txt
[[ Instruqt-Var key="SMLM_ADMIN_PASSWORD" hostname="zbastion" ]]
```

SMLM URL:
```txt
[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]
```


Onboarding Ubuntu
=================

Our graphic designers at the marketing office require a software that is only supported in Ubuntu, we are going to onboard their system so that we can manage and protect the same way as we do with the others.

- Access the system terminal from the tab [button label="Ubuntu 2404 LTS" variant="success"](tab-1)

  Check where it is sourcing the packages:

```bash,run
grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```

It's connecting to the public repositories of Ubuntu, of which you have no control, and is retrieving all the updates from the internet, everytime there is an update on those systems the internet slows down in the office, causing frustration amongst the employees.


- Lets register the system within SMLM so that it doesn't disrupt the internet in the office and we can control on the software that goes in.

```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | HOSTNAME="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-ubuntu2404 bash
```


- Lets check again again where it is sourcing the packages from:

```bash,run
grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```


We can see a new file called:
**/etc/apt/sources.list.d/susemanager:channels.sources**
appeared with repositories pointing at SMLM.

We can also see the existing file **/etc/apt/sources.list.d/ubuntu.sources** has been modified to disable all the respositories listed there but has not been eliminated, this would allow us to roll back easily if we needed to.




> [!NOTE]
> By default we have to approve the registration of each system through the UI or via command line < salt-key -A -y >, here SMLM has been configured to auto approve.




Now lets switch to the [button label="SMLM UI" variant="success"](tab-0) tab


- We navigate to `Systems` ✈ `System List` ✈ `All`

  We can see the system we just registered `Ubuntu2404lts`, note by default it will be registered under the hostname.

  Let's click on it, we will go directly to `Details` - `Overview` where we can see amongst other information:

  - The system status is up to date
  - All the information such as hostname, IP address, type of virtualization, Kernel used and installed products.
  - The channels it is subscribed to.





Managing multiple Linux distributions
=====================================


As mentioned earlier, at <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b> we use different Linux distributions, like we use different airplane models and companies. This helps us to stay ahead of the competition by using the most suitable product for each of our needs.

With SUSE Multi-Linux Manager we can manage all of them with the same procedures, same schedules, etc.. using the same interface and mechanisms.

Below we will explore how to perform different tasks on your systems, following the same process independently of which OS our systems are running, without having to create unecessary customizations.


Let's continue with the system we just registered, we are going to add a few settings and information to it:

- Let's click in `Properties`, where we will add extra information about the system and change some settings.


  - Enable Automatic application of patches:

  <img  style='vertical-align: middle; height: 60%; width: 60%; object-fit: contain' src="../assets/SMLM5.1/option-auto_patch_update-enabled.png"/>

    This will automatically patch the system when there are relevant patches.



  - Add the following details for the system:


| Field | Content                                                  |
| ---: | :-----                                                    |
| **Description** | Multimedia workstation for graphics designers. |
| **Facility Address** | Candy eye street, 1 |
| **City** | Aeolia |
| **Building** | Belem Tower 4 |
| **Room** | Sierra nevada |


then click <img  style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/buttom-Update_Properties.png"/>



- Let's look at what hardware it is running on:

  - Click on `Details` ✈ `Hardware`


<br/>

> [!NOTE]
> All this can be automated through the API.



<br/>

Now we are going to add some extra information to the system using custom keys, this information can be easily consumed in your automation scripts later on.


- Click on `Details` ✈ `Custom Info`

- Click on <img  style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/buttom-Create_Value.png"/>

- Click `application` and fill **value** with the following:

```text
Logo Wings designer pro
```

- Click on <img  style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/buttom-Update_Key.png"/>


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

<br/>

Lets do something on all the systems we have, go back to `Systems` ✈ `System List` ✈ `All` and select all:

<img  style='vertical-align: middle; margin: 2px; height: 50%; width: 50%; object-fit: contain' src="../assets/SMLM5.1/select_all_systems.png"/>

Notice the **Base Channel** column, we have systems running three different OS.

<br/>

Having selected all the systems we want to operate lets go to perform a group action:

`Systems` ✈ `System Set Manager`

Let's run a command on all of them, for that we can go to:

`Misc` ✈ `Remote Command`

then fill in the following details and leave the rest with the default values:


Script:

```bash,run
cat /etc/os-release
```

Don't modify the schedule, we want it to run as soon as possible, click on:

<img  style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/buttom-Schedule.png"/>


<br/>

> [!NOTE]
> SMLM doesn't connect to the systems directly, instead systems connect to it periodically to retrieve the orders, this mechanism reduces the attack surface on those systems and avoids having to open firewalls and the like.


<br/><br/>

You will see a blue notice on the top indicating that the task has been scheduled.

Let's go to see the results, for that we will go to:

`Schedule` ✈ `Completed Actions`

We will see a list of actions, in **Filter by Action** field type:

```text
Run
```
Click on the top entry that appears on the list, should be similar to this:

<img  style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/Select_complete_action_run.png"/>


There we can go to **Completed Systems** and examine the result by clicking on the system name.


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

https://documentation.suse.com/suma/5.0/en/suse-manager/client-configuration/supported-features.html



