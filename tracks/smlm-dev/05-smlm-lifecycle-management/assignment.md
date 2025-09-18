---
slug: smlm-lifecycle-management
id: 5mkftmzuno7p
type: challenge
title: Lifecycle management
tabs:
- id: wdxp5fjicmfm
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Lifecycle management
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

<img class="logos" alt="Welcome!" src="../assets/logos/05-lifecycle.jpeg"/>

In this part we will transition from individual maintenance tasks to establishing a fleet-wide, certified process for managing change. We'll explore how Content Lifecycle Management in <b class="smlmext">SUSE Multi-Linux Manager</b> provides the structure and safety our airline demands.



At [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]], a new part isn't installed on a passenger jet the moment it arrives from the manufacturer. It goes through a rigorous certification process.

First, it's examined and tested in a controlled workshop (**Development**). Next, it's fitted to a non-commercial test aircraft and put through grueling ground and flight tests (**Quality Assurance**). Only after passing every conceivable check is it certified for installation across our active fleet (**Production**).

This methodical, staged approach prevents a single faulty component from grounding a plane, ensuring the safety of our passengers and the reliability of our operations. We apply this exact same philosophy to our IT systems. A software upgrade or a new application is a "component" that, if faulty, could ground our digital operations. Content Lifecycle Management is our official certification process for all software changes.



## <b class="hovereffect">Your Objectives:</b>

- Build a Content Lifecycle Project

- Use the project to manage and certify software updates for our systems.



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


Building Our Software Certification Pathway
==============================================

In this exercise, we will create a Content Lifecycle Project to control the flow of software updates. This ensures that a patch is thoroughly tested before it ever reaches our critical production servers.

<br/>

Our goal is to build a `Dev ✈ QA ✈ Prod` pipeline.

1.  **Development (Dev):** The initial workshop. All new patches and packages arrive here first.
2.  **Quality Assurance (QA):** The testing ground. We will promote a specific, version of the content from Dev to QA for our testing teams to validate.
3.  **Production (Prod):** The active fleet. Only the QA-approved, certified set of patches is promoted to Production, where it can be safely applied to our live systems.

<br/>

## <b class="hovereffect">Create the project</b>

- Navigate to `Content Lifecycle` ✈ `Projects` and click ![Create Project](../assets/SMLM5.1/bottom-create_project.png)

- Fill in the project details:
    * **Project Name:**        "Airtrain SLES15 SPx"

    * **Project Label:**       "at-sles15_spx"

    * **Project Description:** "Certified software channel for Airtrain SLES 15 systems."

- Click ![Create](../assets/SMLM5.1/bottom-create.png)

Now let's populate it, click on `Attach/Detach Sources`

![Create](../assets/SMLM5.1/content_lifecycle_just_created.png)

- On **New Base Channel** select <b class="sles">SLE-Product-SLES15-SP6-Pool for x86_64</b> and click on ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">Create Dev environment</b>

Create the Development Environment Lifecycle

- Click on `Add Environment`

![Create](../assets/SMLM5.1/content_lifecycle_just_created_environment_lifecycle.png)

- Populate with the following:
  * **Name:** 'Development'
  * **label:** 'dev'

- Click on ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">Create QA environment</b>

Create the Quality Assurance Environment Lifecycle

- Click on `Add Environment`

- Populate with the following:
  * **Name:** 'QA'
  * **label:** 'qa'

- Click on ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">Create Prod environment</b>

Create the Production Environment Lifecycle

- Click on `Add Environment`

- Populate with the following:
  * **Name:** 'Production'
  * **label:** 'prod'

- Click on ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">Populate</b>

Now we have all three environments, let's populate them with content.

We will not use a filter in this case since <b class="sles">SLES</b> already provides stable package versions.

[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]' cadence for testing is currently one month, so we will name this build after the current month, October.

- Click on ![Build](../assets/SMLM5.1/bottom-build.png)

- Fill in **Version Message** with 'October'
- Click on `Build`

> [!NOTE]
> This process may take a couple of minutes, you will see some steps like 'cloning', but you might be relieved to know that this doesn't require a lot of storage. The cloning process applies only to the package index points, not the actual packages themselves


<br/>

## <b class="hovereffect">Promoting content</b>

Now, let's promote the content to further stages.

- Click on the `Promote` button between Development and QA
- Another screen with the title **Promote version 1 into QA** will appear, just click `Promote` again.

Repeat the same step for Production.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-create_the_project.gif"/>
  </div>

<br/>

Upgrade our systems.
====================

Now let's try how it works.

We are going to:
- add some of our system to the new environment.
- Create a new version of the content
- Promote the new version and update the systems

<br/>

## <b class="hovereffect">Add systems</b>

Let's go to `Systems` ✈ `System List` ✈ `All`

- Click on **at-ct-qa** system
- Go to `Software` ✈ `Software Channels`
- On **Custom Channels**, select the checkbox for the **at-sles15_spx-qa-...** channel and click ![Next](../assets/SMLM5.1/bottom-next.png)
- Click ![Confirm](../assets/SMLM5.1/bottom-confirm.png)


Go back to `Systems` ✈ `System List` ✈ `All`

- Filter by **at-**
- Select all the systems that end with **-pro**
- Go to `Systems` ✈ `System Set Manager`
- Go to `Channels`
- On **Custom Channels**, select the checkbox for the **at-sles15_spx-prod-...** channel and click ![Next](../assets/SMLM5.1/bottom-next.png)
- Click on 'incclude recommended' to subscribe to all the recommended channels:

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-next.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-add_systems.gif"/>
  </div>

<br/>

## <b class="hovereffect">Create a new version</b>


A month has past and we want to continue with our stable process of upgrades.
You have are going to create a static, unchanging copy of the software channels for the Developer team.

No new patches will suddenly appear and disrupt their work.

- Go back to `Content Lifecycle` ✈ `Projects` and click on the project we just created.

- Click on ![Build](../assets/SMLM5.1/bottom-build.png)

- Fill in **Version Message** with 'November'
- Click on `Build`

Notice the version number has automatically increased.

Now developers can do their work using the new and patched versions of libraries and applications provided by SUSE.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-create_new_version.gif"/>
  </div>


<br/>

## <b class="hovereffect">Promote content from Dev to QA</b>

Let's assume our developers have given their approval. It's time to create a stable version for the QA team so that all the pre-production tests can be performed.

- Click on the `Promote` button between Development and QA
- Another screen with the title **Promote version 2 into QA** will appear, just click `Promote` again.

Now let's go to our QA systems and do an upgrade.

- `Systems` ✈ `System List` ✈ `All`
- Click on **at-ct-qa** system
- Go to `Software` ✈ `Packages` ✈ `Upgrade`
- Click on:

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


Now our QA engineers can perform their tests safely without disruption.


> [!NOTE]
> We don't have enough time to see changes comming through, in a real scenario there should be new versions of packages available to promote in version 2.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-promote_from_dev_to_QA.gif"/>
  </div>


<br/>

## <b class="hovereffect">Promote to Production</b>

The QA team has completed its rigorous testing on `v2` and has certified it as stable and safe for the main fleet. It's time to make it available to our production systems.

We are going to repeat the same process as we did for QA on our production environment:

- First, promote the content.
  This will make the new packages available to our production servers.
  You have successfully ensured that only tested and approved updates can reach your most critical systems.

- Second, upgrade our Production systems, here the only difference is that we are going to schedule the upgrade for **tomorrow at 14:00** to allow for all our teams to be prepared and have a controlled process.


<br/>

Why is it important for [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- We build a series of safety gates, making it easier to implement a core principle of our operational strategy: **risk management**.
- A single bad patch introduced into the **Dev** environment can be caught and fixed long before it has a chance to impact revenue-generating systems.
- This process transforms patching and updates from a risky, nerve-wracking event into a predictable, routine maintenance procedure, the cornerstone of a reliable airline.


<br/>

More information
================

* [Maintenance Windows](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

* [Patch Management](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)

* [Content Lifecycle Management](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/content-lifecycle.html)

* [SUSE Multi-Linux Manager Product Page](https://www.suse.com/products/suse-manager/)


