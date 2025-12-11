---
slug: smls-extended-support
id: hbtkbmra5kws
type: challenge
title: Erweiterter Support für Legacy-Systeme
tabs:
- id: kwpt4olnzeq3
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: amcvpvjsunny
  title: CentOS 7 QA
  type: terminal
  hostname: centos7
- id: owmxnld5pkud
  title: CentOS 7 Prod
  type: terminal
  hostname: zzcentos7
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Erweiterter Support für Legacy-Systeme
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

# Verlängerung der Lebensdauer unserer Legacy-Flotte

In jeder Fluggesellschaft gibt es ältere, zuverlässige Flugzeuge, die Ihnen seit Jahren dienen, für die Sie jedoch noch keinen Ersatz haben. Für uns ist ein Teil dieser Legacy-Flotte unsere CentOS 7 Systeme. Sie sind stabil, aber End-of-Life, was bedeutet, dass sie keine kritischen Sicherheitsupdates mehr von ihrem ursprünglichen Hersteller erhalten. Für eine Fluggesellschaft ist das Fliegen ohne Support ein Risiko, das wir einfach nicht eingehen können.

Die traditionelle Lösung wäre ein vollständiger, kostspieliger Austausch jedes einzelnen Systems.
Aber was wäre, wenn wir ein Upgrade zur Lebensdauerverlängerung durchführen könnten, indem wir sie vor Ort mit minimaler Unterbrechung modernisieren? Genau das ist die Mission für diese Herausforderung. Wir werden die Kraft des <b class="smlmext">SUSE Multi-Linux Manager</b> zusammen mit <b class="smlsext">SUSE Multi-Linux Support</b> nutzen, um diese Systeme sicher zu überführen und sie im Dienst zu halten, bis wir sie durch ein moderneres OS ersetzen können.



## <b class="hovereffect">Unser Flugplan:</b>

- Untersuchen der aktuellen Legacy-Systeme, auf denen Centos 7 läuft

- Onboarden des QA-Systems und Anwenden aller verfügbaren Patches

- Identifizieren und Anwenden von Updates, falls vorhanden.

- Befreien (Liberate) des Systems mit der Liberate-Formel.

- Beobachten, was sich zwischen beiden Systemen geändert hat

- Identifizieren, ob es sich um eine Migration handelt.

<br/>

## <b class="hovereffect">Unsere Flugzeuge</b>

- CentOS 7 QA ✈ Unser Test- und Entwicklungsserver.

- CentOS 7 Prod ✈ Unser Produktionsserver, der bereits im <b class="smlm">SMLM</b> registriert ist

<br/><br/>


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



Onboarding von Centos 7 QA
======================



## <b class="hovereffect">Untersuchung der aktuellen Legacy-Systeme</b>

Greifen Sie über den Tab [button label="Centos 7 QA" variant="success"](tab-1) auf das Systemterminal zu.

Überprüfen Sie die aktuelle Version des Systems:

```bash,run
rpm -qi centos-release centos-logos
```


Führen Sie nun den folgenden Befehl aus, um das System im <b class="smlm">SMLM</b> zu registrieren:


```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | SMLM_DNS="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-liberty7ltss PROFILENAME='airco-dh4a-qa' bash ; echo "Let's wait 2 minutes for all the background processes to finish"; sleep 120
```


Dies ähnelt dem, was wir im vorherigen Labor für das Onboarding von Ubuntu verwendet haben. Was sich ändert, ist:

- **Activation key** (Aktivierungsschlüssel): Ist eine Referenz auf die Einstellungen, die standardmäßig auf das System angewendet werden. In diesem Fall wurde er erstellt, um nur anzugeben, in welchen Softwarekanälen das System registriert wird.

- **Profile name** (Profilname): Wenn wir ihn nicht angeben, wird der Hostname verwendet, aber in diesem Fall möchten wir, dass er einen aussagekräftigeren Namen mit derselben Namenskonvention hat, die wir bei Centos 7 Prod verwendet haben.


**Optional:** Wenn wir neugierig sind und sehen möchten, was passiert, wenn wir ein Upgrade durchführen und die Liberate-Formel ausführen, können wir den folgenden Befehl auf beiden Systemen ausführen ( [button label="Centos 7 QA" variant="success"](tab-1) und [button label="Centos 7 Prod" variant="success"](tab-2) ):


```bash,run
journalctl -f
```

Und sehen Sie, wie die Protokolle in den Terminals erscheinen.


<br/><br/>


## <b class="hovereffect">Identifizieren und Anwenden von Updates aus <b class="liberty">Liberty</b> Repositories</b>

Diese Centos 7 Systeme werden mit den neuesten Paketen geliefert, die Upstream bereitgestellt werden. Wir möchten sicherstellen, dass neue Fehler behoben werden und wir einen freundlichen Support-Mitarbeiter haben, der uns bei Problemen hilft. Nun haben wir die Centos 7 Systeme während des Registrierungsprozesses bereits für die von SUSE bereitgestellten Software-Repositories abonniert, also lassen Sie uns sie alle patchen:



Wechseln wir nun zum [button label="SMLM UI" variant="success"](tab-0) Tab


- Gehen Sie im linken Menü zu `Systems` ✈ `System List`.

- Suchen Sie Ihren Host **airco-dh4a-qa** und klicken Sie darauf.

- Wählen Sie `Software` ✈ `Packages`

- Klicken Sie auf `Update Packages List`, dies dauert etwa eine Minute.

- Wählen Sie `Software` ✈ `Patches`

- Sie werden eine Liste der verfügbaren Patches sehen.

Klicken Sie auf `Select All`, dann oben rechts auf `Apply Patches` und schließlich auf `Confirm`. Der <b class="smlmext">SUSE Multi-Linux Manager</b> wird nun den Upgrade-Vorgang auf dem CentOS-System planen und durchführen.


> [!NOTE]
> Es kann einige Minuten dauern, bis die Liste der Pakete abgerufen ist, bevor Sie die Liste der Patches sehen können, die auf das System angewendet werden können.


Da dies eine Weile dauern kann, lassen Sie uns sehen, was unter der Haube passiert.
Gehen Sie zum Tab `Events`, dann zu `History`. Sie sollten eine Liste von Ereignissen sehen, die seit der Registrierung des Systems im <b class="smlm">SMLM</b> stattgefunden haben. In den ersten Zeilen sollten wir ein Ereignis finden können, das so etwas wie *Combined Patch* enthält.


Wenn wir darauf klicken, können wir alle Details sehen. Schauen Sie sich ruhig um, ansonsten warten Sie, bis das Symbol grün ist:

![Successfully patched](../assets/SMLM5.1/successfully_updated_system.png)

Wir haben gerade Patches angewendet, die Fehler in den vorhandenen Paketen beheben. Diese gepatchten Pakete kommen direkt von SUSE, dies ist keine Migration.

<br/>

Vergleichen wir es mit dem Produktionssystem, das wir noch nicht aktualisiert haben.

Bitte gehen Sie zu `Software` ✈ `Packages` ✈ `Profiles`

Wählen Sie das System `airco-dh4a-prod` aus, welches die Produktionsversion ist, und klicken Sie dann auf:

![Compare](../assets/SMLM5.1/bottom-compare.png)


Wir können sehen, dass sich die meisten Paketversionen nicht geändert haben, immer noch dieselbe Version ( **X.X.X**-xyz ), aber mit einem angewendeten Patch ( X.X.X-**xyz** ).

Bevor wir zum nächsten Abschnitt übergehen, lassen Sie uns ein gespeichertes Profil erstellen. Dies wird uns helfen, die Unterschiede deutlicher zu sehen, nachdem wir im nächsten Abschnitt die Liberate-Formel angewendet haben.


Bitte gehen Sie zu `Software` ✈ `Packages` ✈ `Profile` und klicken Sie auf `Create System Profile`. Als Namen können Sie es nennen:

```txt
before_liberation
```


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-identify_and_apply_updates.gif"/>
  </div>


<br/><br/>


Das System befreien (Liberate) (optional)
==============================

Dies ist ein **optionaler** Schritt und nicht erforderlich, um Support zu erhalten.

Lassen Sie uns nun das System befreien (liberate):

- Gehen Sie zum Tab `Formulas`, suchen Sie nach **Liberate**, und sobald gefunden, wählen Sie es aus und klicken Sie oben rechts auf `Save`.

Sie werden eine blaue Nachricht oben auf dem Bildschirm sehen. Scrollen Sie nach oben, wenn Sie sie nicht sehen können:

![Formula saved](../assets/SMLM5.1/formula_saved.png)


Klicken Sie dort, wo `Highstate` steht. Sie werden zu einem anderen Tab weitergeleitet (`States` ✈ `Highstate`).

Sie können in der Zusammenfassung unten sehen, dass die Liberate-Formel aufgeführt ist.

Um den Befreiungsprozess zu starten, klicken Sie auf:

![Formula saved](../assets/SMLM5.1/bottom-apply_highstates.png)

Dies wird einige Zeit dauern. Bitte überprüfen Sie `Events` -> `History`. Sie sollten ein Ereignis namens **Apply highstate scheduled** sehen.

Lassen Sie uns ein paar Minuten warten, bis es fertig ist. In der Zwischenzeit können Sie beobachten, was passiert, indem Sie auf das Terminal [button label="Centos 7 QA" variant="success"](tab-1) schauen.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-liberate.gif"/>
  </div>

<br/><br/>

## <b class="hovereffect">Beobachten, was sich geändert hat</b>


Sobald es abgeschlossen ist, vergleichen wir das System erneut, um den Unterschied zu sehen. Wenn wir nicht bereits dort sind, klicken wir auf den Systemnamen `airco-dh4a-qa`.

Gehen Sie dann zu `Software` ✈ `Packages` ✈ `Profile`

Unter **Compare to Stored Profile** klicken Sie auf: ![Compare](../assets/SMLM5.1/bottom-compare.png)

Wir können sehen, dass das Einzige, was sich geändert hat, die folgenden Pakete sind:

- **centos-logos**, ersetzt durch **sles_es-logos**

- **centos-release**, ersetzt durch **sles_es-release-server**

Der Rest bleibt gleich, aber jetzt haben Sie den gesamten Support, Upgrades und Patches, die von <b class="suse">SUSE</b> für <b class="liberty">Liberty Linux</b> bereitgestellt werden.

Dasselbe gilt für modernere Versionen von CentOS und RHEL. Sie können sie in <b class="liberty">Liberty</b> umwandeln und von <b class="suse">SUSE</b> unterstützen lassen, ohne Änderungen an der eigentlichen Software und den Bibliotheken vornehmen zu müssen.



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-what_changed.gif"/>
  </div>

<br/>



Den Produktionsserver befreien (Liberate) (optional)
=========================================

Wir haben gesehen, wie wir unseren alten Centos 7 Server in QA patchen und befreien (Liberate). Jetzt ist es an der Zeit, dasselbe mit dem Produktionssystem zu tun, aber dieses Mal werden wir es in einer anderen Reihenfolge tun.

- Zuerst wenden wir die **Liberate** Formel an

  Gehen wir zu unserem Produktionsserver `airco-dh4a-prod` und `Create System Profile`

  Danach wenden wir die **Liberate** Formel an, wie wir es beim QA-System getan haben.

- Sobald es abgeschlossen ist, vergleichen wir das System mit dem Profil, das wir gerade erstellt haben. Wie wir sehen können, war die einzige Änderung die Pakete **centos-logos** und **centos-release**, der Rest bleibt genau gleich.


Ist es eine Migration?
==================

Eine Migration beinhaltet den Aufbau eines brandneuen Servers, die Neuinstallation aller Anwendungen von Grund auf und das sorgfältige Übertragen der Daten – ein Prozess, der zeitaufwändig, teuer und risikoreich ist.

Was wir getan haben, war weitaus eleganter. Wir haben ein In-Place-Upgrade durchgeführt.

Die Identität des Servers, der Hostname, die Anwendungen und die Benutzerdaten blieben völlig unberührt. Wir haben einfach seine zugrunde liegende Quelle für Updates geändert, und diese End-of-Life-Komponenten sind nun vollständig unterstützte Komponenten, die Patches erhalten.

Wir haben die Lebensdauer unseres Systems erfolgreich verlängert, es wieder in die Sicherheits-Compliance gebracht und das alles ohne die Unterbrechung einer vollständigen Migration. Das ist die Effizienz, die [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] hoch fliegen lässt.




Warum ist das wichtig für [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- Es ermöglicht [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]], ihre laufenden Systeme unterstützt zu halten und ihnen Zeit für die Migration zu gewähren, abhängig von ihren geschäftlichen Anforderungen und nicht von den Anforderungen des Anbieters.

- Es mindert das Risiko, das nicht unterstützte Systeme mit sich bringen, indem erweiterter Support angeboten wird. Dieser Ansatz vermeidet die Notwendigkeit einer sofortigen Migration; alles läuft wie gewohnt, aber jetzt gibt es eine Gruppe von Experten, die Ihre Anrufe entgegennehmen können.

- Es gibt Ihnen die Freiheit, den Support-Anbieter zu wechseln, ohne langwierige Migrationen durchlaufen zu müssen, und ermöglicht es Ihnen, dies im großen Maßstab (at scale) zu tun.



Mehr Informationen
================

- [Registering RHEL 7 or CentOS Linux 7 with SUSE Manager](https://documentation.suse.com/liberty/7/html/suma-quickstart/art-suma-quickstart.html)
- [Running OpenSCAP compliance scans for SUSE Multi-Linux Support 7](https://documentation.suse.com/liberty/7/html/compliance-scans/art-compliance-scans.html)
- [Registering CentOS Linux 7 with the SUSE Customer Center](https://documentation.suse.com/liberty/7/html/quickstart-scc/art-quickstart-scc.html)
- [SUSE Multi-Linux Support 9](https://documentation.suse.com/liberty/9/)