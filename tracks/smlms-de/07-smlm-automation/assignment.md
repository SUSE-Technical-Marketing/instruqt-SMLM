---
slug: smlm-automation
id: xpoye9s8qqdr
type: challenge
title: Automatisierung (Optional)
tabs:
- id: 0ilte9gaxgss
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Automatisierung und Konfigurationsmanagement
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

<img class="logos" alt="Welcome!" src="../assets/logos/07-automation.jpeg"/>

In diesem Abschnitt werden wir uns einige der verfügbaren Optionen zur Automatisierung von Aufgaben ansehen.

In diesem Labor gehen wir von manuellen Aufgaben dazu über, eine gewisse Automatisierung zu erstellen, indem wir einige der verfügbaren Optionen nutzen.
<b class="smlmext">SUSE Multi-Linux Manager</b> fungiert als "Autopilot" für unsere IT-Operationen und ermöglicht es uns, Konfigurationsstandards durchzusetzen und Routineaufgaben mit Präzision und Zuverlässigkeit in unserer gesamten Flotte zu automatisieren.

Anstatt Hunderte von Servern manuell zu konfigurieren und zu hoffen, dass wir keinen Schritt verpassen, definieren wir den Prozess und den Zustand und reduzieren den menschlichen Eingriff darauf, einmalig einen Zeitplan festzulegen.



## <b class="hovereffect">Ihre Ziele:</b>

- Erstellen Sie einen Zeitplan, der regelmäßig Updates auf Ihren Entwicklungssystemen durchführt.

- Erstellen Sie ein Skript, um je nach Systemumgebung ein anderes Anmeldebanner anzuzeigen.

Lab-Details
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


Wiederkehrende Updates einrichten (Setup recurring updates)
=======================

Wir möchten, dass Entwickler mit den neuesten stabilen Updates arbeiten, die von SUSE bereitgestellt werden, aber wir können uns nicht darauf verlassen, dass die Leute daran denken, ihre Systeme jeden Tag zu aktualisieren. Deshalb werden wir einen wiederkehrenden Zeitplan erstellen, der genau das tut.


Wir werden dies auf alle Systeme in der dev-Gruppe anwenden, damit dies nicht auf jedem System einzeln durchgeführt werden muss.

- Gehen wir zu `Systems` ✈ `System Groups`
- Klicken Sie auf die Gruppe `dev`.

Wir haben gerade bemerkt, dass keine Systeme zugewiesen sind, lassen Sie uns eines hinzufügen.

- Klicken Sie auf `Target Systems` und wählen Sie `sles15` aus
- Klicken Sie dann auf ![Add Systems](../assets/SMLM5.1/bottom-add_system.png)

Da wir nun ein System haben, lassen Sie uns die wiederkehrende Aktion erstellen.

- Gehen Sie zu `Recurring Actions`
- Klicken Sie auf ![Create](../assets/SMLM5.1/bottom-create.png)
- Füllen wir nun das Formular mit den folgenden Details aus:
	+ **Action Type:** 'Custom state'
 	+ **Schedule Name:** 'Update Dev systems'
	+ **Daily:** '03:00'
	+ **Configure states to execute:** Stellen Sie sicher, dass **uptodate:** ausgewählt ist
	![uptodate Selected](../assets/SMLM5.1/uptodate_selected.png)

- Klicken Sie auf

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-create_schedule.png"/>
</p>



Um unsere Liste der wiederkehrenden Aktionen zu sehen, können wir zu `Schedule` ✈ `Recurring Actions` gehen.

Jetzt werden alle Entwicklungssysteme täglich um 03:00 Uhr UTC aktualisiert.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-setup_recurring_updates.gif"/>
  </div>

<br/>




Sicherstellen, dass jedes System eine Anmeldenachricht hat
==========================================


Wir werden einen Konfigurationskanal erstellen, um sicherzustellen, dass jedes von uns verwaltete System eine angemessene Anmeldenachricht enthält.



- Gehen wir zu `Configuration` ✈ `Channels`
- Klicken Sie auf ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png)
- Füllen Sie das Formular mit den folgenden Details aus:
	+ **Name:** <b class="highlightcopy">Uniform experience</b>
	+ **Label:** <b class="highlightcopy">uniform_experienace</b>
	+ **Description:** <b class="highlightcopy">Create a uniform experience across systems</b>
- Klicken Sie auf ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png)

Nachdem wir den Konfigurationskanal erstellt haben, lassen Sie uns ihn befüllen.

- Gehen Sie zu `Add Files` ✈ `Create File`
- Füllen Sie die folgenden Details aus:
	+ **Filename/Path:** <b class="highlightcopy">/etc/motd</b>
	+ **File Contents:**
<pre>
This system is the property of [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]].

Server ID: {{ grains['id'] }}
{%- if 'custom_info' in pillar %}
{%- if 'application' in pillar['custom_info'] %}
Running Application "{{ pillar['custom_info']['application'] }}"
{%- else %}
No applications running on this server
{%- endif %}
{%- else %}
No applications running on this server
{%- endif %}
</pre>


- Klicken Sie auf ![Create Configuration File](../assets/SMLM5.1/bottom-create_configuration_file.png)

Lassen Sie uns nun jedes System in der Organisation für den neuen Konfigurationskanal abonnieren.

- gehen wir zu `Admin` ✈ `Organizations`
- Klicken Sie auf die Organisation **Organization** (Dies ist die Standardorganisation)
- Gehen Sie zu `States` und wählen Sie den Kanal aus, den wir gerade erstellt haben.
![Uniform experience selected](../assets/SMLM5.1/selected_univorm_experience_Configurationchannel.png)
- Klicken Sie auf


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-execute_states.png"/>
</p>


Dies geschieht nicht sofort, lassen Sie uns die Systeme überprüfen. Wir werden einen einfachen Befehl über die Web-UI ausführen. Wenn er zu früh ausgeführt wird, sehen Sie möglicherweise Systeme mit der alten Nachricht und Systeme, die die Datei bereits aktualisiert haben.

- Gehen wir zu `Salt` ✈ `Remote Commands`
- Geben Sie Folgendes ein:
![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd.png)
- Klicken Sie auf `Find targets`
- Sie sollten eine Liste von Systemen sehen, klicken Sie auf `Run command`

Jetzt sollten Sie etwas Ähnliches sehen:

![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd_first_result.png)

> [!NOTE]
> Dieser Vorgang kann einige Minuten dauern. Wenn Sie die MOTD nicht sehen, führen Sie den Befehl bitte nach einigen Minuten erneut aus.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-login_message.gif"/>
  </div>

<br/>


Warum ist das wichtig für [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================



- Bei der Verwaltung von Tausenden von Systemen können wir es uns nicht leisten, alles einzeln zu tun. Aufgaben müssen automatisiert werden, damit wir 'Rinder' (Cattle) verwalten, keine 'Haustiere' (Pets).



- Indem wir den "korrekten Zustand" definieren, eliminieren wir Konfigurationsabweichungen (Configuration Drift). Jeder Server in der Flotte arbeitet nach demselben Spielbuch, genau wie jeder Pilot dieselbe Checkliste verwendet.



- Aufgaben, die manuell auf Hunderten von Servern Stunden dauern würden, sind in Minuten erledigt. Dies setzt unsere Ingenieure frei, um an Innovationen und Verbesserungen zu arbeiten, anstatt sich mit repetitiver Handarbeit zu beschäftigen.


- Automatisierung ist die ultimative Verteidigung gegen menschliches Versagen. Ein vergessener Schritt oder ein Tippfehler bei der manuellen Konfiguration kann zu einem Ausfall führen. Ein automatisierter, getesteter Prozess wird jedes Mal perfekt ausgeführt und erhöht die Zuverlässigkeit und Sicherheit unserer gesamten Fluggesellschaft.




Mehr Informationen
================


* [SUSE Multi-Linux Manager Produktseite](https://www.suse.com/products/suse-manager/)

* [Ansible-Integration](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/ansible-integration.html)

* [Salt Guide](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/specialized-guides/salt/salt-overview.html)