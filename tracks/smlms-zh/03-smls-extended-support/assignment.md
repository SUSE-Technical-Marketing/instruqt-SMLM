---
slug: smls-extended-support
id: o3zc1mlliis2
type: challenge
title: 遗留系统的扩展支持
tabs:
- id: e2idstvfsyjz
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: 3rh5o96xe3vd
  title: CentOS 7 QA
  type: terminal
  hostname: centos7
- id: 8oxtkwd6t6vb
  title: CentOS 7 Prod
  type: terminal
  hostname: zzcentos7
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 遗留系统的扩展支持
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

# 延长我们遗留机队的寿命

在任何航空公司，您都有已经为您服务多年的老旧、可靠的飞机，但您还没有替代品。对我们来说，该遗留机队的一部分是我们的 CentOS 7 系统。它们很稳定，但已达到生命周期结束 (end-of-life)，这意味着它们不再从原始制造商处收到关键的安全更新。对于一家航空公司来说，在没有支持的情况下飞行是我们根本无法承担的风险。

传统的解决方案是对每一个系统进行全面、昂贵的更换。
但是，如果我们能够执行寿命延长升级，在尽可能减少中断的情况下就地进行现代化改造呢？这正是这一挑战的任务。我们将利用 <b class="smlmext">SUSE Multi-Linux Manager</b> 与 <b class="smlsext">SUSE Multi-Linux Support</b> 的力量，安全地过渡这些系统，并使其保持服务状态，直到我们可以用更现代的操作系统替换它们。



## <b class="hovereffect">我们的飞行计划：</b>

- 检查当前运行 Centos 7 的遗留系统

- 接入 (Onboard) QA 系统并应用任何可用的补丁

- 识别并应用更新（如果有）。

- 使用 liberate 公式 (formula) 解放 (Liberate) 系统。

- 观察两个系统之间发生了什么变化

- 识别这是否是一次迁移。

<br/>

## <b class="hovereffect">我们的飞机</b>

- CentOS 7 QA ✈ 我们的测试和开发服务器。

- CentOS 7 Prod ✈ 我们已经在 <b class="smlm">SMLM</b> 中注册的生产服务器

<br/><br/>


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



接入 Centos 7 QA (Onboarding Centos 7 QA)
======================



## <b class="hovereffect">检查当前的遗留系统</b>

从标签页 [button label="Centos 7 QA" variant="success"](tab-1) 访问系统终端

检查系统的当前版本：

```bash,run
rpm -qi centos-release centos-logos
```


现在运行以下命令将系统注册到 <b class="smlm">SMLM</b> 中：


```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | SMLM_DNS="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-liberty7ltss PROFILENAME='airco-dh4a-qa' bash ; echo "Let's wait 2 minutes for all the background processes to finish"; sleep 120
```


这与我们在上一个实验室中用于接入 Ubuntu 的命令类似，变化的是：

- **Activation key** (激活密钥): 是对默认情况下将应用于系统的设置的引用，在这种情况下，它的创建仅为了指示系统将注册到哪些软件频道。

- **Profile name** (配置文件名称): 如果我们不指定，它将使用主机名 (hostname)，但在这种情况下，我们希望它有一个更有意义的名称，使用我们与 Centos 7 Prod 相同的命名约定。


**可选：** 如果我们很好奇，想看看当我们升级并执行 Liberate 公式时会发生什么，我们可以在两个系统上运行以下命令 ( [button label="Centos 7 QA" variant="success"](tab-1) 和 [button label="Centos 7 Prod" variant="success"](tab-2) )：


```bash,run
journalctl -f
```

并查看终端中出现的日志。


<br/><br/>


## <b class="hovereffect">从 <b class="liberty">Liberty</b> 存储库识别并应用更新</b>

这些 Centos 7 系统带有上游提供的最新软件包，我们希望确保新错误得到修复，并且在出现问题时有友好的支持人员帮助我们。现在我们已经在注册过程中将 Centos 7 系统订阅到了 SUSE 提供的软件存储库，所以让我们修补它们：



现在让我们切换到 [button label="SMLM UI" variant="success"](tab-0) 标签页


- 前往左侧菜单中的 `Systems` ✈ `System List`。

- 找到您的主机 **airco-dh4a-qa** 并点击它。

- 选择 `Software` ✈ `Packages`

- 点击 `Update Packages List`，这大约需要一分钟完成

- 选择 `Software` ✈ `Patches`

- 您将看到可用补丁的列表。

点击 `Select All`，然后点击右上角的 `Apply Patches`，最后点击 `Confirm`。<b class="smlmext">SUSE Multi-Linux Manager</b> 现在将安排并在 CentOS 系统上执行升级程序。


> [!NOTE]
> 在您可以看到可应用于系统的补丁列表之前，获取软件包列表可能需要几分钟。


由于这可能需要一段时间，让我们看看幕后发生了什么。
前往 `Events` 标签页，然后前往 `History`，您应该看到自系统注册到 <b class="smlm">SMLM</b> 以来发生的事件列表，在前几行中我们应该能找到一个包含类似于 *Combined Patch* 内容的事件。


如果我们点击它，我们可以看到所有详细信息，请随意查看，否则请等到图标变绿：

![Successfully patched](../assets/SMLM5.1/successfully_updated_system.png)

我们刚刚应用了修复现有软件包错误的补丁，这些打过补丁的软件包直接来自 SUSE，这不是迁移。

<br/>

让我们将其与我们尚未更新的生产系统进行比较。

请前往 `Software` ✈ `Packages` ✈ `Profiles`

选择系统 `airco-dh4a-prod`，即生产版本，然后点击：

![Compare](../assets/SMLM5.1/bottom-compare.png)


我们可以看到大多数软件包版本没有改变，仍然是相同的版本 ( **X.X.X**-xyz ) 但应用了补丁 ( X.X.X-**xyz** )。

在我们进入下一节之前，让我们创建一个存储的配置文件 (stored profile)，这将帮助我们在下一节应用 liberate 公式后更清楚地看到差异。


请前往 `Software` ✈ `Packages` ✈ `Profile` 并点击 `Create System Profile`。您可以将其命名为：

```txt
before_liberation
```


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-identify_and_apply_updates.gif"/>
  </div>


<br/><br/>


解放 (Liberate) 系统（可选）
==============================

这是一个 **可选** 步骤，获得支持不需要此步骤。

现在让我们解放 (liberate) 系统：

- 前往 `Formulas` 标签页，搜索 **Liberate**，找到后选中它并在右上角点击 `Save`。

您会在屏幕顶部看到一条蓝色消息，如果看不到请向上滚动：

![Formula saved](../assets/SMLM5.1/formula_saved.png)


点击显示 `Highstate` 的地方，您将被定向到另一个标签页 (`States` ✈ `Highstate`)。

您可以在底部的摘要中看到 liberate 公式已列出。

要开始解放过程，请点击：

![Formula saved](../assets/SMLM5.1/bottom-apply_highstates.png)

这将需要一些时间，请检查 `Events` -> `History`，您应该看到一个名为 **Apply highstate scheduled** 的事件

让我们等几分钟让它完成，在此期间您可以通过查看终端 [button label="Centos 7 QA" variant="success"](tab-1) 来观察正在发生的事情。


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-liberate.gif"/>
  </div>

<br/><br/>

## <b class="hovereffect">观察发生了什么变化</b>


完成后，让我们再次比较系统以查看差异，如果我们还不在那里，让我们点击系统名称 `airco-dh4a-qa`。

然后前往 `Software` ✈ `Packages` ✈ `Profile`

在 **Compare to Stored Profile** 下点击： ![Compare](../assets/SMLM5.1/bottom-compare.png)

我们可以看到唯一改变的是以下软件包：

- **centos-logos**，被 **sles_es-logos** 替换

- **centos-release**，被 **sles_es-release-server** 替换

其余部分保持不变，但现在您拥有由 <b class="suse">SUSE</b> 为 <b class="liberty">Liberty Linux</b> 提供的所有支持、升级和补丁。

这同样适用于 CentOS 和 RHEL 的更现代版本，您可以将它们转换为 <b class="liberty">Liberty</b> 并由 <b class="suse">SUSE</b> 提供支持，而无需对实际软件和库进行任何更改。



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-what_changed.gif"/>
  </div>

<br/>



解放 (Liberate) 生产服务器（可选）
=========================================

我们已经看到了如何在 QA 中修补和解放 (Liberate) 我们旧的 Centos 7 服务器，现在是时候对生产系统做同样的事情了，但这次我们将以不同的顺序进行。

- 首先，我们将应用 **Liberate** 公式

  让我们前往我们的生产服务器 `airco-dh4a-prod` 并进行 `Create System Profile`

  之后，让我们像对 QA 系统所做的那样应用 **Liberate** 公式。

- 完成后，让我们将系统与我们刚刚创建的配置文件进行比较，正如我们所见，唯一的变化是 **centos-logos** 和 **centos-release** 软件包，其余部分完全保持不变。


这是一次迁移吗？
==================

迁移涉及构建一个全新的服务器，从头开始重新安装所有应用程序，并小心地转移数据，这是一个耗时、昂贵且充满风险的过程。

我们要做的要优雅得多。我们执行了就地升级 (in-place upgrade)。

服务器的身份、主机名、应用程序和用户数据完全未受影响。我们只是更改了其用于更新的底层来源，那些生命周期结束的组件现在是接收补丁的完全受支持的组件。

我们成功延长了系统的寿命，使其重新符合安全规范，并且在没有完全迁移造成的中断的情况下完成了所有这些工作。这就是让 [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] 飞得更高的效率。




为什么这对 [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] 很重要？
=================================================================================

- 它允许 [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] 保持其运行的系统得到支持，给予他们根据业务需求而不是供应商需求进行迁移的时间。

- 它通过提供扩展支持来减轻拥有不受支持系统所带来的风险。这种方法避免了立即迁移的需要，一切照常运行，但现在有一组专家可以接听您的电话。

- 它让您可以自由更换支持提供商，而无需经历漫长的迁移，并允许您大规模 (at scale) 地进行此操作。



更多信息
================

- [Registering RHEL 7 or CentOS Linux 7 with SUSE Manager](https://documentation.suse.com/liberty/7/html/suma-quickstart/art-suma-quickstart.html)
- [Running OpenSCAP compliance scans for SUSE Multi-Linux Support 7](https://documentation.suse.com/liberty/7/html/compliance-scans/art-compliance-scans.html)
- [Registering CentOS Linux 7 with the SUSE Customer Center](https://documentation.suse.com/liberty/7/html/quickstart-scc/art-quickstart-scc.html)
- [SUSE Multi-Linux Support 9](https://documentation.suse.com/liberty/9/)