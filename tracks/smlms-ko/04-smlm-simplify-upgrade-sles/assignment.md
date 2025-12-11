---
slug: smlm-simplify-upgrade-sles
id: rclcoebs187z
type: challenge
title: 간단하고 신뢰할 수 있는 유지 관리
tabs:
- id: ey80fny21voz
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: 9gya0wwlwfki
  title: SLES 15
  type: terminal
  hostname: sles15
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 간단하고 신뢰할 수 있는 유지 관리
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

지금까지 우리는 혼합 자산(fleet)의 다양성을 관리하고 레거시 시스템의 수명을 연장하는 데 집중했습니다. 이제 우리는 항공사의 핵심인 플래그십 <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>) 시스템으로 관심을 돌립니다.


이들을 우리의 최첨단 장거리 제트기로 생각하십시오. 그들의 신뢰성은 무엇보다 중요하며, 이를 최상의 상태로 유지하려면 정기적이고 계획된 서비스 패치 및 업그레이드가 필요합니다. 다음 연습이 바로 그것입니다: 모든 중요 시스템의 수명 주기를 관리하는 일반적인 작업인 버전 업그레이드 과정을 살펴볼 것입니다.



그리고 SLES를 예로 들고 있지만, 우리의 보편적인 관제탑의 핵심 원칙을 기억하십시오: 여러분이 수행하려는 프로세스는 다른 모든 Linux 배포판에 사용하는 것과 동일합니다. 인터페이스와 방법론은 변하지 않습니다.


## <b class="hovereffect">여러분의 목표:</b>

- 테스트 항공기로 사용할 새로운 SLES 15 SP5 시스템을 온보딩(Onboard)합니다.
- SP5에서 SP6로의 메이저 서비스 업그레이드를 수행합니다.



Lab details
===========

사용자 이름 (Username):
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```

비밀번호 (Password):
```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

<b class="smlm">SMLM</b> URL: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>






온보딩 및 준비 (Onboarding and preparation)
==========================

[button label="SLES 15" variant="success"](tab-1) 탭에서 시스템 터미널에 액세스합니다.


시스템을 <b class="smlm">SMLM</b> 내에 **sles15**로 등록합시다.

```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | HOSTNAME="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-sles15sp5 bash ; echo "Wait 45 seconds for it to finish"; sleep 45
```


이제 [button label="SMLM UI" variant="success"](tab-0) 탭으로 전환해 봅시다.


업그레이드 실행 (Executing the upgrade)
=====================

시스템 목록에서 곧 볼 수 있을 것입니다. `Systems` ✈ `System List` ✈ `All`로 이동하십시오. 보이지 않으면 내부 브라우저에서 새로 고침을 클릭하십시오.


그것을 클릭하고 `Software` ✈ `Packages` ✈ `Upgrade`로 이동합시다.


원활한 마이그레이션을 보장하기 위해 최신 업데이트를 적용하는 것이 가장 좋습니다.



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">다음을 클릭하십시오: </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


완료하는 데 시간이 좀 걸릴 수 있습니다.

<br/>


## <b class="hovereffect">제품 마이그레이션 (Product migration)</b>


완료되면 `Software` ✈ `Product Migration`으로 이동하십시오.



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">**Target Products**라는 섹션이 보일 것입니다. <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #90ebcd">SUSE Linux Enterprise Server 15 SP6 x86_64</b>가 선택되었는지 확인한 다음 다음을 누르십시오: </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; vertical-align: middle; display:block; align:left; padding: 0px;" src="../assets/SMLM5.1/bottom-select_channels.png"/></p>

요약 및 추가 옵션이 포함된 확인 화면이 표시됩니다. 기본값을 그대로 두고 클릭하십시오: ![Schedule Migration](../assets/SMLM5.1/bottom-schedule_migration.png)

시스템이 먼저 드라이 런(dry run, 예행연습)을 하도록 요청할 것입니다. 무시하고 다음을 누르십시오: ![Confirm](../assets/SMLM5.1/bottom-confirm.png)

시간이 좀 걸릴 것입니다. 상태를 모니터링하려면 `Events` ✈ `History`로 이동하여 **Product Migration** 이벤트를 확인하십시오. 상태 아이콘이 녹색으로 바뀌면 마이그레이션이 완료된 것입니다. `Software` ✈ `Software Channels`로 이동하여 시스템이 이제 새로운 SP6 채널을 구독하고 있는지 확인하여 이를 검증할 수 있습니다.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/04-simple_and_reliable_maintenance-executing_the_upgrade.gif"/>
  </div>

<br/>

## <b class="hovereffect">마이그레이션 후 재부팅 (Post-Migration Reboot)</b>

- `Systems` ✈ `System List` ✈ `All`로 다시 이동합니다.

- `sles15` 시스템 옆에 재부팅 아이콘이 있는 것을 확인하십시오:

![Needs reboot icon](../assets/SMLM5.1/icon_needs_reboot.png)

  이는 일반적으로 메이저 커널 업데이트로 인해 재부팅이 필요함을 나타냅니다.

- 그것을 클릭하면 다음과 유사한 화면이 표시됩니다:

![Needs reboot message](../assets/SMLM5.1/system_requires_a_reboot.png)

- `Schedule System Reboot`를 클릭하고 다음 화면에서 ![Reboot System](../assets/SMLM5.1/bottom-reboot_system.png)을 클릭하십시오.

> [!NOTE]
> 재부팅은 즉시 발생하지 않습니다.

<br/>


## <b class="hovereffect">스케줄링의 중요성 (The importance of Scheduling)</b>

우리는 이러한 작업이 즉시 발생하도록 예약했지만, 이것이 항상 바람직한 것은 아닙니다. <b class="smlm">SMLM</b>은 유지 관리 기간(Maintenance Windows) 생성을 지원하여(`Schedule` ✈ `Maintenance Windows`), 재부팅과 같은 주요 이벤트가 사전에 승인된 기간 동안에만 발생하도록 보장할 수 있습니다.



스케줄링은 프로덕션 시스템에 특히 유용하며, 시스템 그룹에 대해 신중하게 계획된 변경과 단계적인 "카나리아(canary)" 배포를 가능하게 합니다.

<br/>

> [!NOTE]
> KLP를 사용하여 커널 라이브 패치(live patching)를 수행할 수 있으며, 이를 통해 재부팅 없이 Linux 커널에 최신 보안 업데이트를 적용할 수 있습니다.



[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]에 이것이 왜 중요한가요?
=================================================================================

- 시스템 업그레이드 및 기타 일상적인 작업은 간단하고 반복 가능해야 합니다. 그렇지 않으면 비용이 많이 드는 실수를 저지를 위험이 있습니다. 이러한 도구를 사용하면 작업을 수행하는 시기와 장소를 정확하게 제어할 수 있어, 자신감을 가지고 자산에 대한 중요한 유지 관리를 예약할 수 있습니다.


- 우리는 언제 어디서 작업을 수행할지 제어할 수 있으며, 지상에 있는 자산에 대한 유지 관리 작업을 예약할 수 있습니다.


추가 정보
================

- [Live kernel patching with KLP](https://documentation.suse.com/en-us/sles/15-SP7/html/SLES-all/cha-klp.html)

- [Maintenance Windows](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

- [Administration Guide](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/admin-overview.html)