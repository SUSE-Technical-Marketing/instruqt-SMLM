---
slug: smlm-simplify-upgrade-sles
id: xogylngs1tl2
type: challenge
title: Einfache und zuverlässige Wartung
tabs:
- id: puw8x0e0rxzc
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: mpoynhjiymsf
  title: SLES 15
  type: terminal
  hostname: sles15
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Einfache und zuverlässige Wartung
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

Bisher haben wir uns darauf konzentriert, die Vielfalt unserer gemischten Flotte zu verwalten und sogar die Lebensdauer unserer Legacy-Systeme zu verlängern. Jetzt richten wir unsere Aufmerksamkeit auf den Kern unserer Fluggesellschaft: unsere Flaggschiff-Systeme <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>).


Betrachten Sie diese als unsere hochmodernen Langstreckenjets. Ihre Zuverlässigkeit ist von größter Bedeutung, und sie in Top-Zustand zu halten, erfordert regelmäßiges, geplantes Service-Patching und Upgrades. Die nächste Übung ist genau das: Wir werden den Prozess eines Versions-Upgrades durchgehen, eine häufige Aufgabe im Lebenszyklus-Management jedes kritischen Systems.



Und obwohl wir SLES als Beispiel verwenden, denken Sie an das Schlüsselprinzip unseres universellen Kontrollturms: Der Prozess, den Sie gleich durchführen werden, ist derselbe, den Sie für jede andere Linux-Distribution verwenden würden. Die Schnittstelle und die Methodik ändern sich nicht.


## <b class="hovereffect">Ihre Ziele:</b>

- Ein neues SLES 15 SP5 System onboarden (integrieren), um als unser Testflugzeug zu dienen.
- Ein größeres Service-Upgrade von SP5 auf SP6 durchführen.



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






Onboarding und Vorbereitung (Onboarding and preparation)
==========================

Greifen Sie über den Tab [button label="SLES 15" variant="success"](tab-1) auf das Systemterminal zu.


Lassen Sie uns das System im <b class="smlm">SMLM</b> als **sles15** registrieren.

```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | HOSTNAME="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-sles15sp5 bash ; echo "Wait 45 seconds for it to finish"; sleep 45
```


Wechseln wir nun zum Tab [button label="SMLM UI" variant="success"](tab-0).


Ausführen des Upgrades (Executing the upgrade)
=====================

Wir sollten es bald in der Liste der Systeme sehen. Gehen Sie zu `Systems` ✈ `System List` ✈ `All`. Bitte klicken Sie im internen Browser auf Aktualisieren, wenn Sie es nicht sehen.


Klicken wir darauf und gehen zu `Software` ✈ `Packages` ✈ `Upgrade`.


Um eine reibungslose Migration zu gewährleisten, ist es am besten, die neuesten Updates anzuwenden.



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">Klicken Sie auf </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


Dies kann einige Zeit in Anspruch nehmen.

<br/>


## <b class="hovereffect">Produktmigration (Product migration)</b>


Sobald es fertig ist, gehen Sie bitte zu `Software` ✈ `Product Migration`.



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">Sie werden einen Abschnitt namens **Target Products** sehen. Stellen Sie sicher, dass <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #90ebcd">SUSE Linux Enterprise Server 15 SP6 x86_64</b> ausgewählt ist, und drücken Sie dann: </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; vertical-align: middle; display:block; align:left; padding: 0px;" src="../assets/SMLM5.1/bottom-select_channels.png"/></p>

Ihnen wird ein Bestätigungsbildschirm mit einer Zusammenfassung und zusätzlichen Optionen angezeigt. Lassen Sie die Standardwerte so, wie sie sind, und klicken Sie auf: ![Schedule Migration](../assets/SMLM5.1/bottom-schedule_migration.png)

Das System wird Sie bitten, zuerst einen Testlauf (Dry Run) durchzuführen; ignorieren Sie dies und drücken Sie: ![Confirm](../assets/SMLM5.1/bottom-confirm.png)

Dies wird einige Zeit dauern. Um den Status zu überwachen, gehen Sie zu `Events` ✈ `History` und achten Sie auf das Ereignis **Product Migration**. Sobald das Statussymbol grün wird, ist die Migration abgeschlossen. Sie können dies überprüfen, indem Sie zu `Software` ✈ `Software Channels` navigieren und bestätigen, dass das System nun die neuen SP6-Kanäle abonniert hat.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/04-simple_and_reliable_maintenance-executing_the_upgrade.gif"/>
  </div>

<br/>

## <b class="hovereffect">Neustart nach der Migration</b>

- Navigieren Sie zurück zu `Systems` ✈ `System List` ✈ `All`.

- Beachten Sie, dass neben dem `sles15`-System nun ein Neustart-Symbol angezeigt wird:

![Needs reboot icon](../assets/SMLM5.1/icon_needs_reboot.png)

  Dies zeigt an, dass ein Neustart erforderlich ist, normalerweise aufgrund eines größeren Kernel-Updates.

- Klicken Sie darauf, wir werden etwas Ähnliches sehen wie:

![Needs reboot message](../assets/SMLM5.1/system_requires_a_reboot.png)

- Klicken Sie auf `Schedule System Reboot` und im folgenden Bildschirm auf ![Reboot System](../assets/SMLM5.1/bottom-reboot_system.png).

> [!NOTE]
> Der Neustart erfolgt nicht sofort.

<br/>


## <b class="hovereffect">Die Bedeutung der Zeitplanung (Scheduling)</b>

Wir haben diese Aktionen so geplant, dass sie sofort stattfinden, aber das ist nicht immer wünschenswert. <b class="smlm">SMLM</b> unterstützt die Erstellung von Wartungsfenstern (Maintenance Windows) (`Schedule` ✈ `Maintenance Windows`), was es Ihnen ermöglicht, sicherzustellen, dass größere Ereignisse wie Neustarts nur während dieser vorab genehmigten Zeiträume stattfinden.



Die Zeitplanung ist besonders nützlich für Produktionssysteme, da sie sorgfältig geplante Änderungen an Systemgruppen und sogar phasenweise "Canary"-Deployments ermöglicht.

<br/>

> [!NOTE]
> Es ist möglich, Kernel-Live-Patching mit KLP durchzuführen; dies ermöglicht es, die neuesten Sicherheitsupdates auf Linux-Kernel anzuwenden, ohne neu zu starten.



Warum ist das wichtig für [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- System-Upgrades und andere Routineaufgaben müssen einfach und wiederholbar sein, andernfalls riskieren wir teure Fehler. Mit diesen Tools können wir präzise steuern, wann und wo wir Aktionen durchführen, und kritische Wartungsarbeiten für unsere Flotte mit Zuversicht planen.


- Wir können steuern, wann und wo wir Aktionen durchführen, und Wartungsarbeiten an unserer am Boden befindlichen Flotte planen.


Mehr Informationen
================

- [Live kernel patching with KLP](https://documentation.suse.com/en-us/sles/15-SP7/html/SLES-all/cha-klp.html)

- [Maintenance Windows](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

- [Administration Guide](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/admin-overview.html)