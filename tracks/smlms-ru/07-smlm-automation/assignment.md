---
slug: smlm-automation
id: mf6zwzkvfqzh
type: challenge
title: Автоматизация (необязательно)
tabs:
- id: rydp0ovxwjed
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Автоматизация и управление конфигурацией
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

В этом разделе мы рассмотрим некоторые доступные варианты автоматизации задач.

В этой лабораторной работе мы переходим от выполнения задач вручную к созданию автоматизации с использованием некоторых имеющихся у нас опций.
<b class="smlmext">SUSE Multi-Linux Manager</b> действует как «автопилот» для наших ИТ-операций, позволяя нам внедрять стандарты конфигурации и автоматизировать рутинные задачи с точностью и надежностью во всем нашем флоте.

Вместо того чтобы вручную настраивать сотни серверов и надеяться, что мы не пропустим ни одного шага, мы определяем процесс и состояние и сводим человеческие операции к определению расписания — один раз.



## <b class="hovereffect">Ваши цели:</b>

- Создать расписание, которое регулярно выполняет обновления на ваших системах разработки.

- Создать скрипт для отображения различного баннера при входе в систему в зависимости от среды системы.

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


Настройка повторяющихся обновлений (Setup recurring updates)
=======================

Мы хотим, чтобы разработчики работали с последними стабильными обновлениями, предоставляемыми SUSE, но мы не можем полагаться на то, что люди будут помнить о необходимости обновлять свои системы каждый день, поэтому мы создадим повторяющееся расписание, которое делает именно это.


Мы применим это ко всем системам в группе dev, чтобы это не нужно было делать на каждой системе отдельно.

- Перейдите в `Systems` ✈ `System Groups`
- Нажмите на группу `dev`.

Мы только что заметили, что ей не назначены системы, давайте добавим одну.

- Нажмите на `Target Systems` и выберите `sles15`
- Затем нажмите на ![Add Systems](../assets/SMLM5.1/bottom-add_system.png)

Теперь, когда у нас есть система, давайте создадим повторяющееся действие.

- Перейдите в `Recurring Actions`
- Нажмите на ![Create](../assets/SMLM5.1/bottom-create.png)
- Теперь заполним форму следующими данными:
	+ **Action Type (Тип действия):** 'Custom state'
 	+ **Schedule Name (Имя расписания):** 'Update Dev systems'
	+ **Daily (Ежедневно):** '03:00'
	+ **Configure states to execute (Настроить состояния для выполнения):** Убедитесь, что выбрано **uptodate:**
	![uptodate Selected](../assets/SMLM5.1/uptodate_selected.png)

- Нажмите на

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-create_schedule.png"/>
</p>



Чтобы просмотреть наш список повторяющихся действий, мы можем перейти в `Schedule` ✈ `Recurring Actions`

Теперь все системы dev будут обновляться ежедневно в 3 часа ночи по времени UTC.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-setup_recurring_updates.gif"/>
  </div>

<br/>




Убедитесь, что у каждой системы есть сообщение при входе
==========================================


Мы собираемся создать канал конфигурации, чтобы убедиться, что каждая система, которой мы управляем, содержит соответствующее сообщение при входе в систему (login message).



- Перейдите в `Configuration` ✈ `Channels`
- Нажмите на ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png)
- Заполните форму следующими данными:
	+ **Name:** <b class="highlightcopy">Uniform experience</b>
	+ **Label:** <b class="highlightcopy">uniform_experienace</b>
	+ **Description:** <b class="highlightcopy">Create a uniform experience across systems</b>
- Нажмите на ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png)

Теперь, когда мы создали канал конфигурации, давайте заполним его.

- Перейдите в `Add Files` ✈ `Create File`
- Заполните следующие данные:
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


- Нажмите на ![Create Configuration File](../assets/SMLM5.1/bottom-create_configuration_file.png)

Теперь давайте подпишем каждую систему в организации на новый канал конфигурации.

- перейдите в `Admin` ✈ `Organizations`
- Нажмите на организацию **Organization** (Это организация по умолчанию)
- Перейдите в `States` и выберите канал, который мы только что создали.
![Uniform experience selected](../assets/SMLM5.1/selected_univorm_experience_Configurationchannel.png)
- Нажмите на


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-execute_states.png"/>
</p>


Это не произойдет мгновенно, давайте проверим системы. Мы запустим простую команду через веб-интерфейс; если запустить слишком рано, вы можете увидеть системы со старым сообщением и системы, у которых файл уже обновлен.

- Перейдите в `Salt` ✈ `Remote Commands`
- Введите следующее:
![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd.png)
- Нажмите на `Find targets`
- Вы должны увидеть список систем, нажмите на `Run command`

Теперь вы должны увидеть что-то вроде этого:

![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd_first_result.png)

> [!NOTE]
> Этот процесс может занять пару минут, если вы не видите MOTD, пожалуйста, запустите команду повторно через несколько минут.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-login_message.gif"/>
  </div>

<br/>


Почему это важно для [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================



- При управлении тысячами систем мы не можем позволить себе делать все по одному, задачи должны быть автоматизированы, чтобы мы управляли «стадом» (cattle), а не «домашними питомцами» (pets).



- Определяя «правильное состояние» (correct state), мы устраняем дрейф конфигурации (configuration drift). Каждый сервер во флоте работает по одной и той же инструкции, так же как каждый пилот использует один и тот же контрольный список.



- Задачи, выполнение которых вручную на сотнях серверов заняло бы часы, выполняются за минуты. Это освобождает наших инженеров для работы над инновациями и улучшениями, а не для повторяющегося ручного труда.


- Автоматизация — это лучшая защита от человеческого фактора. Забытый шаг или опечатка во время ручной настройки могут привести к сбою. Автоматизированный, протестированный процесс выполняется идеально каждый раз, повышая надежность и безопасность всей нашей авиакомпании.




Дополнительная информация
================


* [Страница продукта SUSE Multi-Linux Manager](https://www.suse.com/products/suse-manager/)

* [Интеграция Ansible](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/ansible-integration.html)

* [Руководство по Salt](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/specialized-guides/salt/salt-overview.html)q