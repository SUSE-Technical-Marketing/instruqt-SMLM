---
slug: smlm-managing-linux-distros
id: ahazgpqip3us
type: challenge
title: Gestione di diverse distribuzioni Linux
tabs:
- id: sx74rakwc3bn
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: ux6pgmsidisx
  title: Ubuntu 2404 LTS
  type: terminal
  hostname: ubuntu2404lts
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Gestione di diverse distribuzioni Linux
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

<img class="logos" alt="Welcome!" src="../assets/logos/02-managing_linux_distros.jpeg"/>

Qui alla [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]], <b class="smlmext">SUSE Multi-Linux Manager</b> è la chiave per gestire la nostra flotta diversificata di distribuzioni Linux e architetture da un pannello di controllo unico (single pane of glass). Questo ci ha aiutato a evitare le personalizzazioni extra che complicavano il nostro lavoro di ingegneri, il che a sua volta aumentava i costi e il tempo necessari per mantenere e implementare le nostre policy di sistema.

Con questo strumento, non siamo bloccati in un singolo fornitore, architettura o piattaforma di automazione. Siamo liberi di scegliere ciò di cui abbiamo bisogno per il nostro ambiente e gestirli tutti allo stesso modo. Immagina se per ogni tipo di aereo nella nostra flotta avessimo bisogno di una torre di controllo del traffico aereo diversa con la propria lingua e procedure. La complessità operativa sarebbe ingestibile e i costi sarebbero proibitivi.



Sappiamo tutti che un certo modello di aereo è migliore per una rotta specifica; far volare un jumbo jet per un volo di mezz'ora non è conveniente. Lo stesso vale per le nostre distribuzioni Linux. Mentre le distribuzioni proprie di SUSE sono eccellenti, alcune delle nostre applicazioni hanno requisiti specifici. <b class="smlm">SMLM</b> assicura che non siamo mai bloccati (vendor lock-in) e possiamo sempre integrare la soluzione migliore per il compito da svolgere.


## <b class="hovereffect">I Tuoi Obiettivi:</b>

- Integrare (Onboard) un sistema Ubuntu 24.04 LTS, un sistema specializzato richiesto dal nostro team di marketing.

- Dimostrare come gestiamo questo sistema nuovo e diverso utilizzando gli stessi strumenti e procedure di patching del resto della nostra flotta.



Dettagli del laboratorio
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


Integrazione di Ubuntu (Onboarding)
=================

È arrivata una nuova richiesta di servizio dal nostro dipartimento di marketing. I loro grafici si affidano a una suite creativa specifica che è supportata solo su Ubuntu. Integreremo il loro sistema in modo da poterlo gestire e garantire che soddisfi i nostri standard di sicurezza e conformità, allo stesso modo in cui facciamo con gli altri.

Iniziamo.
<br/>

- Accedi al terminale del sistema dalla scheda [button label="Ubuntu 2404 LTS" variant="success"](tab-1)

  Prima di apportare qualsiasi modifica, controlliamo da dove sta recuperando i pacchetti:

```bash,run
grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```

Questa workstation sta scaricando software direttamente dai repository pubblici di Ubuntu. Questo presenta due problemi: primo, non abbiamo alcun controllo sulle patch applicate, il che è una preoccupazione per la sicurezza. Secondo, come riportato dal team di marketing, ogni volta che queste workstation recuperano aggiornamenti, possono rallentare la connessione internet dell'ufficio, causando frustrazione agli altri dipendenti.



Portiamo questo sistema sotto la nostra gestione. Questo risolverà entrambi i problemi collegandolo alla nostra istanza interna di <b class="smlmext">SUSE Multi-Linux Manager</b> per tutte le esigenze software.

Useremo la [button label="web UI" variant="success"](tab-0) per farlo:

- Sotto `Home` ✈ `Overview`, clicchiamo su `Register Systems`

- Compila i seguenti dettagli:

  - **Host:**

  ```txt
  ubuntu2404lts
  ```

  - **User:** (Utente)

  ```txt
  root
  ```

  - **Password:**

  ```txt
  [[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
  ```

  - **Activation Key:** (Chiave di attivazione)   <b class="highlightcopy">1-ubuntu2404</b>

- Lascia il resto così com'è e clicca su

<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-bootstrap.png"/>


- Il processo di registrazione potrebbe richiedere un paio di minuti per essere completato, andiamo sul [button label="terminal" variant="success"](tab-1) ed eseguiamo il primo comando ancora una volta per vedere cosa è cambiato:


```bash,run
echo 'Waiting for the registration to complete' ;while [[ ! -f /etc/apt/sources.list.d/susemanager_bootstrap.sources ]] || [[ ! -f /etc/apt/sources.list.d/susemanager:channels.sources ]]; do echo -n '.'; sleep 5; done ; sleep 60; grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```


Possiamo vedere che sono apparsi nuovi file:

**/etc/apt/sources.list.d/susemanager:***

Puntano il sistema verso i nostri canali gestiti e controllati centralmente in <b class="smlm">SMLM</b>.


Possiamo anche vedere che il file originale, **/etc/apt/sources.list.d/ubuntu.sources**, è stato modificato per disabilitare tutti i repository pubblici ma non è stato eliminato, questo ci permetterebbe di fare un rollback facilmente se ne avessimo bisogno.


> [!NOTE]
> Usare root via SSH con autenticazione tramite password per la registrazione è solo a scopo dimostrativo e non è raccomandato per la produzione.


> [!NOTE]
> Per impostazione predefinita dobbiamo approvare la registrazione di ogni sistema tramite la UI o via riga di comando < salt-key -A -y >, qui <b class="smlm">SMLM</b> è stato configurato per approvare automaticamente.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-register_ubuntu.gif"/>
  </div>

<br/>



Ora passiamo alla scheda [button label="SMLM UI" variant="success"](tab-0)


- Navighiamo su `Systems` ✈ `System List` ✈ `All`

  Possiamo vedere il sistema che abbiamo appena registrato `Ubuntu2404lts`, nota che per impostazione predefinita sarà registrato sotto l'hostname.

  Clicchiamoci sopra, andremo direttamente a `Details` - `Overview` dove possiamo vedere tra le altre informazioni:

  - Lo stato del sistema.
  - Tutte le informazioni come hostname, indirizzo IP, tipo di virtualizzazione, Kernel utilizzato e prodotti installati.
  - I canali a cui è sottoscritto.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_overview.gif"/>
  </div>


<br/>

Gestione di diverse distribuzioni Linux
=====================================


Come menzionato prima, presso <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b> usiamo diverse distribuzioni Linux, così come usiamo diversi modelli di aerei e compagnie. Questo ci aiuta a rimanere un passo avanti rispetto alla concorrenza utilizzando il prodotto più adatto per ciascuna delle nostre esigenze.

Con <b class="smlmext">SUSE Multi-Linux Manager</b> possiamo gestirle tutte con le stesse procedure, gli stessi programmi, ecc., utilizzando la stessa interfaccia e meccanismi.

Di seguito esploreremo come eseguire diverse attività sui tuoi sistemi, seguendo lo stesso processo indipendentemente dal sistema operativo che i nostri sistemi stanno eseguendo, senza dover creare personalizzazioni non necessarie.


## <b class="hovereffect">Aggiungi informazioni extra</b>


Continuiamo con il sistema che abbiamo appena registrato, aggiungeremo alcune impostazioni e informazioni ad esso:

- Clicchiamo su `Properties`, dove aggiungeremo informazioni extra sul sistema e modificheremo alcune impostazioni.


  - Abilita l'applicazione automatica delle patch (Enable Automatic application of patches):

  <img style='vertical-align: middle; height: 60%; width: 60%; object-fit: contain' src="../assets/SMLM5.1/option-auto_patch_update-enabled.png"/>

    Questo applicherà automaticamente le patch al sistema quando ci sono patch rilevanti.



  - Aggiungi i seguenti dettagli per il sistema:


| Campo (Field) | Contenuto (Content)                                                  |
| ---: | :-----                                                    |
| **Description** | <b class="highlightcopy">Multimedia workstation for graphics designers.</b> |
| **Facility Address** | <b class="highlightcopy">Candy eye street, 1</b> |
| **City** | <b class="highlightcopy">Aeolia</b> |
| **Building** | <b class="highlightcopy">Belem Tower 4</b> |
| **Room** | <b class="highlightcopy">Sierra nevada</b> |


<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-Update_Properties.png"/>



- Vediamo su quale hardware sta girando:

  - Clicca su `Details` ✈ `Hardware`


<br/>

> [!NOTE]
> Tutto questo può essere automatizzato tramite l'API.

<br/>

Ora aggiungeremo alcune informazioni extra al sistema utilizzando chiavi personalizzate, queste informazioni possono essere facilmente consumate nei tuoi script di automazione in seguito.


- Clicca su `Details` ✈ `Custom Info`

<img style='vertical-align: top; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Create_Value.png"/>

- Clicca su `application` e compila **value** (valore) con quanto segue:

```text
Logo Wings designer pro
```

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Update_Key.png"/>


<br/>

> [!NOTE]
> Abbiamo già creato la chiave personalizzata **application** per te, se vuoi creare le tue chiavi è semplice come andare su: `Systems` ✈ `Custom System Info` ✈ `Create key`

<br/><br/>

Torniamo all'elenco Systems

`Systems` ✈ `System List` ✈ `All`


Clicchiamo su uno qualsiasi dei sistemi e andiamo su `Details` ✈ `Custom Info`.

Abbiamo già popolato ogni sistema con un valore,

<br/>

Ora vai su `Details` ✈ `Overview` e nota **Installed Products** e **Subscribed Channels**, questi sono diversi da quelli nel tuo sistema Ubuntu perché stanno eseguendo un sistema operativo diverso.



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_properties.gif"/>
  </div>

<br/>


## <b class="hovereffect">Esegui comandi su più sistemi contemporaneamente</b>


Facciamo qualcosa su tutti i sistemi che abbiamo, torna su `Systems` ✈ `System List` ✈ `All` e seleziona tutto:

<img style='vertical-align: middle; margin: 2px; height: 50%; width: 50%; object-fit: contain' src="../assets/SMLM5.1/select_all_systems.png"/>

Nota la colonna **Base Channel**, abbiamo sistemi che eseguono tre OS diversi.

<br/>

Dopo aver selezionato tutti i sistemi su cui vogliamo operare, andiamo a eseguire un'azione di gruppo:

`Systems` ✈ `System Set Manager`

Eseguiamo un comando su tutti loro, per questo possiamo andare su:

`Misc` ✈ `Remote Command`

quindi compila i seguenti dettagli e lascia il resto con i valori predefiniti:


Script:

```bash,run
cat /etc/os-release
```

Non modificare la pianificazione (schedule), vogliamo che venga eseguita il prima possibile, clicca su:

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Schedule.png"/>


<br/>


<br/><br/>

Vedrai un avviso blu in alto che indica che l'attività è stata pianificata.

Andiamo a vedere i risultati, per questo andremo su:

`Schedule` ✈ `Completed Actions`

Vedremo un elenco di azioni, nel campo **Filter by Action** digita:

```text
Run
```
Clicca sulla voce in alto che appare nell'elenco, dovrebbe essere simile a questa:

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/Select_complete_action_run.png"/>


Lì possiamo andare su **Completed Systems** ed esaminare il risultato cliccando sul nome del sistema.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-multiple_systems_at_once.gif"/>
  </div>

<br/>


<br/><br/>

Con questo completiamo questa parte, vedremo altri esempi di come possiamo gestire più sistemi Linux durante il workshop.



Perché è importante per [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- Nessun vendor lock-in, mantieni la libertà di scelta e la flessibilità per reagire velocemente ai mercati in evoluzione.

- Semplifica e risparmia tempo evitando lavoro extra sulle personalizzazioni.

- Un'unica UI per gestire tutto riduce la complessità e renderà il futuro troubleshooting, scaling, patching e automazione molto più agili e meno dispendiosi in termini di tempo.



Maggiori informazioni
================

Per un elenco delle distribuzioni supportate visita:

[SMLM - Supported Clients and Features](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/client-configuration/supported-features.html)