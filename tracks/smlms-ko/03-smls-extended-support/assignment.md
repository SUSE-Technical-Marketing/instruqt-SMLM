---
slug: smls-extended-support
id: 9kbxsvcffhmi
type: challenge
title: 레거시 시스템을 위한 확장 지원
tabs:
- id: 6kuyjqqclnbb
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: 1euvak8lcwr5
  title: CentOS 7 QA
  type: terminal
  hostname: centos7
- id: nnwp7yogkkbf
  title: CentOS 7 Prod
  type: terminal
  hostname: zzcentos7
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 레거시 시스템을 위한 확장 지원
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

# 레거시 자산(Fleet)의 수명 연장

어떤 항공사든 수년간 여러분을 위해 봉사해 왔지만 아직 교체할 계획이 없는 신뢰할 수 있는 오래된 비행기들이 있습니다. 우리에게 있어, 그 레거시 자산의 일부는 바로 CentOS 7 시스템들입니다. 이들은 안정적이지만 수명 종료(end-of-life) 상태이며, 이는 더 이상 원래 제조업체로부터 중요한 보안 업데이트를 받지 못한다는 것을 의미합니다. 항공사에게 있어 지원 없이 비행하는 것은 우리가 감수할 수 없는 위험입니다.

전통적인 해결책은 모든 시스템을 완전히, 비용을 들여 교체하는 것입니다.
하지만 중단을 최소화하면서 제자리에 현대화하는 수명 연장 업그레이드를 수행할 수 있다면 어떨까요? 그것이 바로 이 과제의 임무입니다. 우리는 <b class="smlmext">SUSE Multi-Linux Manager</b>의 강력함과 <b class="smlsext">SUSE Multi-Linux Support</b>를 함께 사용하여 이 시스템들을 안전하게 전환하고, 더 현대적인 OS로 교체할 수 있을 때까지 서비스 상태를 유지할 것입니다.



## <b class="hovereffect">우리의 비행 계획:</b>

- Centos 7을 실행 중인 현재 레거시 시스템 검사

- QA 시스템을 온보딩(Onboard)하고 사용 가능한 모든 패치 적용

- 업데이트가 있는 경우 식별하고 적용

- liberate 포뮬러(formula)를 사용하여 시스템 해방(Liberate)

- 두 시스템 간에 변경된 사항 관찰

- 이것이 마이그레이션인지 식별

<br/>

## <b class="hovereffect">우리의 비행기들</b>

- CentOS 7 QA ✈ 우리의 테스트 및 개발 서버.

- CentOS 7 Prod ✈ 이미 <b class="smlm">SMLM</b>에 등록된 우리의 프로덕션 서버

<br/><br/>


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



Centos 7 QA 온보딩 (Onboarding Centos 7 QA)
======================



## <b class="hovereffect">현재 레거시 시스템 검사</b>

[button label="Centos 7 QA" variant="success"](tab-1) 탭에서 시스템 터미널에 액세스합니다.

시스템의 현재 버전을 확인합니다:

```bash,run
rpm -qi centos-release centos-logos
```


이제 다음 명령을 실행하여 시스템을 <b class="smlm">SMLM</b>에 등록합니다:


```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | SMLM_DNS="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-liberty7ltss PROFILENAME='airco-dh4a-qa' bash ; echo "Let's wait 2 minutes for all the background processes to finish"; sleep 120
```


이것은 이전 실습에서 Ubuntu를 온보딩하는 데 사용한 것과 유사하지만, 변경된 사항은 다음과 같습니다:

- **Activation key** (활성화 키): 기본적으로 시스템에 적용될 설정에 대한 참조입니다. 이 경우 시스템이 등록될 소프트웨어 채널만 나타내도록 생성되었습니다.

- **Profile name** (프로필 이름): 지정하지 않으면 호스트 이름을 사용하지만, 이 경우 Centos 7 Prod에서 사용한 것과 동일한 명명 규칙을 사용하여 더 의미 있는 이름을 갖도록 하고 싶습니다.


**선택 사항:** 궁금하다면 업그레이드하고 Liberate 포뮬러를 실행할 때 어떤 일이 발생하는지 확인하기 위해 두 시스템( [button label="Centos 7 QA" variant="success"](tab-1) 및 [button label="Centos 7 Prod" variant="success"](tab-2) )에서 다음 명령을 실행할 수 있습니다:


```bash,run
journalctl -f
```

그리고 터미널에 나타나는 로그를 확인하십시오.


<br/><br/>


## <b class="hovereffect"><b class="liberty">Liberty</b> 리포지토리에서 업데이트 식별 및 적용</b>

이 Centos 7 시스템은 업스트림에서 제공하는 최신 패키지와 함께 제공됩니다. 우리는 새로운 버그가 수정되었는지 확인하고 문제가 있을 때 도와줄 친절한 지원 담당자가 있는지 확인하고 싶습니다. 이제 등록 과정 중에 이미 Centos 7 시스템을 SUSE 제공 소프트웨어 리포지토리에 구독시켰으므로 모두 패치해 봅시다:



이제 [button label="SMLM UI" variant="success"](tab-0) 탭으로 전환해 봅시다.


- 왼쪽 메뉴에서 `Systems` ✈ `System List`로 이동합니다.

- 호스트 **airco-dh4a-qa**를 찾아 클릭합니다.

- `Software` ✈ `Packages`를 선택합니다.

- `Update Packages List`를 클릭합니다. 완료하는 데 약 1분 정도 걸립니다.

- `Software` ✈ `Patches`를 선택합니다.

- 사용 가능한 패치 목록이 표시됩니다.

`Select All`을 클릭한 다음, 오른쪽 상단의 `Apply Patches`를 클릭하고 마지막으로 `Confirm`을 클릭합니다. <b class="smlmext">SUSE Multi-Linux Manager</b>는 이제 CentOS 시스템에서 업그레이드 절차를 예약하고 수행합니다.


> [!NOTE]
> 시스템에 적용할 수 있는 패치 목록을 보기 전에 패키지 목록을 가져오는 데 몇 분 정도 걸릴 수 있습니다.


시간이 좀 걸릴 수 있으므로 내부적으로 무슨 일이 일어나는지 살펴봅시다.
`Events` 탭으로 이동한 다음 `History`로 이동하면 시스템이 <b class="smlm">SMLM</b>에 등록된 이후 발생한 이벤트 목록을 볼 수 있습니다. 첫 번째 줄에서 *Combined Patch*와 유사한 내용을 포함하는 이벤트를 찾을 수 있어야 합니다.


클릭하면 모든 세부 정보를 볼 수 있습니다. 자유롭게 살펴보십시오. 그렇지 않으면 아이콘이 녹색이 될 때까지 기다리십시오:

![Successfully patched](../assets/SMLM5.1/successfully_updated_system.png)

방금 기존 패키지의 버그를 수정하는 패치를 적용했습니다. 이 패치된 패키지는 SUSE에서 직접 제공되는 것이며, 이는 마이그레이션이 아닙니다.

<br/>

아직 업데이트하지 않은 프로덕션 시스템과 비교해 봅시다.

`Software` ✈ `Packages` ✈ `Profiles`로 이동하십시오.

프로덕션 버전인 시스템 `airco-dh4a-prod`를 선택한 다음 다음을 클릭하십시오:

![Compare](../assets/SMLM5.1/bottom-compare.png)


대부분의 패키지 버전이 변경되지 않았음을 알 수 있습니다. 여전히 동일한 버전( **X.X.X**-xyz )이지만 패치가 적용되었습니다( X.X.X-**xyz** ).

다음 섹션으로 넘어가기 전에 저장된 프로필(stored profile)을 생성해 봅시다. 이는 다음 섹션에서 liberate 포뮬러를 적용한 후의 차이점을 더 명확하게 보는 데 도움이 될 것입니다.


`Software` ✈ `Packages` ✈ `Profile`로 이동하여 `Create System Profile`을 클릭하십시오. 이름은 다음과 같이 지정할 수 있습니다:

```txt
before_liberation
```


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-identify_and_apply_updates.gif"/>
  </div>


<br/><br/>


시스템 해방(Liberate) (선택 사항)
==============================

이것은 **선택 사항** 단계이며 지원을 받기 위해 반드시 필요한 것은 아닙니다.

이제 시스템을 해방(liberate)해 봅시다:

- `Formulas` 탭으로 이동하여 **Liberate**를 검색하고, 찾으면 선택한 다음 오른쪽 상단의 `Save`를 클릭합니다.

화면 상단에 파란색 메시지가 표시될 것입니다. 보이지 않으면 위로 스크롤하십시오:

![Formula saved](../assets/SMLM5.1/formula_saved.png)


`Highstate`라고 적힌 곳을 클릭하면 다른 탭(`States` ✈ `Highstate`)으로 이동하게 됩니다.

하단 요약에 liberate 포뮬러가 나열된 것을 볼 수 있습니다.

해방 프로세스를 시작하려면 다음을 클릭하십시오:

![Formula saved](../assets/SMLM5.1/bottom-apply_highstates.png)

시간이 좀 걸릴 것입니다. `Events` -> `History`를 확인해 주세요. **Apply highstate scheduled**라는 이벤트가 표시되어야 합니다.

완료될 때까지 몇 분 기다립시다. 그동안 터미널 [button label="Centos 7 QA" variant="success"](tab-1)을 보며 무슨 일이 일어나고 있는지 관찰할 수 있습니다.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-liberate.gif"/>
  </div>

<br/><br/>

## <b class="hovereffect">변경된 사항 관찰</b>


완료되면 시스템을 다시 비교하여 차이점을 확인해 봅시다. 아직 해당 화면이 아니라면 시스템 이름 `airco-dh4a-qa`를 클릭하십시오.

그런 다음 `Software` ✈ `Packages` ✈ `Profile`로 이동합니다.

**Compare to Stored Profile** 아래에서 다음을 클릭하십시오: ![Compare](../assets/SMLM5.1/bottom-compare.png)

유일하게 변경된 것은 다음 패키지들임을 알 수 있습니다:

- **centos-logos**, **sles_es-logos**로 대체됨

- **centos-release**, **sles_es-release-server**로 대체됨

나머지는 동일하지만 이제 <b class="liberty">Liberty Linux</b>를 위해 <b class="suse">SUSE</b>가 제공하는 모든 지원, 업그레이드 및 패치를 받을 수 있습니다.

더 최신 버전의 CentOS 및 RHEL에도 동일하게 적용됩니다. 실제 소프트웨어와 라이브러리를 변경할 필요 없이 이들을 <b class="liberty">Liberty</b>로 변환하고 <b class="suse">SUSE</b>의 지원을 받을 수 있습니다.



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-what_changed.gif"/>
  </div>

<br/>



프로덕션 서버 해방(Liberate) (선택 사항)
=========================================

QA에서 기존 Centos 7 서버를 패치하고 해방(Liberate)하는 방법을 보았습니다. 이제 프로덕션 시스템에서도 같은 작업을 수행할 차례이지만, 이번에는 다른 순서로 진행할 것입니다.

- 먼저, **Liberate** 포뮬러를 적용합니다.

  프로덕션 서버 `airco-dh4a-prod`로 이동하여 `Create System Profile`을 수행합시다.

  그 후 QA 시스템에서 했던 것처럼 **Liberate** 포뮬러를 적용합시다.

- 완료되면 방금 생성한 프로필과 시스템을 비교해 봅시다. 보시다시피 유일한 변경 사항은 **centos-logos** 및 **centos-release** 패키지뿐이며, 나머지는 정확히 동일하게 유지됩니다.


이것은 마이그레이션입니까?
==================

마이그레이션에는 완전히 새로운 서버 구축, 처음부터 모든 애플리케이션 재설치, 그리고 데이터를 신중하게 이동하는 과정이 포함되며, 이는 시간이 많이 걸리고 비용이 많이 들며 위험으로 가득 찬 프로세스입니다.

우리가 한 것은 훨씬 더 우아했습니다. 우리는 인플레이스 업그레이드(in-place upgrade)를 수행했습니다.

서버의 정체성, 호스트 이름, 애플리케이션 및 사용자 데이터는 완전히 손대지 않은 상태로 유지되었습니다. 우리는 단지 업데이트를 위한 기본 소스를 변경했을 뿐이며, 수명이 종료된 구성 요소들은 이제 패치를 받는 완전히 지원되는 구성 요소가 되었습니다.

우리는 시스템의 수명을 성공적으로 연장하고, 보안 규정 준수 상태로 되돌렸으며, 전체 마이그레이션으로 인한 중단 없이 이 모든 것을 수행했습니다. 그것이 바로 [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]이(가) 높이 날 수 있도록 유지하는 효율성입니다.




이것이 [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]에 중요한 이유는 무엇입니까?
=================================================================================

- [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]이(가) 실행 중인 시스템을 계속 지원받을 수 있게 하여, 벤더의 필요가 아닌 비즈니스 필요에 따라 마이그레이션할 수 있는 시간을 줍니다.

- 확장 지원을 제공함으로써 지원되지 않는 시스템을 보유하는 데 따르는 위험을 완화합니다. 이 접근 방식은 즉각적인 마이그레이션의 필요성을 피하며, 모든 것이 평소대로 실행되지만 이제 전화를 받을 수 있는 전문가 그룹이 있습니다.

- 긴 마이그레이션 과정을 거치지 않고도 지원 제공자를 변경할 수 있는 자유를 제공하며, 이를 대규모(at scale)로 수행할 수 있게 합니다.



추가 정보
================

- [Registering RHEL 7 or CentOS Linux 7 with SUSE Manager](https://documentation.suse.com/liberty/7/html/suma-quickstart/art-suma-quickstart.html)
- [Running OpenSCAP compliance scans for SUSE Multi-Linux Support 7](https://documentation.suse.com/liberty/7/html/compliance-scans/art-compliance-scans.html)
- [Registering CentOS Linux 7 with the SUSE Customer Center](https://documentation.suse.com/liberty/7/html/quickstart-scc/art-quickstart-scc.html)
- [SUSE Multi-Linux Support 9](https://documentation.suse.com/liberty/9/)