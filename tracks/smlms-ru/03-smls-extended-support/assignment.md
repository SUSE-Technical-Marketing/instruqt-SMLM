---
slug: smls-extended-support
id: 8w9h016mxf58
type: challenge
title: Расширенная поддержка для устаревших систем
tabs:
- id: s8dbskqoohk5
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: rhe5xslb5eze
  title: CentOS 7 QA
  type: terminal
  hostname: centos7
- id: 478azthzfjd5
  title: CentOS 7 Prod
  type: terminal
  hostname: zzcentos7
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Расширенная поддержка для устаревших систем
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
  ul {
    list-style-image: url('../assets/logos/chameleon_icon.png')
  }
</style>

<img style="width: 10px;" src="../assets/logos/chameleon_icon.png" />
<img class="logos" alt="Welcome!" src="../assets/logos/03_extended_support.jpeg"/>

# Продление срока службы нашего устаревшего парка

В любой авиакомпании есть старые, надежные самолеты, которые служат вам годами, но которым у вас пока нет замены. Для нас частью этого устаревшего парка (legacy fleet) являются наши системы CentOS 7. Они стабильны, но находятся в конце своего жизненного цикла (end-of-life), что означает, что они больше не получают критически важных обновлений безопасности от своего первоначального производителя. Для авиакомпании полет без поддержки — это риск, на который мы просто не можем пойти.

Традиционным решением была бы полная и дорогостоящая замена каждого из них.
Но что, если бы мы могли выполнить модернизацию для продления срока службы, обновив их на месте с минимальными перебоями в работе? Именно в этом заключается миссия данного испытания. Мы будем использовать мощь <b class="smlmext">SUSE Multi-Linux Manager</b> вместе с <b class="smlsext">SUSE Multi-Linux Support</b>, чтобы безопасно перевести эти системы и сохранить их в эксплуатации, пока мы не сможем заменить их на более современную ОС.



## <b class="hovereffect">Наш план полета:</b>

- Изучить текущие устаревшие системы, работающие на Centos 7

- Подключить (Onboard) систему QA и применить все доступные исправления

- Выявить и применить обновления, если они есть.

- Освободить (Liberate) систему с помощью формулы liberate.

- Понаблюдать, что изменилось между обеими системами

- Определить, является ли это миграцией.

<br/>

## <b class="hovereffect">Наши самолеты</b>

- CentOS 7 QA ✈ Наш сервер для тестирования и разработки.

- CentOS 7 Prod ✈ Наш производственный сервер, уже зарегистрированный в <b class="smlm">SMLM</b>

<br/><br/>


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



Подключение Centos 7 QA (Onboarding Centos 7 QA)
======================



## <b class="hovereffect">Изучение текущих устаревших систем</b>

Получите доступ к терминалу системы из вкладки [button label="Centos 7 QA" variant="success"](tab-1)

Проверьте текущую версию системы:

```bash,run
rpm -qi centos-release centos-logos
```


Теперь выполните следующую команду, чтобы зарегистрировать систему в <b class="smlm">SMLM</b>:


```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | SMLM_DNS="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-liberty7ltss PROFILENAME='airco-dh4a-qa' bash ; echo "Let's wait 2 minutes for all the background processes to finish"; sleep 120
```


Это похоже на ту команду, которую мы использовали для подключения Ubuntu в предыдущей лабораторной работе, меняется следующее:

- **Activation key** (Ключ активации): Это ссылка на настройки, которые будут применены к системе по умолчанию; в данном случае он был создан только для указания, в каких каналах программного обеспечения будет зарегистрирована система.

- **Profile name** (Имя профиля): Если мы не укажем его, будет использоваться имя хоста, но в данном случае мы хотим, чтобы у него было более значимое имя с тем же соглашением об именовании, которое мы использовали для Centos 7 Prod.


**Необязательно:** Если нам любопытно и мы хотим увидеть, что происходит, когда мы обновляем систему и выполняем формулу Liberate, мы можем запустить следующую команду на обеих системах ( [button label="Centos 7 QA" variant="success"](tab-1) и [button label="Centos 7 Prod" variant="success"](tab-2) ):


```bash,run
journalctl -f
```

И наблюдать за логами, появляющимися в терминалах.


<br/><br/>


## <b class="hovereffect">Выявление и применение обновлений из репозиториев <b class="liberty">Liberty</b></b>

Эти системы Centos 7 поставляются с последними пакетами, предоставленными апстримом; мы хотим убедиться, что новые ошибки исправлены и у нас есть дружелюбный сотрудник поддержки, который поможет нам в случае проблем. Теперь мы уже подписали системы Centos 7 на репозитории программного обеспечения, предоставляемые SUSE, в процессе регистрации, поэтому давайте установим исправления на все из них:



Теперь давайте переключимся на вкладку [button label="SMLM UI" variant="success"](tab-0)


- Перейдите в `Systems` ✈ `System List` в меню слева.

- Найдите свой хост **airco-dh4a-qa** и нажмите на него.

- Выберите `Software` ✈ `Packages`

- Нажмите `Update Packages List`, это займет около минуты

- Выберите `Software` ✈ `Patches`

- Вы увидите список доступных исправлений.

Нажмите `Select All`, затем `Apply Patches` в правом верхнем углу и, наконец, `Confirm`. <b class="smlmext">SUSE Multi-Linux Manager</b> теперь запланирует и выполнит процедуру обновления в системе CentOS.


> [!NOTE]
> Может потребоваться пара минут для получения списка пакетов, прежде чем вы сможете увидеть список исправлений, которые можно применить к системе.


Так как это может занять некоторое время, давайте посмотрим, что происходит «под капотом».
Перейдите на вкладку `Events`, затем в `History`, вы должны увидеть список событий, произошедших с момента регистрации системы в <b class="smlm">SMLM</b>; в первых строках мы должны найти одно событие, содержащее что-то похожее на *Combined Patch*.


Если мы нажмем на него, мы сможем увидеть все детали, не стесняйтесь взглянуть, в противном случае подождите, пока значок не станет зеленым:

![Successfully patched](../assets/SMLM5.1/successfully_updated_system.png)

Мы только что применили исправления, устраняющие ошибки в существующих пакетах; эти исправленные пакеты поступают напрямую от SUSE, это не миграция.

<br/>

Давайте сравним это с производственной системой, которую мы еще не обновили.

Пожалуйста, перейдите в `Software` ✈ `Packages` ✈ `Profiles`

Выберите систему `airco-dh4a-prod`, которая является производственной версией, затем нажмите на:

![Compare](../assets/SMLM5.1/bottom-compare.png)


Мы видим, что большинство версий пакетов не изменилось, все та же версия ( **X.X.X**-xyz ), но с примененным исправлением ( X.X.X-**xyz** ).

Прежде чем мы перейдем к следующему разделу, давайте создадим сохраненный профиль (stored profile), это поможет нам более четко увидеть различия после того, как мы применим формулу liberate в следующем разделе.


Пожалуйста, перейдите в `Software` ✈ `Packages` ✈ `Profile` и нажмите `Create System Profile`. Имя можно задать так:

```txt
before_liberation
```


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-identify_and_apply_updates.gif"/>
  </div>


<br/><br/>


Освобождение (Liberate) системы (необязательно)
==============================

Это **необязательный** шаг и не требуется для получения поддержки.

Теперь давайте освободим (liberate) систему:

- Перейдите на вкладку `Formulas`, найдите **Liberate**, и как только найдете, выберите ее и нажмите `Save` в правом верхнем углу.

Вы увидите сообщение синего цвета в верхней части экрана, прокрутите вверх, если вы его не видите:

![Formula saved](../assets/SMLM5.1/formula_saved.png)


Нажмите там, где написано `Highstate`, вы будете перенаправлены на другую вкладку (`States` ✈ `Highstate`).

Вы можете видеть в сводке внизу, что формула liberate перечислена.

Чтобы начать процесс освобождения, нажмите:

![Formula saved](../assets/SMLM5.1/bottom-apply_highstates.png)

Это займет некоторое время, пожалуйста, проверьте `Events` -> `History`, вы должны увидеть событие под названием **Apply highstate scheduled**

Давайте подождем пару минут, пока оно закончится, тем временем вы можете наблюдать за тем, что происходит, глядя в терминал [button label="Centos 7 QA" variant="success"](tab-1).


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-liberate.gif"/>
  </div>

<br/><br/>

## <b class="hovereffect">Понаблюдайте, что изменилось</b>


Как только это будет завершено, давайте снова сравним систему, чтобы увидеть разницу. Если мы еще не там, давайте нажмем на имя системы `airco-dh4a-qa`.

Затем перейдите в `Software` ✈ `Packages` ✈ `Profile`

В разделе **Compare to Stored Profile** нажмите: ![Compare](../assets/SMLM5.1/bottom-compare.png)

Мы видим, что единственное, что изменилось, это следующие пакеты:

- **centos-logos**, заменен на **sles_es-logos**

- **centos-release**, заменен на **sles_es-release-server**

Остальное остается прежним, но теперь у вас есть вся поддержка, обновления и исправления, предоставляемые <b class="suse">SUSE</b> для <b class="liberty">Liberty Linux</b>.

То же самое относится и к более современным версиям CentOS и RHEL, вы можете трансформировать их в <b class="liberty">Liberty</b> и получить поддержку от <b class="suse">SUSE</b>, не внося никаких изменений в само программное обеспечение и библиотеки.



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-what_changed.gif"/>
  </div>

<br/>



Освобождение производственного сервера (необязательно)
=========================================

Мы видели, как устанавливать исправления и освобождать (Liberate) наш старый сервер Centos 7 в QA, теперь пришло время сделать то же самое с производственной системой, но на этот раз мы сделаем это в другом порядке.

- Сначала мы применим формулу **Liberate**

  Давайте перейдем к нашему производственному серверу `airco-dh4a-prod` и сделаем `Create System Profile`

  После этого давайте применим формулу **Liberate**, как мы это делали с системой QA.

- Как только это будет завершено, давайте сравним систему с профилем, который мы только что создали; как мы видим, единственным изменением были пакеты **centos-logos** и **centos-release**, остальное остается абсолютно таким же.


Это миграция?
==================

Миграция подразумевает создание совершенно нового сервера, переустановку всех приложений с нуля и тщательный перенос данных — процесс, который отнимает много времени, стоит дорого и сопряжен с рисками.

То, что мы сделали, было гораздо элегантнее. Мы выполнили обновление на месте (in-place upgrade).

Идентичность сервера, имя хоста, приложения и пользовательские данные остались совершенно нетронутыми. Мы просто изменили его базовый источник обновлений, и эти компоненты с истекшим сроком службы теперь являются полностью поддерживаемыми компонентами, получающими исправления.

Мы успешно продлили срок службы нашей системы, вернули ее в соответствие требованиям безопасности, и сделали все это без сбоев, характерных для полной миграции. Это та эффективность, которая позволяет [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] летать высоко.




Почему это важно для [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- Это позволяет [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] поддерживать свои работающие системы, давая им время на миграцию в зависимости от их бизнес-потребностей, а не потребностей вендора.

- Это снижает риск, связанный с наличием неподдерживаемых систем, предлагая расширенную поддержку. Этот подход позволяет избежать необходимости немедленной миграции, все работает как обычно, но теперь есть группа экспертов, которая может ответить на ваши звонки.

- Это дает вам свободу сменить поставщика поддержки, не проходя через длительные миграции, и позволяет делать это в масштабе (at scale).



Дополнительная информация
================

- [Registering RHEL 7 or CentOS Linux 7 with SUSE Manager](https://documentation.suse.com/liberty/7/html/suma-quickstart/art-suma-quickstart.html)
- [Running OpenSCAP compliance scans for SUSE Multi-Linux Support 7](https://documentation.suse.com/liberty/7/html/compliance-scans/art-compliance-scans.html)
- [Registering CentOS Linux 7 with the SUSE Customer Center](https://documentation.suse.com/liberty/7/html/quickstart-scc/art-quickstart-scc.html)
- [SUSE Multi-Linux Support 9](https://documentation.suse.com/liberty/9/)