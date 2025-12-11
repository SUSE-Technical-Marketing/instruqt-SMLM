---
slug: smlm-security
id: xb2f0pdyows7
type: challenge
title: 보안 및 패치
tabs:
- id: whnmcxdoaqzu
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 보안 및 패치 (Security and patching)
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



이 실습에서는 우리가 가진 가장 중요한 책임 중 하나인 전체 디지털 자산(fleet)의 보안을 보장하는 문제를 다룰 것입니다. 우리는 <b class="smlmext">SUSE Multi-Linux Manager</b>가 어떻게 세계적인 수준의 항공사가 요구하는 속도와 정확성으로 보안 위협에 대응할 수 있게 해주는지 알아볼 것입니다.




## <b class="hovereffect">여러분의 목표:</b>

- OpenSCAP을 사용하여 시스템에 대한 보안 규정 준수 감사를 수행합니다.

- 관련 보안 취약점의 영향을 받는 시스템을 식별합니다.

- 영향을 받는 모든 시스템에 필요한 패치를 동시에 적용합니다.



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




시스템 감사 (Audit your systems)
==================

우리는 프로덕션 시스템이 규정을 준수하는지 확인하기 위해 감사를 수행하고자 합니다.

다음 패키지가 설치되어 있는지 이미 확인했습니다:

- openscap-utils
- scap-security-guide


프로덕션 그룹 선택

- `Systems` ✈ `System Groups`로 이동합시다.
- **prod** 그룹을 찾아 `Use in SSM`을 클릭합니다.
![Next](../assets/SMLM5.1/prod_group_selection.png)

**System Set Manager Overview** 페이지로 이동하게 됩니다. 앞서 보았듯이, 여기서 여러 시스템에 작업을 한 번에 적용할 수 있습니다.

- `Audit` 탭으로 이동합니다.
- `OpenSCAP` 아래에서 다음 세부 정보로 양식을 작성하고, 나머지는 기본값으로 둡니다:
  - **Command-line Arguments:** <b class="highlightcopy">--profile xccdf_org.ssgproject.content_profile_stig</b>
  - **Path to XCCDF document:** <b class="highlightcopy">/usr/share/xml/scap/ssg/content/ssg-sle15-ds.xml</b>
- 다음을 누르십시오:


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">
</p>
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-Schedule.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p>



이 작업에는 몇 분 정도 걸립니다.


결과를 보려면 `Audit` ✈ `OpenSCAP` ✈ `All Scans`로 이동하십시오.

![OpenSCAP Results](../assets/SMLM5.1/openscap_results.png)

이 결과 중 하나를 클릭하면 더 자세한 분석을 볼 수 있습니다.

- **report.html**을 클릭하면 OpenSCAP에서 생성한 보고서의 더 보기 좋은 버전을 볼 수 있습니다.

![Detailed OpenSCAP Results](../assets/SMLM5.1/openscap_results_detailed.png)


보고된 문제에 대해서는 걱정하지 마십시오.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-audit_your_system.gif"/>
  </div>

<br/>



취약점의 영향을 받는 시스템 식별
============================================

어떤 시스템이 취약점의 영향을 받는지 확인하고 싶습니다.

- 이제 `Patches` ✈ `Patch List` ✈ `Relevant`로 이동해 봅시다.

  여기에서 시스템에 사용할 수 있는 모든 관련 패치 목록을 볼 수 있습니다. **Security Patches**를 살펴보겠습니다.

- **Advisory** 이름을 클릭하면 해당 권고가 어떤 패키지와 시스템에 영향을 미치는지 보여주는 상세 페이지를 볼 수 있습니다.

- 목록의 오른쪽에는 **CVEs** 열이 있어 공식 취약점 보고서로 바로 연결되는 링크를 제공합니다.

  자체 패치를 생성하는 것도 가능하지만 이 트랙에서는 다루지 않겠습니다. 자세한 내용은 트랙 끝부분의 링크를 참조하십시오.



## <b class="hovereffect">영향을 받는 시스템 패치</b>

시스템 패치는 다음 단계를 따르는 것만큼 간단합니다:

- `Systems` ✈ `System Set Manager`로 이동합니다.
- `Patches` 탭으로 이동하여 ✈ 드롭다운 목록에서 **Security Advisory**를 선택하고 `Show`를 클릭합니다.

![Select Security Advisory](../assets/SMLM5.1/show_only_security_advisories.png)

- `Select All` 클릭 ✈ `Apply Patches` 클릭 ✈ ![Confirm](../assets/SMLM5.1/bottom-confirm.png)


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-indentify_vulnerabilities.gif"/>
  </div>

<br/>


[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]에 이것이 왜 중요한가요?
=================================================================================


- 신속하게 조치할 수 있음으로써 노출 시간을 줄이고 있습니다. 새로운 취약점이 발견되면 우리와 이를 악용하려는 악의적인 행위자들 간의 경주가 시작됩니다. 복잡하고 수동적인 패치 프로세스는 중요한 시스템을 너무 오랫동안 위험에 노출시킵니다.

- <b class="smlmext">SUSE Multi-Linux Manager</b>는 전체 자산(fleet)의 보안 상태에 대한 단일 통합 뷰를 제공하며 일관되고 신뢰할 수 있는 프로세스로 위협을 해결할 수 있게 해줍니다.

- 다양한 보안 프레임워크에 대한 시스템의 준수 여부를 쉽게 확인할 수 있어 시정 조치를 더 빠르게 구현하고 엄격한 산업 규정을 준수할 수 있습니다.


추가 정보
================


* [감사 (Auditing)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/auditing.html)
* [SUSE 보안 (SUSE Security)](https://www.suse.com/support/security/)
* [OpenSCAP을 이용한 시스템 보안](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/openscap.html)
* [패치 관리 (Manage Patches)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)