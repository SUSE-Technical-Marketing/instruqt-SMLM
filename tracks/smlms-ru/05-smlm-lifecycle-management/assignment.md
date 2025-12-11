---
slug: smlm-lifecycle-management
id: sb2p1dfk1boa
type: challenge
title: Управление жизненным циклом
tabs:
- id: s0zm9xdqun6s
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Управление жизненным циклом (Lifecycle management)
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

<img class="logos" alt="Welcome!" src="../assets/logos/05-lifecycle.jpeg"/>

В этой части мы перейдем от индивидуальных задач по обслуживанию к созданию сертифицированного процесса управления изменениями в масштабах всего флота. Мы изучим, как управление жизненным циклом контента (Content Lifecycle Management) в <b class="smlmext">SUSE Multi-Linux Manager</b> обеспечивает структуру и безопасность, которые требуются нашей авиакомпании.



В [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] новая деталь не устанавливается на пассажирский самолет сразу после прибытия от производителя. Она проходит строгий процесс сертификации.

Сначала ее осматривают и тестируют в контролируемой мастерской (**Разработка / Development**). Затем ее устанавливают на некоммерческий испытательный самолет и подвергают изнурительным наземным и летным испытаниям (**Контроль качества / Quality Assurance - QA**). Только после прохождения всех мыслимых проверок она сертифицируется для установки на наш активный флот (**Производство / Production**).



Этот методичный, поэтапный подход предотвращает ситуацию, когда один неисправный компонент может приковать самолет к земле, обеспечивая безопасность наших пассажиров и надежность наших операций. Мы применяем ту же философию к нашим ИТ-системам. Обновление программного обеспечения или новое приложение — это «компонент», который, если он неисправен, может остановить наши цифровые операции. Управление жизненным циклом контента — это наш официальный процесс сертификации для всех изменений программного обеспечения.



## <b class="hovereffect">Ваши цели:</b>

- Создать проект жизненного цикла контента (Content Lifecycle Project).

- Использовать проект для управления и сертификации обновлений программного обеспечения для наших систем.



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


Построение нашего пути сертификации ПО
==============================================

В этом упражнении мы создадим проект жизненного цикла контента для контроля потока обновлений программного обеспечения. Это гарантирует, что исправление будет тщательно протестировано, прежде чем оно попадет на наши критически важные производственные серверы.

<br/>

Наша цель — построить конвейер `Dev ✈ QA ✈ Prod`.

1.  **Разработка (Development - Dev):** Начальная мастерская. Все новые исправления и пакеты попадают сюда первыми.
2.  **Контроль качества (Quality Assurance - QA):** Испытательный полигон. Мы продвинем (promote) конкретную версию контента из Dev в QA для проверки нашими командами тестирования.
3.  **Производство (Production - Prod):** Активный флот. Только одобренный QA и сертифицированный набор исправлений продвигается в Production, где его можно безопасно применить к нашим рабочим системам.



<br/>

## <b class="hovereffect">Создание проекта</b>

- Перейдите в `Content Lifecycle` ✈ `Projects` и нажмите ![Create Project](../assets/SMLM5.1/bottom-create_project.png)

- Заполните детали проекта:

- **Project Name** (Имя проекта):

```txt
Airtrain SLES15 SPx
```

- **Project Label** (Метка проекта):

```txt
at-sles15_spx
```

- **Project Description** (Описание проекта):

```txt
Certified software channel for Airtrain SLES 15 systems.
```


- Нажмите ![Create](../assets/SMLM5.1/bottom-create.png)

Теперь давайте заполним его, нажмите `Attach/Detach Sources`

![Create](../assets/SMLM5.1/content_lifecycle_just_created.png)

- В **New Base Channel** выберите <b class="sles">SLE-Product-SLES15-SP6-Pool for x86_64</b> и нажмите ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">Создание среды Dev</b>

Создайте жизненный цикл среды разработки (Development Environment Lifecycle)

- Нажмите `Add Environment`

![Create](../assets/SMLM5.1/content_lifecycle_just_created_environment_lifecycle.png)

- Заполните следующим образом:
  * **Name:** <b class="highlightcopy">Development</b>
  * **Label:** <b class="highlightcopy">dev</b>

- Нажмите ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">Создание среды QA</b>

Создайте жизненный цикл среды контроля качества (Quality Assurance Environment Lifecycle)

- Нажмите `Add Environment`

- Заполните следующим образом:
  * **Name:** <b class="highlightcopy">QA</b>
  * **Label:** <b class="highlightcopy">qa</b>

- Нажмите ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">Создание среды Prod</b>

Создайте жизненный цикл производственной среды (Production Environment Lifecycle)

- Нажмите `Add Environment`

- Заполните следующим образом:
  * **Name:** <b class="highlightcopy">Production</b>
  * **Label:** <b class="highlightcopy">prod</b>

- Нажмите ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">Заполнение (Populate)</b>

Теперь у нас есть все три среды, давайте наполним их контентом.

В данном случае мы не будем использовать фильтр, так как <b class="sles">SLES</b> уже предоставляет стабильные версии пакетов.

Ритм тестирования в [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] в настоящее время составляет один месяц, поэтому мы назовем эту сборку (build) в честь текущего месяца, Октябрь (October).

- Нажмите ![Build](../assets/SMLM5.1/bottom-build.png)

- В **Version Message** введите:

```txt
October
```


- Нажмите `Build`

> [!NOTE]
> Этот процесс может занять пару минут, вы увидите некоторые шаги, такие как 'cloning' (клонирование), но вам может быть приятно узнать, что это не требует много места для хранения. Процесс клонирования применяется только к точкам индекса пакетов, а не к самим фактическим пакетам.


<br/>

## <b class="hovereffect">Продвижение контента</b>

Теперь давайте продвинем (promote) контент на следующие этапы.

- Нажмите кнопку `Promote` между Development и QA.
- Появится другой экран с заголовком **Promote version 1 into QA**, просто нажмите `Promote` снова.

Повторите тот же шаг для Production.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-create_the_project.gif"/>
  </div>

<br/>

Обновление наших систем.
====================

Теперь давайте попробуем, как это работает.

Мы собираемся:
- добавить некоторые из наших систем в новую среду.
- Создать новую версию контента.
- Продвинуть новую версию и обновить системы.

<br/>

## <b class="hovereffect">Добавление систем</b>

Перейдите в `Systems` ✈ `System List` ✈ `All`

- Нажмите на систему **at-ct-qa**
- Перейдите в `Software` ✈ `Software Channels`
- В **Custom Channels** установите флажок для канала **at-sles15_spx-qa-...** и нажмите ![Next](../assets/SMLM5.1/bottom-next.png)
- Нажмите ![Confirm](../assets/SMLM5.1/bottom-confirm.png)


Вернитесь в `Systems` ✈ `System List` ✈ `All`

- Отфильтруйте по:

```txt
at-
```

- Выберите все системы, которые заканчиваются на **-pro**
- Перейдите в `Systems` ✈ `System Set Manager`
- Перейдите в `Channels`
- В **Custom Channels** установите флажок для канала **at-sles15_spx-prod-...** и нажмите ![Next](../assets/SMLM5.1/bottom-next.png)
- Нажмите 'include recommended' (включить рекомендуемые), чтобы подписаться на все рекомендуемые каналы:

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-next.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-add_systems.gif"/>
  </div>

<br/>

## <b class="hovereffect">Создание новой версии</b>


Прошел месяц, и мы хотим продолжить наш стабильный процесс обновлений.
Вы собираетесь создать статичную, неизменяемую копию каналов программного обеспечения для команды разработчиков.

Никакие новые исправления не появятся внезапно и не нарушат их работу.

- Вернитесь в `Content Lifecycle` ✈ `Projects` и нажмите на проект, который мы только что создали.

- Нажмите ![Build](../assets/SMLM5.1/bottom-build.png)

- В **Version Message** введите:

```txt
November
```


- Нажмите `Build`

Обратите внимание, что номер версии автоматически увеличился.

Теперь разработчики могут выполнять свою работу, используя новые и исправленные версии библиотек и приложений, предоставляемые SUSE.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-create_new_version.gif"/>
  </div>


<br/>

## <b class="hovereffect">Продвижение контента из Dev в QA</b>

Предположим, что наши разработчики дали свое одобрение. Пришло время создать стабильную версию для команды QA, чтобы можно было выполнить все предпроизводственные тесты.

- Нажмите кнопку `Promote` между Development и QA.
- Появится другой экран с заголовком **Promote version 2 into QA**, просто нажмите `Promote` снова.

Теперь давайте перейдем к нашим системам QA и выполним обновление.

- `Systems` ✈ `System List` ✈ `All`
- Нажмите на систему **at-ct-qa**
- Перейдите в `Software` ✈ `Packages` ✈ `Upgrade`
- Нажмите на:

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


Теперь наши инженеры QA могут выполнять свои тесты безопасно и без перерывов.


> [!NOTE]
> У нас недостаточно времени, чтобы увидеть поступление изменений; в реальном сценарии должны быть доступны новые версии пакетов для продвижения в версии 2.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-promote_from_dev_to_QA.gif"/>
  </div>


<br/>

## <b class="hovereffect">Продвижение в Production</b>

Команда QA завершила тщательное тестирование `v2` и сертифицировала ее как стабильную и безопасную для основного флота. Пришло время сделать ее доступной для наших производственных систем.

Мы собираемся повторить тот же процесс, что и для QA, в нашей производственной среде:

- Во-первых, продвиньте контент.
  Это сделает новые пакеты доступными для наших производственных серверов.
  Вы успешно гарантировали, что только протестированные и одобренные обновления могут попасть на ваши самые важные системы.

- Во-вторых, обновите наши системы Production; единственная разница здесь в том, что мы запланируем обновление на **завтра в 14:00**, чтобы все наши команды были готовы и процесс был контролируемым.


<br/>

Почему это важно для [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- Мы строим ряд барьеров безопасности, облегчая реализацию основного принципа нашей операционной стратегии: **управление рисками**.
- Одно плохое исправление, введенное в среду **Dev**, может быть обнаружено и исправлено задолго до того, как оно сможет повлиять на системы, приносящие доход.
- Этот процесс превращает установку исправлений и обновлений из рискованного, нервного события в предсказуемую, рутинную процедуру обслуживания — краеугольный камень надежной авиакомпании.


<br/>

Дополнительная информация
================

* [Окна обслуживания (Maintenance Windows)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

* [Управление исправлениями (Patch Management)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)

* [Управление жизненным циклом контента (Content Lifecycle Management)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/content-lifecycle.html)

* [Страница продукта SUSE Multi-Linux Manager](https://www.suse.com/products/suse-manager/)