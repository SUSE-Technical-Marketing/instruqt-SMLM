---
slug: smlm-security
id: pyncdvbhxfka
type: challenge
title: 安全与补丁
tabs:
- id: 6tkpzlntpxzl
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 安全与补丁 (Security and patching)
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



在本实验室中，我们将处理我们最重要的责任之一：确保我们要整个数字机队的安全性。我们将探索 <b class="smlmext">SUSE Multi-Linux Manager</b> 如何让我们能够以世界级航空公司所需的速度和精度来应对安全威胁。




## <b class="hovereffect">您的目标：</b>

- 使用 OpenSCAP 对您的系统执行安全合规性审计。

- 识别受相关安全漏洞影响的系统。

- 同时对所有受影响的系统应用必要的补丁。



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




审计您的系统
==================

我们希望审计我们的生产系统以确保它们符合规范。

我们已经验证安装了以下软件包：

- openscap-utils
- scap-security-guide


选择生产组

- 让我们前往 `Systems` ✈ `System Groups`
- 找到组 **prod** 并点击 `Use in SSM`
![Next](../assets/SMLM5.1/prod_group_selection.png)

我们将被引导至 **System Set Manager Overview**（系统集管理器概览）页面，正如我们之前看到的，从这里我们可以一次对多个系统应用操作。

- 前往 `Audit` 标签页
- 在 `OpenSCAP` 下，使用以下详细信息完成表单，其余保留默认值：
  - **Command-line Arguments (命令行参数):** <b class="highlightcopy">--profile xccdf_org.ssgproject.content_profile_stig</b>
  - **Path to XCCDF document (XCCDF 文档路径):** <b class="highlightcopy">/usr/share/xml/scap/ssg/content/ssg-sle15-ds.xml</b>
- 按下


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">
</p>
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-Schedule.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p>



这需要几分钟时间。


要查看结果，请前往 `Audit` ✈ `OpenSCAP` ✈ `All Scans`

![OpenSCAP Results](../assets/SMLM5.1/openscap_results.png)

如果我们点击其中一个结果，我们可以看到更详细的细分。

- 通过点击 **report.html**，您可以查看由 OpenSCAP 生成的更美观的报告版本。

![Detailed OpenSCAP Results](../assets/SMLM5.1/openscap_results_detailed.png)


不用担心报告的问题。


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-audit_your_system.gif"/>
  </div>

<br/>



识别受漏洞影响的系统
============================================

我们想看看哪些系统受到漏洞的影响。

- 现在，让我们导航至 `Patches` ✈ `Patch List` ✈ `Relevant`

  在这里我们可以看到我们系统可用的所有相关补丁的列表，让我们看看 **Security Patches**（安全补丁）。

- 通过点击 **Advisory**（公告）名称，您可以查看详细页面，显示它影响哪些软件包和系统以及其他详细信息。

- 在列表的右侧，**CVEs** 列提供了指向官方漏洞报告的直接链接。

  也可以创建我们自己的补丁，但在本课程中我们不会涵盖这一点，有关更多信息，请咨询课程末尾的链接。



## <b class="hovereffect">修补受影响的系统</b>

修补我们的系统只需遵循以下步骤：

- 前往 `Systems` ✈ `System Set Manager`
- 导航至 `Patches` 标签页 ✈ 在下拉列表中选择 **Security Advisory**，然后点击 `Show`

![Select Security Advisory](../assets/SMLM5.1/show_only_security_advisories.png)

- 点击 `Select All` ✈ `Apply Patches` ✈ ![Confirm](../assets/SMLM5.1/bottom-confirm.png)


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-indentify_vulnerabilities.gif"/>
  </div>

<br/>


为什么这对 [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] 很重要？
=================================================================================


- 通过能够快速行动，我们正在减少暴露窗口。当发现新漏洞时，我们与试图利用它的恶意行为者之间就开始了一场竞赛。复杂的手动补丁过程会让我们的关键系统暴露太久。

- <b class="smlmext">SUSE Multi-Linux Manager</b> 为我们整个机队的安全态势提供了一个单一、统一的视图，并允许我们通过一致、可靠的流程来修复威胁。

- 能够轻松检查我们的系统对不同安全框架的合规性，使我们能够更快地实施纠正措施并遵守严格的行业法规。


更多信息
================


* [审计 (Auditing)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/auditing.html)
* [SUSE 安全 (SUSE Security)](https://www.suse.com/support/security/)
* [使用 OpenSCAP 的系统安全](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/openscap.html)
* [管理补丁 (Manage Patches)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)