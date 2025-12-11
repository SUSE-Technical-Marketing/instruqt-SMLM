---
slug: smlm-security
id: cp2yrai94b2c
type: challenge
title: Sicherheit und Patching
tabs:
- id: gyqzwp214um3
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Sicherheit und Patching
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



In diesem Labor werden wir uns einer unserer wichtigsten Aufgaben widmen: der Gewährleistung der Sicherheit unserer gesamten digitalen Flotte. Wir werden untersuchen, wie der <b class="smlmext">SUSE Multi-Linux Manager</b> es uns ermöglicht, auf Sicherheitsbedrohungen mit der Geschwindigkeit und Präzision zu reagieren, die von einer erstklassigen Fluggesellschaft gefordert werden.




## <b class="hovereffect">Ihre Ziele:</b>

- Führen Sie ein Sicherheits-Compliance-Audit Ihrer Systeme mit OpenSCAP durch.

- Identifizieren Sie Systeme, die von relevanten Sicherheitslücken betroffen sind.

- Wenden Sie die notwendigen Patches gleichzeitig auf alle betroffenen Systeme an.



Lab details
===========

Benutzername (Username):
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```

Passwort (Password):
```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

<b class="smlm">SMLM</b> URL: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>




Auditieren Sie Ihre Systeme
==================

Wir möchten unsere Produktionssysteme auditieren, um sicherzustellen, dass sie konform sind.

Wir haben bereits überprüft, dass folgende Pakete installiert sind:

- openscap-utils
- scap-security-guide


Wählen Sie die Produktionsgruppe aus

- Gehen wir zu `Systems` ✈ `System Groups`
- Finden Sie die Gruppe **prod** und klicken Sie auf `Use in SSM`
![Next](../assets/SMLM5.1/prod_group_selection.png)

Wir werden zur Seite **System Set Manager Overview** weitergeleitet; wie wir bereits gesehen haben, können wir von hier aus Aktionen auf mehrere Systeme gleichzeitig anwenden.

- Gehen Sie zum Tab `Audit`
- Füllen Sie unter `OpenSCAP` das Formular mit den folgenden Details aus, lassen Sie den Rest auf den Standardwerten:
  - **Command-line Arguments:** <b class="highlightcopy">--profile xccdf_org.ssgproject.content_profile_stig</b>
  - **Path to XCCDF document:** <b class="highlightcopy">/usr/share/xml/scap/ssg/content/ssg-sle15-ds.xml</b>
- Drücken Sie


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">
</p>
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-Schedule.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p>



Dies wird ein paar Minuten dauern.


Um die Ergebnisse zu sehen, gehen wir zu `Audit` ✈ `OpenSCAP` ✈ `All Scans`

![OpenSCAP Results](../assets/SMLM5.1/openscap_results.png)

Wenn wir auf eines dieser Ergebnisse klicken, können wir eine detailliertere Aufschlüsselung sehen.

- Durch Klicken auf **report.html** können Sie eine schönere Version des Berichts anzeigen, der von OpenSCAP generiert wurde.

![Detailed OpenSCAP Results](../assets/SMLM5.1/openscap_results_detailed.png)


Machen Sie sich keine Sorgen über die gemeldeten Probleme.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-audit_your_system.gif"/>
  </div>

<br/>



Von Schwachstellen betroffene Systeme identifizieren
============================================

Wir wollen sehen, welche Systeme von Schwachstellen betroffen sind.

- Lassen Sie uns nun zu `Patches` ✈ `Patch List` ✈ `Relevant` navigieren

  Hier sehen wir eine Liste aller relevanten Patches, die für unsere Systeme verfügbar sind. Schauen wir uns die **Security Patches** (Sicherheits-Patches) an.

- Durch Klicken auf den Namen eines **Advisory** (Hinweis) können Sie eine detaillierte Seite anzeigen, die unter anderem zeigt, welche Pakete und Systeme betroffen sind.

- Auf der rechten Seite der Liste bietet die Spalte **CVEs** direkte Links zu den offiziellen Schwachstellenberichten.

  Es ist auch möglich, unsere eigenen Patches zu erstellen, aber wir werden das in diesem Kurs nicht behandeln. Für weitere Informationen konsultieren Sie bitte die Links am Ende.



## <b class="hovereffect">Betroffene Systeme patchen</b>

Das Patchen unserer Systeme ist so einfach wie das Befolgen dieser Schritte:

- Gehen Sie zu `Systems` ✈ `System Set Manager`
- Navigieren Sie zum Tab `Patches` ✈ wählen Sie **Security Advisory** in der Dropdown-Liste aus und klicken Sie auf `Show`

![Select Security Advisory](../assets/SMLM5.1/show_only_security_advisories.png)

- Klicken Sie auf `Select All` ✈ `Apply Patches` ✈ ![Confirm](../assets/SMLM5.1/bottom-confirm.png)


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-indentify_vulnerabilities.gif"/>
  </div>

<br/>


Warum ist das wichtig für [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================


- Indem wir schnell handeln können, reduzieren wir das Zeitfenster der Gefährdung. Wenn eine neue Schwachstelle entdeckt wird, beginnt ein Wettlauf zwischen uns und den böswilligen Akteuren, die versuchen, sie auszunutzen. Ein komplexer, manueller Patch-Prozess lässt unsere kritischen Systeme viel zu lange ungeschützt.

- **SUSE Multi-Linux Manager** bietet eine einzige, einheitliche Sicht auf die Sicherheitslage unserer gesamten Flotte und ermöglicht es uns, Bedrohungen mit einem konsistenten, zuverlässigen Prozess zu beheben.

- Die Möglichkeit, die Konformität unserer Systeme mit verschiedenen Sicherheits-Frameworks einfach zu überprüfen, ermöglicht es uns, Korrekturmaßnahmen schneller umzusetzen und strenge Branchenvorschriften einzuhalten.


Mehr Informationen
================


* [Auditierung](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/auditing.html)
* [SUSE Sicherheit](https://www.suse.com/support/security/)
* [System-Sicherheit mit OpenSCAP](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/openscap.html)
* [Patches verwalten](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)