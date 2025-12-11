---
slug: smlm-lifecycle-management
id: zqszqtz35lti
type: challenge
title: Gerenciamento do ciclo de vida
tabs:
- id: e9wc8ofxjfqj
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Gerenciamento do ciclo de vida
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

<img class="logos" alt="Welcome!" src="../assets/logos/05-lifecycle.jpeg"/>

Nesta parte, faremos a transição de tarefas de manutenção individuais para estabelecer um processo certificado em toda a frota para gerenciar mudanças. Exploraremos como o Gerenciamento do Ciclo de Vida do Conteúdo no <b class="smlmext">SUSE Multi-Linux Manager</b> fornece a estrutura e a segurança que nossa companhia aérea exige.



Na [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]], uma nova peça não é instalada em um jato de passageiros no momento em que chega do fabricante. Ela passa por um rigoroso processo de certificação.

Primeiro, é examinado e testado em uma oficina controlada (**Desenvolvimento**). Em seguida, é instalado em uma aeronave de teste não comercial e submetido a testes extenuantes em solo e voo (**Garantia de Qualidade - QA**). Somente após passar por todas as verificações concebíveis é que é certificado para instalação em nossa frota ativa (**Produção**).



Essa abordagem metódica e em etapas evita que um único componente defeituoso impeça um avião de voar, garantindo a segurança de nossos passageiros e a confiabilidade de nossas operações. Aplicamos exatamente a mesma filosofia aos nossos sistemas de TI. Uma atualização de software ou um novo aplicativo é um "componente" que, se defeituoso, pode interromper nossas operações digitais. O Gerenciamento do Ciclo de Vida do Conteúdo é nosso processo oficial de certificação para todas as alterações de software.



## <b class="hovereffect">Seus Objetivos:</b>

- Construir um Projeto de Ciclo de Vida de Conteúdo (Content Lifecycle Project).

- Usar o projeto para gerenciar e certificar atualizações de software para nossos sistemas.



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


Construindo Nosso Caminho de Certificação de Software
==============================================

Neste exercício, criaremos um Projeto de Ciclo de Vida de Conteúdo para controlar o fluxo de atualizações de software. Isso garante que um patch seja exaustivamente testado antes de chegar aos nossos servidores de produção críticos.

<br/>

Nosso objetivo é construir um pipeline `Dev ✈ QA ✈ Prod`.

1.  **Desenvolvimento (Dev):** A oficina inicial. Todos os novos patches e pacotes chegam aqui primeiro.
2.  **Garantia de Qualidade (QA):** O campo de testes. Promoveremos uma versão específica do conteúdo de Dev para QA para que nossas equipes de teste validem.
3.  **Produção (Prod):** A frota ativa. Apenas o conjunto de patches aprovado e certificado pelo QA é promovido para a Produção, onde pode ser aplicado com segurança aos nossos sistemas ativos.



<br/>

## <b class="hovereffect">Criar o projeto</b>

- Navegue para `Content Lifecycle` ✈ `Projects` e clique em ![Create Project](../assets/SMLM5.1/bottom-create_project.png)

- Preencha os detalhes do projeto:

- **Project Name** (Nome do Projeto):

```txt
Airtrain SLES15 SPx
```

- **Project Label** (Rótulo do Projeto):

```txt
at-sles15_spx
```

- **Project Description** (Descrição do Projeto):

```txt
Certified software channel for Airtrain SLES 15 systems.
```


- Clique em ![Create](../assets/SMLM5.1/bottom-create.png)

Agora vamos preenchê-lo, clique em `Attach/Detach Sources`

![Create](../assets/SMLM5.1/content_lifecycle_just_created.png)

- Em **New Base Channel** selecione <b class="sles">SLE-Product-SLES15-SP6-Pool for x86_64</b> e clique em ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">Criar ambiente de Desenvolvimento (Dev)</b>

Crie o Ciclo de Vida do Ambiente de Desenvolvimento

- Clique em `Add Environment`

![Create](../assets/SMLM5.1/content_lifecycle_just_created_environment_lifecycle.png)

- Preencha com o seguinte:
  * **Name:** <b class="highlightcopy">Development</b>
  * **Label:** <b class="highlightcopy">dev</b>

- Clique em ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">Criar ambiente de QA</b>

Crie o Ciclo de Vida do Ambiente de Garantia de Qualidade

- Clique em `Add Environment`

- Preencha com o seguinte:
  * **Name:** <b class="highlightcopy">QA</b>
  * **Label:** <b class="highlightcopy">qa</b>

- Clique em ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">Criar ambiente de Prod</b>

Crie o Ciclo de Vida do Ambiente de Produção

- Clique em `Add Environment`

- Preencha com o seguinte:
  * **Name:** <b class="highlightcopy">Production</b>
  * **Label:** <b class="highlightcopy">prod</b>

- Clique em ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">Preencher (Populate)</b>

Agora que temos todos os três ambientes, vamos preenchê-los com conteúdo.

Não usaremos um filtro neste caso, pois o <b class="sles">SLES</b> já fornece versões estáveis de pacotes.

A cadência de testes da [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] é atualmente de um mês, então nomearemos esta compilação (build) com o mês atual, Outubro.

- Clique em ![Build](../assets/SMLM5.1/bottom-build.png)

- Em **Version Message** digite:

```txt
October
```


- Clique em `Build`

> [!NOTE]
> Este processo pode levar alguns minutos, você verá algumas etapas como 'cloning' (clonagem), mas pode ficar aliviado ao saber que isso não requer muito armazenamento. O processo de clonagem aplica-se apenas aos pontos de índice do pacote, não aos pacotes reais em si.


<br/>

## <b class="hovereffect">Promovendo conteúdo</b>

Agora, vamos promover o conteúdo para estágios posteriores.

- Clique no botão `Promote` entre Development e QA
- Outra tela com o título **Promote version 1 into QA** aparecerá, apenas clique em `Promote` novamente.

Repita o mesmo passo para Production (Produção).


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-create_the_project.gif"/>
  </div>

<br/>

Atualizar nossos sistemas.
====================

Agora vamos testar como funciona.

Nós vamos:
- adicionar alguns de nossos sistemas ao novo ambiente.
- Criar uma nova versão do conteúdo.
- Promover a nova versão e atualizar os sistemas.

<br/>

## <b class="hovereffect">Adicionar sistemas</b>

Vamos para `Systems` ✈ `System List` ✈ `All`

- Clique no sistema **at-ct-qa**
- Vá para `Software` ✈ `Software Channels`
- Em **Custom Channels**, selecione a caixa de seleção para o canal **at-sles15_spx-qa-...** e clique em ![Next](../assets/SMLM5.1/bottom-next.png)
- Clique em ![Confirm](../assets/SMLM5.1/bottom-confirm.png)


Volte para `Systems` ✈ `System List` ✈ `All`

- Filtre por:

```txt
at-
```

- Selecione todos os sistemas que terminam em **-pro**
- Vá para `Systems` ✈ `System Set Manager`
- Vá para `Channels`
- Em **Custom Channels**, selecione a caixa de seleção para o canal **at-sles15_spx-prod-...** e clique em ![Next](../assets/SMLM5.1/bottom-next.png)
- Clique em 'include recommended' (incluir recomendados) para se inscrever em todos os canais recomendados:

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-next.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-add_systems.gif"/>
  </div>

<br/>

## <b class="hovereffect">Criar uma nova versão</b>


Um mês se passou e queremos continuar com nosso processo estável de atualizações.
Você vai criar uma cópia estática e imutável dos canais de software para a equipe de Desenvolvedores.

Nenhum patch novo aparecerá de repente e interromperá o trabalho deles.

- Volte para `Content Lifecycle` ✈ `Projects` e clique no projeto que acabamos de criar.

- Clique em ![Build](../assets/SMLM5.1/bottom-build.png)

- Em **Version Message** digite:

```txt
November
```


- Clique em `Build`

Note que o número da versão aumentou automaticamente.

Agora os desenvolvedores podem fazer seu trabalho usando as versões novas e corrigidas de bibliotecas e aplicativos fornecidos pela SUSE.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-create_new_version.gif"/>
  </div>


<br/>

## <b class="hovereffect">Promover conteúdo de Dev para QA</b>

Vamos assumir que nossos desenvolvedores deram sua aprovação. É hora de criar uma versão estável para a equipe de QA para que todos os testes de pré-produção possam ser realizados.

- Clique no botão `Promote` entre Development e QA
- Outra tela com o título **Promote version 2 into QA** aparecerá, apenas clique em `Promote` novamente.

Agora vamos aos nossos sistemas de QA e fazer uma atualização.

- `Systems` ✈ `System List` ✈ `All`
- Clique no sistema **at-ct-qa**
- Vá para `Software` ✈ `Packages` ✈ `Upgrade`
- Clique em:

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


Agora nossos engenheiros de QA podem realizar seus testes com segurança, sem interrupções.


> [!NOTE]
> Não temos tempo suficiente para ver as mudanças chegando, em um cenário real, deveria haver novas versões de pacotes disponíveis para promover na versão 2.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-promote_from_dev_to_QA.gif"/>
  </div>


<br/>

## <b class="hovereffect">Promover para Produção</b>

A equipe de QA concluiu seus testes rigorosos na `v2` e a certificou como estável e segura para a frota principal. É hora de disponibilizá-la para nossos sistemas de produção.

Vamos repetir o mesmo processo que fizemos para QA em nosso ambiente de produção:

- Primeiro, promova o conteúdo.
  Isso tornará os novos pacotes disponíveis para nossos servidores de produção.
  Você garantiu com sucesso que apenas atualizações testadas e aprovadas possam chegar aos seus sistemas mais críticos.

- Segundo, atualize nossos sistemas de Produção; aqui a única diferença é que vamos agendar a atualização para **amanhã às 14:00** para permitir que todas as nossas equipes estejam preparadas e tenham um processo controlado.


<br/>

Por que isso é importante para a [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- Nós construímos uma série de portões de segurança, facilitando a implementação de um princípio central de nossa estratégia operacional: **gerenciamento de riscos**.
- Um único patch ruim introduzido no ambiente de **Dev** pode ser detectado e corrigido muito antes de ter a chance de impactar os sistemas geradores de receita.
- Este processo transforma a aplicação de patches e atualizações de um evento arriscado e estressante em um procedimento de manutenção rotineiro e previsível, a pedra angular de uma companhia aérea confiável.


<br/>

Mais informações
================

* [Janelas de Manutenção](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

* [Gerenciamento de Patches](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)

* [Gerenciamento do Ciclo de Vida do Conteúdo](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/content-lifecycle.html)

* [Página do Produto SUSE Multi-Linux Manager](https://www.suse.com/products/suse-manager/)