---
slug: smlm-managing-linux-distros
id: jrhasmzno7kd
type: challenge
title: Управление различными дистрибутивами Linux
tabs:
- id: bzgceeci3jed
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: 5usjpllixrbu
  title: Ubuntu 2404 LTS
  type: terminal
  hostname: ubuntu2404lts
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Управление различными дистрибутивами Linux
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

Здесь, в [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]], <b class="smlmext">SUSE Multi-Linux Manager</b> является ключом к управлению нашим разнообразным флотом дистрибутивов Linux и архитектур из единой панели управления (single pane of glass). Это помогло нам избежать дополнительных настроек, которые раньше усложняли нашу работу как инженеров, что, в свою очередь, увеличивало затраты и время, необходимые для поддержки и внедрения наших системных политик.

С этим инструментом мы не привязаны к одному вендору, архитектуре или платформе автоматизации. Мы вольны выбирать то, что нам нужно для нашей среды, и управлять всем этим одинаковым образом. Представьте, если бы для каждого типа самолета в нашем парке нам требовалась отдельная диспетчерская вышка со своим языком и процедурами. Операционная сложность была бы неуправляемой, а затраты — непомерными.



Мы все знаем, что определенная модель самолета лучше подходит для конкретного маршрута; использовать огромный лайнер для получасового перелета нерентабельно. То же самое относится и к нашим дистрибутивам Linux. Хотя собственные дистрибутивы SUSE превосходны, у некоторых наших приложений есть специфические требования. <b class="smlm">SMLM</b> гарантирует, что мы никогда не окажемся в ситуации привязки к вендору (vendor lock-in) и всегда сможем интегрировать лучшее решение для текущей задачи.


## <b class="hovereffect">Ваши цели:</b>

- Подключить (Onboard) систему Ubuntu 24.04 LTS, специализированную систему, требуемую нашей командой маркетинга.

- Продемонстрировать, как мы управляем этой новой, отличной от других системой, используя те же инструменты и процедуры установки исправлений, что и для остального нашего флота.



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


Подключение Ubuntu (Onboarding Ubuntu)
=================

От нашего отдела маркетинга поступил новый запрос на обслуживание. Их графические дизайнеры полагаются на определенный творческий пакет (creative suite), который поддерживается только в Ubuntu. Мы собираемся подключить их систему, чтобы мы могли управлять ею и гарантировать, что она соответствует нашим стандартам безопасности и соответствия требованиям, так же, как мы делаем это с другими.

Давайте начнем.
<br/>

- Получите доступ к терминалу системы из вкладки [button label="Ubuntu 2404 LTS" variant="success"](tab-1)

  Прежде чем вносить какие-либо изменения, давайте проверим, откуда она получает пакеты:

```bash,run
grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```

Эта рабочая станция получает программное обеспечение напрямую из публичных репозиториев Ubuntu. Это создает две проблемы: во-первых, у нас нет контроля над применяемыми исправлениями, что является проблемой безопасности. Во-вторых, как сообщила команда маркетинга, каждый раз, когда эти рабочие станции получают обновления, они могут замедлять офисное интернет-соединение, вызывая разочарование у других сотрудников.



Давайте возьмем эту систему под наше управление. Это решит обе проблемы, подключив ее к нашему внутреннему экземпляру <b class="smlmext">SUSE Multi-Linux Manager</b> для всех потребностей в программном обеспечении.

Мы будем использовать [button label="web UI" variant="success"](tab-0) для этого:

- В разделе `Home` ✈ `Overview`, давайте нажмем на `Register Systems`

- Заполните следующие данные:

  - **Host:**

  ```txt
  ubuntu2404lts
  ```

  - **User:** (Пользователь)

  ```txt
  root
  ```

  - **Password:** (Пароль)

  ```txt
  [[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
  ```

  - **Activation Key:** (Ключ активации)   <b class="highlightcopy">1-ubuntu2404</b>

- Оставьте остальное как есть и нажмите на

<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-bootstrap.png"/>


- Процесс регистрации может занять пару минут. Давайте перейдем в [button label="terminal" variant="success"](tab-1) и запустим первую команду еще раз, чтобы увидеть, что изменилось:


```bash,run
echo 'Waiting for the registration to complete' ;while [[ ! -f /etc/apt/sources.list.d/susemanager_bootstrap.sources ]] || [[ ! -f /etc/apt/sources.list.d/susemanager:channels.sources ]]; do echo -n '.'; sleep 5; done ; sleep 60; grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```


Мы видим, что появились новые файлы:

**/etc/apt/sources.list.d/susemanager:***

Они направляют систему на наши централизованно управляемые и контролируемые каналы в <b class="smlm">SMLM</b>.


Мы также видим, что исходный файл, **/etc/apt/sources.list.d/ubuntu.sources**, был изменен для отключения всех публичных репозиториев, но не был удален; это позволит нам легко выполнить откат (roll back), если потребуется.


> [!NOTE]
> Использование root через SSH с аутентификацией по паролю для регистрации предназначено только для демонстрационных целей и не рекомендуется для производственной среды (production).


> [!NOTE]
> По умолчанию нам нужно одобрять регистрацию каждой системы через UI или через командную строку < salt-key -A -y >, здесь <b class="smlm">SMLM</b> был настроен на автоматическое одобрение.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-register_ubuntu.gif"/>
  </div>

<br/>



Теперь переключимся на вкладку [button label="SMLM UI" variant="success"](tab-0)


- Мы переходим в `Systems` ✈ `System List` ✈ `All`

  Мы можем видеть систему, которую мы только что зарегистрировали `Ubuntu2404lts`. Обратите внимание, что по умолчанию она будет зарегистрирована под именем хоста (hostname).

  Давайте нажмем на нее, мы сразу перейдем в `Details` - `Overview`, где мы можем увидеть среди прочей информации:

  - Статус системы.
  - Всю информацию, такую как имя хоста, IP-адрес, тип виртуализации, используемое ядро и установленные продукты.
  - Каналы, на которые она подписана.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_overview.gif"/>
  </div>


<br/>

Управление множеством дистрибутивов Linux
=====================================


Как упоминалось ранее, в <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b> мы используем разные дистрибутивы Linux, так же как мы используем разные модели самолетов и компании. Это помогает нам опережать конкурентов, используя наиболее подходящий продукт для каждой нашей потребности.

С помощью <b class="smlmext">SUSE Multi-Linux Manager</b> мы можем управлять ими всеми с помощью одних и тех же процедур, расписаний и т. д., используя один и тот же интерфейс и механизмы.

Ниже мы рассмотрим, как выполнять различные задачи в ваших системах, следуя одному и тому же процессу независимо от того, какая ОС работает на наших системах, без необходимости создавать ненужные настройки.


## <b class="hovereffect">Добавление дополнительной информации</b>


Давайте продолжим с системой, которую мы только что зарегистрировали, мы добавим к ней несколько настроек и информацию:

- Давайте нажмем на `Properties`, где мы добавим дополнительную информацию о системе и изменим некоторые настройки.


  - Включить автоматическое применение исправлений (Enable Automatic application of patches):

  <img style='vertical-align: middle; height: 60%; width: 60%; object-fit: contain' src="../assets/SMLM5.1/option-auto_patch_update-enabled.png"/>

    Это автоматически установит исправления на систему, когда появятся соответствующие патчи.



  - Добавьте следующие детали для системы:


| Поле (Field) | Содержание (Content)                                                  |
| ---: | :-----                                                    |
| **Description** | <b class="highlightcopy">Multimedia workstation for graphics designers.</b> |
| **Facility Address** | <b class="highlightcopy">Candy eye street, 1</b> |
| **City** | <b class="highlightcopy">Aeolia</b> |
| **Building** | <b class="highlightcopy">Belem Tower 4</b> |
| **Room** | <b class="highlightcopy">Sierra nevada</b> |


<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-Update_Properties.png"/>



- Давайте посмотрим, на каком оборудовании она работает:

  - Нажмите на `Details` ✈ `Hardware`


<br/>

> [!NOTE]
> Все это можно автоматизировать через API.

<br/>

Теперь мы добавим некоторую дополнительную информацию к системе, используя пользовательские ключи (custom keys); эту информацию можно легко использовать в ваших скриптах автоматизации позже.


- Нажмите на `Details` ✈ `Custom Info`

<img style='vertical-align: top; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Create_Value.png"/>

- Нажмите `application` и заполните **value** (значение) следующим:

```text
Logo Wings designer pro
```

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Update_Key.png"/>


<br/>

> [!NOTE]
> Мы уже создали пользовательский ключ **application** для вас. Если вы хотите создать свои собственные ключи, это так же просто, как перейти в: `Systems` ✈ `Custom System Info` ✈ `Create key`

<br/><br/>

Давайте вернемся к списку Systems

`Systems` ✈ `System List` ✈ `All`


Давайте нажмем на любую из систем и перейдем в `Details` ✈ `Custom Info`.

Мы уже заполнили каждую систему значением,

<br/>

Теперь перейдите в `Details` ✈ `Overview` и обратите внимание на **Installed Products** и **Subscribed Channels**, они отличаются от тех, что в вашей системе Ubuntu, потому что они работают на другой операционной системе.



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_properties.gif"/>
  </div>

<br/>


## <b class="hovereffect">Запуск команд на нескольких системах одновременно</b>


Давайте сделаем что-нибудь на всех системах, которые у нас есть. Вернитесь в `Systems` ✈ `System List` ✈ `All` и выберите все:

<img style='vertical-align: middle; margin: 2px; height: 50%; width: 50%; object-fit: contain' src="../assets/SMLM5.1/select_all_systems.png"/>

Обратите внимание на колонку **Base Channel**, у нас есть системы, работающие на трех разных ОС.

<br/>

Выбрав все системы, с которыми мы хотим работать, давайте перейдем к выполнению группового действия:

`Systems` ✈ `System Set Manager`

Давайте запустим команду на всех них, для этого мы можем перейти в:

`Misc` ✈ `Remote Command`

затем заполните следующие данные и оставьте остальные со значениями по умолчанию:


Скрипт (Script):

```bash,run
cat /etc/os-release
```

Не изменяйте расписание (schedule), мы хотим, чтобы оно запустилось как можно скорее, нажмите на:

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Schedule.png"/>


<br/>


<br/><br/>

Вы увидите синее уведомление вверху, указывающее, что задача была запланирована.

Давайте посмотрим на результаты, для этого мы перейдем в:

`Schedule` ✈ `Completed Actions`

Мы увидим список действий, в поле **Filter by Action** введите:

```text
Run
```
Нажмите на верхнюю запись, которая появится в списке, она должна быть похожа на эту:

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/Select_complete_action_run.png"/>


Там мы можем перейти в **Completed Systems** и изучить результат, нажав на имя системы.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-multiple_systems_at_once.gif"/>
  </div>

<br/>


<br/><br/>

На этом мы завершаем эту часть. Мы увидим больше примеров того, как мы можем управлять несколькими системами Linux в ходе воркшопа.



Почему это важно для [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- Никакой привязки к вендору (vendor lock-in), сохраняйте свободу выбора и гибкость, чтобы быстро реагировать на меняющиеся рынки.

- Упрощайте и экономьте время, избегая дополнительной работы над настройками.

- Единый UI для управления всем снижает сложность и сделает будущее устранение неполадок, масштабирование, установку исправлений и автоматизацию намного более гибкими и менее трудоемкими.



Дополнительная информация
================

Для получения списка поддерживаемых дистрибутивов, пожалуйста, посетите:

[SMLM - Supported Clients and Features](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/client-configuration/supported-features.html)