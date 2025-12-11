---
slug: smlm-managing-linux-distros
id: xs58uljecg25
type: challenge
title: 서로 다른 Linux 배포판 관리
tabs:
- id: 0l2xgmpmh0id
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: taxxpemgi66c
  title: Ubuntu 2404 LTS
  type: terminal
  hostname: ubuntu2404lts
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 서로 다른 Linux 배포판 관리
===================================

<img class="logos" alt="Welcome!" src="../assets/logos/02-managing_linux_distros.jpeg"/>

여기 [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]에서, <b class="smlmext">SUSE Multi-Linux Manager</b>는 단일 창(single pane of glass)에서 다양한 Linux 배포판과 아키텍처 자산(fleet)을 관리하는 열쇠입니다. 이는 엔지니어로서 우리의 업무를 복잡하게 만들었던 추가 커스터마이징을 방지하는 데 도움이 되었으며, 결과적으로 시스템 정책을 유지 관리하고 구현하는 데 필요한 비용과 시간을 줄여주었습니다.

이 도구를 사용하면 단일 벤더, 아키텍처 또는 자동화 플랫폼에 종속(lock-in)되지 않습니다. 우리는 환경에 필요한 것을 자유롭게 선택하고 동일한 방식으로 모두 관리할 수 있습니다. 우리 자산의 모든 항공기 유형에 대해 고유한 언어와 절차를 가진 서로 다른 항공 교통 관제탑이 필요하다고 상상해 보십시오. 운영 복잡성은 감당할 수 없을 것이며 비용은 엄청날 것입니다.



우리는 특정 항공기 모델이 특정 경로에 더 낫다는 것을 알고 있습니다; 30분 비행을 위해 점보 제트기를 띄우는 것은 비용 효율적이지 않습니다. 이는 우리의 Linux 배포판에도 동일하게 적용됩니다. SUSE 자체 배포판도 훌륭하지만, 일부 애플리케이션에는 특정 요구 사항이 있습니다. <b class="smlm">SMLM</b>은 우리가 결코 종속되지 않으며 당면한 과제에 가장 적합한 솔루션을 항상 통합할 수 있음을 보장합니다.


## <b class="hovereffect">여러분의 목표:</b>

- 마케팅 팀에 필요한 전문 시스템인 Ubuntu 24.04 LTS 시스템을 온보딩(Onboard)합니다.

- 나머지 자산과 동일한 도구 및 패치 절차를 사용하여 이 새롭고 다른 시스템을 어떻게 관리하는지 시연합니다.



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


Ubuntu 온보딩 (Onboarding Ubuntu)
=================

마케팅 부서에서 새로운 서비스 요청이 들어왔습니다. 그들의 그래픽 디자이너들은 Ubuntu에서만 지원되는 특정 크리에이티브 제품군(creative suite)에 의존합니다. 우리는 그들의 시스템을 온보딩하여 다른 시스템과 동일한 방식으로 관리하고 보안 및 규정 준수 표준을 충족하는지 확인할 것입니다.

시작해 봅시다.
<br/>

- [button label="Ubuntu 2404 LTS" variant="success"](tab-1) 탭에서 시스템 터미널에 액세스합니다.

  변경하기 전에 패키지를 어디서 가져오는지 확인해 봅시다:

```bash,run
grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```

이 워크스테이션은 공용 Ubuntu 리포지토리에서 소프트웨어를 직접 가져오고 있습니다. 이는 두 가지 문제를 야기합니다: 첫째, 적용되는 패치에 대한 제어권이 없어 보안상 우려가 됩니다. 둘째, 마케팅 팀이 보고한 바와 같이, 이 워크스테이션들이 업데이트를 가져올 때마다 사무실 인터넷 연결 속도가 느려져 다른 직원들에게 불만을 줄 수 있습니다.



이 시스템을 우리의 관리 하에 둡시다. 이는 모든 소프트웨어 요구 사항에 대해 내부 <b class="smlmext">SUSE Multi-Linux Manager</b> 인스턴스에 연결함으로써 두 가지 문제를 모두 해결할 것입니다.

우리는 [button label="web UI" variant="success"](tab-0)를 사용하여 이를 수행할 것입니다:

- `Home` ✈ `Overview` 아래에서, `Register Systems`를 클릭합시다.

- 다음 세부 정보를 입력하십시오:

  - **Host:**

  ```txt
  ubuntu2404lts
  ```

  - **User:** (사용자)

  ```txt
  root
  ```

  - **Password:** (비밀번호)

  ```txt
  [[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
  ```

  - **Activation Key:** (활성화 키)   <b class="highlightcopy">1-ubuntu2404</b>

- 나머지는 그대로 두고 다음을 클릭하십시오.

<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-bootstrap.png"/>


- 등록 프로세스가 완료되는 데 몇 분 정도 걸릴 수 있습니다. [button label="terminal" variant="success"](tab-1)로 이동하여 첫 번째 명령을 한 번 더 실행하여 변경된 사항을 확인해 봅시다:


```bash,run
echo 'Waiting for the registration to complete' ;while [[ ! -f /etc/apt/sources.list.d/susemanager_bootstrap.sources ]] || [[ ! -f /etc/apt/sources.list.d/susemanager:channels.sources ]]; do echo -n '.'; sleep 5; done ; sleep 60; grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```


새로운 파일이 나타난 것을 볼 수 있습니다:

**/etc/apt/sources.list.d/susemanager:***

이들은 시스템이 <b class="smlm">SMLM</b>에 있는 중앙에서 관리 및 제어되는 채널을 가리키도록 합니다.


또한 원본 파일인 **/etc/apt/sources.list.d/ubuntu.sources**가 모든 공용 리포지토리를 비활성화하도록 수정되었지만 제거되지는 않은 것을 볼 수 있습니다. 이는 필요한 경우 쉽게 롤백(roll back)할 수 있게 해줍니다.


> [!NOTE]
> 등록을 위해 비밀번호 인증과 함께 SSH를 통해 root를 사용하는 것은 데모 목적일 뿐이며 프로덕션 환경에는 권장되지 않습니다.


> [!NOTE]
> 기본적으로 UI를 통해 또는 명령줄 < salt-key -A -y >를 통해 각 시스템의 등록을 승인해야 하지만, 여기서는 <b class="smlm">SMLM</b>이 자동 승인(auto approve)하도록 구성되었습니다.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-register_ubuntu.gif"/>
  </div>

<br/>



이제 [button label="SMLM UI" variant="success"](tab-0) 탭으로 전환해 봅시다.


- `Systems` ✈ `System List` ✈ `All`로 이동합니다.

  방금 등록한 시스템 `Ubuntu2404lts`를 볼 수 있습니다. 기본적으로 호스트 이름(hostname)으로 등록됩니다.

  그것을 클릭하면 `Details` - `Overview`로 바로 이동하며 여기서 다음 정보를 포함한 여러 정보를 볼 수 있습니다:

  - 시스템 상태.
  - 호스트 이름, IP 주소, 가상화 유형, 사용된 커널 및 설치된 제품과 같은 모든 정보.
  - 구독 중인 채널.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_overview.gif"/>
  </div>


<br/>

여러 Linux 배포판 관리
=====================================


앞서 언급했듯이, <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b>에서는 우리가 다른 비행기 모델과 회사를 사용하는 것처럼 다른 Linux 배포판을 사용합니다. 이는 각 요구 사항에 가장 적합한 제품을 사용하여 경쟁 우위를 유지하는 데 도움이 됩니다.

<b class="smlmext">SUSE Multi-Linux Manager</b>를 사용하면 동일한 절차, 동일한 일정 등을 사용하여 동일한 인터페이스와 메커니즘으로 모든 것을 관리할 수 있습니다.

아래에서는 시스템이 실행 중인 OS에 관계없이 불필요한 커스터마이징을 생성하지 않고 동일한 프로세스에 따라 시스템에서 다양한 작업을 수행하는 방법을 살펴보겠습니다.


## <b class="hovereffect">추가 정보 추가</b>


방금 등록한 시스템으로 계속 진행해 보겠습니다. 여기에 몇 가지 설정과 정보를 추가할 것입니다:

- `Properties`를 클릭합시다. 여기서 시스템에 대한 추가 정보를 추가하고 일부 설정을 변경할 것입니다.


  - 패치 자동 적용 활성화 (Enable Automatic application of patches):

  <img style='vertical-align: middle; height: 60%; width: 60%; object-fit: contain' src="../assets/SMLM5.1/option-auto_patch_update-enabled.png"/>

    관련 패치가 있을 때 시스템에 자동으로 패치를 적용합니다.



  - 시스템에 대한 다음 세부 정보를 추가합니다:


| 필드 (Field) | 내용 (Content)                                                  |
| ---: | :-----                                                    |
| **Description** | <b class="highlightcopy">Multimedia workstation for graphics designers.</b> |
| **Facility Address** | <b class="highlightcopy">Candy eye street, 1</b> |
| **City** | <b class="highlightcopy">Aeolia</b> |
| **Building** | <b class="highlightcopy">Belem Tower 4</b> |
| **Room** | <b class="highlightcopy">Sierra nevada</b> |


<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-Update_Properties.png"/>



- 어떤 하드웨어에서 실행 중인지 살펴봅시다:

  - `Details` ✈ `Hardware`를 클릭합니다.


<br/>

> [!NOTE]
> 이 모든 것은 API를 통해 자동화할 수 있습니다.

<br/>

이제 커스텀 키(custom keys)를 사용하여 시스템에 추가 정보를 추가하겠습니다. 이 정보는 나중에 자동화 스크립트에서 쉽게 사용할 수 있습니다.


- `Details` ✈ `Custom Info`를 클릭합니다.

<img style='vertical-align: top; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Create_Value.png"/>

- `application`을 클릭하고 **value** (값)을 다음으로 채웁니다:

```text
Logo Wings designer pro
```

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Update_Key.png"/>


<br/>

> [!NOTE]
> 우리는 이미 당신을 위해 커스텀 키 **application**을 생성했습니다. 자신만의 키를 생성하고 싶다면 다음으로 이동하기만 하면 됩니다: `Systems` ✈ `Custom System Info` ✈ `Create key`

<br/><br/>

Systems 목록으로 돌아갑시다.

`Systems` ✈ `System List` ✈ `All`


시스템 중 하나를 클릭하고 `Details` ✈ `Custom Info`로 이동합니다.

우리는 이미 각 시스템에 값을 채워 넣었습니다.

<br/>

이제 `Details` ✈ `Overview`로 이동하여 **Installed Products** 및 **Subscribed Channels**를 확인하십시오. 이들은 다른 운영 체제를 실행하고 있기 때문에 Ubuntu 시스템의 것과는 다릅니다.



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_properties.gif"/>
  </div>

<br/>


## <b class="hovereffect">여러 시스템에서 한 번에 명령 실행</b>


우리가 가진 모든 시스템에서 무언가를 해봅시다. `Systems` ✈ `System List` ✈ `All`로 돌아가서 모두 선택합니다:

<img style='vertical-align: middle; margin: 2px; height: 50%; width: 50%; object-fit: contain' src="../assets/SMLM5.1/select_all_systems.png"/>

**Base Channel** 열을 주목하십시오. 우리는 세 가지 다른 OS를 실행하는 시스템을 가지고 있습니다.

<br/>

작업하려는 모든 시스템을 선택했으므로 그룹 작업을 수행하러 갑시다:

`Systems` ✈ `System Set Manager`

그들 모두에서 명령을 실행해 봅시다. 이를 위해 다음으로 갈 수 있습니다:

`Misc` ✈ `Remote Command`

그런 다음 다음 세부 정보를 채우고 나머지는 기본값으로 둡니다:


스크립트 (Script):

```bash,run
cat /etc/os-release
```

일정(schedule)을 수정하지 마십시오. 가능한 한 빨리 실행되기를 원하므로 다음을 클릭합니다:

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Schedule.png"/>


<br/>


<br/><br/>

작업이 예약되었음을 나타내는 파란색 알림이 상단에 표시됩니다.

결과를 보러 갑시다. 이를 위해 다음으로 이동합니다:

`Schedule` ✈ `Completed Actions`

작업 목록이 표시될 것입니다. **Filter by Action** 필드에 다음을 입력합니다:

```text
Run
```
목록에 나타나는 맨 위 항목을 클릭하십시오. 다음과 비슷할 것입니다:

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/Select_complete_action_run.png"/>


거기서 **Completed Systems**로 이동하여 시스템 이름을 클릭하여 결과를 검토할 수 있습니다.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-multiple_systems_at_once.gif"/>
  </div>

<br/>


<br/><br/>

이것으로 이 부분을 마치며, 워크샵을 진행하면서 여러 Linux 시스템을 관리할 수 있는 방법에 대한 더 많은 예를 보게 될 것입니다.



이것이 [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]에 중요한 이유는 무엇입니까?
=================================================================================

- 벤더 종속(vendor lock-in)이 없으며, 변화하는 시장에 빠르게 대응할 수 있는 선택의 자유와 유연성을 유지합니다.

- 커스터마이징에 대한 추가 작업을 피하여 간소화하고 시간을 절약합니다.

- 모든 것을 관리하는 단일 UI는 복잡성을 줄이고 향후 트러블슈팅, 확장, 패치 적용 및 자동화를 훨씬 더 민첩하게 만들고 시간 소모를 줄여줄 것입니다.



추가 정보
================

지원되는 배포판 목록을 보려면 다음을 방문하십시오:

[SMLM - Supported Clients and Features](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/client-configuration/supported-features.html)
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

여기 [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]에서, <b class="smlmext">SUSE Multi-Linux Manager</b>는 단일 창(single pane of glass)에서 다양한 Linux 배포판과 아키텍처 자산(fleet)을 관리하는 열쇠입니다. 이는 엔지니어로서 우리의 업무를 복잡하게 만들었던 추가 커스터마이징을 방지하는 데 도움이 되었으며, 결과적으로 시스템 정책을 유지 관리하고 구현하는 데 필요한 비용과 시간을 줄여주었습니다.

이 도구를 사용하면 단일 벤더, 아키텍처 또는 자동화 플랫폼에 종속(lock-in)되지 않습니다. 우리는 환경에 필요한 것을 자유롭게 선택하고 동일한 방식으로 모두 관리할 수 있습니다. 우리 자산의 모든 항공기 유형에 대해 고유한 언어와 절차를 가진 서로 다른 항공 교통 관제탑이 필요하다고 상상해 보십시오. 운영 복잡성은 감당할 수 없을 것이며 비용은 엄청날 것입니다.



우리는 특정 항공기 모델이 특정 경로에 더 낫다는 것을 알고 있습니다; 30분 비행을 위해 점보 제트기를 띄우는 것은 비용 효율적이지 않습니다. 이는 우리의 Linux 배포판에도 동일하게 적용됩니다. SUSE 자체 배포판도 훌륭하지만, 일부 애플리케이션에는 특정 요구 사항이 있습니다. <b class="smlm">SMLM</b>은 우리가 결코 종속되지 않으며 당면한 과제에 가장 적합한 솔루션을 항상 통합할 수 있음을 보장합니다.


## <b class="hovereffect">여러분의 목표:</b>

- 마케팅 팀에 필요한 전문 시스템인 Ubuntu 24.04 LTS 시스템을 온보딩(Onboard)합니다.

- 나머지 자산과 동일한 도구 및 패치 절차를 사용하여 이 새롭고 다른 시스템을 어떻게 관리하는지 시연합니다.



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


Ubuntu 온보딩 (Onboarding Ubuntu)
=================

마케팅 부서에서 새로운 서비스 요청이 들어왔습니다. 그들의 그래픽 디자이너들은 Ubuntu에서만 지원되는 특정 크리에이티브 제품군(creative suite)에 의존합니다. 우리는 그들의 시스템을 온보딩하여 다른 시스템과 동일한 방식으로 관리하고 보안 및 규정 준수 표준을 충족하는지 확인할 것입니다.

시작해 봅시다.
<br/>

- [button label="Ubuntu 2404 LTS" variant="success"](tab-1) 탭에서 시스템 터미널에 액세스합니다.

  변경하기 전에 패키지를 어디서 가져오는지 확인해 봅시다:

```bash,run
grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```

이 워크스테이션은 공용 Ubuntu 리포지토리에서 소프트웨어를 직접 가져오고 있습니다. 이는 두 가지 문제를 야기합니다: 첫째, 적용되는 패치에 대한 제어권이 없어 보안상 우려가 됩니다. 둘째, 마케팅 팀이 보고한 바와 같이, 이 워크스테이션들이 업데이트를 가져올 때마다 사무실 인터넷 연결 속도가 느려져 다른 직원들에게 불만을 줄 수 있습니다.



이 시스템을 우리의 관리 하에 둡시다. 이는 모든 소프트웨어 요구 사항에 대해 내부 <b class="smlmext">SUSE Multi-Linux Manager</b> 인스턴스에 연결함으로써 두 가지 문제를 모두 해결할 것입니다.

우리는 [button label="web UI" variant="success"](tab-0)를 사용하여 이를 수행할 것입니다:

- `Home` ✈ `Overview` 아래에서, `Register Systems`를 클릭합시다.

- 다음 세부 정보를 입력하십시오:

  - **Host:**

  ```txt
  ubuntu2404lts
  ```

  - **User:** (사용자)

  ```txt
  root
  ```

  - **Password:** (비밀번호)

  ```txt
  [[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
  ```

  - **Activation Key:** (활성화 키)   <b class="highlightcopy">1-ubuntu2404</b>

- 나머지는 그대로 두고 다음을 클릭하십시오.

<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-bootstrap.png"/>


- 등록 프로세스가 완료되는 데 몇 분 정도 걸릴 수 있습니다. [button label="terminal" variant="success"](tab-1)로 이동하여 첫 번째 명령을 한 번 더 실행하여 변경된 사항을 확인해 봅시다:


```bash,run
echo 'Waiting for the registration to complete' ;while [[ ! -f /etc/apt/sources.list.d/susemanager_bootstrap.sources ]] || [[ ! -f /etc/apt/sources.list.d/susemanager:channels.sources ]]; do echo -n '.'; sleep 5; done ; sleep 60; grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```


새로운 파일이 나타난 것을 볼 수 있습니다:

**/etc/apt/sources.list.d/susemanager:***

이들은 시스템이 <b class="smlm">SMLM</b>에 있는 중앙에서 관리 및 제어되는 채널을 가리키도록 합니다.


또한 원본 파일인 **/etc/apt/sources.list.d/ubuntu.sources**가 모든 공용 리포지토리를 비활성화하도록 수정되었지만 제거되지는 않은 것을 볼 수 있습니다. 이는 필요한 경우 쉽게 롤백(roll back)할 수 있게 해줍니다.


> [!NOTE]
> 등록을 위해 비밀번호 인증과 함께 SSH를 통해 root를 사용하는 것은 데모 목적일 뿐이며 프로덕션 환경에는 권장되지 않습니다.


> [!NOTE]
> 기본적으로 UI를 통해 또는 명령줄 < salt-key -A -y >를 통해 각 시스템의 등록을 승인해야 하지만, 여기서는 <b class="smlm">SMLM</b>이 자동 승인(auto approve)하도록 구성되었습니다.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-register_ubuntu.gif"/>
  </div>

<br/>



이제 [button label="SMLM UI" variant="success"](tab-0) 탭으로 전환해 봅시다.


- `Systems` ✈ `System List` ✈ `All`로 이동합니다.

  방금 등록한 시스템 `Ubuntu2404lts`를 볼 수 있습니다. 기본적으로 호스트 이름(hostname)으로 등록됩니다.

  그것을 클릭하면 `Details` - `Overview`로 바로 이동하며 여기서 다음 정보를 포함한 여러 정보를 볼 수 있습니다:

  - 시스템 상태.
  - 호스트 이름, IP 주소, 가상화 유형, 사용된 커널 및 설치된 제품과 같은 모든 정보.
  - 구독 중인 채널.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_overview.gif"/>
  </div>


<br/>

여러 Linux 배포판 관리
=====================================


앞서 언급했듯이, <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b>에서는 우리가 다른 비행기 모델과 회사를 사용하는 것처럼 다른 Linux 배포판을 사용합니다. 이는 각 요구 사항에 가장 적합한 제품을 사용하여 경쟁 우위를 유지하는 데 도움이 됩니다.

<b class="smlmext">SUSE Multi-Linux Manager</b>를 사용하면 동일한 절차, 동일한 일정 등을 사용하여 동일한 인터페이스와 메커니즘으로 모든 것을 관리할 수 있습니다.

아래에서는 시스템이 실행 중인 OS에 관계없이 불필요한 커스터마이징을 생성하지 않고 동일한 프로세스에 따라 시스템에서 다양한 작업을 수행하는 방법을 살펴보겠습니다.


## <b class="hovereffect">추가 정보 추가</b>


방금 등록한 시스템으로 계속 진행해 보겠습니다. 여기에 몇 가지 설정과 정보를 추가할 것입니다:

- `Properties`를 클릭합시다. 여기서 시스템에 대한 추가 정보를 추가하고 일부 설정을 변경할 것입니다.


  - 패치 자동 적용 활성화 (Enable Automatic application of patches):

  <img style='vertical-align: middle; height: 60%; width: 60%; object-fit: contain' src="../assets/SMLM5.1/option-auto_patch_update-enabled.png"/>

    관련 패치가 있을 때 시스템에 자동으로 패치를 적용합니다.



  - 시스템에 대한 다음 세부 정보를 추가합니다:


| 필드 (Field) | 내용 (Content)                                                  |
| ---: | :-----                                                    |
| **Description** | <b class="highlightcopy">Multimedia workstation for graphics designers.</b> |
| **Facility Address** | <b class="highlightcopy">Candy eye street, 1</b> |
| **City** | <b class="highlightcopy">Aeolia</b> |
| **Building** | <b class="highlightcopy">Belem Tower 4</b> |
| **Room** | <b class="highlightcopy">Sierra nevada</b> |


<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-Update_Properties.png"/>



- 어떤 하드웨어에서 실행 중인지 살펴봅시다:

  - `Details` ✈ `Hardware`를 클릭합니다.


<br/>

> [!NOTE]
> 이 모든 것은 API를 통해 자동화할 수 있습니다.

<br/>

이제 커스텀 키(custom keys)를 사용하여 시스템에 추가 정보를 추가하겠습니다. 이 정보는 나중에 자동화 스크립트에서 쉽게 사용할 수 있습니다.


- `Details` ✈ `Custom Info`를 클릭합니다.

<img style='vertical-align: top; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Create_Value.png"/>

- `application`을 클릭하고 **value** (값)을 다음으로 채웁니다:

```text
Logo Wings designer pro
```

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Update_Key.png"/>


<br/>

> [!NOTE]
> 우리는 이미 당신을 위해 커스텀 키 **application**을 생성했습니다. 자신만의 키를 생성하고 싶다면 다음으로 이동하기만 하면 됩니다: `Systems` ✈ `Custom System Info` ✈ `Create key`

<br/><br/>

Systems 목록으로 돌아갑시다.

`Systems` ✈ `System List` ✈ `All`


시스템 중 하나를 클릭하고 `Details` ✈ `Custom Info`로 이동합니다.

우리는 이미 각 시스템에 값을 채워 넣었습니다.

<br/>

이제 `Details` ✈ `Overview`로 이동하여 **Installed Products** 및 **Subscribed Channels**를 확인하십시오. 이들은 다른 운영 체제를 실행하고 있기 때문에 Ubuntu 시스템의 것과는 다릅니다.



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_properties.gif"/>
  </div>

<br/>


## <b class="hovereffect">여러 시스템에서 한 번에 명령 실행</b>


우리가 가진 모든 시스템에서 무언가를 해봅시다. `Systems` ✈ `System List` ✈ `All`로 돌아가서 모두 선택합니다:

<img style='vertical-align: middle; margin: 2px; height: 50%; width: 50%; object-fit: contain' src="../assets/SMLM5.1/select_all_systems.png"/>

**Base Channel** 열을 주목하십시오. 우리는 세 가지 다른 OS를 실행하는 시스템을 가지고 있습니다.

<br/>

작업하려는 모든 시스템을 선택했으므로 그룹 작업을 수행하러 갑시다:

`Systems` ✈ `System Set Manager`

그들 모두에서 명령을 실행해 봅시다. 이를 위해 다음으로 갈 수 있습니다:

`Misc` ✈ `Remote Command`

그런 다음 다음 세부 정보를 채우고 나머지는 기본값으로 둡니다:


스크립트 (Script):

```bash,run
cat /etc/os-release
```

일정(schedule)을 수정하지 마십시오. 가능한 한 빨리 실행되기를 원하므로 다음을 클릭합니다:

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Schedule.png"/>


<br/>


<br/><br/>

작업이 예약되었음을 나타내는 파란색 알림이 상단에 표시됩니다.

결과를 보러 갑시다. 이를 위해 다음으로 이동합니다:

`Schedule` ✈ `Completed Actions`

작업 목록이 표시될 것입니다. **Filter by Action** 필드에 다음을 입력합니다:

```text
Run
```
목록에 나타나는 맨 위 항목을 클릭하십시오. 다음과 비슷할 것입니다:

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/Select_complete_action_run.png"/>


거기서 **Completed Systems**로 이동하여 시스템 이름을 클릭하여 결과를 검토할 수 있습니다.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-multiple_systems_at_once.gif"/>
  </div>

<br/>


<br/><br/>

이것으로 이 부분을 마치며, 워크샵을 진행하면서 여러 Linux 시스템을 관리할 수 있는 방법에 대한 더 많은 예를 보게 될 것입니다.



이것이 [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]에 중요한 이유는 무엇입니까?
=================================================================================

- 벤더 종속(vendor lock-in)이 없으며, 변화하는 시장에 빠르게 대응할 수 있는 선택의 자유와 유연성을 유지합니다.

- 커스터마이징에 대한 추가 작업을 피하여 간소화하고 시간을 절약합니다.

- 모든 것을 관리하는 단일 UI는 복잡성을 줄이고 향후 트러블슈팅, 확장, 패치 적용 및 자동화를 훨씬 더 민첩하게 만들고 시간 소모를 줄여줄 것입니다.



추가 정보
================

지원되는 배포판 목록을 보려면 다음을 방문하십시오:

[SMLM - Supported Clients and Features](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/client-configuration/supported-features.html)