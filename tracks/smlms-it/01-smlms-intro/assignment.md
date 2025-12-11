---
slug: smlms-intro
id: s5zthndchl4o
type: challenge
title: Benvenuto al SUSE Multi-Linux Hands-on Workshop!
teaser: Benvenuto al SUSE Multi-Linux Hands-on Workshop! In questa sezione ti presenteremo
  il workshop e i suoi componenti principali.
notes:
- type: text
  contents: |
    # Benvenuto al SUSE Multi-Linux Hands-on Workshop!
    Attendi mentre configuriamo il tuo ambiente di laboratorio.
    <img class="logos" src="../assets/logos/suse_logo.svg"/>
tabs:
- id: ekhkcrkgtmbk
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: ""
enhanced_loading: null
---

Benvenuto al <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #30ba78">SUSE</b> Multi-Linux Hands-on Workshop
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

In questo workshop esplorerai un po' della magia che <b class="smlmext">SUSE Multi-Linux Manager</b> (<b class="smlm">SMLM</b>) può fare; è la soluzione di <b class="suse">SUSE</b> per gestire diverse distribuzioni Linux su larga scala da un'interfaccia unificata. E scoprirai anche come mantenere supportati i tuoi server di produzione legacy con <b class="smlsext">SUSE Multi-Linux Support</b> (<b class="smls">SMLS</b>), la nostra soluzione di supporto professionale e affidabile per i sistemi Linux.

&emsp;&emsp; Assumerai il ruolo di un **engineer** presso <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b>, una compagnia aerea dove ogni aereo ha un server Linux a bordo.

&emsp;&emsp; Come per qualsiasi componente di un aereo, è fondamentale che questi server rimangano stabili e affidabili, indipendentemente dal fatto che si trovino a terra in qualche data center o che volino sopra le nuvole ☁ ☁ ☁


&emsp;&emsp; Alcuni modelli di aerei richiederanno una variante Linux diversa o un'architettura CPU diversa. Questo non è un problema per <b class="smlm">SMLM</b>; sei libero di scegliere la distribuzione Linux e l'architettura CPU che meglio si adatta alle tue esigenze senza dover rinunciare a una facile standardizzazione e gestione.


&emsp;&emsp; Come engineer responsabile della gestione del panorama Linux, esaminerai alcune delle soluzioni che <b class="smlm">SMLM</b> e <b class="smls">SMLS</b> ti offrono per facilitare e automatizzare la gestione dei sistemi e risolvere problemi eccezionali che potrebbero verificarsi.


Durante le diverse sfide avrai a disposizione i seguenti strumenti:

 ✈ **SUSE Multi-Linux Manager**:
   Il pannello di controllo unico (single pane of glass) per gestire l'intero stack Linux.

 ✈ **Centos 7**:
   Una distribuzione legacy ancora in uso su alcuni aerei più vecchi e sistemi di terra.

 ✈ **Ubuntu 24**: Una specifica distribuzione Linux richiesta dal nostro dipartimento marketing per eseguire le loro applicazioni di graphic design.

 ✈ **SLES 15**: La distribuzione Linux altamente affidabile, stabile e sicura di <b class="suse">SUSE</b> che costituisce la spina dorsale dei nostri sistemi più critici.


## <b class="smlmext hovereffect">SUSE Multi-Linux Manager</b>

È una soluzione di gestione dell'infrastruttura open source best-in-class per la tua infrastruttura software-defined.

&emsp;&emsp; <b class="smlmext">SUSE Multi-Linux Manager</b> è stato progettato per aiutare i tuoi team aziendali DevOps e IT Operations a ridurre la complessità e riprendere il controllo delle tue risorse IT, uno strumento singolo ma molto potente per gestire i sistemi Linux attraverso una varietà di architetture hardware, hypervisor così come piattaforme container, IoT e cloud.

&emsp;&emsp; Automatizza il provisioning, il patching e la configurazione di server Linux e dispositivi IoT per un deployment dei server più veloce, coerente e ripetibile, aiutando a ottimizzare le operazioni e ridurre i costi. E con il monitoraggio, il tracciamento, l'auditing e il reporting automatizzati dei tuoi sistemi, VM e container nei tuoi ambienti di sviluppo, test e produzione, puoi garantire la conformità con le policy di sicurezza interne e le normative esterne.


## <b class="smlsext hovereffect">SUSE Multi-Linux Support</b>


È un servizio completo che offre assistenza tecnica e manutenzione per varie distribuzioni Linux, inclusi i tuoi esistenti Red Hat Enterprise Linux (RHEL), CentOS, <b class="liberty">SUSE Liberty Linux</b> e <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>), a seconda dell'offerta.

&emsp;&emsp; Consente alle organizzazioni di gestire ambienti Linux misti in modo efficiente sotto un unico framework di supporto.
A seconda del pacchetto acquistato, <b class="smlsext">SUSE Multi-Linux Support</b> può includere anche <b class="smlmext">SUSE Multi-Linux Manager</b>, uno strumento di gestione multi-Linux per gestire queste distribuzioni.



 🌅 Esplora la Instruqt UI
=======================
Prima di iniziare il nostro primo compito, prendiamoci un momento per guardare la Instruqt UI.

+ Il **lato destro** dello schermo ti fornisce queste istruzioni e i controlli di navigazione.

+ Il **lato sinistro** ti dà accesso alle varie macchine e servizi che compongono il nostro ambiente di laboratorio.

All'interno della Instruqt UI puoi saltare tra la [button label="SMLM UI" variant="success"](tab-0) e i [button label="terminals" variant="success"](tab-1) disponibili cliccando sulle schede nella parte superiore del pannello di sinistra.


> [!NOTE]
> Non avviene alcun ricaricamento automatico nella web UI; in alcuni casi potrebbe essere necessario ricaricare il browser web interno di Instruqt per vedere gli aggiornamenti.


🛫 Accesso a <b class="smlmext">SUSE Multi-Linux Manager</b> 🛫
========================================
Prendiamo confidenza con l'ambiente.

- Apri <b class="smlmext">SUSE Multi-Linux Manager</b> all'interno del laboratorio dalla [button label="SMLM UI" variant="success"](tab-0)


- Accedi con le seguenti credenziali:

  - Username:
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```
  - Password:

```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

Se tutto è andato bene, dovresti vedere la pagina **Overview** nella UI di <b class="smlmext">SUSE Multi-Linux Manager</b> loggato come utente `[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]`.

> [!NOTE]
> Se desideri accedere alla UI di <b class="smlmext">SUSE Multi-Linux Manager</b> direttamente tramite il tuo browser, puoi farlo:

URL <b class="smlm">SMLM</b>: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>


> [!NOTE]
> Se la pagina non si carica correttamente, potrebbe essere necessario aggiornare la scheda del browser dopo che l'ambiente di laboratorio ha terminato l'avvio.




🗺  Esplora <b class="smlmext">SUSE Multi-Linux Manager</b> 🗺
======================================

Prima di decollare, familiarizziamo con i controlli. Questo non vuole essere un tour esaustivo, ma una breve panoramica degli strumenti chiave che utilizzeremo durante il workshop. Ti incoraggiamo a essere curioso ed esplorare.


Iniziamo.


- **Menu Systems** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_systems.png"/>

  Sul pannello di sinistra, clicca su `systems`. Questa è la panoramica della nostra flotta, che mostra ogni server registrato. L'elenco è piccolo ora, ma crescerà man mano che completeremo i nostri esercizi.

   - **System Lists**

     Questa sezione fornisce visualizzazioni convenienti e pre-filtrate. Ad esempio, l'elenco `Out of Date` ti mostra istantaneamente quali server richiedono aggiornamenti, risparmiandoti di eseguire una ricerca manuale. </p>

  <br/>

  - **System Groups**

    Per organizzare la nostra flotta logicamente, usiamo i `System Groups`; puoi categorizzarli in base a qualsiasi criterio. In questo modo puoi risparmiare tempo quando applichi azioni o definisci policy. Una volta creati, puoi allegare automaticamente i sistemi a uno o più gruppi, ad es. usando le `activation keys`.


    Sentiti libero di provare a crearne uno ora cliccando su `+ Create Group`.

  <br/>

  - **Operazioni batch**

    `System Set Manager` fornisce un modo potente per eseguire azioni su più sistemi contemporaneamente.


    Invece di applicare le modifiche una per una, puoi selezionare una raccolta di sistemi, sia individualmente dalla System List o sfruttando i System Groups esistenti, e quindi eseguire attività su tutti loro in un'unica operazione.

  <br/>

  - **Provisioning**

    <b class="smlmext">SUSE Multi-Linux Manager</b> fornisce strumenti completi per il provisioning di nuovi sistemi e il ri-provisioning di quelli esistenti. Questa capacità ti aiuta a stabilire un processo standardizzato e ripetibile per il deployment dei sistemi.


    Ad esempio, all'interno della sezione `Autoinstallation` puoi definire distribuzioni e profili Kickstart/AutoYaST che ti consentono di specificare come i tuoi sistemi dovrebbero essere distribuiti, quale software avranno installato, come sarà distribuito lo spazio di archiviazione e altro ancora.


    Tutti questi meccanismi di automazione semplici da configurare possono essere combinati con soluzioni di automazione complesse ma più potenti come Salt o Ansible, mantenendo la tua libertà di scegliere la soluzione migliore per ogni sfida.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_systems.gif"/>
  </div>

<br/>



- **Menu Patches** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_patches.png"/>

  - **Patching**

    Uno dei compiti più comuni nell'IT è mantenere i sistemi aggiornati e di tanto in tanto applicare patch di sicurezza in fretta!
    Con SMLM possiamo vedere facilmente un elenco di patch **rilevanti**, classificate per tipo, e fornite con tutte le informazioni che potresti aver bisogno di sapere, inclusi tutti i sistemi e i pacchetti che influenzano.

    Oltre alle patch fornite dal vendor, possiamo anche creare le nostre patch. Più avanti esploreremo le diverse opzioni che abbiamo per gestire il patching e gli aggiornamenti regolari su tutta la nostra flotta.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_patches.gif"/>
  </div>

<br/>
- **Canali software** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_software.png"/>

  In `Channel List` possiamo vedere tutti i canali/repository/stream di pacchetti disponibili per il consumo; puoi anche creare nuovi canali software per organizzare il tuo software o caricare i tuoi pacchetti.

  Tutti i canali che vedi attualmente sono stati recuperati da SMLM dalle fonti ufficiali e possono essere mantenuti sincronizzati facilmente.

  In `Package Search` siamo in grado di cercare pacchetti specifici e ispezionare il loro contenuto e metadati.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_software.gif"/>
  </div>

<br/>

- **Configuration** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_configuration.png"/>

  È anche possibile gestire e applicare configurazioni specifiche ai sistemi, al momento della registrazione o successivamente; per questo possiamo ispezionare la sezione `Configuration`.

  SMLM fornisce un modo semplice per gestire facilmente le revisioni, distribuire e confrontare i file di configurazione tra i sistemi. E tutto può essere facilmente raggruppato in canali di configurazione.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_configuration.gif"/>
  </div>

<br/>

- **Scheduling** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_schedule.png"/>

  In `Schedule` possiamo osservare e gestire le azioni pianificate, definire finestre di manutenzione specifiche. Questo è particolarmente utile per automatizzare operazioni regolari o eseguire canary deployment quando si gestiscono molti sistemi. Vedremo questo in azione più avanti durante il workshop.

<br/>
<br/>

SUSE Multi-Linux Manager offre molte possibilità per gestire i tuoi sistemi; non possiamo coprirle tutte in questo workshop ma, come sempre, sentiti libero di fare domande ed esplorare.

> [!NOTE]
> Il tuo utente ha privilegi di amministratore completi, quindi ti consigliamo di apportare modifiche solo dopo aver terminato gli esercizi.