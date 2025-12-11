---
slug: smlm-security
id: lzmekz3sel4k
type: challenge
title: セキュリティとパッチ適用
tabs:
- id: vzstyykx9pbx
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 セキュリティとパッチ適用
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



このラボでは、私たちが持つ最も重要な責任の一つである、デジタルフリート全体のセキュリティ確保に取り組みます。<b class="smlmext">SUSE Multi-Linux Manager</b> が、世界クラスの航空会社に求められるスピードと正確さでセキュリティの脅威に対応できるようにする方法を探ります。




## <b class="hovereffect">あなたの目標:</b>

- OpenSCAP を使用してシステムのセキュリティコンプライアンス監査を実行します。

- 関連するセキュリティの脆弱性の影響を受けるシステムを特定します。

- 影響を受けるすべてのシステムに、必要なパッチを同時に適用します。



ラボの詳細 (Lab details)
===========

ユーザー名 (Username):
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```

パスワード (Password):
```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

<b class="smlm">SMLM</b> URL: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>




システムの監査
==================

本番システムがコンプライアンスに準拠していることを確認するために監査を行いたいと考えています。

以下のパッケージがインストールされていることは確認済みです：

- openscap-utils
- scap-security-guide


本番グループの選択

- `Systems` ✈ `System Groups` に移動しましょう。
- グループ **prod** を見つけて、`Use in SSM` をクリックします。
![Next](../assets/SMLM5.1/prod_group_selection.png)

**System Set Manager Overview** ページにリダイレクトされます。以前見たように、ここから複数のシステムに対して一度にアクションを適用できます。

- `Audit` タブに移動します。
- `OpenSCAP` の下で、以下の詳細を入力してフォームを完成させます。残りはデフォルトのままにします：
  - **Command-line Arguments (コマンドライン引数):** <b class="highlightcopy">--profile xccdf_org.ssgproject.content_profile_stig</b>
  - **Path to XCCDF document (XCCDF ドキュメントへのパス):** <b class="highlightcopy">/usr/share/xml/scap/ssg/content/ssg-sle15-ds.xml</b>
- 以下を押します：


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">
</p>
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-Schedule.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p>



これには数分かかります。


結果を見るには、`Audit` ✈ `OpenSCAP` ✈ `All Scans` に移動します。

![OpenSCAP Results](../assets/SMLM5.1/openscap_results.png)

これらの結果のいずれかをクリックすると、より詳細な内訳を確認できます。

- **report.html** をクリックすると、OpenSCAP によって生成されたレポートのより見やすいバージョンを表示できます。

![Detailed OpenSCAP Results](../assets/SMLM5.1/openscap_results_detailed.png)


報告された問題については心配しないでください。


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-audit_your_system.gif"/>
  </div>

<br/>



脆弱性の影響を受けるシステムの特定
============================================

どのシステムが脆弱性の影響を受けているかを確認したいと考えています。

- では、`Patches` ✈ `Patch List` ✈ `Relevant` に移動しましょう。

  ここでは、システムで利用可能なすべての関連パッチのリストを確認できます。**Security Patches**（セキュリティパッチ）を見てみましょう。

- **Advisory**（アドバイザリ）名をクリックすると、それが影響を与えるパッケージやシステムなどの詳細を示すページを表示できます。

- リストの右側にある **CVEs** 列には、公式の脆弱性レポートへの直接リンクがあります。

  独自のパッチを作成することも可能ですが、このトラックでは扱いません。詳細については、トラックの最後にあるリンクを参照してください。



## <b class="hovereffect">影響を受けるシステムへのパッチ適用</b>

システムへのパッチ適用は、以下の手順に従うだけで簡単です：

- `Systems` ✈ `System Set Manager` に移動します。
- `Patches` タブに移動し ✈ ドロップダウンリストで **Security Advisory** を選択して、`Show` をクリックします。

![Select Security Advisory](../assets/SMLM5.1/show_only_security_advisories.png)

- `Select All` をクリック ✈ `Apply Patches` ✈ ![Confirm](../assets/SMLM5.1/bottom-confirm.png)


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-indentify_vulnerabilities.gif"/>
  </div>

<br/>


[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] にとってなぜ重要なのですか？
=================================================================================


- 迅速に行動できることで、リスクにさらされる期間（ウィンドウ）を短縮できます。新しい脆弱性が発見されると、私たちとそれを悪用しようとする悪意ある攻撃者との間で競争が始まります。複雑で手動のパッチ適用プロセスでは、重要なシステムがあまりにも長く危険にさらされたままになります。

- <b class="smlmext">SUSE Multi-Linux Manager</b> は、フリート全体のセキュリティ状況に関する単一の統一されたビューを提供し、一貫した信頼性の高いプロセスで脅威を修復することを可能にします。

- さまざまなセキュリティフレームワークに対するシステムのコンプライアンスを簡単に確認できるため、是正措置をより迅速に実装し、厳しい業界規制を遵守することができます。


詳細情報
================


* [監査 (Auditing)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/auditing.html)
* [SUSE Security](https://www.suse.com/support/security/)
* [OpenSCAP によるシステムセキュリティ](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/openscap.html)
* [パッチの管理 (Manage Patches)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)