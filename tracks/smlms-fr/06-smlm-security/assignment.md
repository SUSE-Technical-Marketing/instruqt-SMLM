---
slug: smlm-security
id: s2blfgrusrzn
type: challenge
title: Sécurité et application de correctifs
tabs:
- id: jzzqynhzz5pq
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Sécurité et application de correctifs
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

<img class="logos" alt="Welcome!" src="../assets/logos/06-security.jpeg"/>



Dans ce laboratoire, nous aborderons l'une des responsabilités les plus importantes que nous ayons : assurer la sécurité de l'ensemble de notre flotte numérique. Nous explorerons comment <b class="smlmext">SUSE Multi-Linux Manager</b> nous permet de répondre aux menaces de sécurité avec la rapidité et la précision requises par une compagnie aérienne de classe mondiale.




## <b class="hovereffect">Vos Objectifs :</b>

- Effectuer un audit de conformité de sécurité sur vos systèmes à l'aide d'OpenSCAP.

- Identifier les systèmes affectés par des vulnérabilités de sécurité pertinentes.

- Appliquer les correctifs nécessaires à tous les systèmes affectés simultanément.



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




Auditez vos systèmes
==================

Nous voulons auditer nos systèmes de production pour nous assurer qu'ils sont conformes.

Nous avons déjà vérifié que les paquets suivants sont installés :

- openscap-utils
- scap-security-guide


Sélectionnez le groupe de production

- Allons dans `Systems` ✈ `System Groups`
- Trouvez le groupe **prod** et cliquez sur `Use in SSM`
![Next](../assets/SMLM5.1/prod_group_selection.png)

Nous serons dirigés vers la page **System Set Manager Overview**, comme nous l'avons vu précédemment, d'ici nous pouvons appliquer des actions à plusieurs systèmes à la fois.

- Allez dans l'onglet `Audit`
- Sous `OpenSCAP`, complétez le formulaire avec les détails suivants, laissez le reste avec les valeurs par défaut :
  - **Command-line Arguments :** <b class="highlightcopy">--profile xccdf_org.ssgproject.content_profile_stig</b>
  - **Path to XCCDF document :** <b class="highlightcopy">/usr/share/xml/scap/ssg/content/ssg-sle15-ds.xml</b>
- Appuyez sur


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">
</p>
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-Schedule.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p>



Cela prendra quelques minutes.


Pour voir les résultats, allons dans `Audit` ✈ `OpenSCAP` ✈ `All Scans`

![OpenSCAP Results](../assets/SMLM5.1/openscap_results.png)

Si nous cliquons sur l'un de ces résultats, nous pouvons voir une analyse plus détaillée.

- En cliquant sur **report.html**, vous pouvez voir une version plus agréable du rapport généré par OpenSCAP.

![Detailed OpenSCAP Results](../assets/SMLM5.1/openscap_results_detailed.png)


Ne vous inquiétez pas des problèmes signalés.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-audit_your_system.gif"/>
  </div>

<br/>



Identifier les systèmes affectés par des vulnérabilités
============================================

Nous voulons voir quels systèmes sont affectés par des vulnérabilités.

- Maintenant, naviguons vers `Patches` ✈ `Patch List` ✈ `Relevant`

  Ici, nous pouvons voir une liste de tous les correctifs pertinents disponibles pour nos systèmes, regardons les **Security Patches** (Correctifs de sécurité).

- En cliquant sur le nom d'un **Advisory** (Avis), vous pouvez voir une page détaillée montrant quels paquets et systèmes il affecte, entre autres détails.

- Sur le côté droit de la liste, la colonne **CVEs** fournit des liens directs vers les rapports officiels de vulnérabilité.

  Il est également possible de créer nos propres correctifs, mais nous ne couvrirons pas cela dans ce parcours, pour plus d'informations, veuillez consulter les liens à la fin.



## <b class="hovereffect">Corriger les systèmes affectés</b>

Corriger nos systèmes est aussi simple que de suivre ces étapes :

- Allez dans `Systems` ✈ `System Set Manager`
- Naviguez vers l'onglet `Patches` ✈ sélectionnez **Security Advisory** dans la liste déroulante, et cliquez sur `Show`

![Select Security Advisory](../assets/SMLM5.1/show_only_security_advisories.png)

- Cliquez sur `Select All` ✈ `Apply Patches` ✈ ![Confirm](../assets/SMLM5.1/bottom-confirm.png)


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-indentify_vulnerabilities.gif"/>
  </div>

<br/>


Pourquoi est-ce important pour [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] ?
=================================================================================


- En étant capables d'agir rapidement, nous réduisons la fenêtre d'exposition. Lorsqu'une nouvelle vulnérabilité est découverte, une course commence entre nous et les acteurs malveillants essayant de l'exploiter. Un processus d'application de correctifs manuel et complexe laisse nos systèmes critiques exposés pendant trop longtemps.

- <b class="smlmext">SUSE Multi-Linux Manager</b> fournit une vue unique et unifiée de la posture de sécurité de toute notre flotte et nous permet de remédier aux menaces avec un processus cohérent et fiable.

- Être capable de vérifier facilement la conformité de nos systèmes par rapport à différents cadres de sécurité nous permet de mettre en œuvre des mesures correctives plus rapidement et de respecter les réglementations strictes de l'industrie.


Plus d'informations
================


* [Audit](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/auditing.html)
* [Sécurité SUSE](https://www.suse.com/support/security/)
* [Sécurité du système avec OpenSCAP](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/openscap.html)
* [Gérer les correctifs](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)