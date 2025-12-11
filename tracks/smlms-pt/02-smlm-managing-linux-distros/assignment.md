---
slug: smlm-managing-linux-distros
id: ert2tslgvzxz
type: challenge
title: Gerenciando diferentes distribuições Linux
tabs:
- id: fcu7orele3rh
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: upqobkpkun0y
  title: Ubuntu 2404 LTS
  type: terminal
  hostname: ubuntu2404lts
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Gerenciando diferentes distribuições Linux
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

Aqui na [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]], o <b class="smlmext">SUSE Multi-Linux Manager</b> é a chave para gerenciar nossa frota diversa de distribuições Linux e arquiteturas a partir de um painel único. Isso nos ajudou a evitar as personalizações extras que costumavam complicar nossos trabalhos como engenheiros, o que por sua vez aumentava o custo e o tempo necessários para manter e implementar nossas políticas de sistema.

Com esta ferramenta, não estamos presos a um único fornecedor, arquitetura ou plataforma de automação. Somos livres para escolher o que precisamos para o nosso ambiente e gerenciá-los todos da mesma maneira. Imagine se para cada tipo de aeronave em nossa frota, precisássemos de uma torre de controle de tráfego aéreo diferente com seu próprio idioma e procedimentos. A complexidade operacional seria incontrolável e os custos seriam proibitivos.

Todos nós sabemos que um determinado modelo de aeronave é melhor para uma rota específica; voar um jumbo jet para um voo de meia hora não é rentável. O mesmo se aplica às nossas distribuições Linux. Embora as próprias distribuições da SUSE sejam excelentes, algumas de nossas aplicações têm requisitos específicos. O <b class="smlm">SMLM</b> garante que nunca fiquemos presos (vendor lock-in) e possamos sempre integrar a melhor solução para a tarefa em questão.


## <b class="hovereffect">Seus Objetivos:</b>

- Integrar (Onboard) um sistema Ubuntu 24.04 LTS, um sistema especializado exigido por nossa equipe de marketing.

- Demonstrar como gerenciamos este sistema novo e diferente usando as mesmas ferramentas e procedimentos de aplicação de patches que o resto de nossa frota.



Detalhes do laboratório
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


Integrando o Ubuntu
=================

Uma nova solicitação de serviço chegou do nosso departamento de marketing. Seus designers gráficos dependem de uma suíte criativa específica que é suportada apenas no Ubuntu. Vamos integrar o sistema deles para que possamos gerenciá-lo e garantir que ele atenda aos nossos padrões de segurança e conformidade, da mesma maneira que fazemos com os outros.

Vamos começar.
<br/>

- Acesse o terminal do sistema na aba [button label="Ubuntu 2404 LTS" variant="success"](tab-1)

  Antes de fazermos quaisquer alterações, vamos verificar de onde ele está obtendo os pacotes:

```bash,run
grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```

Esta estação de trabalho está obtendo software diretamente de repositórios públicos do Ubuntu. Isso apresenta dois problemas: primeiro, não temos controle sobre os patches sendo aplicados, o que é uma preocupação de segurança. Segundo, como a equipe de marketing relatou, toda vez que essas estações de trabalho buscam atualizações, elas podem tornar a conexão de internet do escritório lenta, causando frustração para outros funcionários.


Vamos trazer este sistema para o nosso gerenciamento. Isso resolverá ambos os problemas conectando-o à nossa instância interna do <b class="smlmext">SUSE Multi-Linux Manager</b> para todas as necessidades de software.

Vamos usar a [button label="web UI" variant="success"](tab-0) para fazer isso:

- Em `Home` ✈ `Overview`, vamos clicar em `Register Systems`

- Preencha os seguintes detalhes:

  - **Host:**

  ```txt
  ubuntu2404lts
  ```

  - **User:** (Usuário)

  ```txt
  root
  ```

  - **Password:** (Senha)

  ```txt
  [[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
  ```

  - **Activation Key:** (Chave de ativação)   <b class="highlightcopy">1-ubuntu2404</b>

- Deixe o restante como está e clique em

<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-bootstrap.png"/>


- O processo de registro pode levar alguns minutos para ser concluído, vamos para o [button label="terminal" variant="success"](tab-1) e executar o primeiro comando mais uma vez para ver o que mudou:


```bash,run
echo 'Waiting for the registration to complete' ;while [[ ! -f /etc/apt/sources.list.d/susemanager_bootstrap.sources ]] || [[ ! -f /etc/apt/sources.list.d/susemanager:channels.sources ]]; do echo -n '.'; sleep 5; done ; sleep 60; grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```


Podemos ver que novos arquivos apareceram:

**/etc/apt/sources.list.d/susemanager:***

Eles apontam o sistema para nossos canais gerenciados e controlados centralmente no <b class="smlm">SMLM</b>.


Também podemos ver que o arquivo original, **/etc/apt/sources.list.d/ubuntu.sources**, foi modificado para desabilitar todos os repositórios públicos, mas não foi eliminado; isso nos permitiria reverter facilmente se precisássemos.


> [!NOTE]
> Usar root via SSH com autenticação por senha para registrar é apenas para fins de demonstração e não é recomendado para produção.


> [!NOTE]
> Por padrão, temos que aprovar o registro de cada sistema através da UI ou via linha de comando < salt-key -A -y >, aqui o <b class="smlm">SMLM</b> foi configurado para aprovar automaticamente.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-register_ubuntu.gif"/>
  </div>

<br/>



Agora vamos mudar para a aba [button label="SMLM UI" variant="success"](tab-0)


- Navegamos para `Systems` ✈ `System List` ✈ `All`

  Podemos ver o sistema que acabamos de registrar `Ubuntu2404lts`, note que por padrão ele será registrado sob o nome do host (hostname).

  Vamos clicar nele, iremos diretamente para `Details` - `Overview` onde podemos ver entre outras informações:

  - O status do sistema.
  - Todas as informações como nome do host, endereço IP, tipo de virtualização, Kernel usado e produtos instalados.
  - Os canais nos quais está inscrito.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_overview.gif"/>
  </div>


<br/>

Gerenciando múltiplas distribuições Linux
=====================================


Como mencionado anteriormente, na <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b> usamos diferentes distribuições Linux, assim como usamos diferentes modelos de aviões e companhias. Isso nos ajuda a ficar à frente da concorrência usando o produto mais adequado para cada uma de nossas necessidades.

Com o <b class="smlmext">SUSE Multi-Linux Manager</b> podemos gerenciar todos eles com os mesmos procedimentos, os mesmos agendamentos, etc., usando a mesma interface e mecanismos.

Abaixo exploraremos como realizar diferentes tarefas em seus sistemas, seguindo o mesmo processo independentemente de qual SO nossos sistemas estejam executando, sem ter que criar personalizações desnecessárias.


## <b class="hovereffect">Adicionar informações extras</b>


Vamos continuar com o sistema que acabamos de registrar, vamos adicionar algumas configurações e informações a ele:

- Vamos clicar em `Properties`, onde adicionaremos informações extras sobre o sistema e alteraremos algumas configurações.


  - Habilitar aplicação automática de patches (Enable Automatic application of patches):

  <img style='vertical-align: middle; height: 60%; width: 60%; object-fit: contain' src="../assets/SMLM5.1/option-auto_patch_update-enabled.png"/>

    Isso aplicará patches automaticamente no sistema quando houver patches relevantes.



  - Adicione os seguintes detalhes para o sistema:


| Campo | Conteúdo                                                  |
| ---: | :-----                                                    |
| **Description** | <b class="highlightcopy">Multimedia workstation for graphics designers.</b> |
| **Facility Address** | <b class="highlightcopy">Candy eye street, 1</b> |
| **City** | <b class="highlightcopy">Aeolia</b> |
| **Building** | <b class="highlightcopy">Belem Tower 4</b> |
| **Room** | <b class="highlightcopy">Sierra nevada</b> |


<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-Update_Properties.png"/>



- Vamos ver em qual hardware ele está rodando:

  - Clique em `Details` ✈ `Hardware`


<br/>

> [!NOTE]
> Tudo isso pode ser automatizado através da API.

<br/>

Agora vamos adicionar algumas informações extras ao sistema usando chaves personalizadas, essas informações podem ser facilmente consumidas em seus scripts de automação posteriormente.


- Clique em `Details` ✈ `Custom Info`

<img style='vertical-align: top; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Create_Value.png"/>

- Clique em `application` e preencha o **value** (valor) com o seguinte:

```text
Logo Wings designer pro
```

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Update_Key.png"/>


<br/>

> [!NOTE]
> Já criamos a chave personalizada **application** para você, se você quiser criar suas próprias chaves é tão simples quanto ir em: `Systems` ✈ `Custom System Info` ✈ `Create key`

<br/><br/>

Vamos voltar para a lista de Systems

`Systems` ✈ `System List` ✈ `All`


Vamos clicar em qualquer um dos sistemas e ir para `Details` ✈ `Custom Info`.

Já preenchemos cada sistema com um valor,

<br/>

Agora vá para `Details` ✈ `Overview` e note **Installed Products** e **Subscribed Channels**, estes são diferentes dos do seu sistema Ubuntu porque eles estão executando um sistema operacional diferente.



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_properties.gif"/>
  </div>

<br/>


## <b class="hovereffect">Executar comandos em múltiplos sistemas de uma vez</b>


Vamos fazer algo em todos os sistemas que temos, volte para `Systems` ✈ `System List` ✈ `All` e selecione todos:

<img style='vertical-align: middle; margin: 2px; height: 50%; width: 50%; object-fit: contain' src="../assets/SMLM5.1/select_all_systems.png"/>

Observe a coluna **Base Channel**, temos sistemas executando três SOs diferentes.

<br/>

Tendo selecionado todos os sistemas que queremos operar, vamos realizar uma ação em grupo:

`Systems` ✈ `System Set Manager`

Vamos executar um comando em todos eles, para isso podemos ir em:

`Misc` ✈ `Remote Command`

então preencha os seguintes detalhes e deixe o restante com os valores padrão:


Script:

```bash,run
cat /etc/os-release
```

Não modifique o agendamento (schedule), queremos que ele seja executado o mais rápido possível, clique em:

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Schedule.png"/>


<br/>


<br/><br/>

Você verá um aviso azul no topo indicando que a tarefa foi agendada.

Vamos ver os resultados, para isso iremos em:

`Schedule` ✈ `Completed Actions`

Veremos uma lista de ações, no campo **Filter by Action** digite:

```text
Run
```
Clique na entrada superior que aparece na lista, deve ser semelhante a esta:

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/Select_complete_action_run.png"/>


Lá podemos ir em **Completed Systems** e examinar o resultado clicando no nome do sistema.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-multiple_systems_at_once.gif"/>
  </div>

<br/>


<br/><br/>

Com isso completamos esta parte, veremos mais exemplos de como podemos gerenciar múltiplos sistemas Linux ao longo do workshop.



Por que isso é importante para a [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- Sem dependência de fornecedor (no vendor lock-in), mantenha a liberdade de escolha e a flexibilidade para reagir rápido às mudanças de mercado.

- Simplifique e economize tempo evitando trabalho extra em personalizações.

- Uma UI única para gerenciar tudo reduz a complexidade e tornará a futura solução de problemas, escalonamento, aplicação de patches e automação muito mais ágeis e menos demorados.



Mais informações
================

Para uma lista das distribuições suportadas, por favor visite:

[SMLM - Supported Clients and Features](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/client-configuration/supported-features.html)