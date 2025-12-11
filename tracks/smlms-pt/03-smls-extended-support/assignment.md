---
slug: smls-extended-support
id: sie98oecg4mc
type: challenge
title: Suporte estendido para sistemas legados
tabs:
- id: taqtjirbchx9
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: phxp991xzugu
  title: CentOS 7 QA
  type: terminal
  hostname: centos7
- id: qdqmescg3uy0
  title: CentOS 7 Prod
  type: terminal
  hostname: zzcentos7
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Suporte estendido para sistemas legados
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

# Estendendo a Vida Útil da Nossa Frota Legada

Em qualquer companhia aérea, você tem aviões mais antigos e confiáveis que o serviram por anos, mas para os quais você ainda não tem substituição. Para nós, uma parte dessa frota legada são nossos sistemas CentOS 7. Eles são estáveis, mas estão em fim de vida útil (end-of-life), o que significa que não recebem mais atualizações críticas de segurança de seu fabricante original. Para uma companhia aérea, voar sem suporte é um risco que simplesmente não podemos correr.

A solução tradicional seria uma substituição completa e custosa de cada um deles.
Mas e se pudéssemos realizar uma atualização de extensão de vida, modernizando-os no local com o mínimo de interrupção? Essa é precisamente a missão deste desafio. Usaremos o poder do <b class="smlmext">SUSE Multi-Linux Manager</b> juntamente com o <b class="smlsext">SUSE Multi-Linux Support</b> para fazer a transição segura desses sistemas e mantê-los em serviço até que possamos substituí-los por um SO mais moderno.



## <b class="hovereffect">Nosso plano de voo:</b>

- Examinar os sistemas legados atuais executando Centos 7

- Integrar (Onboard) o sistema de QA e aplicar quaisquer patches disponíveis

- Identificar e aplicar atualizações, se houver.

- Liberar o sistema com a fórmula liberate.

- Observar o que mudou entre ambos os sistemas

- Identificar se isso é uma migração.

<br/>

## <b class="hovereffect">Nossos aviões</b>

- CentOS 7 QA ✈ Nosso servidor de teste e desenvolvimento.

- CentOS 7 Prod ✈ Nosso servidor de produção já registrado no <b class="smlm">SMLM</b>

<br/><br/>


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



Integração do Centos 7 QA (Onboarding Centos 7 QA)
======================



## <b class="hovereffect">Examinando os sistemas legados atuais</b>

Acesse o terminal do sistema na aba [button label="Centos 7 QA" variant="success"](tab-1)

Verifique a versão atual do sistema:

```bash,run
rpm -qi centos-release centos-logos
```


Agora execute o seguinte comando para registrar o sistema no <b class="smlm">SMLM</b>:


```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | SMLM_DNS="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-liberty7ltss PROFILENAME='airco-dh4a-qa' bash ; echo "Let's wait 2 minutes for all the background processes to finish"; sleep 120
```


Isso é semelhante ao que usamos para integrar o Ubuntu no laboratório anterior, o que muda é:

- **Activation key** (Chave de ativação): É uma referência às configurações que serão aplicadas ao sistema por padrão, neste caso foi criada para indicar apenas em quais canais de software o sistema será registrado.

- **Profile name** (Nome do perfil): Se não especificarmos, ele usará o nome do host (hostname), mas neste caso queremos que ele tenha um nome mais significativo com a mesma convenção de nomenclatura que usamos com o Centos 7 Prod.


**Opcional:** Se estivermos curiosos e quisermos ver o que acontece quando atualizamos e executamos a fórmula Liberate, podemos executar o seguinte comando em ambos os sistemas ( [button label="Centos 7 QA" variant="success"](tab-1) e [button label="Centos 7 Prod" variant="success"](tab-2) ):


```bash,run
journalctl -f
```

E ver os logs aparecendo nos terminais.


<br/><br/>


## <b class="hovereffect">Identificar e aplicar atualizações dos repositórios <b class="liberty">Liberty</b></b>

Esses sistemas Centos 7 vêm com os pacotes mais recentes fornecidos upstream, queremos garantir que novos bugs sejam corrigidos e que tenhamos uma pessoa de suporte amigável para nos ajudar quando houver problemas. Agora já inscrevemos os sistemas Centos 7 nos repositórios de software fornecidos pela SUSE durante o processo de registro, então vamos aplicar patches em todos eles:



Agora vamos mudar para a aba [button label="SMLM UI" variant="success"](tab-0)


- Vá para `Systems` ✈ `System List` no menu à esquerda.

- Encontre seu host **airco-dh4a-qa** e clique nele.

- Selecione `Software` ✈ `Packages`

- Clique em `Update Packages List`, isso levará cerca de um minuto para ser concluído

- Selecione `Software` ✈ `Patches`

- Você verá uma lista de patches disponíveis.

Clique em `Select All`, depois em `Apply Patches` no canto superior direito e finalmente em `Confirm`. O <b class="smlmext">SUSE Multi-Linux Manager</b> agora agendará e executará o procedimento de atualização no sistema CentOS.


> [!NOTE]
> Pode levar alguns minutos para obter a lista de pacotes antes que você possa ver a lista de patches que podem ser aplicados ao sistema.


Como isso pode demorar um pouco, vamos ver o que acontece nos bastidores.
Vá para a aba `Events`, depois para `History`, você deve ver uma lista de eventos que aconteceram desde que o sistema foi registrado no <b class="smlm">SMLM</b>; nas primeiras linhas devemos ser capazes de encontrar um evento que contém algo semelhante a *Combined Patch*.


Se clicarmos nele, podemos ver todos os detalhes, fique à vontade para dar uma olhada, caso contrário, espere até que o ícone esteja verde:

![Successfully patched](../assets/SMLM5.1/successfully_updated_system.png)

Acabamos de aplicar patches que corrigem bugs nos pacotes existentes, esses pacotes corrigidos vêm diretamente da SUSE, isso não é uma migração.

<br/>

Vamos compará-lo com o sistema de produção que ainda não atualizamos.

Por favor, vá para `Software` ✈ `Packages` ✈ `Profiles`

Selecione o sistema `airco-dh4a-prod`, que é a versão de produção, depois clique em:

![Compare](../assets/SMLM5.1/bottom-compare.png)


Podemos ver que a maioria das versões dos pacotes não mudou, continua a mesma versão ( **X.X.X**-xyz ), mas com um patch aplicado ( X.X.X-**xyz** ).

Antes de passarmos para a próxima seção, vamos criar um perfil armazenado, isso nos ajudará a ver as diferenças mais claramente depois de aplicarmos a fórmula liberate na próxima seção.


Por favor, vá para `Software` ✈ `Packages` ✈ `Profile` e clique em `Create System Profile`. Para o nome, você pode chamá-lo de:

```txt
before_liberation
```


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-identify_and_apply_updates.gif"/>
  </div>


<br/><br/>


Liberar o sistema (opcional)
==============================

Este é um passo **opcional** e não é obrigatório para obter suporte.

Agora vamos liberar o sistema:

- Vá para a aba `Formulas`, pesquise por **Liberate**, e uma vez encontrado, selecione-o e clique em `Save` no canto superior direito.

Você verá uma mensagem em azul no topo da tela, role para cima se não conseguir ver:

![Formula saved](../assets/SMLM5.1/formula_saved.png)


Clique onde diz `Highstate`, você será direcionado para outra aba (`States` ✈ `Highstate`).

Você pode ver no resumo na parte inferior que a fórmula liberate está listada.

Para iniciar o processo de liberação, clique em:

![Formula saved](../assets/SMLM5.1/bottom-apply_highstates.png)

Isso levará algum tempo, por favor verifique `Events` -> `History`, você deve ver um evento chamado **Apply highstate scheduled**

Vamos esperar alguns minutos para que termine, enquanto isso você pode observar o que está acontecendo olhando para o terminal [button label="Centos 7 QA" variant="success"](tab-1).


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-liberate.gif"/>
  </div>

<br/><br/>

## <b class="hovereffect">Observe o que mudou</b>


Uma vez concluído, vamos comparar o sistema novamente para ver a diferença; se ainda não estivermos lá, vamos clicar no nome do sistema `airco-dh4a-qa`.

Depois vá para `Software` ✈ `Packages` ✈ `Profile`

Em **Compare to Stored Profile** clique em: ![Compare](../assets/SMLM5.1/bottom-compare.png)

Podemos ver que a única coisa que mudou são os seguintes pacotes:

- **centos-logos**, substituído por **sles_es-logos**

- **centos-release**, substituído por **sles_es-release-server**

O resto permanece o mesmo, mas agora você tem todo o suporte, atualizações e patches fornecidos pela <b class="suse">SUSE</b> para o <b class="liberty">Liberty Linux</b>.

O mesmo se aplica a versões mais modernas do CentOS e RHEL, você pode transformá-los em <b class="liberty">Liberty</b> e tê-los suportados pela <b class="suse">SUSE</b> sem ter que fazer nenhuma alteração no software e nas bibliotecas reais.



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-what_changed.gif"/>
  </div>

<br/>



Liberar o servidor de produção (opcional)
=========================================

Vimos como aplicar patches e Liberar nosso antigo servidor Centos 7 em QA, agora é hora de fazer o mesmo com o sistema de produção, mas desta vez faremos em uma ordem diferente.

- Primeiro, aplicaremos a fórmula **Liberate**

  Vamos ao nosso servidor de produção `airco-dh4a-prod` e `Create System Profile`

  Depois vamos aplicar a fórmula **Liberate** como fizemos com o sistema QA.

- Uma vez concluído, vamos comparar o sistema com o perfil que acabamos de criar; como podemos ver, a única mudança foram os pacotes **centos-logos** e **centos-release**, o resto permanece exatamente o mesmo.


É uma migração?
==================

Uma migração envolve construir um servidor totalmente novo, reinstalar todos os aplicativos do zero e mover cuidadosamente os dados, um processo que consome tempo, é caro e cheio de riscos.

O que fizemos foi muito mais elegante. Realizamos uma atualização no local (in-place upgrade).

A identidade do servidor, o nome do host, os aplicativos e os dados do usuário permaneceram completamente intocados. Simplesmente mudamos sua fonte subjacente para atualizações, e esses componentes em fim de vida agora são componentes totalmente suportados recebendo patches.

Estendemos com sucesso a vida útil do nosso sistema, trouxemos de volta à conformidade de segurança e fizemos tudo isso sem a interrupção de uma migração completa. Essa é a eficiência que mantém a [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] voando alto.




Por que isso é importante para a [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- Permite que a [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] mantenha seus sistemas em execução suportados, concedendo-lhes tempo para migrar dependendo de suas necessidades de negócios, em vez das necessidades do fornecedor.

- Mitiga o risco que implica ter sistemas sem suporte oferecendo suporte estendido. Essa abordagem evita a necessidade de uma migração imediata, tudo funciona como de costume, mas agora há um grupo de especialistas que podem atender suas chamadas.

- Dá a você a liberdade de mudar de provedor de suporte sem passar por migrações longas, e permite que você faça isso em escala.



Mais informações
================

- [Registrando RHEL 7 ou CentOS Linux 7 com SUSE Manager](https://documentation.suse.com/liberty/7/html/suma-quickstart/art-suma-quickstart.html)
- [Executando varreduras de conformidade OpenSCAP para SUSE Multi-Linux Support 7](https://documentation.suse.com/liberty/7/html/compliance-scans/art-compliance-scans.html)
- [Registrando CentOS Linux 7 com o SUSE Customer Center](https://documentation.suse.com/liberty/7/html/quickstart-scc/art-quickstart-scc.html)
- [SUSE Multi-Linux Support 9](https://documentation.suse.com/liberty/9/)