---
slug: smlm-automation
id: fpnmzlxefbsr
type: challenge
title: অটোমেশন (ঐচ্ছিক)
tabs:
- id: zbhpp5cfs36q
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 অটোমেশন এবং কনফিগারেশন ম্যানেজমেন্ট (Automation and configuration management)
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
  .highlightcopy {
    color: white;
    font-weight: bold;
    padding: 0 10px;
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

এই বিভাগে আমরা কাজগুলি স্বয়ংক্রিয় করার জন্য উপলব্ধ কিছু বিকল্প দেখতে যাচ্ছি।

এই ল্যাবে, আমরা ম্যানুয়াল কাজ করা থেকে সরে এসে আমাদের কাছে উপলব্ধ কিছু বিকল্প ব্যবহার করে কিছু অটোমেশন তৈরি করব।
<b class="smlmext">SUSE Multi-Linux Manager</b> আমাদের আইটি অপারেশনগুলির জন্য "অটোপাইলট" হিসেবে কাজ করে, যা আমাদের কনফিগারেশন মানগুলি প্রয়োগ করতে এবং আমাদের সম্পূর্ণ ফ্লিট জুড়ে নির্ভুলতা এবং নির্ভরযোগ্যতার সাথে রুটিন কাজগুলি স্বয়ংক্রিয় করতে দেয়।

শত শত সার্ভার ম্যানুয়ালি কনফিগার করা এবং আশা করা যে আমরা কোনো ধাপ মিস করব না, তার পরিবর্তে আমরা প্রক্রিয়া এবং অবস্থা (state) সংজ্ঞায়িত করি এবং মানুষের অপারেশন কমিয়ে একবার একটি সময়সূচী (schedule) নির্ধারণ করি।



## <b class="hovereffect">আপনার উদ্দেশ্য:</b>

- একটি শিডিউল তৈরি করুন যা আপনার ডেভেলপমেন্ট সিস্টেমে নিয়মিত আপডেট সম্পাদন করে।

- সিস্টেমের এনভায়রনমেন্টের উপর ভিত্তি করে একটি ভিন্ন লগইন ব্যানার দেখানোর জন্য একটি স্ক্রিপ্ট তৈরি করুন।

ল্যাবের বিবরণ (Lab details)
===========

ব্যবহারকারীর নাম (Username):
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```

পাসওয়ার্ড (Password):
```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

<b class="smlm">SMLM</b> URL: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>


পুনরাবৃত্তিমূলক আপডেট সেটআপ করুন (Setup recurring updates)
=======================

আমরা চাই ডেভেলপাররা SUSE দ্বারা প্রদত্ত সর্বশেষ স্থিতিশীল আপডেটগুলির সাথে কাজ করুক, কিন্তু আমরা প্রতিদিন তাদের সিস্টেম আপডেট করার কথা মনে রাখার জন্য মানুষের উপর নির্ভর করতে পারি না, তাই আমরা একটি পুনরাবৃত্তিমূলক শিডিউল তৈরি করতে যাচ্ছি যা ঠিক তাই করে।


আমরা dev গ্রুপের সমস্ত সিস্টেমে এটি প্রয়োগ করতে যাচ্ছি যাতে প্রতিটি সিস্টেমে এটি করতে না হয়।

- আসুন `Systems` ✈ `System Groups` -এ যাই
- `dev` গ্রুপে ক্লিক করুন।

আমরা লক্ষ্য করলাম এতে কোনো সিস্টেম বরাদ্দ করা নেই, আসুন একটি যোগ করি।

- `Target Systems` -এ ক্লিক করুন এবং `sles15` নির্বাচন করুন
- তারপর ক্লিক করুন ![Add Systems](../assets/SMLM5.1/bottom-add_system.png)

এখন যেহেতু আমাদের একটি সিস্টেম আছে, আসুন পুনরাবৃত্তিমূলক অ্যাকশনটি তৈরি করি।

- `Recurring Actions` -এ যান
- ক্লিক করুন ![Create](../assets/SMLM5.1/bottom-create.png)
- এখন আসুন নিম্নলিখিত বিবরণ দিয়ে ফর্মটি পূরণ করি:
	+ **Action Type:** 'Custom state'
 	+ **Schedule Name:** 'Update Dev systems'
	+ **Daily:** '03:00'
	+ **Configure states to execute:** নিশ্চিত করুন **uptodate:** নির্বাচিত আছে
	![uptodate Selected](../assets/SMLM5.1/uptodate_selected.png)

- ক্লিক করুন

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-create_schedule.png"/>
</p>



আমাদের পুনরাবৃত্তিমূলক অ্যাকশনগুলির তালিকা পর্যবেক্ষণ করতে আমরা `Schedule` ✈ `Recurring Actions` -এ যেতে পারি।

এখন সমস্ত dev সিস্টেম প্রতিদিন UTC সময় রাত ৩টায় আপডেট হবে।


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-setup_recurring_updates.gif"/>
  </div>

<br/>




নিশ্চিত করুন যে প্রতিটি সিস্টেমে একটি লগইন মেসেজ আছে
==========================================


আমরা একটি কনফিগারেশন চ্যানেল তৈরি করতে যাচ্ছি যাতে নিশ্চিত করা যায় যে আমাদের ম্যানেজ করা প্রতিটি সিস্টেমে একটি উপযুক্ত লগইন মেসেজ রয়েছে।



- আসুন `Configuration` ✈ `Channels` -এ যাই
- ক্লিক করুন ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png)
- নিম্নলিখিত বিবরণ দিয়ে ফর্মটি পূরণ করুন:
	+ **Name:** <b class="highlightcopy">Uniform experience</b>
	+ **Label:** <b class="highlightcopy">uniform_experienace</b>
	+ **Description:** <b class="highlightcopy">Create a uniform experience across systems</b>
- ক্লিক করুন ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png)

এখন যেহেতু আমরা কনফিগ চ্যানেল তৈরি করেছি, আসুন এটি পপুলেট করি।

- `Add Files` ✈ `Create File` -এ যান
- নিম্নলিখিত বিবরণ পূরণ করুন:
	+ **Filename/Path:** <b class="highlightcopy">/etc/motd</b>
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


- ক্লিক করুন ![Create Configuration File](../assets/SMLM5.1/bottom-create_configuration_file.png)

এখন অর্গানাইজেশনের প্রতিটি সিস্টেমকে নতুন কনফিগারেশন চ্যানেলে সাবস্ক্রাইব করা যাক।

- আসুন `Admin` ✈ `Organizations` -এ যাই
- অর্গানাইজেশন **Organization** -এ ক্লিক করুন (এটি ডিফল্ট অর্গানাইজেশন)
- `States` -এ যান এবং আমরা এইমাত্র তৈরি করা চ্যানেলটি নির্বাচন করুন।
![Uniform experience selected](../assets/SMLM5.1/selected_univorm_experience_Configurationchannel.png)
- ক্লিক করুন


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-execute_states.png"/>
</p>


এটি অবিলম্বে ঘটবে না, আসুন সিস্টেমগুলি পরীক্ষা করি। আমরা ওয়েব UI এর মাধ্যমে একটি সাধারণ কমান্ড চালাতে যাচ্ছি, যদি খুব তাড়াতাড়ি চালানো হয়, আপনি পুরানো মেসেজ সহ সিস্টেম এবং যেগুলি ইতিমধ্যে ফাইল আপডেট পেয়েছে সেগুলি দেখতে পারেন।

- আসুন `Salt` ✈ `Remote Commands` -এ যাই
- নিম্নলিখিতটি টাইপ করুন:
![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd.png)
- `Find targets` -এ ক্লিক করুন
- আপনার সিস্টেমের একটি তালিকা দেখা উচিত, `Run command` -এ ক্লিক করুন

এখন আপনার এইরকম কিছু দেখা উচিত:

![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd_first_result.png)

> [!NOTE]
> এই প্রক্রিয়াটি কয়েক মিনিট সময় নিতে পারে, যদি আপনি MOTD না দেখেন তবে দয়া করে কয়েক মিনিট পরে কমান্ডটি পুনরায় চালান।


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-login_message.gif"/>
  </div>

<br/>


এটি [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] এর জন্য কেন গুরুত্বপূর্ণ?
=================================================================================



- হাজার হাজার সিস্টেম ম্যানেজ করার সময় আমরা সবকিছু এক এক করে করার সামর্থ্য রাখি না, কাজগুলি স্বয়ংক্রিয় হতে হবে যাতে আমরা গবাদি পশু (cattle) ম্যানেজ করি, পোষা প্রাণী (pets) নয়।



- "সঠিক অবস্থা" (correct state) সংজ্ঞায়িত করে আমরা কনফিগারেশন ড্রিফট (configuration drift) দূর করি। ফ্লিটের প্রতিটি সার্ভার একই প্লেবুক থেকে কাজ করে, ঠিক যেমন প্রতিটি পাইলট একই চেকলিস্ট ব্যবহার করে।



- যে কাজগুলি শত শত সার্ভার জুড়ে ম্যানুয়ালি সম্পাদন করতে কয়েক ঘন্টা সময় লাগত তা কয়েক মিনিটের মধ্যে সম্পন্ন হয়। এটি আমাদের ইঞ্জিনিয়ারদের উদ্ভাবন এবং উন্নতিতে কাজ করার জন্য মুক্ত করে, পুনরাবৃত্তিমূলক কায়িক শ্রমের জন্য নয়।


- অটোমেশন হলো মানুষের ভুলের (human error) বিরুদ্ধে চূড়ান্ত প্রতিরক্ষা। ম্যানুয়াল কনফিগারেশনের সময় একটি ভুলে যাওয়া ধাপ বা একটি টাইপো বিভ্রাটের (outage) কারণ হতে পারে। একটি স্বয়ংক্রিয়, পরীক্ষিত প্রক্রিয়া প্রতিবার নিখুঁতভাবে সম্পাদিত হয়, যা আমাদের সমগ্র এয়ারলাইনের নির্ভরযোগ্যতা এবং নিরাপত্তা বৃদ্ধি করে।




আরও তথ্য
================


* [SUSE Multi-Linux Manager পণ্য পৃষ্ঠা](https://www.suse.com/products/suse-manager/)

* [Ansible ইন্টিগ্রেশন](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/ansible-integration.html)

* [Salt গাইড](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/specialized-guides/salt/salt-overview.html)