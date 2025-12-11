---
slug: smlms-intro
id: wuis5qjowo43
type: challenge
title: مرحبًا بكم في SUSE Multi-Linux Hands-on Workshop!
teaser: مرحبًا بكم في SUSE Multi-Linux Hands-on Workshop! في هذا القسم سنقدم لكم ورشة
  العمل ومكوناتها الرئيسية.
notes:
- type: text
  contents: |
    # مرحبًا بكم في SUSE Multi-Linux Hands-on Workshop!
    يرجى الانتظار بينما نقوم بإعداد بيئة المختبر الخاصة بك.
    <img class="logos" src="../assets/logos/suse_logo.svg"/>
tabs:
- id: m7evrmx85bfv
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: ""
enhanced_loading: null
---

مرحبًا بكم في <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">SUSE</b> Multi-Linux Hands-on Workshop
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


في ورشة العمل هذه، ستستكشفون بعض السحر الذي يمكن لـ <b class="smlmext">SUSE Multi-Linux Manager</b> (<b class="smlm">SMLM</b>) القيام به؛ إنه حل <b class="suse">SUSE</b> لإدارة توزيعات Linux متعددة على نطاق واسع من واجهة موحدة. وستكتشفون أيضًا كيف يمكنكم الحفاظ على خوادم الإنتاج القديمة (legacy) مدعومة باستخدام <b class="smlsext">SUSE Multi-Linux Support</b> (<b class="smls">SMLS</b>)، وهو حل الدعم المهني والموثوق لدينا لأنظمة Linux.

&emsp;&emsp; ستتبنون دور **مهندس (engineer)** في <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b>، وهي شركة طيران حيث توجد على متن كل طائرة خادم Linux.

&emsp;&emsp; كما هو الحال مع أي مكون من مكونات الطائرة، من الضروري أن تظل هذه الخوادم مستقرة وموثوقة، بغض النظر عما إذا كانت موجودة على الأرض في مركز بيانات ما أو تحلق فوق السحاب ☁ ☁ ☁


&emsp;&emsp; ستتطلب بعض نماذج الطائرات نكهة Linux مختلفة، أو بنية CPU مختلفة. هذه ليست مشكلة بالنسبة لـ <b class="smlm">SMLM</b>؛ فأنتم أحرار في اختيار توزيعة Linux وبنية CPU التي تناسب احتياجاتكم بشكل أفضل دون الحاجة إلى التخلي عن السهولة في المعايرة والإدارة.


&emsp;&emsp; كمهندس مسؤول عن إدارة مشهد Linux، ستمرون ببعض الحلول التي يقدمها لكم <b class="smlm">SMLM</b> و <b class="smls">SMLS</b> لتسهيل وأتمتة إدارة الأنظمة وحل المشكلات الاستثنائية التي قد تحدث.


خلال التحديات المختلفة، ستكون لديكم الأدوات التالية متاحة:

 ✈ **SUSE Multi-Linux Manager**:
   لوحة التحكم الموحدة (single pane of glass) لإدارة كامل الـ Linux stack الخاص بكم.

 ✈ **Centos 7**:
   توزيعة قديمة (legacy) لا تزال قيد الاستخدام في بعض الطائرات القديمة والأنظمة الأرضية.

 ✈ **Ubuntu 24**: توزيعة Linux محددة يطلبها قسم التسويق لدينا لتشغيل تطبيقات التصميم الجرافيكي الخاصة بهم.

 ✈ **SLES 15**: توزيعة Linux عالية الموثوقية والاستقرار والأمان من <b class="suse">SUSE</b> والتي تشكل العمود الفقري لأكثر أنظمتنا أهمية.


## <b class="smlmext hovereffect">SUSE Multi-Linux Manager</b>

إنه حل إدارة بنية تحتية مفتوح المصدر هو الأفضل في فئته للبنية التحتية المعرفة بالبرمجيات الخاصة بكم.

&emsp;&emsp; تم تصميم <b class="smlmext">SUSE Multi-Linux Manager</b> لمساعدة فرق DevOps و IT Operations في مؤسستكم على تقليل التعقيد واستعادة السيطرة على أصول تكنولوجيا المعلومات الخاصة بكم، وهي أداة واحدة ولكنها قوية جدًا لإدارة أنظمة Linux عبر مجموعة متنوعة من معماريات الأجهزة، والـ hypervisors وكذلك الحاويات (containers)، و IoT ومنصات السحابة.

&emsp;&emsp; إنه يؤتمت عملية التوفير (provisioning)، والترقيع (patching)، والتهيئة (configuration) لخوادم Linux وأجهزة IoT من أجل نشر خوادم أسرع ومتسق وقابل للتكرار، مما يساعد على تحسين العمليات وتقليل التكاليف. ومع المراقبة المؤتمتة، والتتبع، والتدقيق، وإعداد التقارير لأنظمتكم، والـ VMs، والحاويات عبر بيئات التطوير والاختبار والإنتاج الخاصة بكم، يمكنكم ضمان الامتثال لسياسات الأمان الداخلية واللوائح الخارجية.


## <b class="smlsext hovereffect">SUSE Multi-Linux Support</b>


إنها خدمة شاملة تقدم المساعدة التقنية والصيانة لمختلف توزيعات Linux، بما في ذلك Red Hat Enterprise Linux (RHEL) الحالية لديكم، و CentOS، و <b class="liberty">SUSE Liberty Linux</b>، و <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>)، اعتمادًا على العرض.

&emsp;&emsp; إنها تمكن المؤسسات من إدارة بيئات Linux المختلطة بكفاءة تحت إطار دعم واحد.
اعتمادًا على الحزمة التي تم شراؤها، قد يتضمن <b class="smlsext">SUSE Multi-Linux Support</b> أيضًا <b class="smlmext">SUSE Multi-Linux Manager</b>، وهي أداة إدارة multi-Linux لإدارة هذه التوزيعات.



 🌅 استكشف Instruqt UI
=======================
قبل أن نبدأ مهمتنا الأولى، دعونا نأخذ لحظة للنظر في Instruqt UI.

+ يوفر لكم **الجانب الأيمن** من الشاشة هذه التعليمات وعناصر التحكم في التنقل.

+ يمنحكم **الجانب الأيسر** الوصول إلى مختلف الآلات والخدمات التي تشكل بيئة المختبر الخاصة بنا.

داخل Instruqt UI يمكنكم التنقل بين [button label="SMLM UI" variant="success"](tab-0) و [button label="terminals" variant="success"](tab-1) المتاحة عن طريق النقر على علامات التبويب في الجزء العلوي من اللوحة اليسرى.


> [!NOTE]
> لا يحدث إعادة تحميل تلقائي على واجهة الويب (Web UI)، في بعض الحالات قد تضطرون إلى إعادة تحميل متصفح الويب الداخلي لـ Instruqt لرؤية التحديثات.


🛫 تسجيل الدخول إلى <b class="smlmext">SUSE Multi-Linux Manager</b> 🛫
========================================
دعونا نطلعكم على البيئة.

- افتح <b class="smlmext">SUSE Multi-Linux Manager</b> داخل المختبر من [button label="SMLM UI" variant="success"](tab-0)


- سجل الدخول باستخدام بيانات الاعتماد التالية:

  - اسم المستخدم (Username):
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```
  - كلمة المرور (Password):

```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

إذا سارت الأمور على ما يرام، يجب أن تروا صفحة **Overview** في واجهة المستخدم <b class="smlmext">SUSE Multi-Linux Manager</b> بعد تسجيل الدخول كمستخدم `[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]`.

> [!NOTE]
> إذا كنتم ترغبون في الوصول إلى واجهة المستخدم <b class="smlmext">SUSE Multi-Linux Manager</b> مباشرة من خلال متصفحكم، يمكنكم القيام بذلك أيضًا:

رابط <b class="smlm">SMLM</b> URL: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>


> [!NOTE]
> إذا لم يتم تحميل الصفحة بشكل صحيح، فقد تحتاجون إلى تحديث علامة تبويب المتصفح بعد انتهاء بيئة المختبر من البدء.




🗺  استكشف <b class="smlmext">SUSE Multi-Linux Manager</b> 🗺
======================================

قبل أن ننطلق، دعونا نتعرف على عناصر التحكم. هذه ليست جولة شاملة، ولكنها نظرة عامة موجزة على الأدوات الرئيسية التي سنستخدمها طوال ورشة العمل. نحن نشجعكم على الفضول والاستكشاف.


لنبدأ.


- **قائمة Systems** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_systems.png"/>

  على اللوحة اليسرى، انقروا على `systems`. هذه نظرة عامة على أسطولنا، وتظهر كل خادم مسجل. القائمة صغيرة الآن، لكنها ستنمو مع إكمالنا لتماريننا.

   - **System Lists**

     يوفر هذا القسم طرق عرض مريحة ومصفاة مسبقًا. على سبيل المثال، تظهر لك قائمة `Out of Date` على الفور الخوادم التي تتطلب تحديثات، مما يوفر عليك إجراء بحث يدوي. </p>

  <br/>

  - **System Groups**

    لتنظيم أسطولنا منطقيًا، نستخدم `System Groups`؛ يمكنكم تصنيفها بناءً على أي معيار. من خلال القيام بذلك، يمكنكم توفير الوقت عند تطبيق الإجراءات أو تحديد السياسات. بمجرد إنشائها، يمكنكم إرفاق الأنظمة تلقائيًا بمجموعة واحدة أو مجموعات متعددة، على سبيل المثال باستخدام `activation keys`.


    لا تترددوا في محاولة إنشاء واحدة الآن بالنقر فوق `+ Create Group`.

  <br/>

  - **عمليات الدفعات (Batch operations)**

    يوفر `System Set Manager` طريقة قوية لتنفيذ الإجراءات على أنظمة متعددة في وقت واحد.


    بدلاً من تطبيق التغييرات واحدة تلو الأخرى، يمكنكم تحديد مجموعة من الأنظمة، إما بشكل فردي من System List أو الاستفادة من System Groups الموجودة، ثم تنفيذ المهام عبرها جميعًا في عملية واحدة.

  <br/>

  - **Provisioning**

    يوفر <b class="smlmext">SUSE Multi-Linux Manager</b> أدوات شاملة لتوفير أنظمة جديدة وإعادة توفير الأنظمة الحالية. تساعدكم هذه القدرة على إنشاء عملية موحدة وقابلة للتكرار لنشر الأنظمة.


    على سبيل المثال، داخل قسم `Autoinstallation`، يمكنكم تحديد التوزيعات وملفات تعريف Kickstart/AutoYaST مما يسمح لكم بتحديد كيفية نشر أنظمتكم، وما هي البرامج التي سيتم تثبيتها، وكيف سيتم توزيع مساحة التخزين والمزيد.


    يمكن دمج كل آليات الأتمتة البسيطة في الإعداد هذه مع حلول أتمتة معقدة ولكنها أكثر قوة مثل Salt أو Ansible، مع الحفاظ على حريتكم في اختيار الحل الأفضل لكل تحد.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_systems.gif"/>
  </div>

<br/>



- **قائمة Patches** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_patches.png"/>

  - **Patching**

    واحدة من أكثر المهام شيوعًا في تكنولوجيا المعلومات هي الحفاظ على الأنظمة محدثة وتطبيق تصحيحات الأمان (security patches) في عجلة من أمرنا من وقت لآخر!
    مع SMLM يمكننا بسهولة رؤية قائمة بالتصحيحات **ذات الصلة**، مصنفة حسب النوع، ومزودة بجميع المعلومات التي قد تحتاجون لمعرفتها بما في ذلك جميع الأنظمة والحزم التي تؤثر عليها.

    بالإضافة إلى التصحيحات المقدمة من البائع، يمكننا أيضًا إنشاء تصحيحات خاصة بنا. لاحقًا سنستكشف الخيارات المختلفة المتاحة لنا لإدارة الترقيع والتحديثات المنتظمة عبر جميع أسطولنا.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_patches.gif"/>
  </div>

<br/>
- **قنوات البرمجيات (Software channels)** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_software.png"/>

  في `Channel List` يمكننا رؤية جميع قنوات/مستودعات/تدفقات الحزم المتاحة للاستهلاك؛ يمكنكم أيضًا إنشاء قنوات برمجيات جديدة لتنظيم برامجكم أو رفع الحزم الخاصة بكم.

  تم استرداد جميع القنوات التي ترونها حاليًا بواسطة SMLM من المصادر الرسمية ويمكن إبقاؤها متزامنة بسهولة.

  في `Package Search` نحن قادرون على البحث عن حزم محددة وفحص محتواها والبيانات الوصفية الخاصة بها.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_software.gif"/>
  </div>

<br/>

- **Configuration** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_configuration.png"/>

  من الممكن أيضًا إدارة وتطبيق تكوينات محددة على الأنظمة، عند التسجيل أو بعد ذلك؛ لذلك يمكننا فحص قسم `Configuration`.

  يوفر SMLM طريقة سهلة لإدارة المراجعات بسهولة، ونشر ومقارنة ملفات التكوين عبر الأنظمة. ويمكن تجميع الكل بسهولة في قنوات تكوين.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_configuration.gif"/>
  </div>

<br/>

- **Scheduling** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_schedule.png"/>

  في `Schedule` يمكننا مراقبة وإدارة الإجراءات المجدولة، وتحديد نوافذ صيانة محددة. هذا مفيد بشكل خاص لأتمتة العمليات المنتظمة أو إجراء عمليات نشر الكناري (canary deployments) عند إدارة العديد من الأنظمة. سنرى هذا قيد العمل لاحقًا خلال ورشة العمل.

<br/>
<br/>

يوفر SUSE Multi-Linux Manager العديد من الإمكانيات لإدارة أنظمتكم؛ لا يمكننا تغطيتها جميعًا في ورشة العمل هذه ولكن، كما هو الحال دائمًا، لا تترددوا في طرح الأسئلة والاستكشاف.

> [!NOTE]
> يتمتع المستخدم الخاص بكم بامتيازات مسؤول (admin) كاملة، لذا نوصي بإجراء التغييرات فقط بعد الانتهاء من التمارين.