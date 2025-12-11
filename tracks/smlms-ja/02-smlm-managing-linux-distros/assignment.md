---
slug: smlm-managing-linux-distros
id: tvnwvtnsfyrt
type: challenge
title: 異なる Linux ディストリビューションの管理
tabs:
- id: 9umuoqsfwrfi
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: mugqszey2ndx
  title: Ubuntu 2404 LTS
  type: terminal
  hostname: ubuntu2404lts
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 異なる Linux ディストリビューションの管理
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

ここ [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] では、<b class="smlmext">SUSE Multi-Linux Manager</b> が、多様な Linux ディストリビューションとアーキテクチャのフリートを単一の管理画面（Single Pane of Glass）から管理するための鍵となっています。これにより、エンジニアとしての仕事を複雑にしていた余分なカスタマイズを回避でき、その結果、システムポリシーの維持と実装に必要なコストと時間を削減できました。

このツールを使用することで、単一のベンダー、アーキテクチャ、または自動化プラットフォームにロックインされることはありません。環境に必要なものを自由に選択し、それらすべてを同じ方法で管理できます。フリート内の航空機の種類ごとに、独自の言語と手順を持つ異なる航空管制塔が必要だとしたらと想像してみてください。運用の複雑さは管理不能になり、コストは法外なものになるでしょう。

特定の航空機モデルが特定のルートに適していることは誰もが知っています。30分のフライトにジャンボジェットを飛ばすのは費用対効果が高くありません。同じことが Linux ディストリビューションにも当てはまります。SUSE 独自のディストリビューションは優れていますが、一部のアプリケーションには特定の要件があります。<b class="smlm">SMLM</b> は、私たちが決してロックインされず、常にそのタスクに最適なソリューションを統合できることを保証します。


## <b class="hovereffect">あなたの目標:</b>

- マーケティングチームが必要とする専用システムである Ubuntu 24.04 LTS システムをオンボード（登録）します。

- この新しい、異なるシステムを、他のフリートと同じツールとパッチ適用手順を使用してどのように管理するかを実演します。



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


Ubuntu のオンボード
=================

マーケティング部門から新しいサービスリクエストが届きました。彼らのグラフィックデザイナーは、Ubuntu でのみサポートされている特定のクリエイティブスイートに依存しています。私たちは彼らのシステムをオンボードし、他のシステムと同様に、セキュリティおよびコンプライアンス基準を満たしていることを管理および保証できるようにします。

始めましょう。
<br/>

- [button label="Ubuntu 2404 LTS" variant="success"](tab-1) タブからシステムターミナルにアクセスします。

  変更を加える前に、パッケージの取得元を確認しましょう：

```bash,run
grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```

このワークステーションは、パブリックな Ubuntu リポジトリから直接ソフトウェアを取得しています。これには2つの問題があります。第一に、適用されるパッチを制御できないため、セキュリティ上の懸念があります。第二に、マーケティングチームが報告したように、これらのワークステーションが更新を取得するたびにオフィスのインターネット接続が遅くなり、他の従業員の不満の原因となる可能性があります。


このシステムを私たちの管理下に置きましょう。これにより、すべてのソフトウェアニーズに対して内部の <b class="smlmext">SUSE Multi-Linux Manager</b> インスタンスに接続することで、両方の問題が解決されます。

[button label="web UI" variant="success"](tab-0) を使用してこれを行います：

- `Home` ✈ `Overview` の下で、`Register Systems` をクリックしましょう。

- 以下の詳細を入力します：

  - **Host:**

  ```txt
  ubuntu2404lts
  ```

  - **User:** (ユーザー)

  ```txt
  root
  ```

  - **Password:** (パスワード)

  ```txt
  [[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
  ```

  - **Activation Key:** (アクティベーションキー)   <b class="highlightcopy">1-ubuntu2404</b>

- 残りはそのままにして、以下をクリックします。

<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-bootstrap.png"/>


- 登録プロセスが完了するまで数分かかる場合があります。[button label="terminal" variant="success"](tab-1) に移動し、何が変わったかを確認するために最初のコマンドをもう一度実行しましょう：


```bash,run
echo 'Waiting for the registration to complete' ;while [[ ! -f /etc/apt/sources.list.d/susemanager_bootstrap.sources ]] || [[ ! -f /etc/apt/sources.list.d/susemanager:channels.sources ]]; do echo -n '.'; sleep 5; done ; sleep 60; grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```


新しいファイルが表示されたことがわかります：

**/etc/apt/sources.list.d/susemanager:***

これらはシステムを <b class="smlm">SMLM</b> 内の、一元管理および制御されたチャンネルに向けています。


また、元のファイル **/etc/apt/sources.list.d/ubuntu.sources** が変更され、すべてのパブリックリポジトリが無効化されているものの、削除はされていないこともわかります。これにより、必要に応じて簡単にロールバックできます。


> [!NOTE]
> 登録のためにパスワード認証付きの SSH で root を使用することは、デモンストレーション目的のみであり、本番環境では推奨されません。


> [!NOTE]
> デフォルトでは、UI またはコマンドライン < salt-key -A -y > を介して各システムの登録を承認する必要がありますが、ここでは <b class="smlm">SMLM</b> が自動承認するように構成されています。


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-register_ubuntu.gif"/>
  </div>

<br/>



では、[button label="SMLM UI" variant="success"](tab-0) タブに切り替えましょう。


- `Systems` ✈ `System List` ✈ `All` に移動します。

  登録したばかりのシステム `Ubuntu2404lts` が表示されます。デフォルトではホスト名の下に登録されることに注意してください。

  それをクリックすると、直接 `Details` - `Overview` に移動し、他の情報と共に以下を確認できます：

  - システムステータス。
  - ホスト名、IP アドレス、仮想化の種類、使用されているカーネル、インストールされている製品などのすべての情報。
  - サブスクライブしているチャンネル。

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_overview.gif"/>
  </div>


<br/>

複数の Linux ディストリビューションの管理
=====================================


前述のように、<b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b> では、異なる飛行機モデルや会社を使用するように、異なる Linux ディストリビューションを使用しています。これは、それぞれのニーズに最も適した製品を使用することで、競争の一歩先を行くのに役立ちます。

<b class="smlmext">SUSE Multi-Linux Manager</b> を使用すると、同じインターフェースとメカニズムを使用して、同じ手順、同じスケジュールなどでそれらすべてを管理できます。

以下では、システムがどの OS を実行しているかに関係なく、同じプロセスに従って、不要なカスタマイズを作成することなく、システムでさまざまなタスクを実行する方法を探ります。


## <b class="hovereffect">追加情報の追加</b>


登録したばかりのシステムを続けましょう。いくつかの設定と情報を追加します：

- `Properties` をクリックしましょう。ここでシステムに関する追加情報を追加し、いくつかの設定を変更します。


  - パッチの自動適用を有効にする (Enable Automatic application of patches):

  <img style='vertical-align: middle; height: 60%; width: 60%; object-fit: contain' src="../assets/SMLM5.1/option-auto_patch_update-enabled.png"/>

    これにより、関連するパッチがある場合にシステムに自動的にパッチが適用されます。



  - システムに以下の詳細を追加します：


| フィールド | 内容                                                  |
| ---: | :-----                                                    |
| **Description** | <b class="highlightcopy">Multimedia workstation for graphics designers.</b> |
| **Facility Address** | <b class="highlightcopy">Candy eye street, 1</b> |
| **City** | <b class="highlightcopy">Aeolia</b> |
| **Building** | <b class="highlightcopy">Belem Tower 4</b> |
| **Room** | <b class="highlightcopy">Sierra nevada</b> |


<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-Update_Properties.png"/>



- どのハードウェアで実行されているか見てみましょう：

  - `Details` ✈ `Hardware` をクリックします。


<br/>

> [!NOTE]
> これらすべては API を介して自動化できます。

<br/>

次に、カスタムキーを使用してシステムに追加情報を追加します。この情報は、後で自動化スクリプトで簡単に使用できます。


- `Details` ✈ `Custom Info` をクリックします。

<img style='vertical-align: top; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Create_Value.png"/>

- `application` をクリックし、**value** (値) を以下のように入力します：

```text
Logo Wings designer pro
```

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Update_Key.png"/>


<br/>

> [!NOTE]
> カスタムキー **application** はすでに作成されています。独自のキーを作成したい場合は、`Systems` ✈ `Custom System Info` ✈ `Create key` に移動するだけで簡単です。

<br/><br/>

Systems リストに戻りましょう。

`Systems` ✈ `System List` ✈ `All`


いずれかのシステムをクリックして、`Details` ✈ `Custom Info` に移動します。

すでに各システムに値を入力しています。

<br/>

次に `Details` ✈ `Overview` に移動し、**Installed Products** と **Subscribed Channels** に注目してください。これらは異なるオペレーティングシステムを実行しているため、Ubuntu システムのものとは異なります。



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_properties.gif"/>
  </div>

<br/>


## <b class="hovereffect">複数のシステムでコマンドを一度に実行する</b>


持っているすべてのシステムに対して何かを行いましょう。`Systems` ✈ `System List` ✈ `All` に戻り、すべて選択します：

<img style='vertical-align: middle; margin: 2px; height: 50%; width: 50%; object-fit: contain' src="../assets/SMLM5.1/select_all_systems.png"/>

**Base Channel** 列に注目してください。3つの異なる OS を実行しているシステムがあります。

<br/>

操作したいすべてのシステムを選択したので、グループアクションを実行しに行きましょう：

`Systems` ✈ `System Set Manager`

それらすべてに対してコマンドを実行しましょう。そのために以下に移動します：

`Misc` ✈ `Remote Command`

次に、以下の詳細を入力し、残りはデフォルト値のままにします：


Script:

```bash,run
cat /etc/os-release
```

スケジュール (Schedule) を変更しないでください。できるだけ早く実行したいので、以下をクリックします：

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Schedule.png"/>


<br/>


<br/><br/>

タスクがスケジュールされたことを示す青い通知が上部に表示されます。

結果を見に行きましょう。そのために以下に移動します：

`Schedule` ✈ `Completed Actions`

アクションのリストが表示されます。**Filter by Action** フィールドに次のように入力します：

```text
Run
```
リストに表示される一番上のエントリをクリックします。以下のようになるはずです：

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/Select_complete_action_run.png"/>


そこで **Completed Systems** に移動し、システム名をクリックして結果を確認できます。


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-multiple_systems_at_once.gif"/>
  </div>

<br/>


<br/><br/>

これでこの部分は完了です。ワークショップを通じて、複数の Linux システムを管理する方法のさらなる例を見ていきます。



[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] にとってなぜ重要なのか？
=================================================================================

- ベンダーロックインがなく、選択の自由と変化する市場に迅速に対応するための柔軟性を維持できます。

- カスタマイズに関する余分な作業を回避し、簡素化して時間を節約できます。

- すべてを管理する単一の UI (UI) により複雑さが軽減され、将来のトラブルシューティング、スケーリング、パッチ適用、自動化がはるかに機敏になり、時間の消費も少なくなります。



詳細情報
================

サポートされているディストリビューションのリストについては、以下をご覧ください：

[SMLM - Supported Clients and Features](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/client-configuration/supported-features.html)