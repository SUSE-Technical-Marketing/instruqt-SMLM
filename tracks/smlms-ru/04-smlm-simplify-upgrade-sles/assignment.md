---
slug: smlm-simplify-upgrade-sles
id: xf7xjyvxy4v5
type: challenge
title: Простое и надежное обслуживание
tabs:
- id: frey8geuynhg
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: 2n4jtxdpwmly
  title: SLES 15
  type: terminal
  hostname: sles15
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Простое и надежное обслуживание
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

До сих пор мы были сосредоточены на управлении разнообразием нашего смешанного флота и даже на продлении срока службы наших устаревших систем. Теперь мы обращаем внимание на ядро нашей авиакомпании: наши флагманские системы <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>).


Думайте о них как о наших самых современных дальнемагистральных самолетах. Их надежность имеет первостепенное значение, и поддержание их в отличном состоянии включает в себя регулярное, плановое сервисное обновление и установку исправлений. Следующее упражнение именно об этом: мы пройдем процесс обновления версии, что является обычной задачей при управлении жизненным циклом любой критически важной системы.



И хотя мы используем SLES в качестве примера, помните ключевой принцип нашей универсальной диспетчерской вышки: процесс, который вы собираетесь выполнить, — это тот же самый процесс, который вы бы использовали для любого другого дистрибутива Linux. Интерфейс и методология не меняются.


## <b class="hovereffect">Ваши цели:</b>

- Подключить (Onboard) новую систему SLES 15 SP5, которая будет служить нашим испытательным самолетом.
- Выполнить крупное сервисное обновление (mayor service upgrade) с SP5 до SP6.



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






Подключение и подготовка (Onboarding and preparation)
==========================

Получите доступ к терминалу системы из вкладки [button label="SLES 15" variant="success"](tab-1)


Давайте зарегистрируем систему внутри <b class="smlm">SMLM</b> как **sles15**

```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | HOSTNAME="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-sles15sp5 bash ; echo "Wait 45 seconds for it to finish"; sleep 45
```


Теперь давайте переключимся на вкладку [button label="SMLM UI" variant="success"](tab-0)


Выполнение обновления (Executing the upgrade)
=====================

Мы должны скоро увидеть ее в списке систем, давайте перейдем в `Systems` ✈ `System List` ✈ `All`, пожалуйста, нажмите «обновить» во внутреннем браузере, если вы ее не видите.


Давайте нажмем на нее и перейдем в `Software` ✈ `Packages` ✈ `Upgrade`.


Чтобы обеспечить плавную миграцию, лучше всего применить последние обновления.



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">Нажмите на </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


Это может занять некоторое время.

<br/>


## <b class="hovereffect">Миграция продукта (Product migration)</b>


Как только это завершится, пожалуйста, перейдите в `Software` ✈ `Product Migration`



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">Вы увидите раздел под названием **Target Products**. Убедитесь, что выбран <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #90ebcd">SUSE Linux Enterprise Server 15 SP6 x86_64</b>, затем нажмите: </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; vertical-align: middle; display:block; align:left; padding: 0px;" src="../assets/SMLM5.1/bottom-select_channels.png"/></p>

Вам будет показан экран подтверждения со сводкой и дополнительными опциями. Оставьте значения по умолчанию как есть и нажмите: ![Schedule Migration](../assets/SMLM5.1/bottom-schedule_migration.png)

Система попросит вас сначала выполнить пробный запуск (dry run), проигнорируйте это и нажмите: ![Confirm](../assets/SMLM5.1/bottom-confirm.png)

Это займет некоторое время. Чтобы отслеживать статус, перейдите в `Events` ✈ `History` и наблюдайте за событием **Product Migration**. Как только иконка статуса станет зеленой, миграция завершена. Вы можете проверить это, перейдя в `Software` ✈ `Software Channels` и убедившись, что система теперь подписана на новые каналы SP6.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/04-simple_and_reliable_maintenance-executing_the_upgrade.gif"/>
  </div>

<br/>

## <b class="hovereffect">Перезагрузка после миграции (Post-Migration Reboot)</b>

- Вернитесь в `Systems` ✈ `System List` ✈ `All`

- Обратите внимание, что рядом с системой `sles15` теперь есть иконка перезагрузки:

![Needs reboot icon](../assets/SMLM5.1/icon_needs_reboot.png)

  Это указывает на то, что требуется перезагрузка, обычно из-за крупного обновления ядра.

- Нажмите на нее, мы увидим что-то похожее на это:

![Needs reboot message](../assets/SMLM5.1/system_requires_a_reboot.png)

- Нажмите на `Schedule System Reboot` и на следующем экране нажмите на ![Reboot System](../assets/SMLM5.1/bottom-reboot_system.png)

> [!NOTE]
> Перезагрузка не произойдет немедленно.

<br/>


## <b class="hovereffect">Важность планирования (Scheduling)</b>

Мы запланировали выполнение этих действий немедленно, но это не всегда желательно. <b class="smlm">SMLM</b> поддерживает создание окон обслуживания (Maintenance Windows) (`Schedule` ✈ `Maintenance Windows`), что позволяет гарантировать, что крупные события, такие как перезагрузки, происходят только в эти заранее утвержденные периоды.



Планирование особенно полезно для производственных систем, поскольку оно позволяет тщательно планировать изменения в группах систем и даже выполнять поэтапные «канареечные» (canary) развертывания.

<br/>

> [!NOTE]
> Можно выполнять установку исправлений ядра «на лету» (live patching) с помощью KLP; это позволяет применять последние обновления безопасности к ядрам Linux без перезагрузки.



Почему это важно для [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- Обновления системы и другие рутинные задачи должны быть простыми и повторяемыми, иначе мы рискуем совершить дорогостоящие ошибки. С помощью этих инструментов мы можем точно контролировать, когда и где мы выполняем действия, с уверенностью планируя критически важное обслуживание для нашего флота.


- Мы можем контролировать, когда и где мы выполняем действия, и планировать операции по техническому обслуживанию нашего наземного флота.


Дополнительная информация
================

- [Live kernel patching with KLP](https://documentation.suse.com/en-us/sles/15-SP7/html/SLES-all/cha-klp.html)

- [Maintenance Windows](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

- [Administration Guide](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/admin-overview.html)