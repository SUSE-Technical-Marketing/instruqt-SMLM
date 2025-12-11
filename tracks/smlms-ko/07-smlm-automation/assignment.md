---
slug: smlm-automation
id: usdep4sycxi2
type: challenge
title: 자동화 (선택 사항)
tabs:
- id: rj2brv6kitnr
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 자동화 및 구성 관리
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

<img class="logos" alt="Welcome!" src="../assets/logos/07-automation.jpeg"/>

이 섹션에서는 작업을 자동화하는 데 사용할 수 있는 몇 가지 옵션을 살펴보겠습니다.

이 실습에서는 수동 작업을 수행하는 것에서 벗어나, 우리가 사용할 수 있는 몇 가지 옵션을 사용하여 자동화를 생성하는 단계로 넘어갑니다.
<b class="smlmext">SUSE Multi-Linux Manager</b>는 IT 운영을 위한 "자동 조종 장치(autopilot)" 역할을 하여, 전체 자산(fleet)에 걸쳐 구성 표준을 시행하고 일상적인 작업을 정밀하고 신뢰성 있게 자동화할 수 있도록 합니다.

수백 대의 서버를 수동으로 구성하면서 단계를 놓치지 않기를 바라는 대신, 프로세스와 상태를 정의하고 사람의 작업을 줄여 스케줄을 단 한 번 정의합니다.



## <b class="hovereffect">여러분의 목표:</b>

- 개발 시스템에서 정기적으로 업데이트를 수행하는 스케줄을 생성합니다.

- 시스템 환경에 따라 다른 로그인 배너를 표시하는 스크립트를 생성합니다.

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


반복 업데이트 설정 (Setup recurring updates)
=======================

우리는 개발자들이 SUSE에서 제공하는 최신 안정 업데이트로 작업하기를 원하지만, 사람들이 매일 시스템을 업데이트하는 것을 기억할 것이라고 기대할 수는 없습니다. 따라서 정확히 그 작업을 수행하는 반복 스케줄을 생성할 것입니다.


이것을 dev 그룹의 모든 시스템에 적용하여 각 시스템에서 개별적으로 수행할 필요가 없도록 하겠습니다.

- `Systems` ✈ `System Groups`로 이동합시다.
- `dev` 그룹을 클릭합니다.

시스템이 할당되지 않은 것을 확인했습니다. 하나 추가해 봅시다.

- `Target Systems`를 클릭하고 `sles15`를 선택합니다.
- 그런 다음 ![Add Systems](../assets/SMLM5.1/bottom-add_system.png)을 클릭합니다.

이제 시스템이 생겼으므로 반복 작업(recurring action)을 생성해 봅시다.

- `Recurring Actions`로 이동합니다.
- ![Create](../assets/SMLM5.1/bottom-create.png)을 클릭합니다.
- 이제 다음 세부 정보로 양식을 채워봅시다:
	+ **Action Type:** 'Custom state'
 	+ **Schedule Name:** 'Update Dev systems'
	+ **Daily:** '03:00'
	+ **Configure states to execute:** **uptodate:**가 선택되어 있는지 확인하십시오.
	![uptodate Selected](../assets/SMLM5.1/uptodate_selected.png)

- 다음을 클릭합니다:

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-create_schedule.png"/>
</p>



반복 작업 목록을 확인하려면 `Schedule` ✈ `Recurring Actions`로 이동하면 됩니다.

이제 모든 개발(dev) 시스템은 매일 UTC 시간으로 오전 3시에 업데이트됩니다.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-setup_recurring_updates.gif"/>
  </div>

<br/>




모든 시스템에 로그인 메시지가 있는지 확인
==========================================


우리가 관리하는 모든 시스템에 적절한 로그인 메시지가 포함되어 있는지 확인하기 위해 구성 채널(configuration channel)을 생성할 것입니다.



- `Configuration` ✈ `Channels`로 이동합시다.
- ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png)을 클릭합니다.
- 다음 세부 정보로 양식을 채웁니다:
	+ **Name:** <b class="highlightcopy">Uniform experience</b>
	+ **Label:** <b class="highlightcopy">uniform_experienace</b>
	+ **Description:** <b class="highlightcopy">Create a uniform experience across systems</b>
- ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png)을 클릭합니다.

이제 구성 채널을 생성했으므로 채워보겠습니다.

- `Add Files` ✈ `Create File`로 이동합니다.
- 다음 세부 정보를 입력합니다:
	+ **Filename/Path:** <b class="highlightcopy">/etc/motd</b>
	+ **File Contents:**
<pre>
This system is the property of [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]].

Server ID: {{ grains['id'] }}
{%- if 'custom_info' in pillar %}
{%- if 'application' in pillar['custom_info'] %}
Running Application "{{ pillar['custom_info']['application'] }}"
{%- else %}
No applications running on this server
{%- endif %}
{%- else %}
No applications running on this server
{%- endif %}
</pre>


- ![Create Configuration File](../assets/SMLM5.1/bottom-create_configuration_file.png)을 클릭합니다.

이제 조직 내의 모든 시스템이 새 구성 채널을 구독하도록 합시다.

- `Admin` ✈ `Organizations`로 이동합시다.
- **Organization** 조직을 클릭합니다 (이것이 기본 조직입니다).
- `States`로 이동하여 방금 생성한 채널을 선택합니다.
![Uniform experience selected](../assets/SMLM5.1/selected_univorm_experience_Configurationchannel.png)
- 다음을 클릭합니다:


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-execute_states.png"/>
</p>


이 작업은 즉시 수행되지 않습니다. 시스템을 확인해 봅시다. 웹 UI를 통해 간단한 명령을 실행할 것입니다. 너무 일찍 실행하면 이전 메시지가 있는 시스템과 파일이 이미 업데이트된 시스템을 볼 수 있습니다.

- `Salt` ✈ `Remote Commands`로 이동합시다.
- 다음을 입력합니다:
![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd.png)
- `Find targets`를 클릭합니다.
- 시스템 목록이 보일 것입니다. `Run command`를 클릭하십시오.

이제 다음과 같은 내용을 볼 수 있을 것입니다:

![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd_first_result.png)

> [!NOTE]
> 이 프로세스는 몇 분 정도 걸릴 수 있습니다. MOTD가 보이지 않으면 몇 분 후에 명령을 다시 실행해 주십시오.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-login_message.gif"/>
  </div>

<br/>


[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]에 이것이 왜 중요한가요?
=================================================================================



- 수천 개의 시스템을 관리할 때 모든 것을 하나씩 수행할 여유가 없습니다. 작업을 자동화하여 반려동물(pets)이 아닌 가축(cattle)처럼 관리해야 합니다.



- "올바른 상태(correct state)"를 정의함으로써 구성 드리프트(configuration drift)를 제거합니다. 모든 조종사가 동일한 체크리스트를 사용하는 것처럼, 자산(fleet)의 모든 서버는 동일한 플레이북으로 작동합니다.



- 수백 대의 서버에서 수동으로 수행하는 데 몇 시간이 걸리던 작업이 몇 분 만에 완료됩니다. 이를 통해 엔지니어는 반복적인 수작업이 아닌 혁신과 개선 작업에 집중할 수 있습니다.


- 자동화는 사람의 실수에 대한 궁극적인 방어책입니다. 수동 구성 중에 단계를 잊어버리거나 오타를 내면 중단이 발생할 수 있습니다. 자동화되고 테스트된 프로세스는 매번 완벽하게 실행되어 전체 항공사의 신뢰성과 보안을 향상시킵니다.




추가 정보
================


* [SUSE Multi-Linux Manager 제품 페이지](https://www.suse.com/products/suse-manager/)

* [Ansible 통합](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/ansible-integration.html)

* [Salt 가이드](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/specialized-guides/salt/salt-overview.html)