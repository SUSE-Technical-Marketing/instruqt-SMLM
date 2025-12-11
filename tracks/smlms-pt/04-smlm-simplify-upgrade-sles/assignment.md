---
slug: smlm-simplify-upgrade-sles
id: t0tpawa1bytl
type: challenge
title: Manutenção simples e confiável
tabs:
- id: avw0kl6hti6f
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: 7lxrnnklhn7q
  title: SLES 15
  type: terminal
  hostname: sles15
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Manutenção simples e confiável
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

Até agora, focamos em gerenciar a diversidade de nossa frota mista e até mesmo em estender a vida útil de nossos sistemas legados. Agora, voltamos nossa atenção para o núcleo de nossa companhia aérea: nossos sistemas carro-chefe <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>).


Pense neles como nossos jatos de longo curso de última geração. Sua confiabilidade é primordial, e mantê-los em condições ideais envolve aplicação de patches e atualizações de serviço regulares e planejadas. Este próximo exercício é exatamente isso: vamos percorrer o processo de uma atualização de versão, uma tarefa comum no gerenciamento do ciclo de vida de qualquer sistema crítico.



E embora estejamos usando SLES como exemplo, lembre-se do princípio chave de nossa torre de controle universal: o processo que você está prestes a realizar é o mesmo que você usaria para qualquer outra distribuição Linux. A interface e a metodologia não mudam.


## <b class="hovereffect">Seus Objetivos:</b>

- Integrar (Onboard) um novo sistema SLES 15 SP5 para servir como nossa aeronave de teste.
- Realizar uma atualização de serviço principal (mayor service upgrade) do SP5 para o SP6.



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






Integração e preparação (Onboarding and preparation)
==========================

Acesse o terminal do sistema na aba [button label="SLES 15" variant="success"](tab-1)


Vamos registrar o sistema dentro do <b class="smlm">SMLM</b> como **sles15**

```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | HOSTNAME="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-sles15sp5 bash ; echo "Wait 45 seconds for it to finish"; sleep 45
```


Agora, vamos mudar para a aba [button label="SMLM UI" variant="success"](tab-0)


Executando a atualização (Executing the upgrade)
=====================

Devemos vê-lo em breve na lista de sistemas, vamos para `Systems` ✈ `System List` ✈ `All`, por favor clique em atualizar no navegador interno se você não o vir.


Vamos clicar nele e ir para `Software` ✈ `Packages` ✈ `Upgrade`.


Para garantir uma migração tranquila, é melhor aplicar as atualizações mais recentes.



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">Clique em </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


Isso pode levar algum tempo para ser concluído.

<br/>


## <b class="hovereffect">Migração de produto</b>


Assim que terminar, por favor vá para `Software` ✈ `Product Migration`



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">Você verá uma seção chamada **Target Products**. Certifique-se de que <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #90ebcd">SUSE Linux Enterprise Server 15 SP6 x86_64</b> esteja selecionado, então pressione: </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; vertical-align: middle; display:block; align:left; padding: 0px;" src="../assets/SMLM5.1/bottom-select_channels.png"/></p>

Será mostrada uma tela de confirmação com um resumo e opções adicionais. Deixe os padrões como estão e clique em: ![Schedule Migration](../assets/SMLM5.1/bottom-schedule_migration.png)

O sistema pedirá para você fazer uma execução de teste (dry run) primeiro, ignore e pressione: ![Confirm](../assets/SMLM5.1/bottom-confirm.png)

Isso levará algum tempo. Para monitorar o status, vá para `Events` ✈ `History` e observe o evento **Product Migration**. Assim que o ícone de status ficar verde, a migração estará concluída. Você pode verificar isso navegando para `Software` ✈ `Software Channels` e confirmando que o sistema agora está inscrito nos novos canais SP6.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/04-simple_and_reliable_maintenance-executing_the_upgrade.gif"/>
  </div>

<br/>

## <b class="hovereffect">Reinicialização Pós-Migração</b>

- Navegue de volta para `Systems` ✈ `System List` ✈ `All`

- Observe que o sistema `sles15` agora tem um ícone de reinicialização ao lado dele:

![Needs reboot icon](../assets/SMLM5.1/icon_needs_reboot.png)

  Isso indica que uma reinicialização é necessária, geralmente devido a uma atualização principal do kernel.

- Clique nele, veremos algo semelhante a isto:

![Needs reboot message](../assets/SMLM5.1/system_requires_a_reboot.png)

- Clique em `Schedule System Reboot` e na tela seguinte clique em ![Reboot System](../assets/SMLM5.1/bottom-reboot_system.png)

> [!NOTE]
> A reinicialização não acontecerá imediatamente.

<br/>


## <b class="hovereffect">A importância do Agendamento (Scheduling)</b>

Agendamos essas ações para acontecer imediatamente, mas isso nem sempre é desejável. O <b class="smlm">SMLM</b> suporta a criação de Janelas de Manutenção (Maintenance Windows) (`Schedule` ✈ `Maintenance Windows`) o que permite garantir que eventos principais como reinicializações ocorram apenas durante esses períodos pré-aprovados.



O agendamento é especialmente útil para sistemas de produção, pois permite mudanças cuidadosamente planejadas em grupos de sistemas e até mesmo implantações "canário" em fases.

<br/>

> [!NOTE]
> É possível fazer live patching do kernel com KLP, o que torna possível aplicar as atualizações de segurança mais recentes aos kernels Linux sem reinicializar.



Por que isso é importante para a [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- As atualizações do sistema e outras tarefas de rotina devem ser simples e repetíveis, caso contrário, corremos o risco de cometer erros dispendiosos. Com essas ferramentas, podemos controlar com precisão quando e onde realizamos ações, agendando a manutenção crítica para nossa frota com confiança.


- Podemos controlar quando e onde realizamos ações, e agendar operações de manutenção em nossa frota em terra.


Mais informações
================

- [Live kernel patching with KLP](https://documentation.suse.com/en-us/sles/15-SP7/html/SLES-all/cha-klp.html)

- [Maintenance Windows](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

- [Administration Guide](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/admin-overview.html)