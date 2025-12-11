---
slug: smlm-lifecycle-management
id: 7ssvzlajbykj
type: challenge
title: ライフサイクル管理
tabs:
- id: lioekie5ityb
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 ライフサイクル管理
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

このパートでは、個々のメンテナンス作業から、変更を管理するためのフリート全体で認定されたプロセスの確立へと移行します。<b class="smlmext">SUSE Multi-Linux Manager</b> のコンテンツライフサイクル管理（Content Lifecycle Management）が、私たちの航空会社が求める構造と安全性を提供する方法を探ります。



[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] では、新しい部品がメーカーから到着した瞬間に旅客ジェット機に取り付けられることはありません。それは厳格な認定プロセスを経ます。

まず、管理されたワークショップ（**開発 - Development**）で検査およびテストされます。次に、非商用のテスト用航空機に取り付けられ、過酷な地上および飛行テスト（**品質保証 - Quality Assurance**）が行われます。考えられるすべてのチェックに合格した後でのみ、アクティブなフリート全体へのインストールが認定されます（**本番 - Production**）。



この体系的で段階的なアプローチにより、たった一つの欠陥部品が飛行機を地上に釘付けにすることを防ぎ、乗客の安全と運航の信頼性を確保します。私たちは、これとまったく同じ哲学を IT システムに適用します。ソフトウェアのアップグレードや新しいアプリケーションは「部品」であり、欠陥があればデジタル運用を停止させる可能性があります。コンテンツライフサイクル管理は、すべてのソフトウェア変更に対する公式の認定プロセスです。



## <b class="hovereffect">あなたの目標:</b>

- コンテンツライフサイクルプロジェクト（Content Lifecycle Project）を構築します。

- プロジェクトを使用して、システムのソフトウェア更新を管理および認定します。



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


ソフトウェア認定経路の構築
==============================================

この演習では、ソフトウェア更新の流れを制御するためのコンテンツライフサイクルプロジェクトを作成します。これにより、パッチが重要な本番サーバーに到達する前に徹底的にテストされることが保証されます。

<br/>

私たちの目標は、`Dev ✈ QA ✈ Prod` パイプラインを構築することです。

1.  **開発 (Development - Dev):** 最初のワークショップ。すべての新しいパッチとパッケージは最初にここに到着します。
2.  **品質保証 (Quality Assurance - QA):** テストの場。開発環境から QA 環境へ、特定のバージョンのコンテンツをプロモート（昇格）し、テストチームが検証できるようにします。
3.  **本番 (Production - Prod):** アクティブなフリート。QA で承認され、認定されたパッチセットのみが本番環境にプロモートされ、そこでライブシステムに安全に適用されます。



<br/>

## <b class="hovereffect">プロジェクトの作成</b>

- `Content Lifecycle` ✈ `Projects` に移動し、![Create Project](../assets/SMLM5.1/bottom-create_project.png) をクリックします。

- プロジェクトの詳細を入力します：

- **Project Name** (プロジェクト名):

```txt
Airtrain SLES15 SPx
```

- **Project Label** (プロジェクトラベル):

```txt
at-sles15_spx
```

- **Project Description** (プロジェクトの説明):

```txt
Certified software channel for Airtrain SLES 15 systems.
```


- ![Create](../assets/SMLM5.1/bottom-create.png) をクリックします。

次にデータを入力しましょう。`Attach/Detach Sources` をクリックします。

![Create](../assets/SMLM5.1/content_lifecycle_just_created.png)

- **New Base Channel** で <b class="sles">SLE-Product-SLES15-SP6-Pool for x86_64</b> を選択し、![Save](../assets/SMLM5.1/bottom-save.png) をクリックします。

<br/>

## <b class="hovereffect">Dev 環境の作成</b>

開発環境（Development Environment）のライフサイクルを作成します。

- `Add Environment` をクリックします。

![Create](../assets/SMLM5.1/content_lifecycle_just_created_environment_lifecycle.png)

- 以下のように入力します：
  * **Name:** <b class="highlightcopy">Development</b>
  * **Label:** <b class="highlightcopy">dev</b>

- ![Save](../assets/SMLM5.1/bottom-save.png) をクリックします。

<br/>

## <b class="hovereffect">QA 環境の作成</b>

品質保証環境（Quality Assurance Environment）のライフサイクルを作成します。

- `Add Environment` をクリックします。

- 以下のように入力します：
  * **Name:** <b class="highlightcopy">QA</b>
  * **Label:** <b class="highlightcopy">qa</b>

- ![Save](../assets/SMLM5.1/bottom-save.png) をクリックします。

<br/>

## <b class="hovereffect">Prod 環境の作成</b>

本番環境（Production Environment）のライフサイクルを作成します。

- `Add Environment` をクリックします。

- 以下のように入力します：
  * **Name:** <b class="highlightcopy">Production</b>
  * **Label:** <b class="highlightcopy">prod</b>

- ![Save](../assets/SMLM5.1/bottom-save.png) をクリックします。

<br/>

## <b class="hovereffect">ポピュレート（Populate）</b>

3つの環境がすべて整ったので、コンテンツを入力しましょう。

<b class="sles">SLES</b> はすでに安定したパッケージバージョンを提供しているため、このケースではフィルターを使用しません。

[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] のテストの頻度は現在1か月ごとなので、このビルドには現在の月である10月（October）の名前を付けます。

- ![Build](../assets/SMLM5.1/bottom-build.png) をクリックします。

- **Version Message** に次のように入力します：

```txt
October
```


- `Build` をクリックします。

> [!NOTE]
> このプロセスには数分かかる場合があります。「cloning（クローン作成中）」などのステップが表示されますが、これには多くのストレージが必要ないことを知って安心してください。クローン作成プロセスはパッケージのインデックスポイントにのみ適用され、実際のパッケージ自体には適用されません。


<br/>

## <b class="hovereffect">コンテンツのプロモート</b>

では、コンテンツを次の段階にプロモート（昇格）させましょう。

- Development と QA の間にある `Promote` ボタンをクリックします。
- **Promote version 1 into QA** というタイトルの別の画面が表示されますので、もう一度 `Promote` をクリックします。

Production（本番）に対しても同じ手順を繰り返します。


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-create_the_project.gif"/>
  </div>

<br/>

システムのアップグレード
====================

それでは、どのように機能するか試してみましょう。

これから行うこと：
- システムの一部を新しい環境に追加する。
- コンテンツの新しいバージョンを作成する。
- 新しいバージョンをプロモートし、システムを更新する。

<br/>

## <b class="hovereffect">システムの追加</b>

`Systems` ✈ `System List` ✈ `All` に移動しましょう。

- **at-ct-qa** システムをクリックします。
- `Software` ✈ `Software Channels` に移動します。
- **Custom Channels** で、**at-sles15_spx-qa-...** チャンネルのチェックボックスを選択し、![Next](../assets/SMLM5.1/bottom-next.png) をクリックします。
- ![Confirm](../assets/SMLM5.1/bottom-confirm.png) をクリックします。


`Systems` ✈ `System List` ✈ `All` に戻ります。

- 以下でフィルタリングします：

```txt
at-
```

- **-pro** で終わるすべてのシステムを選択します。
- `Systems` ✈ `System Set Manager` に移動します。
- `Channels` に移動します。
- **Custom Channels** で、**at-sles15_spx-prod-...** チャンネルのチェックボックスを選択し、![Next](../assets/SMLM5.1/bottom-next.png) をクリックします。
- 'include recommended'（推奨を含める）をクリックして、すべての推奨チャンネルをサブスクライブします：

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-next.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-add_systems.gif"/>
  </div>

<br/>

## <b class="hovereffect">新しいバージョンの作成</b>


1か月が経過し、安定したアップグレードプロセスを継続したいと考えています。
開発者チームのために、ソフトウェアチャンネルの静的で変更されないコピーを作成します。

新しいパッチが突然現れて彼らの作業を中断することはありません。

- `Content Lifecycle` ✈ `Projects` に戻り、作成したばかりのプロジェクトをクリックします。

- ![Build](../assets/SMLM5.1/bottom-build.png) をクリックします。

- **Version Message** に次のように入力します：

```txt
November
```


- `Build` をクリックします。

バージョン番号が自動的に増加したことに注目してください。

これで、開発者は SUSE が提供するライブラリやアプリケーションの新しい修正バージョンを使用して作業を行うことができます。


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-create_new_version.gif"/>
  </div>


<br/>

## <b class="hovereffect">Dev から QA へのコンテンツのプロモート</b>

開発者が承認を与えたと仮定しましょう。すべてのプリプロダクションテストを実行できるように、QA チーム用の安定バージョンを作成する時が来ました。

- Development と QA の間にある `Promote` ボタンをクリックします。
- **Promote version 2 into QA** というタイトルの別の画面が表示されますので、もう一度 `Promote` をクリックします。

それでは、QA システムに移動してアップグレードを行いましょう。

- `Systems` ✈ `System List` ✈ `All`
- **at-ct-qa** システムをクリックします。
- `Software` ✈ `Packages` ✈ `Upgrade` に移動します。
- 以下をクリックします：

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


これで、QA エンジニアは中断することなく安全にテストを実行できます。


> [!NOTE]
> 変更が反映されるのを見る十分な時間がありませんが、実際のシナリオでは、バージョン 2 でプロモートできる新しいバージョンのパッケージが利用可能であるはずです。

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-promote_from_dev_to_QA.gif"/>
  </div>


<br/>

## <b class="hovereffect">本番へのプロモート</b>

QA チームは `v2` に対する厳格なテストを完了し、メインフリートに対して安定しており安全であると認定しました。これを本番システムで利用可能にする時が来ました。

本番環境に対して、QA で行ったのと同じプロセスを繰り返します：

- まず、コンテンツをプロモートします。
  これにより、新しいパッケージが本番サーバーで利用可能になります。
  テストされ承認された更新のみが最も重要なシステムに到達できるようにすることに成功しました。

- 次に、本番システムをアップグレードします。ここでの唯一の違いは、すべてのチームが準備を整え、制御されたプロセスを持てるように、アップグレードを **明日の 14:00** にスケジュールすることです。


<br/>

[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] にとってなぜ重要なのですか？
=================================================================================

- 一連の安全ゲートを構築し、運用戦略の核心原則である **リスク管理** の実装を容易にします。
- **Dev** 環境に導入されたたった1つの悪いパッチでも、収益を生み出すシステムに影響を与えるずっと前に発見して修正できます。
- このプロセスにより、パッチ適用と更新が、リスクを伴う神経をすり減らすイベントから、信頼できる航空会社の基礎となる予測可能なルーチンメンテナンス手順へと変わります。


<br/>

詳細情報
================

* [Maintenance Windows (メンテナンスウィンドウ)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

* [Patch Management (パッチ管理)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)

* [Content Lifecycle Management (コンテンツライフサイクル管理)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/content-lifecycle.html)

* [SUSE Multi-Linux Manager Product Page (製品ページ)](https://www.suse.com/products/suse-manager/)