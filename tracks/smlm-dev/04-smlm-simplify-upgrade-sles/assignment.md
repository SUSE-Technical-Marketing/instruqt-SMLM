---
slug: smlm-simplify-upgrade-sles
id: bcty19jh0cic
type: challenge
title: Simple and reliable maintenance
tabs:
- id: p3ne7mjqq9xf
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: jgoy19ouejw2
  title: SLES 15
  type: terminal
  hostname: sles15
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Simple and reliable maintenance
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

<img class="logos" alt="Welcome!" src="../assets/logos/04-upgrade.jpeg"/>

So far, we’ve focused on managing the diversity of our mixed fleet and even extending the life of our legacy systems. Now, we turn our attention to the core of our airline: our flagship <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>) systems.


Think of these as our state-of-the-art, long-haul jets. Their reliability is paramount, and keeping them in peak condition involves regular, planned service patching and upgrades. This next exercise is exactly that: we're going to walk through the process of a version upgrade, a common task in managing the lifecycle of any critical system.

And while we're using SLES as the example, remember the key principle of our universal control tower: the process you're about to perform is the same one you would use for any other Linux distribution. The interface and the methodology do not change.


## <b class="hovereffect">Your Objectives:</b>

- Onboard a new SLES 15 SP5 system to serve as our test aircraft.
- Perform a major service upgrade from SP5 to SP6.



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

<b class="smlm">SMLM</b> URL:
```txt
[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]
```




Onboarding and preparation
==========================

Access the system terminal from the tab [button label="SLES 15" variant="success"](tab-1)


Let's register the system within <b class="smlm">SMLM</b> as **sles15**

```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | HOSTNAME="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-sles15sp5 bash
```


Now, let's switch to the [button label="SMLM UI" variant="success"](tab-0) tab


Executing the upgrade
=====================

We should see it soon on the list of systems, let's go to `Systems` ✈ `System List` ✈ `All`, please click refresh on the internal browser if you don't see it.


Let's click on it and go to `Software` ✈ `Packages` ✈ `Upgrade`.


To ensure a smooth migration is best to apply the latests updates.



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">Click on </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


This may take some time to complete.

<br/>


## <b class="hovereffect">Product migration</b>


Once it finish, please go to `Software` ✈ `Product Migration`

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">You will see a section called **Target Products**. Ensure that <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #90ebcd">SUSE Linux Enterprise Server 15 SP6 x86_64</b> is selected, then press: </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; vertical-align: middle; display:block; align:left; padding: 0px;" src="../assets/SMLM5.1/bottom-select_channels.png"/></p>

You will be shown a confirmation screen with a summary and aditional options. Leave the defaults as they are and click: ![Schedule Migration](../assets/SMLM5.1/bottom-schedule_migration.png)

The system will ask you to do a dry run first, ignore it and press: ![Confirm](../assets/SMLM5.1/bottom-confirm.png)

This will take some time. To monitor the status, go to `Events` ✈ `History` and watch for the **Product Migration** event. Once its status icon turns green, the migration is completed. You can verify this by navigating to `Software` ✈ `Software Channels` and confirming the system is now subscribed to the new SP6 channels.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/04-simple_and_reliable_maintenance-executing_the_upgrade.gif"/>
  </div>

<br/>

## <b class="hovereffect">Post-Migration Reboot</b>

- Navigate back to `Systems` ✈ `System List` ✈ `All`

- Notice that the `sles15` system now has a reboot icon next to it:

![Needs reboot icon](../assets/SMLM5.1/icon_needs_reboot.png)

  This indicates a reboot is required, usually due to a mayor kernel update.

- Click on it, we will see something similar to this:

![Needs reboot message](../assets/SMLM5.1/system_requires_a_reboot.png)

- Click on `Schedule System Reboot` and in the following screen click on ![Reboot System](../assets/SMLM5.1/bottom-reboot_system.png)

> [!NOTE]
> The reboot won't happen immediatly.

<br/>


## <b class="hovereffect">The importance of Scheduling</b>

We have scheduled these actions to happen immediately, but this is not always desirable. <b class="smlm">SMLM</b> supports the creation of Maintenance Windows ( `Schedule` ✈ `Maintenance Windows` ) which allows you to ensure the major events like reboots onlye occur during those pre-approved periods .

Scheduling is especially useful for production systems, as it allows for carefully planned changes on groups of systems and even phased "canary" deployments.

<br/>

> [!NOTE]
> It is possible to do kernel live patching with KLP, it makes it possible to apply the latest security updates to Linux kernels without rebooting.



Why is it important for [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- System upgrades and other routine tasks must be simple and repeatable, otherwise, we risk making costly mistakes. With these tools, we can control precisely when and where we perform actions, scheduling critical maintenance for our fleet with confidence.


- We can control when and where we perform actions, and schedule maintenance operations on our grounded fleet.


More information
================

- [Live kernel patching with KLP](https://documentation.suse.com/en-us/sles/15-SP7/html/SLES-all/cha-klp.html)

- [Maintenance Windows](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

- [Administration Guide](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/admin-overview.html)
