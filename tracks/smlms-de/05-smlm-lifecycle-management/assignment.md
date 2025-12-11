---
slug: smlm-lifecycle-management
id: x9ip7lxbxew4
type: challenge
title: Lebenszyklusmanagement
tabs:
- id: syb07lnbwgrx
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Lebenszyklusmanagement
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

In diesem Teil gehen wir von individuellen Wartungsaufgaben zur Etablierung eines flottenweiten, zertifizierten Prozesses für das Änderungsmanagement über. Wir werden untersuchen, wie das Content Lifecycle Management im <b class="smlmext">SUSE Multi-Linux Manager</b> die Struktur und Sicherheit bietet, die unsere Fluggesellschaft verlangt.



Bei [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] wird ein neues Teil nicht in dem Moment in einen Passagierjet eingebaut, in dem es vom Hersteller eintrifft. Es durchläuft einen strengen Zertifizierungsprozess.

Zuerst wird es in einer kontrollierten Werkstatt untersucht und getestet (**Development** / Entwicklung). Als Nächstes wird es in ein nicht-kommerzielles Testflugzeug eingebaut und zermürbenden Boden- und Flugtests unterzogen (**Quality Assurance** / Qualitätssicherung). Erst nachdem es jede denkbare Prüfung bestanden hat, wird es für den Einbau in unsere aktive Flotte zertifiziert (**Production** / Produktion).



Dieser methodische, abgestufte Ansatz verhindert, dass eine einzelne fehlerhafte Komponente ein Flugzeug am Boden hält, und gewährleistet die Sicherheit unserer Passagiere und die Zuverlässigkeit unseres Betriebs. Wir wenden genau dieselbe Philosophie auf unsere IT-Systeme an. Ein Software-Upgrade oder eine neue Anwendung ist eine "Komponente", die, wenn sie fehlerhaft ist, unseren digitalen Betrieb zum Erliegen bringen könnte. Das Content Lifecycle Management ist unser offizieller Zertifizierungsprozess für alle Softwareänderungen.



## <b class="hovereffect">Ihre Ziele:</b>

- Ein Content-Lifecycle-Projekt erstellen.

- Das Projekt verwenden, um Software-Updates für unsere Systeme zu verwalten und zu zertifizieren.



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


Aufbau unseres Software-Zertifizierungspfades
==============================================

In dieser Übung erstellen wir ein Content-Lifecycle-Projekt, um den Fluss von Software-Updates zu steuern. Dies stellt sicher, dass ein Patch gründlich getestet wird, bevor er jemals unsere kritischen Produktionsserver erreicht.

<br/>

Unser Ziel ist es, eine `Dev ✈ QA ✈ Prod` Pipeline aufzubauen.

1.  **Development (Dev):** Die erste Werkstatt. Alle neuen Patches und Pakete kommen zuerst hier an.
2.  **Quality Assurance (QA):** Das Testgelände. Wir werden eine spezifische Version des Inhalts von Dev nach QA befördern (promoten), damit unsere Testteams sie validieren können.
3.  **Production (Prod):** Die aktive Flotte. Nur der von der QA genehmigte, zertifizierte Satz von Patches wird in die Produktion befördert, wo er sicher auf unsere Live-Systeme angewendet werden kann.



<br/>

## <b class="hovereffect">Das Projekt erstellen</b>

- Navigieren Sie zu `Content Lifecycle` ✈ `Projects` und klicken Sie auf ![Create Project](../assets/SMLM5.1/bottom-create_project.png)

- Füllen Sie die Projektdetails aus:

- **Project Name** (Projektname):

```txt
Airtrain SLES15 SPx
```

- **Project Label** (Projektlabel):

```txt
at-sles15_spx
```

- **Project Description** (Projektbeschreibung):

```txt
Certified software channel for Airtrain SLES 15 systems.
```


- Klicken Sie auf ![Create](../assets/SMLM5.1/bottom-create.png)

Lassen Sie es uns nun befüllen. Klicken Sie auf `Attach/Detach Sources`

![Create](../assets/SMLM5.1/content_lifecycle_just_created.png)

- Wählen Sie unter **New Base Channel** <b class="sles">SLE-Product-SLES15-SP6-Pool for x86_64</b> aus und klicken Sie auf ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">Dev-Umgebung erstellen</b>

Erstellen Sie den Lebenszyklus der Entwicklungsumgebung (Development Environment Lifecycle)

- Klicken Sie auf `Add Environment`

![Create](../assets/SMLM5.1/content_lifecycle_just_created_environment_lifecycle.png)

- Befüllen Sie es mit Folgendem:
  * **Name:** <b class="highlightcopy">Development</b>
  * **Label:** <b class="highlightcopy">dev</b>

- Klicken Sie auf ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">QA-Umgebung erstellen</b>

Erstellen Sie den Lebenszyklus der Qualitätssicherungsumgebung (Quality Assurance Environment Lifecycle)

- Klicken Sie auf `Add Environment`

- Befüllen Sie es mit Folgendem:
  * **Name:** <b class="highlightcopy">QA</b>
  * **Label:** <b class="highlightcopy">qa</b>

- Klicken Sie auf ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">Prod-Umgebung erstellen</b>

Erstellen Sie den Lebenszyklus der Produktionsumgebung (Production Environment Lifecycle)

- Klicken Sie auf `Add Environment`

- Befüllen Sie es mit Folgendem:
  * **Name:** <b class="highlightcopy">Production</b>
  * **Label:** <b class="highlightcopy">prod</b>

- Klicken Sie auf ![Save](../assets/SMLM5.1/bottom-save.png)

<br/>

## <b class="hovereffect">Befüllen (Populate)</b>

Jetzt haben wir alle drei Umgebungen, lassen Sie uns diese mit Inhalt befüllen.

Wir werden in diesem Fall keinen Filter verwenden, da <b class="sles">SLES</b> bereits stabile Paketversionen bereitstellt.

Der Testrhythmus von [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] beträgt derzeit einen Monat, daher benennen wir diesen Build nach dem aktuellen Monat, Oktober.

- Klicken Sie auf ![Build](../assets/SMLM5.1/bottom-build.png)

- Geben Sie in **Version Message** ein:

```txt
October
```


- Klicken Sie auf `Build`

> [!NOTE]
> Dieser Vorgang kann einige Minuten dauern. Sie werden einige Schritte wie 'Cloning' sehen, aber Sie können beruhigt sein, dass dies nicht viel Speicherplatz erfordert. Der Klonvorgang betrifft nur die Paketindexpunkte, nicht die eigentlichen Pakete selbst.


<br/>

## <b class="hovereffect">Inhalte promoten</b>

Lassen Sie uns nun den Inhalt in weitere Phasen befördern (promoten).

- Klicken Sie auf die Schaltfläche `Promote` zwischen Development und QA.
- Ein weiterer Bildschirm mit dem Titel **Promote version 1 into QA** wird angezeigt. Klicken Sie einfach erneut auf `Promote`.

Wiederholen Sie denselben Schritt für Production.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-create_the_project.gif"/>
  </div>

<br/>

Unsere Systeme upgraden.
====================

Lassen Sie uns nun ausprobieren, wie es funktioniert.

Wir werden:
- einige unserer Systeme zur neuen Umgebung hinzufügen.
- Eine neue Version des Inhalts erstellen.
- Die neue Version promoten und die Systeme aktualisieren.

<br/>

## <b class="hovereffect">Systeme hinzufügen</b>

Gehen wir zu `Systems` ✈ `System List` ✈ `All`

- Klicken Sie auf das System **at-ct-qa**
- Gehen Sie zu `Software` ✈ `Software Channels`
- Wählen Sie unter **Custom Channels** das Kontrollkästchen für den Kanal **at-sles15_spx-qa-...** aus und klicken Sie auf ![Next](../assets/SMLM5.1/bottom-next.png)
- Klicken Sie auf ![Confirm](../assets/SMLM5.1/bottom-confirm.png)


Gehen Sie zurück zu `Systems` ✈ `System List` ✈ `All`

- Filtern Sie nach:

```txt
at-
```

- Wählen Sie alle Systeme aus, die mit **-pro** enden
- Gehen Sie zu `Systems` ✈ `System Set Manager`
- Gehen Sie zu `Channels`
- Wählen Sie unter **Custom Channels** das Kontrollkästchen für den Kanal **at-sles15_spx-prod-...** aus und klicken Sie auf ![Next](../assets/SMLM5.1/bottom-next.png)
- Klicken Sie auf 'include recommended' (Empfohlene einschließen), um alle empfohlenen Kanäle zu abonnieren:

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-next.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-add_systems.gif"/>
  </div>

<br/>

## <b class="hovereffect">Eine neue Version erstellen</b>


Ein Monat ist vergangen und wir wollen mit unserem stabilen Upgrade-Prozess fortfahren.
Sie werden eine statische, unveränderliche Kopie der Softwarekanäle für das Entwicklerteam erstellen.

Es werden keine neuen Patches plötzlich auftauchen und ihre Arbeit stören.

- Gehen Sie zurück zu `Content Lifecycle` ✈ `Projects` und klicken Sie auf das Projekt, das wir gerade erstellt haben.

- Klicken Sie auf ![Build](../assets/SMLM5.1/bottom-build.png)

- Geben Sie in **Version Message** ein:

```txt
November
```


- Klicken Sie auf `Build`

Beachten Sie, dass sich die Versionsnummer automatisch erhöht hat.

Jetzt können Entwickler ihre Arbeit mit den neuen und gepatchten Versionen von Bibliotheken und Anwendungen verrichten, die von SUSE bereitgestellt werden.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-create_new_version.gif"/>
  </div>


<br/>

## <b class="hovereffect">Inhalte von Dev nach QA promoten</b>

Nehmen wir an, unsere Entwickler haben ihre Zustimmung gegeben. Es ist Zeit, eine stabile Version für das QA-Team zu erstellen, damit alle Vorproduktionstests durchgeführt werden können.

- Klicken Sie auf die Schaltfläche `Promote` zwischen Development und QA.
- Ein weiterer Bildschirm mit dem Titel **Promote version 2 into QA** wird angezeigt. Klicken Sie einfach erneut auf `Promote`.

Gehen wir nun zu unseren QA-Systemen und führen ein Upgrade durch.

- `Systems` ✈ `System List` ✈ `All`
- Klicken Sie auf das System **at-ct-qa**
- Gehen Sie zu `Software` ✈ `Packages` ✈ `Upgrade`
- Klicken Sie auf:

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


Jetzt können unsere QA-Ingenieure ihre Tests sicher und ohne Unterbrechung durchführen.


> [!NOTE]
> Wir haben nicht genug Zeit, um Änderungen durchlaufen zu sehen. In einem realen Szenario sollten neue Versionen von Paketen verfügbar sein, um sie in Version 2 zu promoten.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/05-lifecycle_management-promote_from_dev_to_QA.gif"/>
  </div>


<br/>

## <b class="hovereffect">Nach Produktion promoten</b>

Das QA-Team hat seine strengen Tests an `v2` abgeschlossen und sie als stabil und sicher für die Hauptflotte zertifiziert. Es ist an der Zeit, sie unseren Produktionssystemen zur Verfügung zu stellen.

Wir werden denselben Prozess wie für QA in unserer Produktionsumgebung wiederholen:

- Erstens, den Inhalt promoten.
  Dadurch werden die neuen Pakete für unsere Produktionsserver verfügbar.
  Sie haben erfolgreich sichergestellt, dass nur getestete und genehmigte Updates Ihre kritischsten Systeme erreichen können.

- Zweitens, unsere Produktionssysteme upgraden. Der einzige Unterschied hierbei ist, dass wir das Upgrade für **morgen um 14:00 Uhr** planen, damit alle unsere Teams vorbereitet sind und wir einen kontrollierten Prozess haben.


<br/>

Warum ist das wichtig für [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- Wir bauen eine Reihe von Sicherheitsschleusen auf, die es einfacher machen, ein Kernprinzip unserer Betriebsstrategie umzusetzen: **Risikomanagement**.
- Ein einzelner schlechter Patch, der in die **Dev**-Umgebung eingeführt wird, kann erkannt und behoben werden, lange bevor er die Chance hat, umsatzgenerierende Systeme zu beeinträchtigen.
- Dieser Prozess verwandelt das Patchen und Aktualisieren von einem riskanten, nervenaufreibenden Ereignis in ein vorhersehbares Routine-Wartungsverfahren, den Grundstein einer zuverlässigen Fluggesellschaft.


<br/>

Mehr Informationen
================

* [Maintenance Windows (Wartungsfenster)](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

* [Patch Management](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)

* [Content Lifecycle Management](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/content-lifecycle.html)

* [SUSE Multi-Linux Manager Produktseite](https://www.suse.com/products/suse-manager/)