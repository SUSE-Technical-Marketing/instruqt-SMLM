---
slug: smlm-simplify-upgrade-sles
id: jrlbaehx5ovc
type: challenge
title: シンプルで信頼性の高いメンテナンス
tabs:
- id: vydrbxyk4x63
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: w1tsdcptj7kj
  title: SLES 15
  type: terminal
  hostname: sles15
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 シンプルで信頼性の高いメンテナンス
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

これまでは、混合フリートの多様性の管理や、レガシーシステムの寿命延長に焦点を当ててきました。今度は、航空会社の中核である主力システム <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>) に目を向けます。


これらを、最新鋭の長距離ジェット機だと考えてください。それらの信頼性は最優先事項であり、最高の状態を維持するには、定期的かつ計画的なサービスパッチの適用とアップグレードが必要です。次の演習はまさにそれです。重要なシステムのライフサイクル管理における一般的なタスクである、バージョンアップグレードのプロセスを順を追って説明します。



そして、例として SLES を使用していますが、ユニバーサルコントロールタワーの重要な原則を忘れないでください。これから実行するプロセスは、他のどの Linux ディストリビューションでも使用するものと同じです。インターフェースと方法は変わりません。


## <b class="hovereffect">あなたの目標:</b>

- テスト用航空機として機能する新しい SLES 15 SP5 システムをオンボード（登録）します。
- SP5 から SP6 へのメジャーサービスアップグレードを実行します。



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






オンボードと準備 (Onboarding and preparation)
==========================

[button label="SLES 15" variant="success"](tab-1) タブからシステムターミナルにアクセスします。


システムを **sles15** として <b class="smlm">SMLM</b> 内に登録しましょう。

```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | HOSTNAME="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-sles15sp5 bash ; echo "Wait 45 seconds for it to finish"; sleep 45
```


では、[button label="SMLM UI" variant="success"](tab-0) タブに切り替えましょう。


アップグレードの実行 (Executing the upgrade)
=====================

システムのリストにすぐに表示されるはずです。`Systems` ✈ `System List` ✈ `All` に移動しましょう。表示されない場合は、内部ブラウザの更新をクリックしてください。


それをクリックして、`Software` ✈ `Packages` ✈ `Upgrade` に移動しましょう。


スムーズな移行を確実にするには、最新の更新プログラムを適用するのが最善です。



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">以下をクリックしてください： </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


これには完了するまで時間がかかる場合があります。

<br/>


## <b class="hovereffect">製品の移行 (Product migration)</b>


完了したら、`Software` ✈ `Product Migration` に移動してください。



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">**Target Products** というセクションが表示されます。<b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #90ebcd">SUSE Linux Enterprise Server 15 SP6 x86_64</b> が選択されていることを確認し、以下を押します： </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; vertical-align: middle; display:block; align:left; padding: 0px;" src="../assets/SMLM5.1/bottom-select_channels.png"/></p>

要約と追加オプションを含む確認画面が表示されます。デフォルトのままにして、以下をクリックします： ![Schedule Migration](../assets/SMLM5.1/bottom-schedule_migration.png)

システムは最初にドライラン（予行演習）を行うように求めますが、無視して以下を押します： ![Confirm](../assets/SMLM5.1/bottom-confirm.png)

これには時間がかかります。ステータスを監視するには、`Events` ✈ `History` に移動し、**Product Migration** イベントを監視します。ステータスアイコンが緑色になったら、移行は完了です。`Software` ✈ `Software Channels` に移動し、システムが新しい SP6 チャンネルにサブスクライブされていることを確認することで、これを検証できます。

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/04-simple_and_reliable_maintenance-executing_the_upgrade.gif"/>
  </div>

<br/>

## <b class="hovereffect">移行後の再起動 (Post-Migration Reboot)</b>

- `Systems` ✈ `System List` ✈ `All` に戻ります。

- `sles15` システムの横に再起動アイコンが表示されていることに注目してください：

![Needs reboot icon](../assets/SMLM5.1/icon_needs_reboot.png)

  これは、通常はメジャーなカーネル更新のために、再起動が必要であることを示しています。

- それをクリックすると、次のようなものが表示されます：

![Needs reboot message](../assets/SMLM5.1/system_requires_a_reboot.png)

- `Schedule System Reboot` をクリックし、次の画面で ![Reboot System](../assets/SMLM5.1/bottom-reboot_system.png) をクリックします。

> [!NOTE]
> 再起動はすぐには行われません。

<br/>


## <b class="hovereffect">スケジューリングの重要性 (The importance of Scheduling)</b>

これらのアクションをすぐに実行するようにスケジュールしましたが、これが常に望ましいとは限りません。<b class="smlm">SMLM</b> はメンテナンスウィンドウ（Maintenance Windows）の作成（`Schedule` ✈ `Maintenance Windows`）をサポートしており、再起動のような主要なイベントが、事前に承認された期間中にのみ発生するようにすることができます。



スケジューリングは、本番システムにとって特に有用であり、システムグループに対する慎重に計画された変更や、段階的な「カナリア」展開さえも可能にします。

<br/>

> [!NOTE]
> KLP を使用してカーネルライブパッチを行うことが可能であり、再起動せずに Linux カーネルに最新のセキュリティ更新プログラムを適用できます。



[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] にとってなぜ重要なのですか？
=================================================================================

- システムアップグレードやその他のルーチンタスクは、シンプルで反復可能でなければなりません。そうでないと、高価なミスを犯すリスクがあります。これらのツールを使用すると、アクションを実行する日時と場所を正確に制御でき、フリートの重要なメンテナンスを自信を持ってスケジュールできます。


- いつどこでアクションを実行するかを制御し、地上にあるフリートのメンテナンス作業をスケジュールできます。


詳細情報
================

- [Live kernel patching with KLP](https://documentation.suse.com/en-us/sles/15-SP7/html/SLES-all/cha-klp.html)

- [Maintenance Windows](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

- [Administration Guide](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/admin-overview.html)