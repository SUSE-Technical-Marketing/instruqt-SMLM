---
slug: smlm-simplify-upgrade-sles
id: bcty19jh0cic
type: challenge
title: RC - Simple and reliable maintenance
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

![Welcome](../assets/logos/04-upgrade.jpeg)

So far, we’ve focused on managing the diversity of our mixed fleet and even extending the life of our legacy systems. Now, we turn our attention to the core of our airline: our flagship SUSE Linux Enterprise Server (SLES) systems.


Think of these as our state-of-the-art, long-haul jets. Their reliability is paramount, and keeping them in peak condition involves regular, planned service patching and upgrades. This next exercise is exactly that: we're going to walk through the process of a version upgrade, a common task in managing the lifecycle of any critical system.

And while we're using SLES as the example, remember the key principle of our universal control tower: the process you're about to perform is the same one you would use for any other Linux distribution. The interface and the methodology do not change.


### Your Objectives:

- Onboard a new SLES 15 SP5 system to test the upgrade.
- Upgrade it from SP5 to SP6



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




Onboarding SLES 15 SP5
======================

Access the system terminal from the tab [button label="SLES 15" variant="success"](tab-1)


Lets register the system within SMLM as **sles15**

```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | HOSTNAME="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-sles15sp5 bash
```

Now lets switch to the [button label="SMLM UI" variant="success"](tab-0) tab


Upgrade from SP5 to SP6
=======================

We should see it soon on the list of systems, lets go to `Systems` ✈ `System List` ✈ `All`


Lets click on it and go to `Software` ✈ `Packages` ✈ `Upgrade`.


To ensure a smooth migration is best to apply the latests updates.

Click on ![Select All](../assets/SMLM5.1/buttom-select_all.png) ✈ ![Upgrade Packages](../assets/SMLM5.1/buttom-upgrade_packages.png) ✈ ![Confirm](../assets/SMLM5.1/buttom-confirm.png)

This may take some time, once finish please go to `Software` ✈ `Product Migration`

You will see below a section called **Target Products**, make sure **SUSE L	inux Enterprise Server 15 SP6 x86_64** is selected, then press  ![Select Channels](../assets/SMLM5.1/buttom-select_channels.png)

You will be shown a screen with the summary and also aditional options, just leave it as is and click on  ![Schedule Migration](../assets/SMLM5.1/buttom-schedule_migration.png)

Finally it wil ask you to do a dry run first, ignore and press ![Confirm](../assets/SMLM5.1/buttom-confirm.png)

This may take a while, to see the status please go to `Events` ✈ `History` and watch for **Product Migration** Once it's set to green we can see in `Software` ✈ `Software Channels` the channels it is subscribed are the new ones we choose.

<br/>

Afterwards we will go to `Systems` ✈ `System List` ✈ `All`

Notice the system `sles15` we just migrated has the following icon:

![Needs reboot icon](../assets/SMLM5.1/icon_needs_reboot.png)

This indicates the system needs to be rebooted, usually because of some mayor kernel update.

Let's click on it, we will see something similar to this:

![Needs reboot message](../assets/SMLM5.1/system_requires_a_reboot.png)

Click on `Schedule System Reboot` and in the following screen click on ![Reboot System](../assets/SMLM5.1/buttom-reboot_system.png)

<br/>

We have scheduled actions to happen immediatly but this doesn't have to be the case, we can plan actions to be applied on specific dates and times and that apply to groups of systems. SMLM support the use and creation of Maintenance Windows ( `Schedule` ✈ `Maintenance Windows` ) so you can make sure specific events can only happen during that periods.

Scheduling is specially useful to make changes on production systems, allowing also to do even canary deployments.

<br/>

> [!NOTE]
> It is possible to do kernel live patching with KLP, it makes it possible to apply the latest security updates to Linux kernels without rebooting.



Why is it important for [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- System upgrades and other routine tasks have to be simple to perform otherwise we risk making mistakes.


- We can control when and where we perform actions, and schedule maintenance operations on our grounded fleet.


More information
================

- [Live kernel patching with KLP](https://documentation.suse.com/en-us/sles/15-SP7/html/SLES-all/cha-klp.html)

- [Maintenance Windows](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

- [Administration Guide](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/admin-overview.html)
