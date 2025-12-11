---
slug: smls-extended-support
id: yi9j1mh00k30
type: challenge
title: Support étendu pour les systèmes hérités
tabs:
- id: vrf6xypownbw
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: rehxybo35zwi
  title: CentOS 7 QA
  type: terminal
  hostname: centos7
- id: s8yugtjoi7tx
  title: CentOS 7 Prod
  type: terminal
  hostname: zzcentos7
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Support étendu pour les systèmes hérités
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

# Prolonger la durée de vie de notre flotte héritée

Dans toute compagnie aérienne, vous avez des avions plus anciens et fiables qui vous ont servi pendant des années mais pour lesquels vous n'avez pas encore de remplacement. Pour nous, une partie de cette flotte héritée est constituée de nos systèmes CentOS 7. Ils sont stables mais en fin de vie (end-of-life), ce qui signifie qu'ils ne reçoivent plus de mises à jour de sécurité critiques de leur fabricant d'origine. Pour une compagnie aérienne, voler sans support est un risque que nous ne pouvons tout simplement pas prendre.

La solution traditionnelle serait un remplacement complet et coûteux de chacun d'eux.
Mais et si nous pouvions effectuer une mise à niveau d'extension de vie, en les modernisant sur place avec une interruption minimale ? C'est précisément la mission de ce défi. Nous utiliserons la puissance de <b class="smlmext">SUSE Multi-Linux Manager</b> avec <b class="smlsext">SUSE Multi-Linux Support</b> pour faire la transition de ces systèmes en toute sécurité et les maintenir en service jusqu'à ce que nous puissions les remplacer par un OS plus moderne.



## <b class="hovereffect">Notre plan de vol :</b>

- Examiner les systèmes hérités actuels exécutant Centos 7

- Intégrer (Onboard) le système QA et appliquer les correctifs disponibles

- Identifier et appliquer les mises à jour le cas échéant.

- Libérer (Liberate) le système avec la formule liberate.

- Observer ce qui a changé entre les deux systèmes

- Identifier s'il s'agit d'une migration.

<br/>

## <b class="hovereffect">Nos avions</b>

- CentOS 7 QA ✈ Notre serveur de test et de développement.

- CentOS 7 Prod ✈ Notre serveur de production déjà enregistré dans <b class="smlm">SMLM</b>

<br/><br/>


Détails du laboratoire (Lab details)
===========

Nom d'utilisateur (Username) :
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```

Mot de passe (Password) :
```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

URL <b class="smlm">SMLM</b> : <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>



Intégration de Centos 7 QA (Onboarding Centos 7 QA)
======================



## <b class="hovereffect">Examen des systèmes hérités actuels</b>

Accédez au terminal du système depuis l'onglet [button label="Centos 7 QA" variant="success"](tab-1)

Vérifiez la version actuelle du système :

```bash,run
rpm -qi centos-release centos-logos
```


Maintenant, exécutez la commande suivante pour enregistrer le système dans <b class="smlm">SMLM</b> :


```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | SMLM_DNS="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-liberty7ltss PROFILENAME='airco-dh4a-qa' bash ; echo "Let's wait 2 minutes for all the background processes to finish"; sleep 120
```


Ceci est similaire à celle que nous avons utilisée pour intégrer Ubuntu dans le laboratoire précédent, ce qui change est :

- **Activation key** (Clé d'activation) : Est une référence aux paramètres qui seront appliqués au système par défaut, dans ce cas, elle a été créée pour indiquer uniquement à quels canaux logiciels le système sera enregistré.

- **Profile name** (Nom du profil) : Si nous ne le spécifions pas, il utilisera le nom d'hôte (hostname) mais dans ce cas, nous voulons qu'il ait un nom plus significatif avec la même convention de nommage que celle que nous avons utilisée avec Centos 7 Prod.


**Optionnel :** Si nous sommes curieux et voulons voir ce qui se passe lorsque nous mettons à jour et exécutons la formule Liberate, nous pouvons exécuter la commande suivante sur les deux systèmes ( [button label="Centos 7 QA" variant="success"](tab-1) et [button label="Centos 7 Prod" variant="success"](tab-2) ) :


```bash,run
journalctl -f
```

Et voir les journaux apparaître dans les terminaux.


<br/><br/>


## <b class="hovereffect">Identifier et appliquer les mises à jour des dépôts <b class="liberty">Liberty</b></b>

Ces systèmes Centos 7 sont livrés avec les derniers paquets fournis en amont, nous voulons nous assurer que les nouveaux bogues sont corrigés et que nous avons une personne de support amicale pour nous aider en cas de problèmes. Maintenant, nous avons déjà abonné les systèmes Centos 7 aux dépôts logiciels fournis par SUSE lors du processus d'enregistrement, alors appliquons les correctifs à tous :



Maintenant, passons à l'onglet [button label="SMLM UI" variant="success"](tab-0)


- Allez dans `Systems` ✈ `System List` dans le menu de gauche.

- Trouvez votre hôte **airco-dh4a-qa** et cliquez dessus.

- Sélectionnez `Software` ✈ `Packages`

- Cliquez sur `Update Packages List`, cela prendra environ une minute pour se terminer

- Sélectionnez `Software` ✈ `Patches`

- Vous verrez une liste des correctifs disponibles.

Cliquez sur `Select All`, puis `Apply Patches` en haut à droite et enfin `Confirm`. <b class="smlmext">SUSE Multi-Linux Manager</b> va maintenant planifier et effectuer la procédure de mise à niveau sur le système CentOS.


> [!NOTE]
> Cela peut prendre quelques minutes pour obtenir la liste des paquets avant que vous puissiez voir la liste des correctifs pouvant être appliqués au système.


Comme cela peut prendre un certain temps, voyons ce qui se passe en coulisses.
Allez dans l'onglet `Events`, puis `History`, vous devriez voir une liste d'événements qui se sont produits depuis que le système a été enregistré dans <b class="smlm">SMLM</b>, dans les premières lignes, nous devrions pouvoir trouver un événement contenant quelque chose de similaire à *Combined Patch*.


Si nous cliquons dessus, nous pouvons voir tous les détails, n'hésitez pas à jeter un coup d'œil, sinon attendez que l'icône soit verte :

![Successfully patched](../assets/SMLM5.1/successfully_updated_system.png)

Nous venons d'appliquer des correctifs qui corrigent des bogues aux paquets existants, ces paquets corrigés proviennent directement de SUSE, ce n'est pas une migration.

<br/>

Comparons-le avec le système de production que nous n'avons pas encore mis à jour.

Veuillez aller dans `Software` ✈ `Packages` ✈ `Profiles`

Sélectionnez le système `airco-dh4a-prod`, qui est la version de production, puis cliquez sur :

![Compare](../assets/SMLM5.1/bottom-compare.png)


Nous pouvons voir que la plupart des versions de paquets n'ont pas changé, toujours la même version ( **X.X.X**-xyz ) mais avec un correctif appliqué ( X.X.X-**xyz** ).

Avant de passer à la section suivante, créons un profil stocké, cela nous aidera à voir les différences plus clairement après avoir appliqué la formule liberate dans la section suivante.


Veuillez aller dans `Software` ✈ `Packages` ✈ `Profile` et cliquez sur `Create System Profile`. Pour le nom, vous pouvez l'appeler :

```txt
before_liberation
```


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-identify_and_apply_updates.gif"/>
  </div>


<br/><br/>


Libérer le système (optionnel)
==============================

Ceci est une étape **optionnelle** et n'est pas requise pour obtenir le support.

Maintenant, libérons le système :

- Allez dans l'onglet `Formulas`, recherchez **Liberate**, et une fois trouvé, sélectionnez-le et cliquez sur `Save` en haut à droite.

Vous verrez un message en bleu en haut de l'écran, faites défiler vers le haut si vous ne pouvez pas le voir :

![Formula saved](../assets/SMLM5.1/formula_saved.png)


Cliquez là où il est écrit `Highstate`, vous serez dirigé vers un autre onglet (`States` ✈ `Highstate`).

Vous pouvez voir dans le résumé en bas que la formule liberate est listée.

Pour démarrer le processus de libération, cliquez sur :

![Formula saved](../assets/SMLM5.1/bottom-apply_highstates.png)

Cela prendra un certain temps, veuillez vérifier `Events` -> `History`, vous devriez voir un événement appelé **Apply highstate scheduled**

Attendons quelques minutes que cela se termine, en attendant, vous pouvez observer ce qui se passe en regardant le terminal [button label="Centos 7 QA" variant="success"](tab-1).


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-liberate.gif"/>
  </div>

<br/><br/>

## <b class="hovereffect">Observer ce qui a changé</b>


Une fois terminé, comparons à nouveau le système pour voir la différence, si nous n'y sommes pas déjà, cliquons sur le nom du système `airco-dh4a-qa`.

Ensuite, allez dans `Software` ✈ `Packages` ✈ `Profile`

Sous **Compare to Stored Profile** cliquez sur : ![Compare](../assets/SMLM5.1/bottom-compare.png)

Nous pouvons voir que les seuls changements sont les paquets suivants :

- **centos-logos**, remplacé par **sles_es-logos**

- **centos-release**, remplacé par **sles_es-release-server**

Le reste demeure le même mais maintenant vous avez tout le support, les mises à niveau et les correctifs fournis par <b class="suse">SUSE</b> pour <b class="liberty">Liberty Linux</b>.

Il en va de même pour les versions plus modernes de CentOS et RHEL, vous pouvez les transformer en <b class="liberty">Liberty</b> et les faire supporter par <b class="suse">SUSE</b> sans avoir à apporter de modifications aux logiciels et bibliothèques réels.



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-what_changed.gif"/>
  </div>

<br/>



Libérer le serveur de production (optionnel)
=========================================

Nous avons vu comment appliquer des correctifs et Libérer notre ancien serveur Centos 7 en QA, il est maintenant temps de faire de même avec le système de production, mais cette fois nous le ferons dans un ordre différent.

- Tout d'abord, nous appliquerons la formule **Liberate**

  Allons sur notre serveur de production `airco-dh4a-prod` et faisons `Create System Profile`

  Ensuite, appliquons la formule **Liberate** comme nous l'avons fait avec le système QA.

- Une fois terminé, comparons le système avec le profil que nous venons de créer, comme nous pouvons le voir, le seul changement a été les paquets **centos-logos** et **centos-release**, le reste reste exactement le même.


Est-ce une migration ?
==================

Une migration implique de construire un tout nouveau serveur, de réinstaller toutes les applications à partir de zéro et de déplacer soigneusement les données, un processus qui prend du temps, coûte cher et comporte des risques.

Ce que nous avons fait était beaucoup plus élégant. Nous avons effectué une mise à niveau sur place (in-place upgrade).

L'identité du serveur, le nom d'hôte, les applications et les données utilisateur sont restés complètement intacts. Nous avons simplement changé sa source sous-jacente pour les mises à jour, et ces composants en fin de vie sont maintenant des composants entièrement supportés recevant des correctifs.

Nous avons prolongé avec succès la durée de vie de notre système, l'avons remis en conformité avec la sécurité, et avons fait tout cela sans l'interruption d'une migration complète. C'est l'efficacité qui permet à [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] de voler haut.




Pourquoi est-ce important pour [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] ?
=================================================================================

- Cela permet à [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] de maintenir ses systèmes en cours d'exécution supportés, leur accordant du temps pour migrer en fonction de leurs besoins commerciaux plutôt que des besoins du fournisseur.

- Cela atténue le risque qu'implique le fait d'avoir des systèmes non supportés en offrant un support étendu. Cette approche évite le besoin d'une migration immédiate, tout fonctionne comme d'habitude mais il y a maintenant un groupe d'experts qui peut répondre à vos appels.

- Cela vous donne la liberté de changer de fournisseur de support sans passer par de longues migrations, et vous permet de le faire à l'échelle.



Plus d'informations
================

- [Registering RHEL 7 or CentOS Linux 7 with SUSE Manager](https://documentation.suse.com/liberty/7/html/suma-quickstart/art-suma-quickstart.html)
- [Running OpenSCAP compliance scans for SUSE Multi-Linux Support 7](https://documentation.suse.com/liberty/7/html/compliance-scans/art-compliance-scans.html)
- [Registering CentOS Linux 7 with the SUSE Customer Center](https://documentation.suse.com/liberty/7/html/quickstart-scc/art-quickstart-scc.html)
- [SUSE Multi-Linux Support 9](https://documentation.suse.com/liberty/9/)