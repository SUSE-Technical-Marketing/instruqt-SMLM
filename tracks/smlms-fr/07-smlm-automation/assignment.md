---
slug: smlm-automation
id: jtqkpcdxhp7h
type: challenge
title: Automatisation (Optionnel)
tabs:
- id: npgumkctqrjl
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Automatisation et gestion de la configuration
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

Dans cette section, nous allons examiner certaines des options disponibles pour automatiser les tâches.

Dans ce laboratoire, nous passons de l'exécution de tâches manuelles à la création d'une certaine automatisation en utilisant certaines des options dont nous disposons.
<b class="smlmext">SUSE Multi-Linux Manager</b> agit comme le « pilote automatique » pour nos opérations informatiques, nous permettant d'appliquer des normes de configuration et d'automatiser les tâches de routine avec précision et fiabilité sur l'ensemble de notre flotte.

Au lieu de configurer manuellement des centaines de serveurs en espérant ne pas manquer une étape, nous définissons le processus et l'état, et réduisons l'opération humaine à la définition d'un planning, une seule fois.



## <b class="hovereffect">Vos Objectifs :</b>

- Créer un planning qui effectue régulièrement des mises à jour sur vos systèmes de développement.

- Créer un script pour afficher une bannière de connexion différente selon l'environnement du système.

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


Configurer des mises à jour récurrentes (Setup recurring updates)
=======================

Nous voulons que les développeurs travaillent avec les dernières mises à jour stables fournies par SUSE, mais nous ne pouvons pas compter sur les gens pour se souvenir de mettre à jour leurs systèmes tous les jours, nous allons donc créer un planning récurrent qui fait exactement cela.


Nous allons appliquer cela à tous les systèmes du groupe dev afin que cela n'ait pas à être fait sur chaque système.

- Allons dans `Systems` ✈ `System Groups`
- Cliquez sur le groupe `dev`.

Nous venons de remarquer qu'aucun système ne lui est assigné, ajoutons-en un.

- Cliquez sur `Target Systems` et sélectionnez `sles15`
- Puis cliquez sur ![Add Systems](../assets/SMLM5.1/bottom-add_system.png)

Maintenant que nous avons un système, créons l'action récurrente.

- Allez dans `Recurring Actions`
- Cliquez sur ![Create](../assets/SMLM5.1/bottom-create.png)
- Maintenant, remplissons le formulaire avec les détails suivants :
	+ **Action Type :** 'Custom state'
 	+ **Schedule Name :** 'Update Dev systems'
	+ **Daily :** '03:00'
	+ **Configure states to execute :** Assurez-vous que **uptodate:** est sélectionné
	![uptodate Selected](../assets/SMLM5.1/uptodate_selected.png)

- Cliquez sur

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-create_schedule.png"/>
</p>



Pour observer notre liste d'actions récurrentes, nous pouvons aller dans `Schedule` ✈ `Recurring Actions`

Désormais, tous les systèmes dev seront mis à jour quotidiennement à 03h00 UTC.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-setup_recurring_updates.gif"/>
  </div>

<br/>




S'assurer que chaque système a un message de connexion
==========================================


Nous allons créer un canal de configuration pour nous assurer que chaque système que nous gérons contient un message de connexion adéquat.



- Allons dans `Configuration` ✈ `Channels`
- Cliquez sur ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png)
- Remplissez le formulaire avec les détails suivants :
	+ **Name :** <b class="highlightcopy">Uniform experience</b>
	+ **Label :** <b class="highlightcopy">uniform_experienace</b>
	+ **Description :** <b class="highlightcopy">Create a uniform experience across systems</b>
- Cliquez sur ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png)

Maintenant que nous avons créé le canal de configuration, peuplons-le.

- Allez dans `Add Files` ✈ `Create File`
- Remplissez les détails suivants :
	+ **Filename/Path :** <b class="highlightcopy">/etc/motd</b>
	+ **File Contents :**
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


- Cliquez sur ![Create Configuration File](../assets/SMLM5.1/bottom-create_configuration_file.png)

Maintenant, abonnons chaque système de l'organisation au nouveau canal de configuration.

- Allons dans `Admin` ✈ `Organizations`
- Cliquez sur l'organisation **Organization** (C'est l'organisation par défaut)
- Allez dans `States` et sélectionnez le canal que nous venons de créer.
![Uniform experience selected](../assets/SMLM5.1/selected_univorm_experience_Configurationchannel.png)
- Cliquez sur


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-execute_states.png"/>
</p>


Cela ne se produira pas immédiatement, vérifions les systèmes. Nous allons exécuter une commande simple via l'interface Web, si elle est exécutée trop tôt, vous pourriez voir des systèmes avec l'ancien message et des systèmes qui ont déjà eu le fichier mis à jour.

- Allons dans `Salt` ✈ `Remote Commands`
- Tapez ce qui suit :
![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd.png)
- Cliquez sur `Find targets`
- Vous devriez voir une liste de systèmes, cliquez sur `Run command`

Maintenant, vous devriez voir quelque chose comme ceci :

![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd_first_result.png)

> [!NOTE]
> Ce processus peut prendre quelques minutes, si vous ne voyez pas le MOTD, veuillez réexécuter la commande après quelques minutes.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-login_message.gif"/>
  </div>

<br/>


Pourquoi est-ce important pour [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] ?
=================================================================================



- Lors de la gestion de milliers de systèmes, nous ne pouvons pas nous permettre de tout faire un par un, les tâches doivent être automatisées afin que nous gérions du bétail, pas des animaux de compagnie.



- En définissant l'« état correct », nous éliminons la dérive de configuration (configuration drift). Chaque serveur de la flotte fonctionne à partir du même manuel, tout comme chaque pilote utilise la même liste de contrôle.



- Les tâches qui prendraient des heures à effectuer manuellement sur des centaines de serveurs sont terminées en quelques minutes. Cela libère nos ingénieurs pour travailler sur l'innovation et l'amélioration, et non sur un travail manuel répétitif.


- L'automatisation est la défense ultime contre l'erreur humaine. Une étape oubliée ou une faute de frappe lors de la configuration manuelle peut entraîner une panne. Un processus automatisé et testé s'exécute parfaitement à chaque fois, améliorant la fiabilité et la sécurité de l'ensemble de notre compagnie aérienne.




Plus d'informations
================


* [Page produit SUSE Multi-Linux Manager](https://www.suse.com/products/suse-manager/)

* [Intégration Ansible](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/ansible-integration.html)

* [Guide Salt](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/specialized-guides/salt/salt-overview.html)