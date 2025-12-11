---
slug: smlm-automation
id: p8x5n7m9p83r
type: challenge
title: Automação (Opcional)
tabs:
- id: kzwdtkjvrzht
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Automação e gerenciamento de configuração
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

Nesta seção, vamos analisar algumas das opções disponíveis para automatizar tarefas.

Neste laboratório, passamos da execução de tarefas manuais para a criação de alguma automação usando algumas das opções que temos disponíveis.
O <b class="smlmext">SUSE Multi-Linux Manager</b> atua como o "piloto automático" para nossas operações de TI, permitindo-nos impor padrões de configuração e automatizar tarefas de rotina com precisão e confiabilidade em toda a nossa frota.

Em vez de configurar manualmente centenas de servidores e esperar que não percamos uma etapa, definimos o processo e o estado e reduzimos a operação humana para definir um cronograma, uma única vez.



## <b class="hovereffect">Seus Objetivos:</b>

- Criar um cronograma que realize atualizações regularmente em seus sistemas de desenvolvimento.

- Criar um script para mostrar um banner de login diferente dependendo do ambiente do sistema.

Detalhes do laboratório (Lab details)
===========

Usuário (Username):
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```

Senha (Password):
```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

URL do <b class="smlm">SMLM</b>: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>


Configurar atualizações recorrentes (Setup recurring updates)
=======================

Queremos que os desenvolvedores trabalhem com as atualizações estáveis mais recentes fornecidas pela SUSE, mas não podemos confiar que as pessoas se lembrem de atualizar seus sistemas todos os dias, então vamos criar um cronograma recorrente que faça exatamente isso.


Vamos aplicar isso a todos os sistemas no grupo dev para que isso não precise ser feito em cada sistema.

- Vamos para `Systems` ✈ `System Groups`
- Clique no grupo `dev`.

Acabamos de notar que ele não tem sistemas atribuídos, vamos adicionar um.

- Clique em `Target Systems` e selecione `sles15`
- Depois clique em ![Add Systems](../assets/SMLM5.1/bottom-add_system.png)

Agora que temos um sistema, vamos criar a ação recorrente.

- Vá para `Recurring Actions`
- Clique em ![Create](../assets/SMLM5.1/bottom-create.png)
- Agora vamos preencher o formulário com os seguintes detalhes:
	+ **Action Type:** 'Custom state'
 	+ **Schedule Name:** 'Update Dev systems'
	+ **Daily:** '03:00'
	+ **Configure states to execute:** Certifique-se de que **uptodate:** esteja selecionado
	![uptodate Selected](../assets/SMLM5.1/uptodate_selected.png)

- Clique em

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-create_schedule.png"/>
</p>



Para observar nossa lista de ações recorrentes, podemos ir para `Schedule` ✈ `Recurring Actions`

Agora todos os sistemas dev serão atualizados diariamente às 3h UTC.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-setup_recurring_updates.gif"/>
  </div>

<br/>




Certifique-se de que cada sistema tenha uma mensagem de login
==========================================


Vamos criar um canal de configuração para garantir que cada sistema que gerenciamos contenha uma mensagem de login adequada.



- Vamos para `Configuration` ✈ `Channels`
- Clique em ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png)
- Preencha o formulário com os seguintes detalhes:
	+ **Name:** <b class="highlightcopy">Uniform experience</b>
	+ **Label:** <b class="highlightcopy">uniform_experienace</b>
	+ **Description:** <b class="highlightcopy">Create a uniform experience across systems</b>
- Clique em ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png)

Agora que criamos o canal de configuração, vamos preenchê-lo.

- Vá para `Add Files` ✈ `Create File`
- Preencha os seguintes detalhes:
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


- Clique em ![Create Configuration File](../assets/SMLM5.1/bottom-create_configuration_file.png)

Agora vamos inscrever cada sistema na organização no novo canal de configuração.

- Vamos para `Admin` ✈ `Organizations`
- Clique na organização **Organization** (Esta é a organização padrão)
- Vá para `States` e selecione o canal que acabamos de criar.
![Uniform experience selected](../assets/SMLM5.1/selected_univorm_experience_Configurationchannel.png)
- Clique em


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-execute_states.png"/>
</p>


Isso não acontecerá imediatamente, vamos verificar os sistemas. Vamos executar um comando simples via interface web; se executado muito cedo, você poderá ver sistemas com a mensagem antiga e sistemas que já tiveram o arquivo atualizado.

- Vamos para `Salt` ✈ `Remote Commands`
- Digite o seguinte:
![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd.png)
- Clique em `Find targets`
- Você deve ver uma lista de sistemas, clique em `Run command`

Agora você deve ver algo assim:

![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd_first_result.png)

> [!NOTE]
> Este processo pode levar alguns minutos; se você não vir o MOTD, por favor, execute o comando novamente após alguns minutos.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-login_message.gif"/>
  </div>

<br/>


Por que isso é importante para a [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================



- Ao gerenciar milhares de sistemas, não podemos nos dar ao luxo de fazer tudo um por um; as tarefas precisam ser automatizadas para que gerenciemos gado, não animais de estimação.



- Ao definir o "estado correto", eliminamos o desvio de configuração (configuration drift). Cada servidor na frota opera a partir do mesmo manual, assim como cada piloto usa a mesma lista de verificação.



- Tarefas que levariam horas para serem realizadas manualmente em centenas de servidores são concluídas em minutos. Isso libera nossos engenheiros para trabalhar em inovação e melhoria, não em trabalho manual repetitivo.


- A automação é a defesa definitiva contra o erro humano. Uma etapa esquecida ou um erro de digitação durante a configuração manual pode levar a uma interrupção. Um processo automatizado e testado é executado perfeitamente todas as vezes, aumentando a confiabilidade e a segurança de toda a nossa companhia aérea.




Mais informações
================


* [Página do Produto SUSE Multi-Linux Manager](https://www.suse.com/products/suse-manager/)

* [Integração Ansible](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/ansible-integration.html)

* [Guia do Salt](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/specialized-guides/salt/salt-overview.html)