---
slug: smlms-intro
id: pxlhl1w90bxo
type: challenge
title: Bem-vindo ao SUSE Multi-Linux Hands-on Workshop!
teaser: Bem-vindo ao SUSE Multi-Linux Hands-on Workshop! Nesta seção apresentaremos
  você ao workshop e aos seus principais componentes. o workshop e seus principais
  componentes.
notes:
- type: text
  contents: |
    # Bem-vindo ao SUSE Multi-Linux Hands-on Workshop!
    Por favor, aguarde enquanto configuramos seu ambiente de laboratório.
    <img class="logos" src="../assets/logos/suse_logo.svg"/>
tabs:
- id: atpfcofoqgsj
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: ""
enhanced_loading: null
---

Bem-vindo ao <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">SUSE</b> Multi-Linux Hands-on Workshop
==================================================================

<link  rel="stylesheet" href="https://raw.githubusercontent.com/SUSE-Technical-Marketing/lab-setup/refs/heads/develop/web/css/instruqt.css" type="text/css" crossorigin="anonymous" fetchpriority="high" />

<style type="text/css">

  @import url("https://raw.githubusercontent.com/SUSE-Technical-Marketing/lab-setup/refs/heads/develop/web/css/instruqt.css");
  @import "https://raw.githubusercontent.com/SUSE-Technical-Marketing/lab-setup/refs/heads/develop/web/css/instruqt.css";

  * {
    font-family: suse;
    src: url('https://fonts.google.com/specimen/SUSE');
/*    background-color: #30ba78; */
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
  .highlightcopy {
    color: white;
    font-weight: bold;
    padding: 0 10px;
  }


</style>


<img class="logos" alt="Welcome!" src="../assets/logos/01-welcome.jpeg"/>

Neste workshop você explorará um pouco da mágica que o <b class="smlmext">SUSE Multi-Linux Manager</b> (<b class="smlm">SMLM</b>) pode fazer; é a solução da <b class="suse">SUSE</b> para gerenciar múltiplas distribuições Linux em escala a partir de uma interface unificada. E também descobrirá como manter seus servidores de produção legados suportados com o <b class="smlsext">SUSE Multi-Linux Support</b> (<b class="smls">SMLS</b>), nossa solução de suporte profissional e confiável para sistemas Linux.

&emsp;&emsp; Você assumirá o papel de um **engenheiro** na <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b>, uma companhia aérea onde cada avião possui um servidor Linux a bordo.

&emsp;&emsp; Assim como qualquer componente de um avião, é crítico que esses servidores permaneçam estáveis e confiáveis, não importa se estão localizados no solo em algum datacenter ou voando acima das nuvens ☁ ☁ ☁


&emsp;&emsp; Alguns modelos de avião exigirão um tipo diferente de Linux, ou uma arquitetura de CPU diferente. Isso não é um problema para o <b class="smlm">SMLM</b>; você é livre para escolher a distribuição Linux e a arquitetura de CPU que melhor atenda às suas necessidades sem ter que abrir mão da padronização e gerenciamento fáceis.


&emsp;&emsp; Como engenheiro responsável pelo gerenciamento do ambiente Linux, você passará por algumas das soluções que o <b class="smlm">SMLM</b> e o <b class="smls">SMLS</b> oferecem para facilitar e automatizar o gerenciamento de sistemas e resolver problemas excepcionais que possam ocorrer.


Ao longo dos diferentes desafios, você terá as seguintes ferramentas disponíveis:

 ✈ **SUSE Multi-Linux Manager**:
   O painel único para gerenciar toda a sua pilha Linux.

 ✈ **Centos 7**:
   Uma distribuição legada ainda em uso em algumas aeronaves mais antigas e sistemas terrestres.

 ✈ **Ubuntu 24**: Uma distribuição Linux específica exigida pelo nosso departamento de marketing para executar seus aplicativos de design gráfico.

 ✈ **SLES 15**: A distribuição Linux altamente confiável, estável e segura da <b class="suse">SUSE</b> que forma a espinha dorsal dos nossos sistemas mais críticos.


## <b class="smlmext hovereffect">SUSE Multi-Linux Manager</b>

É uma solução de gerenciamento de infraestrutura de código aberto líder em sua classe para sua infraestrutura definida por software.

&emsp;&emsp; O <b class="smlmext">SUSE Multi-Linux Manager</b> foi projetado para ajudar suas equipes empresariais de DevOps e Operações de TI a reduzir a complexidade e recuperar o controle de seus ativos de TI, uma ferramenta única, mas muito poderosa, para gerenciar sistemas Linux em uma variedade de arquiteturas de hardware, hipervisores, bem como plataformas de contêineres, IoT e nuvem.

&emsp;&emsp; Ele automatiza o provisionamento, aplicação de patches e configuração de servidores Linux e dispositivos IoT para uma implantação de servidores mais rápida, consistente e repetível, ajudando a otimizar as operações e reduzir custos. E com monitoramento automatizado, rastreamento, auditoria e relatórios de seus sistemas, VMs e contêineres em seus ambientes de desenvolvimento, teste e produção, você pode garantir a conformidade com as políticas de segurança internas e regulamentações externas.


## <b class="smlsext hovereffect">SUSE Multi-Linux Support</b>


É um serviço abrangente que oferece assistência técnica e manutenção para várias distribuições Linux, incluindo seu Red Hat Enterprise Linux (RHEL) existente, CentOS, <b class="liberty">SUSE Liberty Linux</b> e <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>), dependendo da oferta.

&emsp;&emsp; Permite às organizações gerenciar ambientes Linux mistos de forma eficiente sob uma única estrutura de suporte.
Dependendo do pacote adquirido, o <b class="smlsext">SUSE Multi-Linux Support</b> também pode incluir o <b class="smlmext">SUSE Multi-Linux Manager</b>, uma ferramenta de gerenciamento multi-Linux para gerenciar essas distribuições.



 🌅 Explore a Instruqt UI
=======================
Antes de começarmos nossa primeira tarefa, vamos dedicar um momento para observar a Instruqt UI.

+ O **lado direito** da tela fornece estas instruções e controles de navegação.

+ O **lado esquerdo** dá acesso às várias máquinas e serviços que compõem nosso ambiente de laboratório.

Dentro da Instruqt UI você pode alternar entre a [button label="SMLM UI" variant="success"](tab-0) e os [button label="terminals" variant="success"](tab-1) disponíveis clicando nas abas na parte superior do painel esquerdo.


> [!NOTE]
> Nenhum recarregamento automático acontece na web UI; em alguns casos, você pode precisar recarregar o navegador web interno do Instruqt para ver as atualizações.


🛫 Fazendo login no <b class="smlmext">SUSE Multi-Linux Manager</b> 🛫
========================================
Vamos familiarizá-lo com o ambiente.

- Abra o <b class="smlmext">SUSE Multi-Linux Manager</b> dentro do laboratório a partir da [button label="SMLM UI" variant="success"](tab-0)


- Faça login com as seguintes credenciais:

  - Username:
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```
  - Password:

```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

Se tudo correu bem, você deve ver a página **Overview** na UI do <b class="smlmext">SUSE Multi-Linux Manager</b> logado como o usuário `[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]`.

> [!NOTE]
> Se você deseja acessar a UI do <b class="smlmext">SUSE Multi-Linux Manager</b> diretamente através do seu navegador, você também pode:

URL do <b class="smlm">SMLM</b>: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>


> [!NOTE]
> Se a página não carregar corretamente, você pode precisar atualizar a aba do navegador após o ambiente de laboratório ter terminado de inicializar.




🗺  Explore o <b class="smlmext">SUSE Multi-Linux Manager</b> 🗺
======================================

Antes de decolarmos, vamos nos familiarizar com os controles. Isso não pretende ser um tour exaustivo, mas uma breve visão geral dos principais instrumentos que usaremos ao longo do workshop. Encorajamos você a ser curioso e explorar.


Vamos começar.


- **Menu Systems** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_systems.png"/>

  No painel esquerdo, clique em `systems`. Esta é a visão geral da nossa frota, mostrando cada servidor registrado. A lista é pequena agora, mas crescerá à medida que completarmos nossos exercícios.

   - **System Lists**

     Esta seção fornece visualizações convenientes e pré-filtradas. Por exemplo, a lista `Out of Date` mostra instantaneamente quais servidores requerem atualizações, poupando você de realizar uma busca manual. </p>

  <br/>

  - **System Groups**

    Para organizar nossa frota logicamente, usamos `System Groups`; você pode categorizá-los com base em qualquer critério. Ao fazer isso, você pode economizar tempo ao aplicar ações ou definir políticas. Uma vez criados, você pode anexar sistemas automaticamente a um ou múltiplos grupos, por exemplo, usando `activation keys`.


    Sinta-se à vontade para tentar criar um agora clicando em `+ Create Group`.

  <br/>

  - **Operações em lote**

    O `System Set Manager` fornece uma maneira poderosa de realizar ações em múltiplos sistemas simultaneamente.


    Em vez de aplicar alterações uma a uma, você pode selecionar uma coleção de sistemas, individualmente a partir da System List ou aproveitando System Groups existentes, e então executar tarefas em todos eles em uma única operação.

  <br/>

  - **Provisioning**

    O <b class="smlmext">SUSE Multi-Linux Manager</b> fornece ferramentas abrangentes para o provisionamento de novos sistemas e o reprovisionamento de existentes. Essa capacidade ajuda você a estabelecer um processo padronizado e repetível para a implantação de sistemas.


    Por exemplo, dentro da seção `Autoinstallation`, você pode definir distribuições e perfis Kickstart/AutoYaST, o que permite especificar como seus sistemas devem ser implantados, qual software terão instalado, como o espaço de armazenamento será distribuído e muito mais.


    Todos esses mecanismos de automação simples de configurar podem ser combinados com soluções de automação complexas, mas mais poderosas, como Salt ou Ansible, mantendo sua liberdade de escolher a melhor solução para cada desafio.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_systems.gif"/>
  </div>

<br/>



- **Menu Patches** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_patches.png"/>

  - **Patching**

    Uma das tarefas mais comuns em TI é manter os sistemas atualizados e, de tempos em tempos, aplicar patches de segurança às pressas!
    Com o SMLM podemos ver facilmente uma lista de patches **relevantes**, classificados por tipo e fornecidos com todas as informações que você pode precisar saber, incluindo todos os sistemas e pacotes que eles afetam.

    Além dos patches fornecidos pelo fornecedor, também podemos criar nossos próprios patches. Mais tarde, exploraremos as diferentes opções que temos para gerenciar o patching e as atualizações regulares em toda a nossa frota.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_patches.gif"/>
  </div>

<br/>
- **Software channels** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_software.png"/>

  Em `Channel List` podemos ver todos os canais/repositórios/fluxos de pacotes disponíveis para consumo; você também pode criar novos canais de software para organizar seu software ou fazer upload de seus próprios pacotes.

  Todos os canais que você vê atualmente foram recuperados pelo SMLM das fontes oficiais e podem ser mantidos sincronizados facilmente.

  Em `Package Search` somos capazes de pesquisar pacotes específicos e inspecionar seu conteúdo e metadados.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_software.gif"/>
  </div>

<br/>

- **Configuration** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_configuration.png"/>

  Também é possível gerenciar e aplicar configurações específicas aos sistemas, no momento do registro ou posteriormente; para isso podemos inspecionar a seção `Configuration`.

  O SMLM fornece uma maneira fácil de gerenciar revisões, implantar e comparar arquivos de configuração entre sistemas. E tudo pode ser facilmente agrupado em canais de configuração.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_configuration.gif"/>
  </div>

<br/>

- **Scheduling** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_schedule.png"/>

  Em `Schedule` podemos observar e gerenciar ações agendadas, definir janelas de manutenção específicas. Isso é especialmente útil para automatizar operações regulares ou realizar implantações canário (canary deployments) ao gerenciar muitos sistemas. Veremos isso em ação mais tarde durante o workshop.

<br/>
<br/>

O SUSE Multi-Linux Manager oferece muitas possibilidades para gerenciar seus sistemas; não podemos cobrir todas elas neste workshop mas, como sempre, sinta-se à vontade para fazer perguntas e explorar.

> [!NOTE]
> Seu usuário tem privilégios totais de administrador, portanto, recomendamos fazer alterações apenas após ter terminado os exercícios.
````
