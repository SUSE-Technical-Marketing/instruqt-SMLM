---
slug: smlm-simplify-upgrade-sles
id: o5abfvj7sctm
type: challenge
title: صيانة بسيطة وموثوقة
tabs:
- id: kketf1sxsjas
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: c2xr1xlrjz4g
  title: SLES 15
  type: terminal
  hostname: sles15
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 صيانة بسيطة وموثوقة
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

حتى الآن، ركزنا على إدارة تنوع أسطولنا المختلط وحتى تمديد عمر أنظمتنا القديمة. الآن، نوجه انتباهنا إلى جوهر شركة الطيران لدينا: أنظمة <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>) الرائدة لدينا.


فكر في هذه الأنظمة كطائراتنا النفاثة الحديثة طويلة المدى. موثوقيتها أمر بالغ الأهمية، والحفاظ عليها في أفضل حالة ينطوي على ترقيع (patching) وترقيات خدمة منتظمة ومخطط لها. التمرين التالي هو بالضبط ذلك: سنستعرض عملية ترقية الإصدار، وهي مهمة شائعة في إدارة دورة حياة أي نظام بالغ الأهمية.



وبينما نستخدم SLES كمثال، تذكر المبدأ الأساسي لبرج المراقبة العالمي لدينا: العملية التي أنت بصدد تنفيذها هي نفسها التي ستستخدمها لأي توزيعة Linux أخرى. الواجهة والمنهجية لا تتغيران.


## <b class="hovereffect">أهدافك:</b>

- إلحاق (Onboard) نظام SLES 15 SP5 جديد ليعمل كطائرة اختبار لدينا.
- إجراء ترقية خدمة رئيسية (major service upgrade) من SP5 إلى SP6.



تفاصيل المختبر (Lab details)
===========

اسم المستخدم (Username):
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```

كلمة المرور (Password):
```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

رابط <b class="smlm">SMLM</b> URL: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>






الإلحاق والتحضير (Onboarding and preparation)
==========================

قم بالوصول إلى طرفية النظام من علامة التبويب [button label="SLES 15" variant="success"](tab-1)


لنسجل النظام داخل <b class="smlm">SMLM</b> باسم **sles15**

```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | HOSTNAME="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-sles15sp5 bash ; echo "Wait 45 seconds for it to finish"; sleep 45
```


الآن، دعنا ننتقل إلى علامة التبويب [button label="SMLM UI" variant="success"](tab-0)


تنفيذ الترقية (Executing the upgrade)
=====================

يجب أن نراه قريبًا في قائمة الأنظمة، لنذهب إلى `Systems` ✈ `System List` ✈ `All`، يرجى النقر فوق تحديث (refresh) في المتصفح الداخلي إذا لم تره.


لننقر عليه وننتقل إلى `Software` ✈ `Packages` ✈ `Upgrade`.


لضمان هجرة سلسة، من الأفضل تطبيق أحدث التحديثات.



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">انقر على </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


قد يستغرق هذا بعض الوقت ليكتمل.

<br/>


## <b class="hovereffect">هجرة المنتج (Product migration)</b>


بمجرد الانتهاء، يرجى الذهاب إلى `Software` ✈ `Product Migration`



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">سترى قسمًا يسمى **Target Products**. تأكد من تحديد <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #90ebcd">SUSE Linux Enterprise Server 15 SP6 x86_64</b>، ثم اضغط على: </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; vertical-align: middle; display:block; align:left; padding: 0px;" src="../assets/SMLM5.1/bottom-select_channels.png"/></p>

ستظهر لك شاشة تأكيد مع ملخص وخيارات إضافية. اترك الإعدادات الافتراضية كما هي وانقر على: ![Schedule Migration](../assets/SMLM5.1/bottom-schedule_migration.png)

سيطلب منك النظام إجراء تشغيل تجريبي (dry run) أولاً، تجاهله واضغط على: ![Confirm](../assets/SMLM5.1/bottom-confirm.png)

سيستغرق هذا بعض الوقت. لمراقبة الحالة، اذهب إلى `Events` ✈ `History` وراقب حدث **Product Migration**. بمجرد أن يتحول رمز الحالة الخاص به إلى اللون الأخضر، تكون الهجرة قد اكتملت. يمكنك التحقق من ذلك عن طريق الانتقال إلى `Software` ✈ `Software Channels` والتأكد من أن النظام مشترك الآن في قنوات SP6 الجديدة.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/04-simple_and_reliable_maintenance-executing_the_upgrade.gif"/>
  </div>

<br/>

## <b class="hovereffect">إعادة التشغيل بعد الهجرة (Post-Migration Reboot)</b>

- عد إلى `Systems` ✈ `System List` ✈ `All`

- لاحظ أن نظام `sles15` لديه الآن أيقونة إعادة تشغيل بجانبه:

![Needs reboot icon](../assets/SMLM5.1/icon_needs_reboot.png)

  هذا يشير إلى أن إعادة التشغيل مطلوبة، عادةً بسبب تحديث رئيسي للنواة (kernel).

- انقر عليها، وسنرى شيئًا مشابهًا لهذا:

![Needs reboot message](../assets/SMLM5.1/system_requires_a_reboot.png)

- انقر على `Schedule System Reboot` وفي الشاشة التالية انقر على ![Reboot System](../assets/SMLM5.1/bottom-reboot_system.png)

> [!NOTE]
> لن تحدث إعادة التشغيل فورًا.

<br/>


## <b class="hovereffect">أهمية الجدولة (Scheduling)</b>

لقد قمنا بجدولة هذه الإجراءات لتحدث فورًا، ولكن هذا ليس مرغوبًا دائمًا. يدعم <b class="smlm">SMLM</b> إنشاء نوافذ الصيانة (Maintenance Windows) (`Schedule` ✈ `Maintenance Windows`) مما يسمح لك بضمان حدوث الأحداث الرئيسية مثل إعادة التشغيل فقط خلال تلك الفترات الموافق عليها مسبقًا.



الجدولة مفيدة بشكل خاص لأنظمة الإنتاج، حيث تسمح بتغييرات مخططة بعناية على مجموعات من الأنظمة وحتى عمليات نشر "الكناري" (canary) المرحلية.

<br/>

> [!NOTE]
> من الممكن القيام بالترقيع المباشر للنواة (live patching) باستخدام KLP، مما يجعل من الممكن تطبيق أحدث تحديثات الأمان على أنوية Linux دون إعادة التشغيل.



لماذا هذا مهم لـ [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]؟
=================================================================================

- يجب أن تكون ترقيات النظام والمهام الروتينية الأخرى بسيطة وقابلة للتكرار، وإلا فإننا نخاطر بارتكاب أخطاء مكلفة. باستخدام هذه الأدوات، يمكننا التحكم بدقة في متى وأين نقوم بتنفيذ الإجراءات، وجدولة الصيانة الحرجة لأسطولنا بثقة.


- يمكننا التحكم في متى وأين نقوم بتنفيذ الإجراءات، وجدولة عمليات الصيانة على أسطولنا الأرضي.


مزيد من المعلومات
================

- [Live kernel patching with KLP](https://documentation.suse.com/en-us/sles/15-SP7/html/SLES-all/cha-klp.html)

- [Maintenance Windows](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

- [Administration Guide](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/admin-overview.html)