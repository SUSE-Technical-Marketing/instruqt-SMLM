---
slug: smlm-managing-linux-distros
id: 3ultom8jgths
type: challenge
title: إدارة توزيعات Linux المختلفة
tabs:
- id: 7pt4bmdajzt8
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: xewthj8f1giy
  title: Ubuntu 2404 LTS
  type: terminal
  hostname: ubuntu2404lts
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 إدارة توزيعات Linux المختلفة
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

<img class="logos" alt="Welcome!" src="../assets/logos/02-managing_linux_distros.jpeg"/>


هنا في [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]، يُعد <b class="smlmext">SUSE Multi-Linux Manager</b> هو المفتاح لإدارة أسطولنا المتنوع من توزيعات وهندسات Linux من لوحة تحكم موحدة (single pane of glass). لقد ساعدنا هذا على تجنب التخصيصات الإضافية التي كانت تعقد وظائفنا كمهندسين، والتي كانت تزيد بدورها من التكلفة والوقت اللازمين لصيانة وتنفيذ سياسات النظام الخاصة بنا.

باستخدام هذه الأداة، لسنا مقيدين بمورد واحد أو هندسة أو منصة أتمتة واحدة. نحن أحرار في اختيار ما نحتاجه لبيئتنا وإدارتها جميعًا بنفس الطريقة. تخيل لو أننا احتجنا، لكل نوع من الطائرات في أسطولنا، إلى برج مراقبة جوية مختلف بلغة وإجراءات خاصة به. سيكون التعقيد التشغيلي غير قابل للإدارة، وستكون التكاليف باهظة.

نعلم جميعًا أن طرازًا معينًا من الطائرات أفضل لمسار معين؛ تحليق طائرة جامبو لرحلة مدتها نصف ساعة ليس فعالًا من حيث التكلفة. ينطبق الشيء نفسه على توزيعات Linux الخاصة بنا. في حين أن توزيعات SUSE الخاصة ممتازة، فإن بعض تطبيقاتنا لها متطلبات محددة. يضمن <b class="smlm">SMLM</b> أننا لسنا مقيدين (locked in) أبدًا ويمكننا دائمًا دمج الحل الأفضل للمهمة المطروحة.


## <b class="hovereffect">أهدافك:</b>

- إلحاق (Onboard) نظام Ubuntu 24.04 LTS، وهو نظام متخصص يطلبه فريق التسويق لدينا.

- إظهار كيفية إدارتنا لهذا النظام الجديد والمختلف باستخدام نفس الأدوات وإجراءات الترقيع (patching) مثل باقي أسطولنا.



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


إلحاق Ubuntu (Onboarding Ubuntu)
=================

ورد طلب خدمة جديد من قسم التسويق لدينا. يعتمد مصممو الجرافيك لديهم على حزمة إبداعية محددة مدعومة فقط على Ubuntu. سنقوم بإلحاق نظامهم حتى نتمكن من إدارته والتأكد من استيفائه لمعايير الأمان والامتثال الخاصة بنا، بنفس الطريقة التي نتبعها مع الآخرين.

لنبدأ.
<br/>

- قم بالوصول إلى طرفية النظام من علامة التبويب [button label="Ubuntu 2404 LTS" variant="success"](tab-1)

  قبل إجراء أي تغييرات، دعنا نتحقق من المصدر الذي تجلب منه الحزم:

```bash,run
grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```

تقوم محطة العمل هذه بسحب البرامج مباشرة من مستودعات Ubuntu العامة. يمثل هذا مشكلتين: أولاً، ليس لدينا سيطرة على التصحيحات التي يتم تطبيقها، وهو ما يمثل مصدر قلق أمني. ثانيًا، كما أفاد فريق التسويق، في كل مرة تجلب فيها محطات العمل هذه التحديثات، يمكن أن تؤدي إلى إبطاء اتصال الإنترنت في المكتب، مما يسبب إحباطًا للموظفين الآخرين.


لنضع هذا النظام تحت إدارتنا. سيؤدي هذا إلى حل المشكلتين من خلال ربطه بمثيلة <b class="smlmext">SUSE Multi-Linux Manager</b> الداخلية الخاصة بنا لجميع احتياجات البرمجيات.

سنستخدم [button label="web UI" variant="success"](tab-0) للقيام بذلك:

- تحت `Home` ✈ `Overview`، لننقر على `Register Systems`

- املأ التفاصيل التالية:

  - **Host:**

  ```txt
  ubuntu2404lts
  ```

  - **User:** (المستخدم)

  ```txt
  root
  ```

  - **Password:** (كلمة المرور)

  ```txt
  [[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
  ```

  - **Activation Key:** (مفتاح التفعيل)   <b class="highlightcopy">1-ubuntu2404</b>

- اترك الباقي كما هو وانقر على

<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-bootstrap.png"/>


- قد تستغرق عملية التسجيل بضع دقائق لتكتمل، فلنذهب إلى [button label="terminal" variant="success"](tab-1) ونشغل الأمر الأول مرة أخرى لنرى ما تغير:


```bash,run
echo 'Waiting for the registration to complete' ;while [[ ! -f /etc/apt/sources.list.d/susemanager_bootstrap.sources ]] || [[ ! -f /etc/apt/sources.list.d/susemanager:channels.sources ]]; do echo -n '.'; sleep 5; done ; sleep 60; grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```


يمكننا أن نرى ظهور ملفات جديدة:

**/etc/apt/sources.list.d/susemanager:***

إنها توجه النظام إلى قنواتنا المدارة والمسيطر عليها مركزياً في <b class="smlm">SMLM</b>.


يمكننا أيضًا أن نرى أن الملف الأصلي، **/etc/apt/sources.list.d/ubuntu.sources**، قد تم تعديله لتعطيل جميع المستودعات العامة ولكن لم يتم حذفه، وهذا سيسمح لنا بالتراجع (roll back) بسهولة إذا احتجنا لذلك.


> [!NOTE]
> استخدام root عبر SSH مع المصادقة بكلمة المرور للتسجيل هو لأغراض العرض التوضيحي فقط ولا ينصح به للإنتاج (production).


> [!NOTE]
> افتراضيًا، يتعين علينا الموافقة على تسجيل كل نظام من خلال واجهة المستخدم أو عبر سطر الأوامر < salt-key -A -y >، هنا تم تكوين <b class="smlm">SMLM</b> للموافقة التلقائية (auto approve).


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-register_ubuntu.gif"/>
  </div>

<br/>



الآن دعنا ننتقل إلى علامة التبويب [button label="SMLM UI" variant="success"](tab-0)


- ننتقل إلى `Systems` ✈ `System List` ✈ `All`

  يمكننا رؤية النظام الذي سجلناه للتو `Ubuntu2404lts`، لاحظ أنه سيتم تسجيله افتراضيًا تحت اسم المضيف (hostname).

  لننقر عليه، سننتقل مباشرة إلى `Details` - `Overview` حيث يمكننا رؤية من بين معلومات أخرى:

  - حالة النظام.
  - جميع المعلومات مثل اسم المضيف، وعنوان IP، ونوع المحاكاة الافتراضية (virtualization)، و Kernel المستخدم والمنتجات المثبتة.
  - القنوات المشترك فيها.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_overview.gif"/>
  </div>


<br/>

إدارة توزيعات Linux متعددة
=====================================


كما ذكرنا سابقًا، في <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b> نستخدم توزيعات Linux مختلفة، مثلما نستخدم نماذج طائرات وشركات مختلفة. يساعدنا هذا على البقاء في صدارة المنافسة باستخدام المنتج الأنسب لكل احتياج من احتياجاتنا.

مع <b class="smlmext">SUSE Multi-Linux Manager</b> يمكننا إدارتها جميعًا بنفس الإجراءات، ونفس الجداول الزمنية، وما إلى ذلك.. باستخدام نفس الواجهة والآليات.

أدناه سنستكشف كيفية تنفيذ مهام مختلفة على أنظمتك، باتباع نفس العملية بغض النظر عن نظام التشغيل الذي تعمل به أنظمتنا، دون الحاجة إلى إنشاء تخصيصات غير ضرورية.


## <b class="hovereffect">إضافة معلومات إضافية</b>


لنستمر مع النظام الذي سجلناه للتو، سنضيف إليه بعض الإعدادات والمعلومات:

- لننقر في `Properties`، حيث سنضيف معلومات إضافية حول النظام ونغير بعض الإعدادات.


  - تمكين التطبيق التلقائي للتصحيحات (Enable Automatic application of patches):

  <img style='vertical-align: middle; height: 60%; width: 60%; object-fit: contain' src="../assets/SMLM5.1/option-auto_patch_update-enabled.png"/>

    سيقوم هذا بتصحيح النظام تلقائيًا عند وجود تصحيحات ذات صلة.



  - أضف التفاصيل التالية للنظام:


| الحقل (Field) | المحتوى (Content)                                                  |
| ---: | :-----                                                    |
| **Description** | <b class="highlightcopy">Multimedia workstation for graphics designers.</b> |
| **Facility Address** | <b class="highlightcopy">Candy eye street, 1</b> |
| **City** | <b class="highlightcopy">Aeolia</b> |
| **Building** | <b class="highlightcopy">Belem Tower 4</b> |
| **Room** | <b class="highlightcopy">Sierra nevada</b> |


<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-Update_Properties.png"/>



- دعنا نلقي نظرة على الأجهزة التي يعمل عليها:

  - انقر على `Details` ✈ `Hardware`


<br/>

> [!NOTE]
> يمكن أتمتة كل هذا من خلال الـ API.

<br/>

الآن سنقوم بإضافة بعض المعلومات الإضافية إلى النظام باستخدام مفاتيح مخصصة (custom keys)، يمكن استهلاك هذه المعلومات بسهولة في نصوص الأتمتة الخاصة بك لاحقًا.


- انقر على `Details` ✈ `Custom Info`

<img style='vertical-align: top; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Create_Value.png"/>

- انقر فوق `application` واملأ **value** (القيمة) بما يلي:

```text
Logo Wings designer pro
```

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Update_Key.png"/>


<br/>

> [!NOTE]
> لقد قمنا بالفعل بإنشاء المفتاح المخصص **application** لك، إذا كنت ترغب في إنشاء مفاتيحك الخاصة فالأمر بسيط مثل الذهاب إلى: `Systems` ✈ `Custom System Info` ✈ `Create key`

<br/><br/>

لنعد إلى قائمة الأنظمة (Systems)

`Systems` ✈ `System List` ✈ `All`


لننقر على أي من الأنظمة ونذهب إلى `Details` ✈ `Custom Info`.

لقد قمنا بالفعل بملء كل نظام بقيمة،

<br/>

الآن اذهب إلى `Details` ✈ `Overview` ولاحظ **Installed Products** و **Subscribed Channels**، هذه تختلف عن تلك الموجودة في نظام Ubuntu الخاص بك لأنها تشغل نظام تشغيل مختلف.



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_properties.gif"/>
  </div>

<br/>


## <b class="hovereffect">تشغيل الأوامر على أنظمة متعددة في وقت واحد</b>


لنقم بشيء ما على جميع الأنظمة التي لدينا، عد إلى `Systems` ✈ `System List` ✈ `All` وحدد الكل:

<img style='vertical-align: middle; margin: 2px; height: 50%; width: 50%; object-fit: contain' src="../assets/SMLM5.1/select_all_systems.png"/>

لاحظ عمود **Base Channel**، لدينا أنظمة تشغل ثلاثة أنظمة تشغيل مختلفة.

<br/>

بعد تحديد جميع الأنظمة التي نريد تشغيلها، لنذهب لتنفيذ إجراء جماعي:

`Systems` ✈ `System Set Manager`

لنشغل أمرًا عليها جميعًا، لذلك يمكننا الذهاب إلى:

`Misc` ✈ `Remote Command`

ثم املأ التفاصيل التالية واترك الباقي بالقيم الافتراضية:


البرنامج النصي (Script):

```bash,run
cat /etc/os-release
```

لا تقم بتعديل الجدول الزمني (schedule)، نريد تشغيله في أسرع وقت ممكن، انقر على:

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Schedule.png"/>


<br/>


<br/><br/>

سترى إشعارًا أزرق في الأعلى يشير إلى أنه تمت جدولة المهمة.

لنذهب لرؤية النتائج، لذلك سنذهب إلى:

`Schedule` ✈ `Completed Actions`

سنرى قائمة بالإجراءات، في حقل **Filter by Action** اكتب:

```text
Run
```
انقر على الإدخال العلوي الذي يظهر في القائمة، يجب أن يكون مشابهًا لهذا:

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/Select_complete_action_run.png"/>


هناك يمكننا الذهاب إلى **Completed Systems** وفحص النتيجة بالنقر على اسم النظام.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-multiple_systems_at_once.gif"/>
  </div>

<br/>


<br/><br/>

بهذا ننهي هذا الجزء، سنرى المزيد من الأمثلة حول كيفية إدارة أنظمة Linux متعددة خلال ورشة العمل.



لماذا هذا مهم لـ [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]؟
=================================================================================

- لا يوجد تقيد بمورد (no vendor lock-in)، حافظ على حرية الاختيار والمرونة للاستجابة السريعة للأسواق المتغيرة.

- التبسيط وتوفير الوقت بتجنب العمل الإضافي على التخصيصات.

- واجهة مستخدم واحدة لإدارة كل شيء تقلل من التعقيد وستجعل استكشاف الأخطاء وإصلاحها (troubleshooting)، والتوسع، والترقيع، والأتمتة في المستقبل أكثر مرونة وأقل استهلاكًا للوقت.



مزيد من المعلومات
================

للحصول على قائمة بالتوزيعات المدعومة يرجى زيارة:

[SMLM - Supported Clients and Features](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/client-configuration/supported-features.html)