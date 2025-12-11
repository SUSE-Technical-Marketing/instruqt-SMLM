---
slug: smlms-intro
id: zaeakwb4zmfo
type: challenge
title: Willkommen zum SUSE Multi-Linux Hands-on Workshop!
teaser: Willkommen zum SUSE Multi-Linux Hands-on Workshop! In diesem Abschnitt stellen
  wir Ihnen den Workshop und seine Hauptkomponenten vor.
notes:
- type: text
  contents: |
    # Willkommen zum SUSE Multi-Linux Hands-on Workshop!
    Bitte warten Sie, während wir Ihre Laborumgebung einrichten.
    <img class="logos" src="../assets/logos/suse_logo.svg"/>
tabs:
- id: un6rx80ujzky
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: ""
enhanced_loading: null
---

Willkommen zum <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">SUSE</b> Multi-Linux Hands-on Workshop
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

In diesem Workshop werden Sie etwas von der Magie entdecken, die der <b class="smlmext">SUSE Multi-Linux Manager</b> (<b class="smlm">SMLM</b>) bewirken kann; es ist die Lösung von <b class="suse">SUSE</b>, um mehrere Linux-Distributionen im großen Maßstab von einer einheitlichen Oberfläche aus zu verwalten. Außerdem werden Sie entdecken, wie Sie Ihre Legacy-Produktionsserver mit <b class="smlsext">SUSE Multi-Linux Support</b> (<b class="smls">SMLS</b>) unterstützt halten können, unserer professionellen und zuverlässigen Support-Lösung für Linux-Systeme.

&emsp;&emsp; Sie schlüpfen in die Rolle eines **Ingenieurs** bei <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b>, einer Fluggesellschaft, bei der jedes Flugzeug einen Linux-Server an Bord hat.

&emsp;&emsp; Wie bei jeder Flugzeugkomponente ist es entscheidend, dass diese Server stabil und zuverlässig bleiben, egal ob sie sich am Boden in einem Rechenzentrum befinden oder über den Wolken fliegen ☁ ☁ ☁


&emsp;&emsp; Einige Flugzeugmodelle erfordern möglicherweise eine andere Linux-Variante oder eine andere CPU-Architektur. Dies ist kein Problem für <b class="smlm">SMLM</b>; Sie können die Linux-Distribution und CPU-Architektur frei wählen, die Ihren Bedürfnissen am besten entspricht, ohne auf einfache Standardisierung und Verwaltung verzichten zu müssen.


&emsp;&emsp; Als Ingenieur, der für die Verwaltung der Linux-Landschaft verantwortlich ist, werden Sie einige der Lösungen durchgehen, die <b class="smlm">SMLM</b> und <b class="smls">SMLS</b> Ihnen bieten, um die Systemverwaltung zu erleichtern und zu automatisieren sowie außergewöhnliche Probleme zu lösen, die auftreten können.


Entlang der verschiedenen Herausforderungen stehen Ihnen die folgenden Werkzeuge zur Verfügung:

 ✈ **SUSE Multi-Linux Manager**:
   Die zentrale Konsole (Single Pane of Glass) zur Verwaltung Ihres gesamten Linux-Stacks.

 ✈ **Centos 7**:
   Eine Legacy-Distribution, die noch auf einigen älteren Flugzeugen und Bodensystemen verwendet wird.

 ✈ **Ubuntu 24**: Eine spezifische Linux-Distribution, die von unserer Marketingabteilung benötigt wird, um ihre Grafikdesign-Anwendungen auszuführen.

 ✈ **SLES 15**: Die äußerst zuverlässige, stabile und sichere Linux-Distribution von <b class="suse">SUSE</b>, die das Rückgrat unserer kritischsten Systeme bildet.


## <b class="smlmext hovereffect">SUSE Multi-Linux Manager</b>

Es ist eine erstklassige Open-Source-Infrastruktur-Management-Lösung für Ihre softwaredefinierte Infrastruktur.

&emsp;&emsp; <b class="smlmext">SUSE Multi-Linux Manager</b> wurde entwickelt, um Ihren Enterprise DevOps- und IT-Operations-Teams zu helfen, Komplexität zu reduzieren und die Kontrolle über Ihre IT-Assets zurückzugewinnen – ein einziges, aber sehr leistungsfähiges Tool zur Verwaltung von Linux-Systemen über eine Vielzahl von Hardware-Architekturen, Hypervisoren sowie Container-, IoT- und Cloud-Plattformen hinweg.

&emsp;&emsp; Es automatisiert die Bereitstellung, das Patching und die Konfiguration von Linux-Servern und IoT-Geräten für eine schnellere, konsistente und wiederholbare Serverbereitstellung, was hilft, Abläufe zu optimieren und Kosten zu senken. Und mit automatisierter Überwachung, Nachverfolgung, Auditierung und Berichterstattung Ihrer Systeme, VMs und Container in Ihren Entwicklungs-, Test- und Produktionsumgebungen können Sie die Einhaltung interner Sicherheitsrichtlinien und externer Vorschriften sicherstellen.


## <b class="smlsext hovereffect">SUSE Multi-Linux Support</b>


Es ist ein umfassender Service, der technische Unterstützung und Wartung für verschiedene Linux-Distributionen bietet, einschließlich Ihres bestehenden Red Hat Enterprise Linux (RHEL), CentOS, <b class="liberty">SUSE Liberty Linux</b> und <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>), je nach Angebot.

&emsp;&emsp; Es ermöglicht Organisationen, gemischte Linux-Umgebungen effizient unter einem einzigen Support-Framework zu verwalten.
Je nach gekauftem Paket kann <b class="smlsext">SUSE Multi-Linux Support</b> auch den <b class="smlmext">SUSE Multi-Linux Manager</b> enthalten, ein Multi-Linux-Management-Tool zur Verwaltung dieser Distributionen.



 🌅 Erkunden Sie die Instruqt UI
=======================
Bevor wir mit unserer ersten Aufgabe beginnen, lassen Sie uns einen Moment Zeit nehmen, um die Instruqt UI zu betrachten.

+ Die **rechte Seite** des Bildschirms bietet Ihnen diese Anweisungen und Navigationssteuerungen.

+ Die **linke Seite** gibt Ihnen Zugriff auf die verschiedenen Maschinen und Dienste, aus denen unsere Laborumgebung besteht.

Innerhalb der Instruqt UI können Sie zwischen der [button label="SMLM UI" variant="success"](tab-0) und den verfügbaren [button label="terminals" variant="success"](tab-1) wechseln, indem Sie auf die Tabs oben im linken Bereich klicken.


> [!NOTE]
> In der Web-UI erfolgt kein automatisches Neuladen; in einigen Fällen müssen Sie möglicherweise den internen Webbrowser von Instruqt neu laden, um Aktualisierungen zu sehen.


🛫 Anmelden beim <b class="smlmext">SUSE Multi-Linux Manager</b> 🛫
========================================
Machen wir Sie mit der Umgebung vertraut.

- Öffnen Sie den <b class="smlmext">SUSE Multi-Linux Manager</b> innerhalb des Labors über die [button label="SMLM UI" variant="success"](tab-0)


- Melden Sie sich mit folgenden Zugangsdaten an:

  - Benutzername:
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```
  - Passwort:

```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

Wenn alles gut ging, sollten Sie die **Overview**-Seite in der <b class="smlmext">SUSE Multi-Linux Manager</b> UI sehen, eingeloggt als Benutzer `[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]`.

> [!NOTE]
> Wenn Sie direkt über Ihren Browser auf die <b class="smlmext">SUSE Multi-Linux Manager</b> UI zugreifen möchten, können Sie dies ebenfalls tun:

<b class="smlm">SMLM</b> URL: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>


> [!NOTE]
> Wenn die Seite nicht korrekt lädt, müssen Sie möglicherweise den Browser-Tab aktualisieren, nachdem die Laborumgebung den Startvorgang abgeschlossen hat.




🗺  Erkunden Sie den <b class="smlmext">SUSE Multi-Linux Manager</b> 🗺
======================================

Bevor wir abheben, machen wir uns mit den Steuerungen vertraut. Dies ist keine erschöpfende Tour, sondern ein kurzer Überblick über die wichtigsten Instrumente, die wir während des gesamten Workshops verwenden werden. Wir ermutigen Sie, neugierig zu sein und zu erkunden.


Lassen Sie uns beginnen.


- **Menü Systems** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_systems.png"/>

  Klicken Sie im linken Bereich auf `systems`. Dies ist unsere Flottenübersicht, die jeden registrierten Server anzeigt. Die Liste ist jetzt klein, wird aber wachsen, während wir unsere Übungen abschließen.

   - **System Lists**

     Dieser Abschnitt bietet praktische, vorgefilterte Ansichten. Zum Beispiel zeigt Ihnen die Liste `Out of Date` sofort an, welche Server Updates benötigen, und erspart Ihnen so eine manuelle Suche. </p>

  <br/>

  - **System Groups**

    Um unsere Flotte logisch zu organisieren, verwenden wir `System Groups`; Sie können sie nach beliebigen Kriterien kategorisieren. Dadurch sparen Sie Zeit beim Anwenden von Aktionen oder beim Definieren von Richtlinien. Einmal erstellt, können Sie Systeme automatisch einer oder mehreren Gruppen zuordnen, z. B. unter Verwendung von `activation keys`.


    Versuchen Sie ruhig, jetzt eine zu erstellen, indem Sie auf `+ Create Group` klicken.

  <br/>

  - **Batch operations**

    Der `System Set Manager` bietet eine leistungsstarke Möglichkeit, Aktionen auf mehreren Systemen gleichzeitig durchzuführen.


    Anstatt Änderungen einzeln anzuwenden, können Sie eine Sammlung von Systemen auswählen, entweder einzeln aus der System List oder durch Nutzung bestehender System Groups, und dann Aufgaben für alle in einer einzigen Operation ausführen.

  <br/>

  - **Provisioning**

    <b class="smlmext">SUSE Multi-Linux Manager</b> bietet umfassende Tools für die Bereitstellung neuer Systeme und die erneute Bereitstellung bestehender Systeme. Diese Fähigkeit hilft Ihnen, einen standardisierten und wiederholbaren Prozess für die Systembereitstellung zu etablieren.


    Beispielsweise können Sie im Abschnitt `Autoinstallation` Distributionen und Kickstart/AutoYaST-Profile definieren, mit denen Sie festlegen können, wie Ihre Systeme bereitgestellt werden sollen, welche Software installiert wird, wie der Speicherplatz verteilt wird und mehr.


    All diese einfach einzurichtenden Automatisierungsmechanismen können mit komplexen, aber leistungsfähigeren Automatisierungslösungen wie Salt oder Ansible kombiniert werden, sodass Sie die Freiheit behalten, die beste Lösung für jede Herausforderung zu wählen.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_systems.gif"/>
  </div>

<br/>



- **Menü Patches** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_patches.png"/>

  - **Patching**

    Eine der häufigsten Aufgaben in der IT ist es, Systeme auf dem neuesten Stand zu halten und von Zeit zu Zeit Sicherheitspatches in Eile anzuwenden!
    Mit SMLM können wir leicht eine Liste **relevanter** Patches sehen, nach Typ klassifiziert und mit allen Informationen versehen, die Sie wissen müssen, einschließlich aller Systeme und Pakete, die sie betreffen.

    Über die vom Anbieter gelieferten Patches hinaus können wir auch unsere eigenen Patches erstellen. Später werden wir die verschiedenen Optionen erkunden, die wir haben, um das Patching und regelmäßige Updates über unsere gesamte Flotte hinweg zu verwalten.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_patches.gif"/>
  </div>

<br/>
- **Software channels** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_software.png"/>

  In der `Channel List` können wir alle Paket-Kanäle/Repositories/Streams sehen, die zur Nutzung verfügbar sind; Sie können auch neue Software-Kanäle erstellen, um Ihre Software zu organisieren oder Ihre eigenen Pakete hochzuladen.

  Alle Kanäle, die Sie derzeit sehen, wurden von SMLM aus den offiziellen Quellen abgerufen und können leicht synchron gehalten werden.

  In der `Package Search` können wir nach bestimmten Paketen suchen und deren Inhalt und Metadaten inspizieren.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_software.gif"/>
  </div>

<br/>

- **Configuration** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_configuration.png"/>

  Es ist auch möglich, spezifische Konfigurationen auf Systeme anzuwenden und zu verwalten, bei der Registrierung oder danach; dafür können wir den Abschnitt `Configuration` inspizieren.

  SMLM bietet einen einfachen Weg, Revisionen zu verwalten, Konfigurationsdateien über Systeme hinweg bereitzustellen und zu vergleichen. Und alles kann leicht in Konfigurationskanälen gruppiert werden.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_configuration.gif"/>
  </div>

<br/>

- **Scheduling** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_schedule.png"/>

  In `Schedule` können wir geplante Aktionen beobachten und verwalten sowie spezifische Wartungsfenster definieren. Dies ist besonders nützlich, um regelmäßige Operationen zu automatisieren oder Canary-Deployments durchzuführen, wenn viele Systeme verwaltet werden. Wir werden dies später während des Workshops in Aktion sehen.

<br/>
<br/>

Der SUSE Multi-Linux Manager bietet viele Möglichkeiten, Ihre Systeme zu verwalten; wir können in diesem Workshop nicht alle abdecken, aber fühlen Sie sich wie immer frei, Fragen zu stellen und zu erkunden.

> [!NOTE]
> Ihr Benutzer verfügt über volle Admin-Rechte, daher empfehlen wir, Änderungen erst nach Abschluss der Übungen vorzunehmen.