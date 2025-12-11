---
slug: smlms-intro
id: pea2nqarspdv
type: challenge
title: SUSE Multi-Linux Hands-on Workshop へようこそ！
teaser: SUSE Multi-Linux Hands-on Workshop へようこそ！このセクションでは、 ワークショップとその主要コンポーネントについて紹介します。
notes:
- type: text
  contents: |
    # SUSE Multi-Linux Hands-on Workshop へようこそ！
    ラボ環境をセットアップしています。少々お待ちください。
    <img class="logos" src="../assets/logos/suse_logo.svg"/>
tabs:
- id: tehbx0ypuety
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: ""
enhanced_loading: null
---

<b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">SUSE</b> Multi-Linux Hands-on Workshop へようこそ
==================================================================

<link  rel="stylesheet" href="https://raw.githubusercontent.com/SUSE-Technical-Marketing/lab-setup/refs/heads/develop/web/css/instruqt.css" type="text/css" crossorigin="anonymous" fetchpriority="high" />

<style type="text/css">

  @import url("https://raw.githubusercontent.com/SUSE-Technical-Marketing/lab-setup/refs/heads/develop/web/css/instruqt.css");
  @import "https://raw.githubusercontent.com/SUSE-Technical-Marketing/lab-setup/refs/heads/develop/web/css/instruqt.css";

  * {
    font-family: suse;
    src: url('https://fonts.google.com/specimen/SUSE');
/*    background-color: #30ba78; */
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
  .highlightcopy {
    color: white;
    font-weight: bold;
    padding: 0 10px;
  }


</style>



<img class="logos" alt="Welcome!" src="../assets/logos/01-welcome.jpeg"/>

このワークショップでは、<b class="smlmext">SUSE Multi-Linux Manager</b> (<b class="smlm">SMLM</b>) が実現する魔法の一部を体験していただきます。これは、統一されたインターフェースから複数の Linux ディストリビューションを大規模に管理するための <b class="suse">SUSE</b> のソリューションです。また、Linux システム向けのプロフェッショナルで信頼性の高いサポートソリューションである <b class="smlsext">SUSE Multi-Linux Support</b> (<b class="smls">SMLS</b>) を使用して、レガシーな本番サーバーのサポートを維持する方法についても学びます。

&emsp;&emsp; あなたは、すべての航空機に Linux サーバーを搭載している航空会社 <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b> の **エンジニア** の役割を担います。

&emsp;&emsp; 航空機のあらゆるコンポーネントと同様に、それらのサーバーが地上のデータセンターにある場合でも、雲の上を飛んでいる場合でも、安定性と信頼性を維持することが重要です ☁ ☁ ☁


&emsp;&emsp; 一部の機体モデルでは、異なる種類の Linux や異なる CPU アーキテクチャが必要になる場合があります。これは <b class="smlm">SMLM</b> にとって問題ではありません。容易な標準化と管理を諦めることなく、ニーズに最適な Linux ディストリビューションと CPU アーキテクチャを自由に選択できます。


&emsp;&emsp; Linux ランドスケープの管理を担当するエンジニアとして、システム管理を容易にして自動化し、発生する可能性のある例外的な問題を解決するために <b class="smlm">SMLM</b> と <b class="smls">SMLS</b> が提供するいくつかのソリューションを体験します。


さまざまな課題を通じて、以下のツールを利用できます：

 ✈ **SUSE Multi-Linux Manager**:
   Linux スタック全体を管理するための単一の管理画面（Single Pane of Glass）。

 ✈ **Centos 7**:
   一部の古い航空機や地上システムでまだ使用されているレガシーディストリビューション。

 ✈ **Ubuntu 24**: グラフィックデザインアプリケーションを実行するためにマーケティング部門が必要とする特定の Linux ディストリビューション。

 ✈ **SLES 15**: 最も重要なシステムのバックボーンを形成する、信頼性が高く安定したセキュアな <b class="suse">SUSE</b> の Linux ディストリビューション。


## <b class="smlmext hovereffect">SUSE Multi-Linux Manager</b>

これは、ソフトウェアデファインドインフラストラクチャのためのクラス最高のオープンソースインフラストラクチャ管理ソリューションです。

&emsp;&emsp; <b class="smlmext">SUSE Multi-Linux Manager</b> は、企業の DevOps および IT Operations チームが複雑さを軽減し、IT 資産の制御を取り戻すのを支援するように設計されています。これは、さまざまなハードウェアアーキテクチャ、ハイパーバイザー、およびコンテナ、IoT、クラウドプラットフォームにわたる Linux システムを管理するための、単一かつ非常に強力なツールです。

&emsp;&emsp; Linux サーバーと IoT デバイスのプロビジョニング、パッチ適用、および構成を自動化し、より迅速で一貫性のある反復可能なサーバー展開を実現することで、運用の最適化とコスト削減を支援します。また、開発、テスト、本番環境全体にわたるシステム、VM、コンテナの監視、追跡、監査、レポートを自動化することで、内部セキュリティポリシーや外部規制へのコンプライアンスを確保できます。


## <b class="smlsext hovereffect">SUSE Multi-Linux Support</b>


これは、既存の Red Hat Enterprise Linux (RHEL)、CentOS、<b class="liberty">SUSE Liberty Linux</b>、および <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>) など、さまざまな Linux ディストリビューションに対する技術支援とメンテナンスを提供する包括的なサービスです（提供内容によります）。

&emsp;&emsp; これにより、組織は単一のサポートフレームワークの下で、混在する Linux 環境を効率的に管理できます。
購入したパッケージによっては、<b class="smlsext">SUSE Multi-Linux Support</b> に、これらのディストリビューションを管理するためのマルチ Linux 管理ツールである <b class="smlmext">SUSE Multi-Linux Manager</b> が含まれる場合もあります。



 🌅 Instruqt UI の探索
=======================
最初のタスクを始める前に、Instruqt UI を少し見てみましょう。

+ 画面の **右側** には、これらの手順とナビゲーションコントロールが表示されます。

+ **左側** では、ラボ環境を構成するさまざまなマシンやサービスにアクセスできます。

Instruqt UI 内では、左側のパネルの上部にあるタブをクリックすることで、[button label="SMLM UI" variant="success"](tab-0) と利用可能な [button label="terminals" variant="success"](tab-1) を切り替えることができます。


> [!NOTE]
> Web UI では自動リロードは行われません。更新を確認するには、Instruqt の内部 Web ブラウザをリロードする必要がある場合があります。


🛫 <b class="smlmext">SUSE Multi-Linux Manager</b> へのログイン 🛫
========================================
環境に慣れていきましょう。

- [button label="SMLM UI" variant="success"](tab-0) からラボ内の <b class="smlmext">SUSE Multi-Linux Manager</b> を開きます。


- 以下の認証情報でログインします：

  - ユーザー名:
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```
  - パスワード:

```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

すべてがうまくいけば、`[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]` ユーザーとしてログインした <b class="smlmext">SUSE Multi-Linux Manager</b> UI の **Overview** ページが表示されるはずです。

> [!NOTE]
> ブラウザから直接 <b class="smlmext">SUSE Multi-Linux Manager</b> UI にアクセスしたい場合は、以下からも可能です：

<b class="smlm">SMLM</b> URL: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>


> [!NOTE]
> ページが正しく読み込まれない場合は、ラボ環境の起動が完了した後にブラウザのタブを更新する必要があるかもしれません。




🗺  <b class="smlmext">SUSE Multi-Linux Manager</b> の探索 🗺
======================================

離陸する前に、コントロールに慣れておきましょう。これは徹底的なツアーではなく、ワークショップ全体で使用する主要な機器の簡単な概要です。好奇心を持って探索することをお勧めします。


始めましょう。


- **Systems メニュー** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_systems.png"/>

  左側のパネルで、`systems` をクリックします。これはフリートの概要であり、登録されているすべてのサーバーが表示されます。リストは今は小さいですが、演習を完了するにつれて大きくなります。

   - **System Lists**

     このセクションでは、便利で事前にフィルタリングされたビューを提供します。たとえば、`Out of Date` リストは、更新が必要なサーバーを即座に表示するため、手動で検索する手間が省けます。</p>

  <br/>

  - **System Groups**

    フリートを論理的に整理するために、`System Groups` を使用します。任意の基準に基づいて分類できます。そうすることで、アクションを適用したりポリシーを定義したりする際の時間を節約できます。一度作成すると、たとえば `activation keys` を使用して、システムを 1 つまたは複数のグループに自動的にアタッチできます。


    `+ Create Group` をクリックして、今すぐ作成してみてください。

  <br/>

  - **バッチ操作**

    `System Set Manager` は、複数のシステムに対して同時にアクションを実行するための強力な方法を提供します。


    変更を 1 つずつ適用するのではなく、System List から個別に、または既存の System Groups を活用してシステムのコレクションを選択し、単一の操作ですべてのシステムに対してタスクを実行できます。

  <br/>

  - **Provisioning**

    <b class="smlmext">SUSE Multi-Linux Manager</b> は、新しいシステムのプロビジョニングと既存のシステムの再プロビジョニングのための包括的なツールを提供します。この機能は、システム展開のための標準化された反復可能なプロセスを確立するのに役立ちます。


    たとえば、`Autoinstallation` セクション内では、ディストリビューションと Kickstart/AutoYaST プロファイルを定義できます。これにより、システムをどのように展開するか、どのソフトウェアをインストールするか、ストレージ容量をどのように配分するかなどを指定できます。


    これらすべての簡単に設定できる自動化メカニズムは、Salt や Ansible のような複雑ですがより強力な自動化ソリューションと組み合わせることができ、各課題に最適なソリューションを選択する自由を維持できます。


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_systems.gif"/>
  </div>

<br/>



- **Patches メニュー** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_patches.png"/>

  - **Patching**

    IT における最も一般的なタスクの 1 つは、システムを最新の状態に保ち、時には急いでセキュリティパッチを適用することです！
    SMLM を使用すると、タイプ別に分類された **関連する** パッチのリストを簡単に確認でき、影響を受けるすべてのシステムやパッケージなど、知る必要のあるすべての情報が提供されます。

    ベンダー提供のパッチ以外にも、独自のパッチを作成することもできます。後ほど、フリート全体でのパッチ適用と定期的な更新を管理するために利用できるさまざまなオプションについて説明します。

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_patches.gif"/>
  </div>

<br/>
- **Software channels** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_software.png"/>

  `Channel List` では、利用可能なすべてのパッケージチャンネル/リポジトリ/ストリームを確認できます。また、ソフトウェアを整理したり独自のパッケージをアップロードしたりするために、新しいソフトウェアチャンネルを作成することもできます。

  現在表示されているすべてのチャンネルは、SMLM によって公式ソースから取得されており、簡単に同期を維持できます。

  `Package Search` では、特定のパッケージを検索し、その内容やメタデータを検査できます。

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_software.gif"/>
  </div>

<br/>

- **Configuration** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_configuration.png"/>

  登録時またはその後に、特定の構成をシステムに管理および適用することも可能です。そのためには `Configuration` セクションを検査できます。

  SMLM は、システム間でリビジョンを管理し、構成ファイルを展開および比較するための簡単な方法を提供します。そして、すべてを構成チャンネルに簡単にグループ化できます。

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_configuration.gif"/>
  </div>

<br/>

- **Scheduling** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_schedule.png"/>

  `Schedule` では、スケジュールされたアクションを監視および管理し、特定のメンテナンスウィンドウを定義できます。これは、多くのシステムを管理する際に、定期的な操作を自動化したり、カナリア展開を実行したりする場合に特に役立ちます。これについては、ワークショップの後半で実際に確認します。

<br/>
<br/>

SUSE Multi-Linux Manager はシステムを管理するための多くの可能性を提供します。このワークショップですべてを網羅することはできませんが、いつものように、自由に質問して探索してください。

> [!NOTE]
> ユーザーには完全な管理者権限があるため、演習を完了した後にのみ変更を加えることをお勧めします。