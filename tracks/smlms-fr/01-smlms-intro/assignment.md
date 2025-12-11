---
slug: smlms-intro
id: xonyxlexxfcy
type: challenge
title: Bienvenue au SUSE Multi-Linux Hands-on Workshop !
teaser: Bienvenue au SUSE Multi-Linux Hands-on Workshop ! Dans cette section, nous
  vous présenterons l'atelier et ses principaux composants.
notes:
- type: text
  contents: |
    # Bienvenue au SUSE Multi-Linux Hands-on Workshop !
    Veuillez patienter pendant que nous configurons votre environnement de laboratoire.
    <img class="logos" src="../assets/logos/suse_logo.svg"/>
tabs:
- id: kwu74g1sg6vw
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: ""
enhanced_loading: null
---

Bienvenue au <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">SUSE</b> Multi-Linux Hands-on Workshop
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

Dans cet atelier, vous explorerez une partie de la magie que <b class="smlmext">SUSE Multi-Linux Manager</b> (<b class="smlm">SMLM</b>) peut opérer ; c'est la solution de <b class="suse">SUSE</b> pour gérer plusieurs distributions Linux à l'échelle depuis une interface unifiée. Et vous découvrirez également comment maintenir le support de vos serveurs de production existants (legacy) avec <b class="smlsext">SUSE Multi-Linux Support</b> (<b class="smls">SMLS</b>), notre solution de support professionnelle et fiable pour les systèmes Linux.

&emsp;&emsp; Vous adopterez le rôle d'un **ingénieur** chez <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b>, une compagnie aérienne où chaque avion possède un serveur Linux à bord.

&emsp;&emsp; Comme pour tout composant d'avion, il est critique que ces serveurs restent stables et fiables, qu'ils soient situés au sol dans un datacenter ou qu'ils volent au-dessus des nuages ☁ ☁ ☁


&emsp;&emsp; Certains modèles d'avions nécessiteront une version de Linux différente, ou une architecture CPU différente. Ce n'est pas un problème pour <b class="smlm">SMLM</b> ; vous êtes libre de choisir la distribution Linux et l'architecture CPU qui conviennent le mieux à vos besoins sans avoir à renoncer à une standardisation et une gestion faciles.


&emsp;&emsp; En tant qu'ingénieur responsable de la gestion du paysage Linux, vous passerez en revue certaines des solutions que <b class="smlm">SMLM</b> et <b class="smls">SMLS</b> vous offrent pour faciliter et automatiser la gestion des systèmes et résoudre les problèmes exceptionnels qui peuvent survenir.


Tout au long des différents défis, vous disposerez des outils suivants :

 ✈ **SUSE Multi-Linux Manager**:
   Le panneau de verre unique (single pane of glass) pour gérer l'ensemble de votre pile Linux.

 ✈ **Centos 7**:
   Une distribution héritée encore utilisée sur certains avions plus anciens et systèmes au sol.

 ✈ **Ubuntu 24**: Une distribution Linux spécifique requise par notre département marketing pour exécuter leurs applications de conception graphique.

 ✈ **SLES 15**: La distribution Linux hautement fiable, stable et sécurisée de <b class="suse">SUSE</b> qui forme l'épine dorsale de nos systèmes les plus critiques.


## <b class="smlmext hovereffect">SUSE Multi-Linux Manager</b>

C'est une solution de gestion d'infrastructure open source de premier ordre pour votre infrastructure définie par logiciel.

&emsp;&emsp; <b class="smlmext">SUSE Multi-Linux Manager</b> a été conçu pour aider vos équipes d'entreprise DevOps et Opérations IT à réduire la complexité et à reprendre le contrôle de vos actifs informatiques, un outil unique mais très puissant pour gérer les systèmes Linux à travers une variété d'architectures matérielles, d'hyperviseurs ainsi que de plateformes de conteneurs, IoT et cloud.

&emsp;&emsp; Il automatise le provisionnement, l'application de correctifs et la configuration des serveurs Linux et des appareils IoT pour un déploiement de serveur plus rapide, cohérent et reproductible, aidant à optimiser les opérations et à réduire les coûts. Et avec la surveillance, le suivi, l'audit et le reporting automatisés de vos systèmes, VM et conteneurs dans vos environnements de développement, de test et de production, vous pouvez assurer la conformité avec les politiques de sécurité internes et les réglementations externes.


## <b class="smlsext hovereffect">SUSE Multi-Linux Support</b>


C'est un service complet offrant une assistance technique et une maintenance pour diverses distributions Linux, y compris vos Red Hat Enterprise Linux (RHEL) existants, CentOS, <b class="liberty">SUSE Liberty Linux</b>, et <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>), selon l'offre.

&emsp;&emsp; Il permet aux organisations de gérer efficacement des environnements Linux mixtes sous un cadre de support unique.
Selon le paquet acheté, <b class="smlsext">SUSE Multi-Linux Support</b> peut également inclure <b class="smlmext">SUSE Multi-Linux Manager</b>, un outil de gestion multi-Linux pour gérer ces distributions.



 🌅 Explorez l'UI Instruqt
=======================
Avant de commencer notre première tâche, prenons un moment pour regarder l'UI Instruqt.

+ Le **côté droit** de l'écran vous fournit ces instructions et les contrôles de navigation.

+ Le **côté gauche** vous donne accès aux différentes machines et services qui composent notre environnement de laboratoire.

Au sein de l'UI Instruqt, vous pouvez passer entre le [button label="SMLM UI" variant="success"](tab-0) et les [button label="terminals" variant="success"](tab-1) disponibles en cliquant sur les onglets en haut du panneau de gauche.


> [!NOTE]
> Aucun rechargement automatique ne se produit sur l'UI web ; dans certains cas, vous devrez peut-être recharger le navigateur web interne d'Instruqt pour voir les mises à jour.


🛫 Connexion à <b class="smlmext">SUSE Multi-Linux Manager</b> 🛫
========================================
Familiarisons-nous avec l'environnement.

- Ouvrez <b class="smlmext">SUSE Multi-Linux Manager</b> à l'intérieur du laboratoire depuis le [button label="SMLM UI" variant="success"](tab-0)


- Connectez-vous avec les identifiants suivants :

  - Nom d'utilisateur :
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```
  - Mot de passe :

```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

Si tout s'est bien passé, vous devriez voir la page **Overview** dans l'UI <b class="smlmext">SUSE Multi-Linux Manager</b> connecté en tant qu'utilisateur `[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]`.

> [!NOTE]
> Si vous souhaitez accéder à l'UI <b class="smlmext">SUSE Multi-Linux Manager</b> directement via votre navigateur, vous pouvez aussi le faire :

URL <b class="smlm">SMLM</b> : <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>


> [!NOTE]
> Si la page ne se charge pas correctement, vous devrez peut-être actualiser l'onglet du navigateur une fois que l'environnement de laboratoire a fini de démarrer.




🗺  Explorez <b class="smlmext">SUSE Multi-Linux Manager</b> 🗺
======================================

Avant de décoller, familiarisons-nous avec les commandes. Ce n'est pas censé être une visite exhaustive, mais un bref aperçu des instruments clés que nous utiliserons tout au long de l'atelier. Nous vous encourageons à être curieux et à explorer.


Commençons.


- **Menu Systems** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_systems.png"/>

  Sur le panneau de gauche, cliquez sur `systems`. C'est notre vue d'ensemble de la flotte, montrant chaque serveur enregistré. La liste est petite maintenant, mais elle grandira à mesure que nous compléterons nos exercices.

   - **System Lists**

     Cette section fournit des vues pratiques et pré-filtrées. Par exemple, la liste `Out of Date` vous montre instantanément quels serveurs nécessitent des mises à jour, vous évitant d'effectuer une recherche manuelle. </p>

  <br/>

  - **System Groups**

    Pour organiser notre flotte logiquement, nous utilisons les `System Groups` ; vous pouvez les catégoriser sur la base de n'importe quel critère. Ce faisant, vous pouvez gagner du temps lors de l'application d'actions ou de la définition de politiques. Une fois créés, vous pouvez attacher automatiquement des systèmes à un ou plusieurs groupes, par exemple en utilisant des `activation keys`.


    N'hésitez pas à essayer d'en créer un maintenant en cliquant sur `+ Create Group`.

  <br/>

  - **Opérations par lots**

    `System Set Manager` offre un moyen puissant d'effectuer des actions sur plusieurs systèmes simultanément.


    Au lieu d'appliquer les changements un par un, vous pouvez sélectionner une collection de systèmes, soit individuellement depuis la System List ou en tirant parti des System Groups existants, puis exécuter des tâches sur l'ensemble d'entre eux en une seule opération.

  <br/>

  - **Provisioning**

    <b class="smlmext">SUSE Multi-Linux Manager</b> fournit des outils complets pour le provisionnement de nouveaux systèmes et le reprovisionnement des systèmes existants. Cette capacité vous aide à établir un processus standardisé et reproductible pour le déploiement de systèmes.


    Par exemple, dans la section `Autoinstallation`, vous pouvez définir des distributions et des profils Kickstart/AutoYaST, ce qui vous permet de spécifier comment vos systèmes doivent être déployés, quels logiciels ils auront installés, comment l'espace de stockage sera distribué et plus encore.


    Tous ces mécanismes d'automatisation simples à configurer peuvent être combinés avec des solutions d'automatisation complexes mais plus puissantes comme Salt ou Ansible, préservant votre liberté de choisir la meilleure solution pour chaque défi.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_systems.gif"/>
  </div>

<br/>



- **Menu Patches** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_patches.png"/>

  - **Patching**

    L'une des tâches les plus courantes en informatique est de maintenir les systèmes à jour et, de temps en temps, d'appliquer des correctifs de sécurité dans l'urgence !
    Avec SMLM, nous pouvons facilement voir une liste de correctifs **pertinents**, classés par type, et fournis avec toutes les informations que vous pourriez avoir besoin de connaître, y compris tous les systèmes et paquets qu'ils affectent.

    Au-delà des correctifs fournis par le fournisseur, nous pouvons également créer nos propres correctifs. Plus tard, nous explorerons les différentes options dont nous disposons pour gérer l'application de correctifs et les mises à jour régulières sur toute notre flotte.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_patches.gif"/>
  </div>

<br/>
- **Canaux logiciels** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_software.png"/>

  Dans `Channel List`, nous pouvons voir tous les canaux/dépôts/flux de paquets disponibles pour la consommation ; vous pouvez également créer de nouveaux canaux logiciels pour organiser vos logiciels ou télécharger vos propres paquets.

  Tous les canaux que vous voyez actuellement ont été récupérés par SMLM depuis les sources officielles et peuvent être maintenus synchronisés facilement.

  Dans `Package Search`, nous sommes capables de rechercher des paquets spécifiques et d'inspecter leur contenu et leurs métadonnées.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_software.gif"/>
  </div>

<br/>

- **Configuration** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_configuration.png"/>

  Il est également possible de gérer et d'appliquer des configurations spécifiques aux systèmes, lors de l'enregistrement ou par la suite ; pour cela, nous pouvons inspecter la section `Configuration`.

  SMLM fournit un moyen facile de gérer les révisions, de déployer et de comparer les fichiers de configuration entre les systèmes. Et tout peut être facilement regroupé dans des canaux de configuration.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_configuration.gif"/>
  </div>

<br/>

- **Scheduling** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_schedule.png"/>

  Dans `Schedule`, nous pouvons observer et gérer les actions planifiées, définir des fenêtres de maintenance spécifiques. C'est particulièrement utile pour automatiser les opérations régulières ou effectuer des déploiements canaris lors de la gestion de nombreux systèmes. Nous verrons cela en action plus tard au cours de l'atelier.

<br/>
<br/>

SUSE Multi-Linux Manager offre de nombreuses possibilités pour gérer vos systèmes ; nous ne pouvons pas toutes les couvrir dans cet atelier mais, comme toujours, n'hésitez pas à poser des questions et à explorer.

> [!NOTE]
> Votre utilisateur dispose de privilèges d'administrateur complets, nous vous recommandons donc de n'effectuer des modifications qu'après avoir terminé les exercices.