---
slug: smlm-automation
id: r3qjodahyliz
type: challenge
title: Automatización (Opcional)
tabs:
- id: vjo9bjdmtlgn
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Automatización y gestión de la configuración
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

En esta sección vamos a ver algunas de las opciones disponibles para automatizar tareas.

En este laboratorio, pasamos de realizar tareas manuales a crear cierta automatización utilizando algunas de las opciones que tenemos disponibles.
<b class="smlmext">SUSE Multi-Linux Manager</b> actúa como el "piloto automático" para nuestras operaciones de TI, permitiéndonos imponer estándares de configuración y automatizar tareas rutinarias con precisión y fiabilidad en toda nuestra flota.

En lugar de configurar manualmente cientos de servidores y esperar no saltarnos ningún paso, definimos el proceso y el estado y reducimos la operación humana a definir un horario, una sola vez.



## <b class="hovereffect">Sus Objetivos:</b>

- Crear un horario que realice actualizaciones regularmente en sus sistemas de desarrollo.

- Crear un script para mostrar un banner de inicio de sesión diferente según el entorno del sistema.

Detalles del laboratorio (Lab details)
===========

Usuario (Username):
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```

Contraseña (Password):
```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

URL de <b class="smlm">SMLM</b>: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>


Configurar actualizaciones recurrentes (Setup recurring updates)
=======================

Queremos que los desarrolladores trabajen con las últimas actualizaciones estables proporcionadas por SUSE, pero no podemos confiar en que la gente recuerde actualizar sus sistemas todos los días, así que vamos a crear un horario recurrente que haga exactamente eso.


Vamos a aplicar esto a todos los sistemas en el grupo dev para que esto no tenga que hacerse en cada sistema.

- Vayamos a `Systems` ✈ `System Groups`
- Haga clic en el grupo `dev`.

Acabamos de notar que no tiene sistemas asignados, agreguemos uno.

- haga clic en `Target Systems` y seleccione `sles15`
- luego haga clic en ![Add Systems](../assets/SMLM5.1/bottom-add_system.png)

Ahora que tenemos un sistema, creemos la acción recurrente.

- Vaya a `Recurring Actions`
- Haga clic en ![Create](../assets/SMLM5.1/bottom-create.png)
- Ahora completemos el formulario con los siguientes detalles:
	+ **Action Type:** 'Custom state'
 	+ **Schedule Name:** 'Update Dev systems'
	+ **Daily:** '03:00'
	+ **Configure states to execute:** Asegúrese de que **uptodate:** esté seleccionado
	![uptodate Selected](../assets/SMLM5.1/uptodate_selected.png)

- Haga clic en

<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-create_schedule.png"/>
</p>



Para observar nuestra lista de acciones recurrentes podemos ir a `Schedule` ✈ `Recurring Actions`

Ahora todos los sistemas dev se actualizarán diariamente a las 3 am hora UTC.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-setup_recurring_updates.gif"/>
  </div>

<br/>




Asegúrese de que cada sistema tenga un mensaje de inicio de sesión
==========================================


Vamos a crear un canal de configuración para asegurarnos de que cada sistema que gestionamos contenga un mensaje de inicio de sesión adecuado.



- Vayamos a `Configuration` ✈ `Channels`
- Haga clic en ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png)
- Llene el formulario con los siguientes detalles:
	+ **Name:** <b class="highlightcopy">Uniform experience</b>
	+ **Label:** <b class="highlightcopy">uniform_experienace</b>
	+ **Description:** <b class="highlightcopy">Create a uniform experience across systems</b>
- Haga clic en ![Create Config Channel](../assets/SMLM5.1/bottom-create_config_channel.png)

Ahora que hemos creado el canal de configuración, poblémoslo.

- Vaya a `Add Files` ✈ `Create File`
- Llene los siguientes detalles:
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


- Haga clic en ![Create Configuration File](../assets/SMLM5.1/bottom-create_configuration_file.png)

Ahora suscribamos cada sistema en la organización al nuevo canal de configuración.

- vayamos a `Admin` ✈ `Organizations`
- Haga clic en la organización **Organization** (Esta es la organización predeterminada)
- Vaya a `States` y seleccione el canal que acabamos de crear.
![Uniform experience selected](../assets/SMLM5.1/selected_univorm_experience_Configurationchannel.png)
- Haga clic en


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;"> </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-save_changes.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-execute_states.png"/>
</p>


Esto no sucederá inmediatamente, verifiquemos los sistemas. Vamos a ejecutar un comando simple a través de la interfaz web, si se ejecuta demasiado pronto, puede ver sistemas con el mensaje antiguo y sistemas que ya obtuvieron el archivo actualizado.

- Vayamos a `Salt` ✈ `Remote Commands`
- Escriba lo siguiente:
![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd.png)
- Haga clic en `Find targets`
- Debería ver una lista de sistemas, haga clic en `Run command`

Ahora debería ver algo como esto:

![cat /etc/motd - sles15](../assets/SMLM5.1/run_cat_etcmotd_first_result.png)

> [!NOTE]
> Este proceso puede tardar un par de minutos, si no ve el MOTD por favor vuelva a ejecutar el comando después de unos minutos.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/07-automation-login_message.gif"/>
  </div>

<br/>


¿Por qué es importante para [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================



- Al gestionar miles de sistemas no podemos permitirnos hacer todo uno por uno, las tareas necesitan ser automatizadas para que gestionemos ganado, no mascotas.



- Al definir el "estado correcto" eliminamos la desviación de configuración (configuration drift). Cada servidor en la flota opera desde el mismo libro de jugadas, al igual que cada piloto usa la misma lista de verificación.



- Las tareas que tomarían horas para realizar manualmente en cientos de servidores se completan en minutos. Esto libera a nuestros ingenieros para trabajar en innovación y mejora, no en trabajo manual repetitivo.


- La automatización es la defensa definitiva contra el error humano. Un paso olvidado o un error tipográfico durante la configuración manual puede llevar a una interrupción. Un proceso automatizado y probado se ejecuta perfectamente cada vez, mejorando la fiabilidad y seguridad de toda nuestra aerolínea.




Más información
================


* [Página del Producto SUSE Multi-Linux Manager](https://www.suse.com/products/suse-manager/)

* [Integración de Ansible](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/ansible-integration.html)

* [Guía de Salt](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/specialized-guides/salt/salt-overview.html)