---
slug: smlm-simplify-upgrade-sles
id: rszlprjvbjmp
type: challenge
title: Maintenance simple et fiable
tabs:
- id: f2uky59fyis4
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: kzxipepyvy0b
  title: SLES 15
  type: terminal
  hostname: sles15
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Maintenance simple et fiable
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

Jusqu'à présent, nous nous sommes concentrés sur la gestion de la diversité de notre flotte mixte et même sur l'extension de la durée de vie de nos systèmes hérités. Maintenant, nous tournons notre attention vers le cœur de notre compagnie aérienne : nos systèmes phares <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>).


Considérez-les comme nos jets long-courriers de pointe. Leur fiabilité est primordiale, et les maintenir en parfait état implique l'application régulière et planifiée de correctifs de service et de mises à niveau. Ce prochain exercice est exactement cela : nous allons parcourir le processus d'une mise à niveau de version, une tâche courante dans la gestion du cycle de vie de tout système critique.



Et bien que nous utilisions SLES comme exemple, rappelez-vous le principe clé de notre tour de contrôle universelle : le processus que vous êtes sur le point d'effectuer est le même que celui que vous utiliseriez pour toute autre distribution Linux. L'interface et la méthodologie ne changent pas.


## <b class="hovereffect">Vos Objectifs :</b>

- Intégrer (Onboard) un nouveau système SLES 15 SP5 pour servir d'avion de test.
- Effectuer une mise à niveau de service majeure de SP5 vers SP6.



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






Intégration et préparation (Onboarding and preparation)
==========================

Accédez au terminal du système depuis l'onglet [button label="SLES 15" variant="success"](tab-1)


Enregistrons le système dans <b class="smlm">SMLM</b> en tant que **sles15**

```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | HOSTNAME="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-sles15sp5 bash ; echo "Wait 45 seconds for it to finish"; sleep 45
```


Maintenant, passons à l'onglet [button label="SMLM UI" variant="success"](tab-0)


Exécution de la mise à niveau (Executing the upgrade)
=====================

Nous devrions le voir bientôt dans la liste des systèmes, allons dans `Systems` ✈ `System List` ✈ `All`, veuillez cliquer sur rafraîchir dans le navigateur interne si vous ne le voyez pas.


Cliquons dessus et allons dans `Software` ✈ `Packages` ✈ `Upgrade`.


Pour assurer une migration fluide, il est préférable d'appliquer les dernières mises à jour.



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">Cliquez sur </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


Cela peut prendre un certain temps pour se terminer.

<br/>


## <b class="hovereffect">Migration de produit</b>


Une fois terminé, veuillez aller dans `Software` ✈ `Product Migration`



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">Vous verrez une section appelée **Target Products**. Assurez-vous que <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #90ebcd">SUSE Linux Enterprise Server 15 SP6 x86_64</b> est sélectionné, puis appuyez sur : </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; vertical-align: middle; display:block; align:left; padding: 0px;" src="../assets/SMLM5.1/bottom-select_channels.png"/></p>

Un écran de confirmation s'affichera avec un résumé et des options supplémentaires. Laissez les valeurs par défaut telles quelles et cliquez sur : ![Schedule Migration](../assets/SMLM5.1/bottom-schedule_migration.png)

Le système vous demandera d'abord de faire une simulation (dry run), ignorez-la et appuyez sur : ![Confirm](../assets/SMLM5.1/bottom-confirm.png)

Cela prendra un certain temps. Pour surveiller l'état, allez dans `Events` ✈ `History` et surveillez l'événement **Product Migration**. Une fois que son icône d'état devient verte, la migration est terminée. Vous pouvez vérifier cela en naviguant vers `Software` ✈ `Software Channels` et en confirmant que le système est maintenant abonné aux nouveaux canaux SP6.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/04-simple_and_reliable_maintenance-executing_the_upgrade.gif"/>
  </div>

<br/>

## <b class="hovereffect">Redémarrage post-migration</b>

- Naviguez de retour vers `Systems` ✈ `System List` ✈ `All`

- Remarquez que le système `sles15` a maintenant une icône de redémarrage à côté :

![Needs reboot icon](../assets/SMLM5.1/icon_needs_reboot.png)

  Cela indique qu'un redémarrage est requis, généralement dû à une mise à jour majeure du noyau.

- Cliquez dessus, nous verrons quelque chose de similaire à ceci :

![Needs reboot message](../assets/SMLM5.1/system_requires_a_reboot.png)

- Cliquez sur `Schedule System Reboot` et dans l'écran suivant cliquez sur ![Reboot System](../assets/SMLM5.1/bottom-reboot_system.png)

> [!NOTE]
> Le redémarrage ne se produira pas immédiatement.

<br/>


## <b class="hovereffect">L'importance de la Planification (Scheduling)</b>

Nous avons planifié ces actions pour qu'elles se produisent immédiatement, mais ce n'est pas toujours souhaitable. <b class="smlm">SMLM</b> prend en charge la création de Fenêtres de Maintenance (Maintenance Windows) (`Schedule` ✈ `Maintenance Windows`) ce qui vous permet de vous assurer que les événements majeurs comme les redémarrages ne se produisent que pendant ces périodes pré-approuvées.



La planification est particulièrement utile pour les systèmes de production, car elle permet des changements soigneusement planifiés sur des groupes de systèmes et même des déploiements « canari » par étapes.

<br/>

> [!NOTE]
> Il est possible de faire du patching de noyau en direct (live patching) avec KLP, cela permet d'appliquer les dernières mises à jour de sécurité aux noyaux Linux sans redémarrer.



Pourquoi est-ce important pour [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] ?
=================================================================================

- Les mises à niveau du système et autres tâches de routine doivent être simples et reproductibles, sinon, nous risquons de commettre des erreurs coûteuses. Avec ces outils, nous pouvons contrôler précisément quand et où nous effectuons des actions, planifiant la maintenance critique pour notre flotte en toute confiance.


- Nous pouvons contrôler quand et où nous effectuons des actions, et planifier les opérations de maintenance sur notre flotte au sol.


Plus d'informations
================

- [Live kernel patching with KLP](https://documentation.suse.com/en-us/sles/15-SP7/html/SLES-all/cha-klp.html)

- [Maintenance Windows](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

- [Administration Guide](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/admin-overview.html)