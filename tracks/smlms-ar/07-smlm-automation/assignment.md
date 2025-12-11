---
slug: smlm-automation
id: yvbhqwdqcvkd
type: challenge
title: الأتمتة (اختياري)
tabs:
- id: 56gyyv4q1lea
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 الأتمتة وإدارة التكوين
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

في هذا القسم سننظر في بعض الخيارات المتاحة لأتمتة المهام.

في هذا المختبر، ننتقل من أداء المهام اليدوية إلى إنشاء بعض الأتمتة باستخدام بعض الخيارات المتاحة لدينا.
يعمل <b class="smlmext">SUSE Multi-Linux Manager</b> بمثابة "الطيار الآلي" لعمليات تكنولوجيا المعلومات لدينا، مما يسمح لنا بفرض معايير التكوين وأتمتة المهام الروتينية بدقة وموثوقية عبر أسطولنا بالكامل.

بدلاً من تكوين مئات الخوادم يدويًا والأمل في ألا نفوت أي خطوة، نحدد العملية والحالة ونقلل من التشغيل البشري لتحديد جدول زمني، مرة واحدة.



## <b class="hovereffect">أهدافك:</b>

- إنشاء جدول زمني يقوم بإجراء تحديثات بانتظام على أنظمة التطوير الخاصة بك.

- إنشاء برنامج نصي لإظهار شعار تسجيل دخول مختلف حسب بيئة النظام.

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


إعداد التحديثات المتكررة (Setup recurring updates)
=======================

نريد من المطورين العمل بأحدث التحديثات المستقرة التي تقدمها SUSE، ولكن لا يمكننا الاعتماد على تذكر الأشخاص لتحديث أنظمتهم كل يوم، لذلك سنقوم بإنشاء جدول زمني متكرر يقوم بذلك بالضبط.


سنقوم بتطبيق هذا على جميع الأنظمة في مجموعة dev حتى لا يتوجب القيام بذلك على كل نظام على حدة.

- لنذهب إلى `Systems` ✈ `System Groups`
- انقر على مجموعة `dev`.

لقد لاحظنا للتو أنه لا توجد أنظمة مخصصة لها، دعنا نضيف واحداً.

- انقر على `Target Systems` وحدد `sles15`
- ثم انقر على ![Add Systems](../assets/SMLM5.1/bottom-add_system.png)

الآن بعد أن أصبح لدينا نظام، دعنا ننشئ الإجراء المتكرر.

- اذهب إلى `Recurring Actions`
- انقر على ![Create](../assets/SMLM5.1/bottom-create.png)
- الآن دعنا نملأ النموذج بالتفاصيل التالية:
	+ **Action Type (نوع الإجراء):** 'Custom state'
 	+ **Schedule Name (اسم الجدول):** 'Update Dev systems'
	+ **Daily (يومياً):** '03:00'
	+ **Configure states to execute (تكوين الحالات للتنفيذ):** تأكد من تحديد **uptodate:**
	![uptodate Selected](../assets/SMLM5.1/uptodate_selected.png)

- انقر على

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-create_schedule.png"/>
</p>



لمراقبة قائمتنا للإجراءات المتكررة يمكننا الذهاب إلى `Schedule` ✈ `Recurring Actions`

الآن سيتم تحديث جميع أنظمة dev يومياً في الساعة 3 صباحاً بتوقيت UTC.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-setup_recurring_updates.gif"/>
  </div>

<br/>




تأكد من أن كل نظام لديه رسالة تسجيل دخول
==========================================


سنقوم بإنشاء قناة تكوين (configuration channel) للتأكد من أن كل نظام نديره يحتوي على رسالة تسجيل دخول مناسبة.



- لنذهب إلى `Configuration` ✈ `Channels`
- انقر على ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png)
- املأ النموذج بالتفاصيل التالية:
	+ **Name:** <b class="highlightcopy">Uniform experience</b>
	+ **Label:** <b class="highlightcopy">uniform_experienace</b>
	+ **Description:** <b class="highlightcopy">Create a uniform experience across systems</b>
- انقر على ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png)

الآن بعد أن أنشأنا قناة التكوين، دعنا نملأها.

- اذهب إلى `Add Files` ✈ `Create File`
- املأ التفاصيل التالية:
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


- انقر على ![Create Configuration File](../assets/SMLM5.1/bottom-create_configuration_file.png)

الآن دعنا نشترك في كل نظام في المؤسسة في قناة التكوين الجديدة.

- لنذهب إلى `Admin` ✈ `Organizations`
- انقر على منظمة **Organization** (هذه هي المنظمة الافتراضية)
- اذهب إلى `States` وحدد القناة التي أنشأناها للتو.
![Uniform experience selected](../assets/SMLM5.1/selected_univorm_experience_Configurationchannel.png)
- انقر على


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-execute_states.png"/>
</p>


لن يحدث هذا على الفور، دعنا نتحقق من الأنظمة. سنقوم بتشغيل أمر بسيط عبر واجهة الويب، إذا تم تشغيله مبكراً جداً، فقد ترى أنظمة بها الرسالة القديمة وأنظمة تم تحديث الملف بها بالفعل.

- لنذهب إلى `Salt` ✈ `Remote Commands`
- اكتب ما يلي:
![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd.png)
- انقر على `Find targets`
- يجب أن ترى قائمة بالأنظمة، انقر على `Run command`

الآن يجب أن ترى شيئاً مثل هذا:

![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd_first_result.png)

> [!NOTE]
> قد تستغرق هذه العملية بضع دقائق، إذا لم ترَ MOTD يرجى إعادة تشغيل الأمر بعد بضع دقائق.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-login_message.gif"/>
  </div>

<br/>


لماذا هذا مهم لـ [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]؟
=================================================================================



- عند إدارة آلاف الأنظمة، لا يمكننا تحمل القيام بكل شيء واحداً تلو الآخر، يجب أتمتة المهام حتى ندير القطيع (cattle)، وليس الحيوانات الأليفة (pets).



- من خلال تحديد "الحالة الصحيحة" (correct state) نقضي على انحراف التكوين (configuration drift). يعمل كل خادم في الأسطول من نفس الدليل، تماماً كما يستخدم كل طيار نفس قائمة المراجعة.



- المهام التي قد تستغرق ساعات للقيام بها يدوياً عبر مئات الخوادم تكتمل في دقائق. هذا يحرر مهندسينا للعمل على الابتكار والتحسين، وليس العمل اليدوي المتكرر.


- الأتمتة هي الدفاع النهائي ضد الخطأ البشري. خطوة منسية أو خطأ مطبعي أثناء التكوين اليدوي يمكن أن يؤدي إلى انقطاع الخدمة. تنفذ العملية المؤتمتة والمُختبرة بشكل مثالي في كل مرة، مما يعزز موثوقية وأمن شركة الطيران بأكملها.




مزيد من المعلومات
================


* [صفحة منتج SUSE Multi-Linux Manager](https://www.suse.com/products/suse-manager/)

* [تكامل Ansible](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/ansible-integration.html)

* [دليل Salt](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/specialized-guides/salt/salt-overview.html)