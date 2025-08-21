---
slug: smlm-automation
id: ucmcl4dfi1gq
type: challenge
title: Automation (Optional)
tabs:
- id: jdlfyzxbrckx
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Automation and configuration management
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

<img class="logos" alt="Welcome!" src="../assets/logos/07-automation.jpeg"/>

In this section we are going to look at some of the options available to automate tasks.

In this lab, we move from doing manual tasks to create some automation using some of the options we have available.
<b class="smlmext">SUSE Multi-Linux Manager</b> acts as the "autopilot" for our IT operations, allowing us to enforce configuration standards and automate routine tasks with precision and reliability across our entire fleet.

Instead of manually configuring hundreds of servers and hoping we don't miss a step, we define the process and state and reduce the human operation to define a schedule, once.



## <b class="hovereffect">Your Objectives:</b>

- Create a schedule that regularly perform updates on your development systems

- Create a script to show a different login banner depending on the system's environment

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




Setup recurring updates
=======================

We want developers to work with the latest stable updates provided by SUSE, but we can't rely on people remembering to update their systems every day, so we are going to create a recurring schedule that does exactly that.


We are going to apply this to all the systems in the dev group so that this doesn't have to be done on every system.

- Let's go to `Systems` ✈ `System Groups`
- Click on `dev` group.

We just noticed it has no systems assigned, let's add one.

- click on `Target Systems` and select `sles15`
- then click on ![Add Systems](../assets/SMLM5.1/bottom-add_system.png)

Now that we have a system let's create the recurring action.

- Go to `Recurring Actions`
- Click on ![Create](../assets/SMLM5.1/bottom-create.png)
- Now let's populate the form with the following details:
	+ **Action Type:** 'Custom state'
 	+ **Schedule Name:** 'Update Dev systems'
	+ **Daily:** '03:00'
	+ **Configure states to execute:** Make sure **uptodate:** is selected
	![uptodate Selected](../assets/SMLM5.1/uptodate_selected.png)

- Click on

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-create_schedule.png"/>
</p>



To observe our list of recurring actions we can go to `Schedule` ✈ `Recurring Actions`

Now all the dev systems will be updated daily at 3am UTC time.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-setup_recurring_updates.gif"/>
  </div>

<br/>




Make sure every system has a login message
==========================================


We are going to create a configuration channel to make sure every system we manage contains an adequate login message.

- Let's go to `Configuration` ✈ `Channels`
- Click on ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png)
- Fill the form with the following details:
	+ **Name:**          Uniform experience
	+ **Label:**         uniform_experienace
	+ **Description:**   Create a uniform experience across systems
- Click on ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png)

Now that we have created the config channel let's populate it.

- Go to `Add Files` ✈ `Create File`
- Fill in the following details:
	+ **Filename/Path:** /etc/motd
	+ **File Contents:**
<pre>
This system is the property of [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]].

Server ID: {{ grains['id'] }}
{%- if 'custom_info' in pillar %}
{%- if 'application' in pillar['custom_info'] %}
Running Application "{{ pillar['custom_info']['application'] }}"
{%- else %}
No applications running on this server
{%- endif %}
{%- else %}
No applications running on this server
{%- endif %}
</pre>


- Click on ![Create Configuration File](../assets/SMLM5.1/bottom-create_configuration_file.png)

Now let's subscribe every system in the organization to the new configuration channel.

- let's go to `Admin` ✈ `Organizations`
- Click on organization **Organization** (This is the default organization)
- Go to `States` and select the channel we just created.
![Uniform experience selected](../assets/SMLM5.1/selected_univorm_experience_Configurationchannel.png)
- Click on


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-execute_states.png"/>
</p>


This won't happen immediately, let's check the systems. We are going to run a simple command via the web UI, if run too early, you may see systems with the old message and systems which already got the file updated.

- Let's go to `Salt` ✈ `Remote Commands`
- Type the following:
![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd.png)
- Click on `Find targets`
- You should see a list of systems click on `Run command`

Now you should see something like this:

![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd_first_result.png)

> [!NOTE]
> This process may take a couple of minutes, if you don't see the MOTD please re run the command after a few minutes.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-login_message.gif"/>
  </div>

<br/>


Why is it important for [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================



- When managing 1000s of systems we cannot afford to do everything one by one, tasks need to be automated so we manage cattle, not pets.

- By defining the "correct state" we eliminate configuration drift. Every server in the fleet operates from the same playbook, just like every pilot uses the same checklist.


- Tasks that would take hours to perform manually across hundreds of servers are completed in minutes. This frees up our engineers to work on innovation and improvement, not repetitive manual labor.


- Automation is the ultimate defense against human error. A forgotten step or a typo during manual configuration can lead to an outage. An automated, tested process executes perfectly every time, enhancing the reliability and security of our entire airline.




More information
================


* [SUSE Multi-Linux Manager Product Page](https://www.suse.com/products/suse-manager/)

* [Ansible Integration](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/ansible-integration.html)

* [Salt Guide](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/specialized-guides/salt/salt-overview.html)






