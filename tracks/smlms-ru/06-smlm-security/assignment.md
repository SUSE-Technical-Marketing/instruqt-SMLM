---
slug: smlm-security
id: absc72oduzxl
type: challenge
title: Безопасность и установка исправлений
tabs:
- id: mfvukmt8qxcx
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Безопасность и установка исправлений
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



В этой лабораторной работе мы займемся одной из самых важных обязанностей, которые у нас есть: обеспечением безопасности всего нашего цифрового флота. Мы изучим, как <b class="smlmext">SUSE Multi-Linux Manager</b> позволяет нам реагировать на угрозы безопасности со скоростью и точностью, требуемыми авиакомпанией мирового класса.




## <b class="hovereffect">Ваши цели:</b>

- Выполнить аудит соответствия требованиям безопасности на ваших системах с помощью OpenSCAP.

- Определить системы, затронутые актуальными уязвимостями безопасности.

- Применить необходимые исправления (патчи) ко всем затронутым системам одновременно.



Детали лаборатории (Lab details)
===========

Имя пользователя (Username):
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```

Пароль (Password):
```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

URL <b class="smlm">SMLM</b>: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>




Аудит ваших систем
==================

Мы хотим провести аудит наших производственных систем, чтобы убедиться в их соответствии требованиям.

Мы уже убедились, что следующие пакеты установлены:

- openscap-utils
- scap-security-guide


Выберите производственную группу

- Перейдите в `Systems` ✈ `System Groups`
- Найдите группу **prod** и нажмите `Use in SSM`
![Next](../assets/SMLM5.1/prod_group_selection.png)

Мы будем перенаправлены на страницу **System Set Manager Overview**; как мы видели ранее, отсюда мы можем применять действия к нескольким системам одновременно.

- Перейдите на вкладку `Audit`
- В разделе `OpenSCAP` заполните форму следующими данными, остальное оставьте по умолчанию:
  - **Command-line Arguments (Аргументы командной строки):** <b class="highlightcopy">--profile xccdf_org.ssgproject.content_profile_stig</b>
  - **Path to XCCDF document (Путь к документу XCCDF):** <b class="highlightcopy">/usr/share/xml/scap/ssg/content/ssg-sle15-ds.xml</b>
- Нажмите


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">
</p>
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-Schedule.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p>



Это займет пару минут.


Чтобы увидеть результаты, перейдите в `Audit` ✈ `OpenSCAP` ✈ `All Scans`

![OpenSCAP Results](../assets/SMLM5.1/openscap_results.png)

Если мы нажмем на один из этих результатов, мы сможем увидеть более подробную разбивку.

- Нажав на **report.html**, вы сможете просмотреть более удобную версию отчета, созданного OpenSCAP.

![Detailed OpenSCAP Results](../assets/SMLM5.1/openscap_results_detailed.png)


Не беспокойтесь о сообщенных проблемах.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-audit_your_system.gif"/>
  </div>

<br/>



Определение систем, затронутых уязвимостями
============================================

Мы хотим увидеть, какие системы затронуты уязвимостями.

- Теперь перейдите в `Patches` ✈ `Patch List` ✈ `Relevant`

  Здесь мы видим список всех актуальных исправлений, доступных для наших систем; давайте посмотрим на **Security Patches** (Исправления безопасности).

- Нажав на имя **Advisory** (Бюллетень), вы можете просмотреть подробную страницу, показывающую, какие пакеты и системы это затрагивает, среди прочих деталей.

- В правой части списка столбец **CVEs** предоставляет прямые ссылки на официальные отчеты об уязвимостях.

  Также возможно создавать собственные исправления, но мы не будем рассматривать это в данном треке; для получения дополнительной информации, пожалуйста, обратитесь к ссылкам в конце трека.



## <b class="hovereffect">Исправление затронутых систем</b>

Установка исправлений на наши системы так же проста, как выполнение следующих шагов:

- Перейдите в `Systems` ✈ `System Set Manager`
- Перейдите на вкладку `Patches` ✈ выберите **Security Advisory** в выпадающем списке и нажмите `Show`

![Select Security Advisory](../assets/SMLM5.1/show_only_security_advisories.png)

- Нажмите `Select All` ✈ `Apply Patches` ✈ ![Confirm](../assets/SMLM5.1/bottom-confirm.png)


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-indentify_vulnerabilities.gif"/>
  </div>

<br/>


Почему это важно для [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================


- Имея возможность действовать быстро, мы сокращаем окно уязвимости. Когда обнаруживается новая уязвимость, начинается гонка между нами и злоумышленниками, пытающимися ее использовать. Сложный ручной процесс установки исправлений оставляет наши критически важные системы открытыми слишком долго.

- <b class="smlmext">SUSE Multi-Linux Manager</b> предоставляет единое унифицированное представление о состоянии безопасности всего нашего флота и позволяет нам устранять угрозы с помощью последовательного и надежного процесса.

- Возможность легко проверять соответствие наших систем различным фреймворкам безопасности позволяет нам быстрее внедрять корректирующие меры и соблюдать строгие отраслевые нормы.


Дополнительная информация
================


* [Аудит (Auditing)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/auditing.html)
* [Безопасность SUSE](https://www.suse.com/support/security/)
* [Безопасность системы с OpenSCAP](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/openscap.html)
* [Управление исправлениями](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)