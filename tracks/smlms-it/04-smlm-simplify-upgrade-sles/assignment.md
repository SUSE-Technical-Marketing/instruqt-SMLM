---
slug: smlm-simplify-upgrade-sles
id: hnk6ejdxg7gy
type: challenge
title: Manutenzione semplice e affidabile
tabs:
- id: xyph5c0ga0fo
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: d378sbg50zor
  title: SLES 15
  type: terminal
  hostname: sles15
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Manutenzione semplice e affidabile
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

Finora, ci siamo concentrati sulla gestione della diversità della nostra flotta mista e persino sull'estensione della vita dei nostri sistemi legacy. Ora, rivolgiamo la nostra attenzione al nucleo della nostra compagnia aerea: i nostri sistemi di punta <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>).


Pensate a questi come ai nostri jet a lungo raggio all'avanguardia. La loro affidabilità è fondamentale, e mantenerli in condizioni ottimali comporta l'applicazione regolare e pianificata di patch di servizio e aggiornamenti. Il prossimo esercizio è esattamente questo: percorreremo il processo di un aggiornamento di versione, un compito comune nella gestione del ciclo di vita di qualsiasi sistema critico.



E mentre stiamo usando SLES come esempio, ricordate il principio chiave della nostra torre di controllo universale: il processo che state per eseguire è lo stesso che usereste per qualsiasi altra distribuzione Linux. L'interfaccia e la metodologia non cambiano.


## <b class="hovereffect">I Tuoi Obiettivi:</b>

- Integrare (Onboard) un nuovo sistema SLES 15 SP5 per servire come nostro aereo di prova.
- Eseguire un aggiornamento di servizio principale (major service upgrade) da SP5 a SP6.



Dettagli del laboratorio (Lab details)
===========

Nome utente (Username):
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```

Password:
```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

URL di <b class="smlm">SMLM</b>: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>






Integrazione e preparazione (Onboarding and preparation)
==========================

Accedi al terminale del sistema dalla scheda [button label="SLES 15" variant="success"](tab-1)


Registriamo il sistema all'interno di <b class="smlm">SMLM</b> come **sles15**

```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | HOSTNAME="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-sles15sp5 bash ; echo "Wait 45 seconds for it to finish"; sleep 45
```


Ora, passiamo alla scheda [button label="SMLM UI" variant="success"](tab-0)


Esecuzione dell'aggiornamento (Executing the upgrade)
=====================

Dovremmo vederlo presto nella lista dei sistemi, andiamo su `Systems` ✈ `System List` ✈ `All`, per favore clicca su aggiorna nel browser interno se non lo vedi.


Clicchiamoci sopra e andiamo su `Software` ✈ `Packages` ✈ `Upgrade`.


Per garantire una migrazione fluida è meglio applicare gli ultimi aggiornamenti.



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">Clicca su </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


Questo potrebbe richiedere del tempo per essere completato.

<br/>


## <b class="hovereffect">Migrazione del prodotto</b>


Una volta terminato, per favore vai su `Software` ✈ `Product Migration`



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">Vedrai una sezione chiamata **Target Products**. Assicurati che <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #90ebcd">SUSE Linux Enterprise Server 15 SP6 x86_64</b> sia selezionato, poi premi: </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; vertical-align: middle; display:block; align:left; padding: 0px;" src="../assets/SMLM5.1/bottom-select_channels.png"/></p>

Ti verrà mostrata una schermata di conferma con un riepilogo e opzioni aggiuntive. Lascia i valori predefiniti così come sono e clicca su: ![Schedule Migration](../assets/SMLM5.1/bottom-schedule_migration.png)

Il sistema ti chiederà prima di fare una prova simulata (dry run), ignorala e premi: ![Confirm](../assets/SMLM5.1/bottom-confirm.png)

Questo richiederà del tempo. Per monitorare lo stato, vai su `Events` ✈ `History` e osserva l'evento **Product Migration**. Una volta che la sua icona di stato diventa verde, la migrazione è completata. Puoi verificarlo navigando su `Software` ✈ `Software Channels` e confermando che il sistema è ora sottoscritto ai nuovi canali SP6.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/04-simple_and_reliable_maintenance-executing_the_upgrade.gif"/>
  </div>

<br/>

## <b class="hovereffect">Riavvio Post-Migrazione</b>

- Naviga indietro su `Systems` ✈ `System List` ✈ `All`

- Nota che il sistema `sles15` ora ha un'icona di riavvio accanto:

![Needs reboot icon](../assets/SMLM5.1/icon_needs_reboot.png)

  Questo indica che è richiesto un riavvio, di solito a causa di un aggiornamento principale del kernel.

- Cliccaci sopra, vedremo qualcosa di simile a questo:

![Needs reboot message](../assets/SMLM5.1/system_requires_a_reboot.png)

- Clicca su `Schedule System Reboot` e nella schermata successiva clicca su ![Reboot System](../assets/SMLM5.1/bottom-reboot_system.png)

> [!NOTE]
> Il riavvio non avverrà immediatamente.

<br/>


## <b class="hovereffect">L'importanza della Pianificazione (Scheduling)</b>

Abbiamo programmato queste azioni affinché avvengano immediatamente, ma questo non è sempre desiderabile. <b class="smlm">SMLM</b> supporta la creazione di Finestre di Manutenzione (Maintenance Windows) (`Schedule` ✈ `Maintenance Windows`) che ti consentono di garantire che gli eventi principali come i riavvii avvengano solo durante quei periodi pre-approvati.



La pianificazione è particolarmente utile per i sistemi di produzione, in quanto consente modifiche attentamente pianificate su gruppi di sistemi e persino deploy "canary" a fasi.

<br/>

> [!NOTE]
> È possibile eseguire il patching del kernel in tempo reale con KLP, il che rende possibile applicare gli ultimi aggiornamenti di sicurezza ai kernel Linux senza riavviare.



Perché è importante per [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- Gli aggiornamenti di sistema e altre attività di routine devono essere semplici e ripetibili, altrimenti rischiamo di commettere errori costosi. Con questi strumenti, possiamo controllare con precisione quando e dove eseguiamo le azioni, pianificando la manutenzione critica per la nostra flotta con fiducia.


- Possiamo controllare quando e dove eseguiamo le azioni, e pianificare le operazioni di manutenzione sulla nostra flotta a terra.


Maggiori informazioni
================

- [Live kernel patching with KLP](https://documentation.suse.com/en-us/sles/15-SP7/html/SLES-all/cha-klp.html)

- [Maintenance Windows](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

- [Administration Guide](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/admin-overview.html)