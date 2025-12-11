---
slug: smlm-lifecycle-management
id: tsrdfyryl5q6
type: challenge
title: লাইফসাইকেল ম্যানেজমেন্ট
tabs:
- id: vsk2g6xwo1ra
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 লাইফসাইকেল ম্যানেজমেন্ট (Lifecycle management)
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

<img class="logos" alt="Welcome!" src="../assets/logos/05-lifecycle.jpeg"/>

এই অংশে আমরা ব্যক্তিগত রক্ষণাবেক্ষণের কাজগুলি থেকে সরে এসে পরিবর্তন পরিচালনার (managing change) জন্য একটি ফ্লিট-ব্যাপী, সার্টিফাইড প্রক্রিয়া প্রতিষ্ঠার দিকে অগ্রসর হব। আমরা অন্বেষণ করব কিভাবে <b class="smlmext">SUSE Multi-Linux Manager</b> -এ কন্টেন্ট লাইফসাইকেল ম্যানেজমেন্ট (Content Lifecycle Management) আমাদের এয়ারলাইনের চাহি অনুযায়ী কাঠামো এবং নিরাপত্তা প্রদান করে।



[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] -এ, প্রস্তুতকারকের কাছ থেকে আসার মুহূর্তেই একটি যাত্রীবাহী জেটে একটি নতুন পার্টস ইনস্টল করা হয় না। এটি একটি কঠোর সার্টিফিকেশন প্রক্রিয়ার মধ্য দিয়ে যায়।

প্রথমে, এটি একটি নিয়ন্ত্রিত ওয়ার্কশপে পরীক্ষা এবং টেস্ট করা হয় (**Development**)। এরপর, এটি একটি অ-বাণিজ্যিক টেস্ট এয়ারক্রাফ্টে ফিট করা হয় এবং কঠিন গ্রাউন্ড এবং ফ্লাইট টেস্টের মধ্য দিয়ে যায় (**Quality Assurance**)। প্রতিটি সম্ভাব্য পরীক্ষায় উত্তীর্ণ হওয়ার পরেই এটি আমাদের সক্রিয় ফ্লিট জুড়ে ইনস্টলেশনের জন্য সার্টিফাইড হয় (**Production**)।

এই পদ্ধতিগত, পর্যায়ক্রমিক পদ্ধতি একটি একক ত্রুটিপূর্ণ উপাদানের কারণে বিমানকে গ্রাউন্ডেড হতে বাধা দেয়, আমাদের যাত্রীদের নিরাপত্তা এবং আমাদের অপারেশনের নির্ভরযোগ্যতা নিশ্চিত করে। আমরা আমাদের আইটি সিস্টেমগুলিতে ঠিক এই একই দর্শন প্রয়োগ করি। একটি সফটওয়্যার আপগ্রেড বা একটি নতুন অ্যাপ্লিকেশন হলো একটি "কম্পোনেন্ট" যা, যদি ত্রুটিপূর্ণ হয়, তবে আমাদের ডিজিটাল অপারেশনগুলিকে বন্ধ করে দিতে পারে। কন্টেন্ট লাইফসাইকেল ম্যানেজমেন্ট হলো সমস্ত সফটওয়্যার পরিবর্তনের জন্য আমাদের অফিসিয়াল সার্টিফিকেশন প্রক্রিয়া।



## <b class="hovereffect">আপনার উদ্দেশ্য:</b>

- একটি কন্টেন্ট লাইফসাইকেল প্রজেক্ট (Content Lifecycle Project) তৈরি করুন।

- আমাদের সিস্টেমের জন্য সফটওয়্যার আপডেট ম্যানেজ এবং সার্টিফাই করতে প্রজেক্টটি ব্যবহার করুন।



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


আমাদের সফটওয়্যার সার্টিফিকেশন পাথওয়ে তৈরি করা
==============================================

এই অনুশীলনে, আমরা সফটওয়্যার আপডেটের প্রবাহ নিয়ন্ত্রণ করতে একটি কন্টেন্ট লাইফসাইকেল প্রজেক্ট তৈরি করব। এটি নিশ্চিত করে যে একটি প্যাচ আমাদের গুরুত্বপূর্ণ প্রোডাকশন সার্ভারে পৌঁছানোর আগে পুঙ্খানুপুঙ্খভাবে পরীক্ষা করা হয়েছে।

<br/>

আমাদের লক্ষ্য হলো একটি `Dev ✈ QA ✈ Prod` পাইপলাইন তৈরি করা।

1.  **Development (Dev):** প্রাথমিক ওয়ার্কশপ। সমস্ত নতুন প্যাচ এবং প্যাকেজ প্রথমে এখানে আসে।
2.  **Quality Assurance (QA):** পরীক্ষার ক্ষেত্র। আমরা আমাদের টেস্টিং টিমগুলির যাচাইকরণের জন্য Dev থেকে QA -তে কন্টেন্টের একটি নির্দিষ্ট সংস্করণ প্রোমোট করব।
3.  **Production (Prod):** সক্রিয় ফ্লিট। শুধুমাত্র QA-অনুমোদিত, প্যাচগুলির সার্টিফাইড সেট প্রোডাকশনে প্রোমোট করা হয়, যেখানে এটি নিরাপদে আমাদের লাইভ সিস্টেমগুলিতে প্রয়োগ করা যেতে পারে।

<br/>

## <b class="hovereffect">প্রজেক্ট তৈরি করুন</b>

- `Content Lifecycle` ✈ `Projects` -এ নেভিগেট করুন এবং ক্লিক করুন ![Create Project](../assets/SMLM5.1/bottom-create_project.png)

- প্রজেক্টের বিবরণ পূরণ করুন:

- **Project Name** (প্রজেক্ট নাম):

```txt
Airtrain SLES15 SPx
```

- **Project Label** (প্রজেক্ট লেবেল):

```txt
at-sles15_spx
```

- **Project Description** (প্রজেক্ট বিবরণ):

```txt
Certified software channel for Airtrain SLES 15 systems.
```


- ক্লিক করুন ![Create](../assets/SMLM5.1/bottom-create.png)

এখন এটি পপুলেট (populate) করা যাক, `Attach/Detach Sources` -এ ক্লিক করুন

![Create](../assets/SMLM5.1/content_lifecycle_just_created.png)

- **New Base Channel** -এ <b class="sles">SLE-Product-SLES15-SP6-Pool for x86_64</b> নির্বাচন করুন এবং ক্লিক করুন ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">Dev এনভায়রনমেন্ট তৈরি করুন</b>

ডেভেলপমেন্ট এনভায়রনমেন্ট লাইফসাইকেল তৈরি করুন

- `Add Environment` -এ ক্লিক করুন

![Create](../assets/SMLM5.1/content_lifecycle_just_created_environment_lifecycle.png)

- নিম্নলিখিত দিয়ে পূরণ করুন:
  * **Name:** <b class="highlightcopy">Development</b>
  * **Label:** <b class="highlightcopy">dev</b>

- ক্লিক করুন ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">QA এনভায়রনমেন্ট তৈরি করুন</b>

কোয়ালিটি অ্যাসিউরেন্স এনভায়রনমেন্ট লাইফসাইকেল তৈরি করুন

- `Add Environment` -এ ক্লিক করুন

- নিম্নলিখিত দিয়ে পূরণ করুন:
  * **Name:** <b class="highlightcopy">QA</b>
  * **Label:** <b class="highlightcopy">qa</b>

- ক্লিক করুন ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">Prod এনভায়রনমেন্ট তৈরি করুন</b>

প্রোডাকশন এনভায়রনমেন্ট লাইফসাইকেল তৈরি করুন

- `Add Environment` -এ ক্লিক করুন

- নিম্নলিখিত দিয়ে পূরণ করুন:
  * **Name:** <b class="highlightcopy">Production</b>
  * **Label:** <b class="highlightcopy">prod</b>

- ক্লিক করুন ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">পপুলেট (Populate)</b>

এখন আমাদের কাছে তিনটি এনভায়রনমেন্ট আছে, আসুন সেগুলিকে কন্টেন্ট দিয়ে পূর্ণ করি।

আমরা এই ক্ষেত্রে একটি ফিল্টার ব্যবহার করব না যেহেতু <b class="sles">SLES</b> ইতিমধ্যেই স্থিতিশীল প্যাকেজ সংস্করণ প্রদান করে।

[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] -এর টেস্টিং এর ক্যাডেন্স বর্তমানে এক মাস, তাই আমরা বর্তমান মাস, অক্টোবরের নামানুসারে এই বিল্ডটির নামকরণ করব।

- ক্লিক করুন ![Build](../assets/SMLM5.1/bottom-build.png)

- **Version Message** -এ টাইপ করুন

```txt
October
```


- `Build` -এ ক্লিক করুন

> [!NOTE]
> এই প্রক্রিয়াটি কয়েক মিনিট সময় নিতে পারে, আপনি 'cloning' এর মতো কিছু ধাপ দেখতে পাবেন, তবে আপনি জেনে স্বস্তি পেতে পারেন যে এর জন্য প্রচুর স্টোরেজের প্রয়োজন নেই। ক্লোনিং প্রক্রিয়াটি শুধুমাত্র প্যাকেজ ইনডেক্স পয়েন্টগুলিতে প্রযোজ্য, প্রকৃত প্যাকেজগুলিতে নয়।


<br/>

## <b class="hovereffect">কন্টেন্ট প্রোমোট করা</b>

এখন, আসুন কন্টেন্টটিকে পরবর্তী ধাপে প্রোমোট করি।

- Development এবং QA এর মাঝখানে `Promote` বোতামে ক্লিক করুন
- **Promote version 1 into QA** শিরোনাম সহ আরেকটি স্ক্রিন উপস্থিত হবে, শুধু আবার `Promote` ক্লিক করুন।

Production এর জন্য একই ধাপ পুনরাবৃত্তি করুন।


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-create_the_project.gif"/>
  </div>

<br/>

আমাদের সিস্টেম আপগ্রেড করুন।
====================

এখন চেষ্টা করে দেখি এটি কিভাবে কাজ করে।

আমরা যা করতে যাচ্ছি:
- নতুন এনভায়রনমেন্টে আমাদের কিছু সিস্টেম যোগ করা।
- কন্টেন্টের একটি নতুন সংস্করণ তৈরি করা
- নতুন সংস্করণটি প্রোমোট করা এবং সিস্টেমগুলি আপডেট করা

<br/>

## <b class="hovereffect">সিস্টেম যোগ করুন</b>

আসুন `Systems` ✈ `System List` ✈ `All` -এ যাই

- **at-ct-qa** সিস্টেমে ক্লিক করুন
- `Software` ✈ `Software Channels` -এ যান
- **Custom Channels** -এ, **at-sles15_spx-qa-...** চ্যানেলের চেকবক্সটি নির্বাচন করুন এবং ক্লিক করুন ![Next](../assets/SMLM5.1/bottom-next.png)
- ক্লিক করুন ![Confirm](../assets/SMLM5.1/bottom-confirm.png)


ফিরে যান `Systems` ✈ `System List` ✈ `All` -এ

- ফিল্টার করুন:

```txt
at-
```

- **-pro** দিয়ে শেষ হওয়া সমস্ত সিস্টেম নির্বাচন করুন
- `Systems` ✈ `System Set Manager` -এ যান
- `Channels` -এ যান
- **Custom Channels** -এ, **at-sles15_spx-prod-...** চ্যানেলের চেকবক্সটি নির্বাচন করুন এবং ক্লিক করুন ![Next](../assets/SMLM5.1/bottom-next.png)
- সমস্ত প্রস্তাবিত চ্যানেলে সাবস্ক্রাইব করতে 'include recommended'-এ ক্লিক করুন:

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-next.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-add_systems.gif"/>
  </div>

<br/>

## <b class="hovereffect">একটি নতুন সংস্করণ তৈরি করুন</b>


এক মাস পেরিয়ে গেছে এবং আমরা আমাদের আপগ্রেডের স্থিতিশীল প্রক্রিয়াটি চালিয়ে যেতে চাই।
আপনি ডেভেলপার টিমের জন্য সফটওয়্যার চ্যানেলগুলির একটি স্ট্যাটিক, অপরিবর্তনীয় কপি তৈরি করতে যাচ্ছেন।

কোনো নতুন প্যাচ হঠাৎ উপস্থিত হবে না এবং তাদের কাজে ব্যাঘাত ঘটাবে না।

- `Content Lifecycle` ✈ `Projects` -এ ফিরে যান এবং আমরা এইমাত্র তৈরি করা প্রজেক্টটিতে ক্লিক করুন।

- ক্লিক করুন ![Build](../assets/SMLM5.1/bottom-build.png)

- **Version Message** -এ টাইপ করুন

```txt
November
```


- `Build` -এ ক্লিক করুন

লক্ষ্য করুন সংস্করণ নম্বর স্বয়ংক্রিয়ভাবে বৃদ্ধি পেয়েছে।

এখন ডেভেলপাররা SUSE দ্বারা প্রদত্ত লাইব্রেরি এবং অ্যাপ্লিকেশনগুলির নতুন এবং প্যাচ করা সংস্করণগুলি ব্যবহার করে তাদের কাজ করতে পারে।


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-create_new_version.gif"/>
  </div>


<br/>

## <b class="hovereffect">Dev থেকে QA -তে কন্টেন্ট প্রোমোট করুন</b>

ধরে নিই আমাদের ডেভেলপাররা তাদের অনুমোদন দিয়েছে। QA টিমের জন্য একটি স্থিতিশীল সংস্করণ তৈরি করার সময় এসেছে যাতে সমস্ত প্রাক-প্রোডাকশন (pre-production) পরীক্ষা করা যায়।

- Development এবং QA এর মাঝখানে `Promote` বোতামে ক্লিক করুন
- **Promote version 2 into QA** শিরোনাম সহ আরেকটি স্ক্রিন উপস্থিত হবে, শুধু আবার `Promote` ক্লিক করুন।

এখন আসুন আমাদের QA সিস্টেমে যাই এবং একটি আপগ্রেড করি।

- `Systems` ✈ `System List` ✈ `All`
- **at-ct-qa** সিস্টেমে ক্লিক করুন
- `Software` ✈ `Packages` ✈ `Upgrade` -এ যান
- ক্লিক করুন:

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


এখন আমাদের QA ইঞ্জিনিয়াররা কোনো ব্যাঘাত ছাড়াই নিরাপদে তাদের পরীক্ষাগুলি সম্পাদন করতে পারে।


> [!NOTE]
> পরিবর্তনগুলি আসার জন্য আমাদের কাছে পর্যাপ্ত সময় নেই, বাস্তব পরিস্থিতিতে সংস্করণ 2-এ প্রোমোট করার জন্য প্যাকেজগুলির নতুন সংস্করণ উপলব্ধ থাকা উচিত।

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-promote_from_dev_to_QA.gif"/>
  </div>


<br/>

## <b class="hovereffect">Production -এ প্রোমোট করুন</b>

QA টিম `v2` তে তাদের কঠোর পরীক্ষা সম্পন্ন করেছে এবং এটিকে প্রধান ফ্লিটের জন্য স্থিতিশীল এবং নিরাপদ হিসেবে প্রত্যয়িত করেছে। এখন এটি আমাদের প্রোডাকশন সিস্টেমের জন্য উপলব্ধ করার সময়।

আমরা আমাদের প্রোডাকশন এনভায়রনমেন্টে QA এর জন্য যেমন করেছি ঠিক একই প্রক্রিয়ার পুনরাবৃত্তি করতে যাচ্ছি:

- প্রথমত, কন্টেন্ট প্রোমোট করুন।
  এটি আমাদের প্রোডাকশন সার্ভারে নতুন প্যাকেজগুলি উপলব্ধ করবে।
  আপনি সফলভাবে নিশ্চিত করেছেন যে শুধুমাত্র পরীক্ষিত এবং অনুমোদিত আপডেটগুলি আপনার সবচেয়ে গুরুত্বপূর্ণ সিস্টেমগুলিতে পৌঁছাতে পারে।

- দ্বিতীয়ত, আমাদের প্রোডাকশন সিস্টেম আপগ্রেড করুন, এখানে একমাত্র পার্থক্য হলো যে আমরা আপগ্রেডটি **আগামীকাল 14:00** টার জন্য শিডিউল করতে যাচ্ছি যাতে আমাদের সমস্ত টিম প্রস্তুত থাকে এবং একটি নিয়ন্ত্রিত প্রক্রিয়া থাকে।


<br/>

এটি [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] এর জন্য কেন গুরুত্বপূর্ণ?
=================================================================================

- আমরা সেফটি গেটগুলির (safety gates) একটি সিরিজ তৈরি করি, যা আমাদের অপারেশনাল কৌশলের একটি মূল নীতি বাস্তবায়ন করা সহজ করে তোলে: **ঝুঁকি ব্যবস্থাপনা** (risk management)।
- **Dev** এনভায়রনমেন্টে প্রবর্তিত একটি একক খারাপ প্যাচ রাজস্ব-উৎপাদনকারী সিস্টেমগুলিকে প্রভাবিত করার সুযোগ পাওয়ার অনেক আগেই ধরা পড়তে পারে এবং ঠিক করা যেতে পারে।
- এই প্রক্রিয়াটি প্যাচিং এবং আপডেটগুলিকে একটি ঝুঁকিপূর্ণ, স্নায়ু-বিধ্বংসী ইভেন্ট থেকে একটি অনুমানযোগ্য, রুটিন রক্ষণাবেক্ষণ পদ্ধতিতে রূপান্তরিত করে, যা একটি নির্ভরযোগ্য এয়ারলাইনের ভিত্তিপ্রস্তর।


<br/>

আরও তথ্য
================

* [Maintenance Windows](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

* [Patch Management](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)

* [Content Lifecycle Management](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/content-lifecycle.html)

* [SUSE Multi-Linux Manager Product Page](https://www.suse.com/products/suse-manager/)