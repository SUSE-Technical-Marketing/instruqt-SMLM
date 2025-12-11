---
slug: smlm-security
id: m1ysgto5yp3l
type: challenge
title: الأمان وتطبيق التصحيحات
tabs:
- id: nyelxsamuaz3
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 الأمان وتطبيق التصحيحات (Security and patching)
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

<img class="logos" alt="Welcome!" src="../assets/logos/06-security.jpeg"/>



في هذا المختبر، سنتناول واحدة من أهم المسؤوليات التي تقع على عاتقنا: ضمان أمن أسطولنا الرقمي بالكامل. سنستكشف كيف يسمح لنا <b class="smlmext">SUSE Multi-Linux Manager</b> بالاستجابة للتهديدات الأمنية بالسرعة والدقة المطلوبة من قبل شركة طيران عالمية المستوى.




## <b class="hovereffect">أهدافك:</b>

- إجراء تدقيق امتثال أمني (security compliance audit) على أنظمتك باستخدام OpenSCAP.

- تحديد الأنظمة المتأثرة بالثغرات الأمنية ذات الصلة.

- تطبيق التصحيحات (patches) اللازمة على جميع الأنظمة المتأثرة في وقت واحد.



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




تدقيق أنظمتك (Audit your systems)
==================

نريد تدقيق أنظمة الإنتاج لدينا للتأكد من أنها متوافقة.

لقد تحققنا بالفعل من تثبيت الحزم التالية:

- openscap-utils
- scap-security-guide


حدد مجموعة الإنتاج

- لنذهب إلى `Systems` ✈ `System Groups`
- ابحث عن المجموعة **prod** وانقر على `Use in SSM`
![Next](../assets/SMLM5.1/prod_group_selection.png)

سيتم توجيهنا إلى صفحة **System Set Manager Overview**، وكما رأينا سابقًا، من هنا يمكننا تطبيق إجراءات على أنظمة متعددة في وقت واحد.

- اذهب إلى علامة تبويب `Audit`
- تحت `OpenSCAP` أكمل النموذج بالتفاصيل التالية، واترك الباقي بالإعدادات الافتراضية:
  - **Command-line Arguments (وسيطات سطر الأوامر):** <b class="highlightcopy">--profile xccdf_org.ssgproject.content_profile_stig</b>
  - **Path to XCCDF document (مسار مستند XCCDF):** <b class="highlightcopy">/usr/share/xml/scap/ssg/content/ssg-sle15-ds.xml</b>
- اضغط على


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">
</p>
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-Schedule.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p>



سيستغرق هذا بضع دقائق.


لرؤية النتائج، دعنا نذهب إلى `Audit` ✈ `OpenSCAP` ✈ `All Scans`

![OpenSCAP Results](../assets/SMLM5.1/openscap_results.png)

إذا نقرنا على إحدى هذه النتائج، يمكننا رؤية تفاصيل أكثر دقة.

- بالنقر على **report.html**، يمكنك عرض نسخة أجمل من التقرير الذي تم إنشاؤه بواسطة OpenSCAP.

![Detailed OpenSCAP Results](../assets/SMLM5.1/openscap_results_detailed.png)


لا تقلق بشأن المشاكل التي تم الإبلاغ عنها.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-audit_your_system.gif"/>
  </div>

<br/>



تحديد الأنظمة المتأثرة بالثغرات الأمنية
============================================

نريد أن نرى الأنظمة التي تأثرت بالثغرات الأمنية.

- الآن، دعنا ننتقل إلى `Patches` ✈ `Patch List` ✈ `Relevant`

  هنا يمكننا رؤية قائمة بجميع التصحيحات ذات الصلة المتاحة لأنظمتنا، دعنا نلقي نظرة على **Security Patches** (تصحيحات الأمان).

- بالنقر على اسم **Advisory** (تنبيه/إرشاد)، يمكنك عرض صفحة مفصلة تظهر الحزم والأنظمة التي يؤثر عليها، من بين تفاصيل أخرى.

- على الجانب الأيمن من القائمة، يوفر عمود **CVEs** روابط مباشرة لتقارير الثغرات الأمنية الرسمية.

  من الممكن أيضًا إنشاء تصحيحات خاصة بنا، لكننا لن نغطي ذلك في هذا المسار، لمزيد من المعلومات يرجى مراجعة الروابط في نهاية المسار.



## <b class="hovereffect">تصحيح الأنظمة المتأثرة</b>

تصحيح أنظمتنا بسيط مثل اتباع الخطوات التالية:

- اذهب إلى `Systems` ✈ `System Set Manager`
- انتقل إلى علامة تبويب `Patches` ✈ حدد **Security Advisory** في القائمة المنسدلة، وانقر على `Show`

![Select Security Advisory](../assets/SMLM5.1/show_only_security_advisories.png)

- انقر على `Select All` ✈ `Apply Patches` ✈ ![Confirm](../assets/SMLM5.1/bottom-confirm.png)


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-indentify_vulnerabilities.gif"/>
  </div>

<br/>


لماذا هذا مهم لـ [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]؟
=================================================================================


- من خلال القدرة على التصرف بسرعة، نقوم بتقليل نافذة التعرض للخطر. عندما يتم اكتشاف ثغرة أمنية جديدة، يبدأ سباق بيننا وبين الجهات الخبيثة التي تحاول استغلالها. تترك عملية التصحيح اليدوية والمعقدة أنظمتنا الحيوية مكشوفة لفترة طويلة جدًا.

- يوفر <b class="smlmext">SUSE Multi-Linux Manager</b> رؤية واحدة وموحدة للوضع الأمني لأسطولنا بالكامل ويسمح لنا بمعالجة التهديدات بعملية متسقة وموثوقة.

- القدرة على التحقق بسهولة من امتثال أنظمتنا لأطر الأمان المختلفة تسمح لنا بتنفيذ التدابير التصحيحية بشكل أسرع والالتزام باللوائح الصناعية الصارمة.


مزيد من المعلومات
================


* [التدقيق (Auditing)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/auditing.html)
* [أمان SUSE](https://www.suse.com/support/security/)
* [أمان النظام باستخدام OpenSCAP](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/openscap.html)
* [إدارة التصحيحات (Manage Patches)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)