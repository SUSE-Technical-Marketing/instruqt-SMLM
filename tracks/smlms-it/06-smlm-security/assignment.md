---
slug: smlm-security
id: kdamiesyxcjl
type: challenge
title: Sicurezza e applicazione di patch
tabs:
- id: unuezcexmqd5
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Sicurezza e applicazione di patch
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



In questo laboratorio, affronteremo una delle responsabilità più importanti che abbiamo: garantire la sicurezza dell'intera nostra flotta digitale. Esploreremo come <b class="smlmext">SUSE Multi-Linux Manager</b> ci consente di rispondere alle minacce alla sicurezza con la velocità e la precisione richieste da una compagnia aerea di livello mondiale.




## <b class="hovereffect">I Tuoi Obiettivi:</b>

- Eseguire un audit di conformità della sicurezza sui tuoi sistemi utilizzando OpenSCAP.

- Identificare i sistemi interessati da vulnerabilità di sicurezza rilevanti.

- Applicare le patch necessarie a tutti i sistemi interessati contemporaneamente.



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




Audita i tuoi sistemi
==================

Vogliamo eseguire un audit sui nostri sistemi di produzione per assicurarci che siano conformi.

Abbiamo già verificato che i seguenti pacchetti siano installati:

- openscap-utils
- scap-security-guide


Seleziona il gruppo di produzione

- Andiamo su `Systems` ✈ `System Groups`
- Trova il gruppo **prod** e clicca su `Use in SSM`
![Next](../assets/SMLM5.1/prod_group_selection.png)

Verremo indirizzati alla pagina **System Set Manager Overview**, come abbiamo visto in precedenza, da qui possiamo applicare azioni a più sistemi contemporaneamente.

- Vai alla scheda `Audit`
- Sotto `OpenSCAP` compila il modulo con i seguenti dettagli, lascia il resto con i valori predefiniti:
  - **Command-line Arguments:** <b class="highlightcopy">--profile xccdf_org.ssgproject.content_profile_stig</b>
  - **Path to XCCDF document:** <b class="highlightcopy">/usr/share/xml/scap/ssg/content/ssg-sle15-ds.xml</b>
- Premi


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">
</p>
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-Schedule.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p>



Ci vorranno un paio di minuti.


Per vedere i risultati andiamo su `Audit` ✈ `OpenSCAP` ✈ `All Scans`

![OpenSCAP Results](../assets/SMLM5.1/openscap_results.png)

Se clicchiamo su uno di questi risultati, possiamo vedere una ripartizione più dettagliata.

- Cliccando su **report.html**, puoi visualizzare una versione più gradevole del report generato da OpenSCAP.

![Detailed OpenSCAP Results](../assets/SMLM5.1/openscap_results_detailed.png)


Non preoccuparti dei problemi segnalati.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-audit_your_system.gif"/>
  </div>

<br/>



Identifica i sistemi interessati da vulnerabilità
============================================

Vogliamo vedere quali sistemi sono interessati da vulnerabilità.

- Ora, navighiamo su `Patches` ✈ `Patch List` ✈ `Relevant`

  Qui possiamo vedere un elenco di tutte le patch rilevanti disponibili per i nostri sistemi, guardiamo le **Security Patches** (Patch di sicurezza).

- Cliccando sul nome di un **Advisory** (Avviso), puoi visualizzare una pagina dettagliata che mostra quali pacchetti e sistemi sono interessati, tra gli altri dettagli.

- Sul lato destro dell'elenco, la colonna **CVEs** fornisce collegamenti diretti ai rapporti ufficiali sulle vulnerabilità.

  È anche possibile creare le nostre patch personalizzate, ma non lo tratteremo in questo percorso; per ulteriori informazioni consultare i link alla fine del percorso.



## <b class="hovereffect">Patchare i sistemi interessati</b>

Patchare i nostri sistemi è semplice come seguire questi passaggi:

- Vai su `Systems` ✈ `System Set Manager`
- Naviga alla scheda `Patches` ✈ seleziona **Security Advisory** nell'elenco a discesa, e clicca su `Show`

![Select Security Advisory](../assets/SMLM5.1/show_only_security_advisories.png)

- Clicca su `Select All` ✈ `Apply Patches` ✈ ![Confirm](../assets/SMLM5.1/bottom-confirm.png)


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-indentify_vulnerabilities.gif"/>
  </div>

<br/>


Perché è importante per [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================


- Essendo in grado di agire velocemente, riduciamo la finestra di esposizione. Quando viene scoperta una nuova vulnerabilità, inizia una gara tra noi e gli attori malintenzionati che cercano di sfruttarla. Un processo di patching manuale e complesso lascia i nostri sistemi critici esposti per troppo tempo.

- <b class="smlmext">SUSE Multi-Linux Manager</b> fornisce una vista singola e unificata della postura di sicurezza dell'intera nostra flotta e ci consente di rimediare alle minacce con un processo coerente e affidabile.

- Essere in grado di controllare facilmente la conformità dei nostri sistemi rispetto a diversi framework di sicurezza ci consente di implementare misure correttive più velocemente e di aderire a rigide normative del settore.


Maggiori informazioni
================


* [Auditing](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/auditing.html)
* [Sicurezza SUSE](https://www.suse.com/support/security/)
* [Sicurezza del Sistema con OpenSCAP](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/openscap.html)
* [Gestire le Patch](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)