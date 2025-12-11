---
slug: smls-extended-support
id: iqohdqtsmuvz
type: challenge
title: Supporto esteso per sistemi legacy
tabs:
- id: yhzf1j4nncgb
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: wctikhndllrn
  title: CentOS 7 QA
  type: terminal
  hostname: centos7
- id: rt3nmydpb8ke
  title: CentOS 7 Prod
  type: terminal
  hostname: zzcentos7
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Supporto esteso per sistemi legacy
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

# Estendere la vita della nostra flotta legacy

In qualsiasi compagnia aerea, hai aerei più vecchi e affidabili che ti hanno servito per anni ma per i quali non hai ancora una sostituzione. Per noi, una parte di quella flotta legacy sono i nostri sistemi CentOS 7. Sono stabili ma a fine vita (end-of-life), il che significa che non ricevono più aggiornamenti di sicurezza critici dal loro produttore originale. Per una compagnia aerea, volare senza supporto è un rischio che semplicemente non possiamo correre.

La soluzione tradizionale sarebbe una sostituzione completa e costosa di ognuno di essi.
Ma se potessimo eseguire un aggiornamento per l'estensione della vita operativa, modernizzandoli in loco con un'interruzione minima? Questa è precisamente la missione di questa sfida. Useremo la potenza di <b class="smlmext">SUSE Multi-Linux Manager</b> insieme a <b class="smlsext">SUSE Multi-Linux Support</b> per transitare in sicurezza questi sistemi e mantenerli in servizio fino a quando non potremo sostituirli con un OS più moderno.



## <b class="hovereffect">Il nostro piano di volo:</b>

- Esaminare gli attuali sistemi legacy che eseguono Centos 7

- Integrare (Onboard) il sistema QA e applicare eventuali patch disponibili

- Identificare e applicare aggiornamenti se presenti.

- Liberare (Liberate) il sistema con la formula liberate.

- Osservare cosa è cambiato tra entrambi i sistemi

- Identificare se questa è una migrazione.

<br/>

## <b class="hovereffect">I nostri aerei</b>

- CentOS 7 QA ✈ Il nostro server di test e sviluppo.

- CentOS 7 Prod ✈ Il nostro server di produzione già registrato in <b class="smlm">SMLM</b>

<br/><br/>


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



Integrazione di Centos 7 QA (Onboarding Centos 7 QA)
======================



## <b class="hovereffect">Esaminando gli attuali sistemi legacy</b>

Accedi al terminale del sistema dalla scheda [button label="Centos 7 QA" variant="success"](tab-1)

Controlla la versione attuale del sistema:

```bash,run
rpm -qi centos-release centos-logos
```


Ora esegui il seguente comando per registrare il sistema in <b class="smlm">SMLM</b>:


```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | SMLM_DNS="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-liberty7ltss PROFILENAME='airco-dh4a-qa' bash ; echo "Let's wait 2 minutes for all the background processes to finish"; sleep 120
```


Questo è simile a quello che abbiamo usato per integrare Ubuntu nel laboratorio precedente, ciò che cambia è:

- **Activation key** (Chiave di attivazione): È un riferimento alle impostazioni che verranno applicate al sistema per impostazione predefinita, in questo caso è stata creata per indicare solo a quali canali software verrà registrato il sistema.

- **Profile name** (Nome del profilo): Se non lo specifichiamo utilizzerà l'hostname ma in questo caso vogliamo che abbia un nome più significativo con la stessa convenzione di denominazione che abbiamo usato con Centos 7 Prod.


**Opzionale:** Se siamo curiosi e vogliamo vedere cosa succede quando aggiorniamo ed eseguiamo la formula Liberate, possiamo eseguire il seguente comando su entrambi i sistemi ( [button label="Centos 7 QA" variant="success"](tab-1) e [button label="Centos 7 Prod" variant="success"](tab-2) ):


```bash,run
journalctl -f
```

E vedere i log apparire nei terminali.


<br/><br/>


## <b class="hovereffect">Identificare e applicare aggiornamenti dai repository <b class="liberty">Liberty</b></b>

Questi sistemi Centos 7 arrivano con gli ultimi pacchetti forniti upstream, vogliamo assicurarci che i nuovi bug siano corretti e avere una persona di supporto amichevole che ci aiuti quando ci sono problemi. Ora abbiamo già sottoscritto i sistemi Centos 7 ai repository software forniti da SUSE durante il processo di registrazione, quindi applichiamo le patch a tutti:



Ora passiamo alla scheda [button label="SMLM UI" variant="success"](tab-0)


- Vai a `Systems` ✈ `System List` nel menu a sinistra.

- Trova il tuo host **airco-dh4a-qa** e cliccaci sopra.

- Seleziona `Software` ✈ `Packages`

- Clicca su `Update Packages List`, questo richiederà circa un minuto per essere completato

- Seleziona `Software` ✈ `Patches`

- Vedrai un elenco di patch disponibili.

Clicca su `Select All`, poi `Apply Patches` in alto a destra e infine `Confirm`. <b class="smlmext">SUSE Multi-Linux Manager</b> ora pianificherà ed eseguirà la procedura di aggiornamento sul sistema CentOS.


> [!NOTE]
> Potrebbero volerci un paio di minuti per ottenere l'elenco dei pacchetti prima di poter vedere l'elenco delle patch che possono essere applicate al sistema.


Dato che questo potrebbe richiedere un po' di tempo, vediamo cosa succede sotto il cofano.
Vai alla scheda `Events`, poi su `History`, dovresti vedere un elenco di eventi che sono accaduti da quando il sistema è stato registrato in <b class="smlm">SMLM</b>, nelle prime righe dovremmo essere in grado di trovare un evento che contiene qualcosa di simile a *Combined Patch*.


Se ci clicchiamo sopra possiamo vedere tutti i dettagli, sentiti libero di dare un'occhiata, altrimenti aspetta che l'icona sia verde:

![Successfully patched](../assets/SMLM5.1/successfully_updated_system.png)

Abbiamo appena applicato patch che correggono bug ai pacchetti esistenti, questi pacchetti patchati provengono direttamente da SUSE, questa non è una migrazione.

<br/>

Confrontiamolo con il sistema di produzione che non abbiamo ancora aggiornato.

Per favore vai su `Software` ✈ `Packages` ✈ `Profiles`

Seleziona il sistema `airco-dh4a-prod`, che è la versione di produzione, poi clicca su:

![Compare](../assets/SMLM5.1/bottom-compare.png)


Possiamo vedere che la maggior parte delle versioni dei pacchetti non è cambiata, ancora la stessa versione ( **X.X.X**-xyz ) ma con una patch applicata ( X.X.X-**xyz** ).

Prima di passare alla sezione successiva, creiamo un profilo memorizzato, questo ci aiuterà a vedere le differenze più chiaramente dopo aver applicato la formula liberate nella sezione successiva.


Per favore vai su `Software` ✈ `Packages` ✈ `Profile` e clicca su `Create System Profile`. Per il nome puoi chiamarlo:

```txt
before_liberation
```


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-identify_and_apply_updates.gif"/>
  </div>


<br/><br/>


Liberare il sistema (opzionale)
==============================

Questo è un passaggio **opzionale** e non richiesto per ottenere supporto.

Ora liberiamo (liberate) il sistema:

- Vai alla scheda `Formulas`, cerca **Liberate**, e una volta trovato, selezionalo e clicca su `Save` in alto a destra.

Vedrai un messaggio in blu nella parte superiore dello schermo, scorri verso l'alto se non riesci a vederlo:

![Formula saved](../assets/SMLM5.1/formula_saved.png)


Clicca dove dice `Highstate`, verrai indirizzato a un'altra scheda (`States` ✈ `Highstate`).

Puoi vedere nel riepilogo in basso che la formula liberate è elencata.

Per avviare il processo di liberazione, clicca su:

![Formula saved](../assets/SMLM5.1/bottom-apply_highstates.png)

Questo richiederà del tempo, per favore controlla `Events` -> `History`, dovresti vedere un evento chiamato **Apply highstate scheduled**

Aspettiamo un paio di minuti che finisca, nel frattempo puoi osservare cosa sta succedendo guardando il terminale [button label="Centos 7 QA" variant="success"](tab-1).


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-liberate.gif"/>
  </div>

<br/><br/>

## <b class="hovereffect">Osserva cosa è cambiato</b>


Una volta completato, confrontiamo di nuovo il sistema per vedere la differenza, se non siamo già lì clicchiamo sul nome del sistema `airco-dh4a-qa`.

Poi vai su `Software` ✈ `Packages` ✈ `Profile`

Sotto **Compare to Stored Profile** clicca su: ![Compare](../assets/SMLM5.1/bottom-compare.png)

Possiamo vedere che l'unica cosa che è cambiata sono i seguenti pacchetti:

- **centos-logos**, sostituito da **sles_es-logos**

- **centos-release**, sostituito da **sles_es-release-server**

Il resto rimane lo stesso ma ora hai tutto il supporto, gli aggiornamenti e le patch forniti da <b class="suse">SUSE</b> per <b class="liberty">Liberty Linux</b>.

Lo stesso vale per le versioni più moderne di CentOS e RHEL, puoi trasformarle in <b class="liberty">Liberty</b> e averle supportate da <b class="suse">SUSE</b> senza dover apportare modifiche al software e alle librerie effettive.



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-what_changed.gif"/>
  </div>

<br/>



Liberare il server di produzione (opzionale)
=========================================

Abbiamo visto come applicare patch e Liberare il nostro vecchio server Centos 7 in QA, ora è il momento di fare lo stesso con il sistema di produzione, ma questa volta lo faremo in un ordine diverso.

- Prima, applicheremo la formula **Liberate**

  Andiamo al nostro server di produzione `airco-dh4a-prod` e facciamo `Create System Profile`

  Successivamente applichiamo la formula **Liberate** come abbiamo fatto con il sistema QA.

- Una volta completato, confrontiamo il sistema con il profilo che abbiamo appena creato, come possiamo vedere l'unico cambiamento sono stati i pacchetti **centos-logos** e **centos-release**, il resto rimane esattamente lo stesso.


È una migrazione?
==================

Una migrazione comporta la costruzione di un server nuovo di zecca, la reinstallazione di tutte le applicazioni da zero e lo spostamento accurato dei dati, un processo che richiede tempo, è costoso e pieno di rischi.

Quello che abbiamo fatto è stato molto più elegante. Abbiamo eseguito un aggiornamento in loco (in-place upgrade).

L'identità del server, l'hostname, le applicazioni e i dati utente sono rimasti completamente intatti. Abbiamo semplicemente cambiato la sua fonte sottostante per gli aggiornamenti, e quei componenti a fine vita sono ora componenti completamente supportati che ricevono patch.

Abbiamo esteso con successo la vita del nostro sistema, lo abbiamo riportato alla conformità di sicurezza e abbiamo fatto tutto questo senza l'interruzione di una migrazione completa. Questa è l'efficienza che mantiene [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] in volo alto.




Perché è importante per [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- Consente a [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] di mantenere i propri sistemi in esecuzione supportati, concedendo loro tempo per migrare in base alle proprie esigenze aziendali piuttosto che alle esigenze del fornitore.

- Mitiga il rischio che implica avere sistemi non supportati offrendo supporto esteso. Questo approccio evita la necessità di una migrazione immediata, tutto funziona come al solito ma ora c'è un gruppo di esperti che può rispondere alle tue chiamate.

- Ti dà la libertà di cambiare fornitore di supporto senza passare attraverso lunghe migrazioni, e ti permette di farlo su larga scala.



Maggiori informazioni
================

- [Registering RHEL 7 or CentOS Linux 7 with SUSE Manager](https://documentation.suse.com/liberty/7/html/suma-quickstart/art-suma-quickstart.html)
- [Running OpenSCAP compliance scans for SUSE Multi-Linux Support 7](https://documentation.suse.com/liberty/7/html/compliance-scans/art-compliance-scans.html)
- [Registering CentOS Linux 7 with the SUSE Customer Center](https://documentation.suse.com/liberty/7/html/quickstart-scc/art-quickstart-scc.html)
- [SUSE Multi-Linux Support 9](https://documentation.suse.com/liberty/9/)