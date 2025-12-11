---
slug: smlm-lifecycle-management
id: 2zqpa9befcyu
type: challenge
title: 生命周期管理
tabs:
- id: ofa0acgxqubl
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 生命周期管理 (Lifecycle management)
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

在这一部分，我们将从单独的维护任务过渡到建立一个全机队范围的、经过认证的变更管理流程。我们将探讨 <b class="smlmext">SUSE Multi-Linux Manager</b> 中的内容生命周期管理 (Content Lifecycle Management) 如何提供我们航空公司所需的结构和安全性。



在 [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]，新零件不会在从制造商处到达的那一刻就安装在客机上。它要经过严格的认证流程。

首先，它要在受控车间进行检查和测试 (**Development / 开发**)。接下来，它会被安装在一架非商用的测试飞机上，并进行艰苦的地面和飞行测试 (**Quality Assurance / 质量保证 - QA**)。只有通过了所有可以想象到的检查后，它才会被认证用于在我们的现役机队中安装 (**Production / 生产**)。



这种有条理的、分阶段的方法可以防止单个故障组件导致飞机停飞，从而确保乘客的安全和运营的可靠性。我们将完全相同的理念应用于我们的 IT 系统。软件升级或新应用程序是一个“组件”，如果出现故障，可能会导致我们的数字化运营停滞。内容生命周期管理是我们对所有软件变更的官方认证流程。



## <b class="hovereffect">您的目标：</b>

- 构建一个内容生命周期项目 (Content Lifecycle Project)。

- 使用该项目来管理和认证我们系统的软件更新。



实验室详情 (Lab details)
===========

用户名 (Username):
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```

密码 (Password):
```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

<b class="smlm">SMLM</b> URL: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>


构建我们的软件认证路径
==============================================

在这个练习中，我们将创建一个内容生命周期项目来控制软件更新的流程。这确保了补丁在到达我们关键的生产服务器之前经过了彻底的测试。

<br/>

我们的目标是构建一个 `Dev ✈ QA ✈ Prod` 流水线。

1.  **开发 (Development - Dev):** 初始车间。所有新补丁和软件包首先到达这里。
2.  **质量保证 (Quality Assurance - QA):** 试验场。我们将把特定版本的内容从 Dev 晋升 (promote) 到 QA，以便我们的测试团队进行验证。
3.  **生产 (Production - Prod):** 现役机队。只有经过 QA 批准、认证的补丁集才会被晋升到 Production，在那里它们可以安全地应用于我们的实时系统。



<br/>

## <b class="hovereffect">创建项目</b>

- 导航至 `Content Lifecycle` ✈ `Projects` 并点击 ![Create Project](../assets/SMLM5.1/bottom-create_project.png)

- 填写项目详细信息：

- **Project Name** (项目名称):

```txt
Airtrain SLES15 SPx
```

- **Project Label** (项目标签):

```txt
at-sles15_spx
```

- **Project Description** (项目描述):

```txt
Certified software channel for Airtrain SLES 15 systems.
```


- 点击 ![Create](../assets/SMLM5.1/bottom-create.png)

现在让我们填充它，点击 `Attach/Detach Sources`

![Create](../assets/SMLM5.1/content_lifecycle_just_created.png)

- 在 **New Base Channel** 上选择 <b class="sles">SLE-Product-SLES15-SP6-Pool for x86_64</b> 并点击 ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">创建 Dev 环境</b>

创建开发环境生命周期 (Development Environment Lifecycle)

- 点击 `Add Environment`

![Create](../assets/SMLM5.1/content_lifecycle_just_created_environment_lifecycle.png)

- 填写以下内容：
  * **Name:** <b class="highlightcopy">Development</b>
  * **Label:** <b class="highlightcopy">dev</b>

- 点击 ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">创建 QA 环境</b>

创建质量保证环境生命周期 (Quality Assurance Environment Lifecycle)

- 点击 `Add Environment`

- 填写以下内容：
  * **Name:** <b class="highlightcopy">QA</b>
  * **Label:** <b class="highlightcopy">qa</b>

- 点击 ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">创建 Prod 环境</b>

创建生产环境生命周期 (Production Environment Lifecycle)

- 点击 `Add Environment`

- 填写以下内容：
  * **Name:** <b class="highlightcopy">Production</b>
  * **Label:** <b class="highlightcopy">prod</b>

- 点击 ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">填充 (Populate)</b>

现在我们有了所有三个环境，让我们用内容填充它们。

在这种情况下我们不会使用过滤器，因为 <b class="sles">SLES</b> 已经提供了稳定的软件包版本。

[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] 目前的测试节奏是一个月，所以我们将以当前月份“十月 (October)”来命名此构建 (build)。

- 点击 ![Build](../assets/SMLM5.1/bottom-build.png)

- 在 **Version Message** 中输入

```txt
October
```


- 点击 `Build`

> [!NOTE]
> 这个过程可能需要几分钟，您会看到像 'cloning' (克隆) 这样的步骤，但您可能会松一口气，这不需要大量存储空间。克隆过程仅适用于软件包索引点，而不适用于实际软件包本身。


<br/>

## <b class="hovereffect">晋升内容 (Promoting content)</b>

现在，让我们将内容晋升 (promote) 到更后期的阶段。

- 点击 Development 和 QA 之间的 `Promote` 按钮
- 将出现另一个标题为 **Promote version 1 into QA** 的屏幕，只需再次点击 `Promote`。

对 Production 重复相同的步骤。


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-create_the_project.gif"/>
  </div>

<br/>

升级我们的系统。
====================

现在让我们试试它是如何工作的。

我们将：
- 将我们的一些系统添加到新环境中。
- 创建内容的新版本
- 晋升新版本并更新系统

<br/>

## <b class="hovereffect">添加系统</b>

让我们前往 `Systems` ✈ `System List` ✈ `All`

- 点击 **at-ct-qa** 系统
- 前往 `Software` ✈ `Software Channels`
- 在 **Custom Channels** 上，选中 **at-sles15_spx-qa-...** 频道的复选框，然后点击 ![Next](../assets/SMLM5.1/bottom-next.png)
- 点击 ![Confirm](../assets/SMLM5.1/bottom-confirm.png)


回到 `Systems` ✈ `System List` ✈ `All`

- 过滤条件：

```txt
at-
```

- 选择所有以 **-pro** 结尾的系统
- 前往 `Systems` ✈ `System Set Manager`
- 前往 `Channels`
- 在 **Custom Channels** 上，选中 **at-sles15_spx-prod-...** 频道的复选框，然后点击 ![Next](../assets/SMLM5.1/bottom-next.png)
- 点击 'include recommended' (包含推荐) 以订阅所有推荐频道：

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-next.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-add_systems.gif"/>
  </div>

<br/>

## <b class="hovereffect">创建一个新版本</b>


一个月过去了，我们希望继续我们要稳定的升级流程。
您将为开发人员团队创建软件频道的一个静态、不变的副本。

不会突然出现新补丁来打断他们的工作。

- 回到 `Content Lifecycle` ✈ `Projects` 并点击我们刚刚创建的项目。

- 点击 ![Build](../assets/SMLM5.1/bottom-build.png)

- 在 **Version Message** 中输入

```txt
November
```


- 点击 `Build`

注意版本号已自动增加。

现在开发人员可以使用 SUSE 提供的库和应用程序的新版本和修补版本来完成他们的工作。


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-create_new_version.gif"/>
  </div>


<br/>

## <b class="hovereffect">将内容从 Dev 晋升到 QA</b>

假设我们的开发人员已经批准了。现在是时候为 QA 团队创建一个稳定版本，以便可以执行所有预生产测试。

- 点击 Development 和 QA 之间的 `Promote` 按钮
- 将出现另一个标题为 **Promote version 2 into QA** 的屏幕，只需再次点击 `Promote`。

现在让我们前往我们的 QA 系统并进行升级。

- `Systems` ✈ `System List` ✈ `All`
- 点击 **at-ct-qa** 系统
- 前往 `Software` ✈ `Packages` ✈ `Upgrade`
- 点击：

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


现在我们的 QA 工程师可以安全地执行测试，而不会中断。


> [!NOTE]
> 我们没有足够的时间来查看更改的通过，在真实场景中，应该有新版本的软件包可用于在版本 2 中晋升。

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-promote_from_dev_to_QA.gif"/>
  </div>


<br/>

## <b class="hovereffect">晋升到 Production</b>

QA 团队已经完成了对 `v2` 的严格测试，并证明它对于主机队是稳定且安全的。现在是时候让我们的生产系统可以使用它了。

我们将在我们的生产环境上重复我们为 QA 所做的相同过程：

- 第一，晋升内容。
  这将使新软件包对我们的生产服务器可用。
  您已成功确保只有经过测试和批准的更新才能到达您最关键的系统。

- 第二，升级我们的 Production 系统，这里唯一的区别是我们将在 **明天 14:00** 安排升级，以便我们所有团队都做好准备并拥有一个受控的流程。


<br/>

这对 [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] 有什么重要意义？
=================================================================================

- 我们建立了一系列安全关卡，使实施我们运营战略的核心原则变得更加容易：**风险管理**。
- 引入 **Dev** 环境的单个错误补丁可以在它有机会影响创收系统之前很久就被发现并修复。
- 这个过程将打补丁和更新从一个冒险的、令人伤脑筋的事件转变为一个可预测的、常规的维护程序，这是一个可靠航空公司的基石。


<br/>

更多信息
================

* [维护窗口 (Maintenance Windows)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

* [补丁管理 (Patch Management)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)

* [内容生命周期管理 (Content Lifecycle Management)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/content-lifecycle.html)

* [SUSE Multi-Linux Manager 产品页面](https://www.suse.com/products/suse-manager/)