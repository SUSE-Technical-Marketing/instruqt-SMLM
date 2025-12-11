---
slug: smlm-simplify-upgrade-sles
id: rludjnxj4o1p
type: challenge
title: সহজ এবং নির্ভরযোগ্য রক্ষণাবেক্ষণ
tabs:
- id: cwhss71bj8ii
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: stuc1efjlczx
  title: SLES 15
  type: terminal
  hostname: sles15
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 সহজ এবং নির্ভরযোগ্য রক্ষণাবেক্ষণ
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

<img class="logos" alt="Welcome!" src="../assets/logos/04-upgrade.jpeg"/>

এখন পর্যন্ত, আমরা আমাদের মিশ্র ফ্লিটের বৈচিত্র্য পরিচালনার দিকে এবং এমনকি আমাদের লিগ্যাসি সিস্টেমগুলির আয়ু বাড়ানোর দিকে মনোনিবেশ করেছি। এখন, আমরা আমাদের এয়ারলাইনের মূল অংশের দিকে মনোযোগ দিচ্ছি: আমাদের ফ্ল্যাগশিপ <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>) সিস্টেম।


এগুলিকে আমাদের অত্যাধুনিক, দূরপাল্লার জেট হিসেবে ভাবুন। তাদের নির্ভরযোগ্যতা সর্বাপেক্ষা গুরুত্বপূর্ণ, এবং সেগুলিকে সর্বোত্তম অবস্থায় রাখার জন্য নিয়মিত, পরিকল্পিত সার্ভিস প্যাচিং এবং আপগ্রেড জড়িত। এই পরবর্তী অনুশীলনটি ঠিক তাই: আমরা একটি সংস্করণ আপগ্রেড প্রক্রিয়ার মধ্য দিয়ে যেতে চলেছি, যা যেকোনো গুরুত্বপূর্ণ সিস্টেমের জীবনচক্র পরিচালনার একটি সাধারণ কাজ।



এবং যদিও আমরা উদাহরণ হিসেবে SLES ব্যবহার করছি, আমাদের সার্বজনীন কন্ট্রোল টাওয়ারের মূল নীতিটি মনে রাখবেন: আপনি যে প্রক্রিয়াটি সম্পাদন করতে চলেছেন তা অন্য যেকোনো Linux ডিস্ট্রিবিউশনের জন্য আপনি যা ব্যবহার করবেন তা একই। ইন্টারফেস এবং পদ্ধতি পরিবর্তন হয় না।


## <b class="hovereffect">আপনার উদ্দেশ্য:</b>

- আমাদের টেস্ট এয়ারক্রাফ্ট হিসেবে কাজ করার জন্য একটি নতুন SLES 15 SP5 সিস্টেম অনবোর্ড (Onboard) করুন।
- SP5 থেকে SP6-এ একটি মেজর সার্ভিস আপগ্রেড সম্পাদন করুন।



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






অনবোর্ডিং এবং প্রস্তুতি (Onboarding and preparation)
==========================

ট্যাব [button label="SLES 15" variant="success"](tab-1) থেকে সিস্টেম টার্মিনালে প্রবেশ করুন


আসুন সিস্টেমটিকে <b class="smlm">SMLM</b> -এর মধ্যে **sles15** হিসেবে রেজিস্টার করি

```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | HOSTNAME="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-sles15sp5 bash ; echo "Wait 45 seconds for it to finish"; sleep 45
```


এখন, আসুন [button label="SMLM UI" variant="success"](tab-0) ট্যাবে যাই


আপগ্রেড এক্সিকিউট করা (Executing the upgrade)
=====================

আমাদের এটি শীঘ্রই সিস্টেমের তালিকায় দেখতে পাওয়া উচিত, আসুন `Systems` ✈ `System List` ✈ `All` -এ যাই, যদি আপনি এটি দেখতে না পান তবে অনুগ্রহ করে অভ্যন্তরীণ ব্রাউজারে রিফ্রেশ ক্লিক করুন।


আসুন এটিতে ক্লিক করি এবং `Software` ✈ `Packages` ✈ `Upgrade` -এ যাই।


একটি মসৃণ মাইগ্রেশন নিশ্চিত করতে সর্বশেষ আপডেটগুলি প্রয়োগ করা সর্বোত্তম।



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">ক্লিক করুন </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


এটি সম্পূর্ণ হতে কিছুটা সময় নিতে পারে।

<br/>


## <b class="hovereffect">প্রোডাক্ট মাইগ্রেশন</b>


একবার এটি শেষ হলে, অনুগ্রহ করে `Software` ✈ `Product Migration` -এ যান



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">আপনি **Target Products** নামে একটি বিভাগ দেখতে পাবেন। নিশ্চিত করুন যে <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #90ebcd">SUSE Linux Enterprise Server 15 SP6 x86_64</b> নির্বাচিত আছে, তারপর চাপুন: </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; vertical-align: middle; display:block; align:left; padding: 0px;" src="../assets/SMLM5.1/bottom-select_channels.png"/></p>

আপনাকে একটি সারাংশ এবং অতিরিক্ত বিকল্প সহ একটি নিশ্চিতকরণ স্ক্রিন দেখানো হবে। ডিফল্টগুলি যেমন আছে তেমনই রাখুন এবং ক্লিক করুন: ![Schedule Migration](../assets/SMLM5.1/bottom-schedule_migration.png)

সিস্টেম আপনাকে প্রথমে একটি ড্রাই রান (dry run) করতে বলবে, এটি উপেক্ষা করুন এবং চাপুন: ![Confirm](../assets/SMLM5.1/bottom-confirm.png)

এটিতে কিছুটা সময় লাগবে। স্ট্যাটাস মনিটর করতে, `Events` ✈ `History` -তে যান এবং **Product Migration** ইভেন্টটি দেখুন। একবার এর স্ট্যাটাস আইকন সবুজ হয়ে গেলে, মাইগ্রেশন সম্পূর্ণ হয়। আপনি `Software` ✈ `Software Channels` -এ নেভিগেট করে এবং সিস্টেমটি এখন নতুন SP6 চ্যানেলগুলিতে সাবস্ক্রাইব করা হয়েছে কিনা তা নিশ্চিত করে এটি যাচাই করতে পারেন।

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/04-simple_and_reliable_maintenance-executing_the_upgrade.gif"/>
  </div>

<br/>

## <b class="hovereffect">পোস্ট-মাইগ্রেশন রিবুট</b>

- `Systems` ✈ `System List` ✈ `All` -এ ফিরে যান

- লক্ষ্য করুন যে `sles15` সিস্টেমটির পাশে এখন একটি রিবুট আইকন রয়েছে:

![Needs reboot icon](../assets/SMLM5.1/icon_needs_reboot.png)

  এটি নির্দেশ করে যে একটি রিবুট প্রয়োজন, সাধারণত একটি মেজর কার্নেল আপডেটের কারণে।

- এটিতে ক্লিক করুন, আমরা এর মতো কিছু দেখতে পাব:

![Needs reboot message](../assets/SMLM5.1/system_requires_a_reboot.png)

- `Schedule System Reboot` -এ ক্লিক করুন এবং পরের স্ক্রিনে ক্লিক করুন ![Reboot System](../assets/SMLM5.1/bottom-reboot_system.png)

> [!NOTE]
> রিবুট অবিলম্বে ঘটবে না।

<br/>


## <b class="hovereffect">শিডিউলিং (Scheduling) এর গুরুত্ব</b>

আমরা এই অ্যাকশনগুলি অবিলম্বে ঘটার জন্য শিডিউল করেছি, তবে এটি সর্বদা वांछनीय নয়। <b class="smlm">SMLM</b> রক্ষণাবেক্ষণ উইন্ডোজ (Maintenance Windows) (`Schedule` ✈ `Maintenance Windows`) তৈরি সমর্থন করে যা আপনাকে নিশ্চিত করতে দেয় যে রিবুটের মতো মেজর ইভেন্টগুলি শুধুমাত্র সেই পূর্ব-অনুমোদিত সময়ে ঘটে।



শিডিউলিং প্রোডাকশন সিস্টেমের জন্য বিশেষভাবে কার্যকর, কারণ এটি সিস্টেমের গ্রুপগুলিতে সাবধানে পরিকল্পিত পরিবর্তন এবং এমনকি পর্যায়ক্রমে "ক্যানারি" (canary) ডিপ্লয়মেন্টের অনুমতি দেয়।

<br/>

> [!NOTE]
> KLP দিয়ে কার্নেল লাইভ প্যাচিং করা সম্ভব, এটি রিবুট না করেই Linux কার্নেলগুলিতে সর্বশেষ নিরাপত্তা আপডেটগুলি প্রয়োগ করা সম্ভব করে তোলে।



এটি [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] এর জন্য কেন গুরুত্বপূর্ণ?
=================================================================================

- সিস্টেম আপগ্রেড এবং অন্যান্য রুটিন কাজগুলি অবশ্যই সহজ এবং পুনরাবৃত্তিযোগ্য হতে হবে, অন্যথায়, আমরা ব্যয়বহুল ভুল করার ঝুঁকি নিই। এই টুলগুলির সাহায্যে, আমরা কখন এবং কোথায় অ্যাকশন সম্পাদন করব তা সুনির্দিষ্টভাবে নিয়ন্ত্রণ করতে পারি, আত্মবিশ্বাসের সাথে আমাদের ফ্লিটের জন্য গুরুত্বপূর্ণ রক্ষণাবেক্ষণ শিডিউল করতে পারি।


- আমরা কখন এবং কোথায় অ্যাকশন সম্পাদন করব তা নিয়ন্ত্রণ করতে পারি, এবং আমাদের গ্রাউন্ডেড ফ্লিটে রক্ষণাবেক্ষণ অপারেশন শিডিউল করতে পারি।


আরও তথ্য
================

- [Live kernel patching with KLP](https://documentation.suse.com/en-us/sles/15-SP7/html/SLES-all/cha-klp.html)

- [Maintenance Windows](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

- [Administration Guide](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/admin-overview.html)