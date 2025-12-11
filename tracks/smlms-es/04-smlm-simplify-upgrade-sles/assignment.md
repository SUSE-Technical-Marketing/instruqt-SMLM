---
slug: smlm-simplify-upgrade-sles
id: vu7qhjyplrxo
type: challenge
title: Mantenimiento simple y fiable
tabs:
- id: qlsnrloauj7q
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: plbjwmzwv3dm
  title: SLES 15
  type: terminal
  hostname: sles15
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Mantenimiento simple y fiable
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

Hasta ahora, nos hemos centrado en gestionar la diversidad de nuestra flota mixta e incluso en extender la vida útil de nuestros sistemas heredados. Ahora, dirigimos nuestra atención al núcleo de nuestra aerolínea: nuestros sistemas insignia <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>).


Piense en estos como nuestros jets de larga distancia de última generación. Su fiabilidad es primordial, y mantenerlos en condiciones óptimas implica la aplicación de parches y actualizaciones de servicio regulares y planificadas. Este próximo ejercicio es exactamente eso: vamos a repasar el proceso de una actualización de versión, una tarea común en la gestión del ciclo de vida de cualquier sistema crítico.



Y aunque estamos usando SLES como ejemplo, recuerde el principio clave de nuestra torre de control universal: el proceso que está a punto de realizar es el mismo que usaría para cualquier otra distribución Linux. La interfaz y la metodología no cambian.


## <b class="hovereffect">Sus Objetivos:</b>

- Incorporar (Onboard) un nuevo sistema SLES 15 SP5 para que sirva como nuestro avión de prueba.
- Realizar una actualización de servicio mayor de SP5 a SP6.



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






Incorporación y preparación (Onboarding and preparation)
==========================

Acceda a la terminal del sistema desde la pestaña [button label="SLES 15" variant="success"](tab-1)


Registremos el sistema dentro de <b class="smlm">SMLM</b> como **sles15**

```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | HOSTNAME="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-sles15sp5 bash ; echo "Wait 45 seconds for it to finish"; sleep 45
```


Ahora, cambiemos a la pestaña [button label="SMLM UI" variant="success"](tab-0)


Ejecutando la actualización (Executing the upgrade)
=====================

Deberíamos verlo pronto en la lista de sistemas, vayamos a `Systems` ✈ `System List` ✈ `All`, por favor haga clic en actualizar en el navegador interno si no lo ve.


Hagamos clic en él y vayamos a `Software` ✈ `Packages` ✈ `Upgrade`.


Para asegurar una migración fluida es mejor aplicar las últimas actualizaciones.



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">Haga clic en </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-select_all.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;"><img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-upgrade_packages.png"/></p> ✈ <p style="margin: 1px; padding: 1px;vertical-align: middle;display:inline-block; align:right;"> <img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:right;" src="../assets/SMLM5.1/bottom-confirm.png"/></p>


Esto puede tardar algún tiempo en completarse.

<br/>


## <b class="hovereffect">Migración de producto</b>


Una vez que termine, por favor vaya a `Software` ✈ `Product Migration`



<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">Verá una sección llamada **Target Products**. Asegúrese de que <b style="font-family: suse; src: url('https://fonts.google.com/specimen/SUSE'); color: #90ebcd">SUSE Linux Enterprise Server 15 SP6 x86_64</b> esté seleccionado, luego presione: </p><p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;"><img style="margin: 1px; vertical-align: middle; display:block; align:left; padding: 0px;" src="../assets/SMLM5.1/bottom-select_channels.png"/></p>

Se le mostrará una pantalla de confirmación con un resumen y opciones adicionales. Deje los valores predeterminados como están y haga clic en: ![Schedule Migration](../assets/SMLM5.1/bottom-schedule_migration.png)

El sistema le pedirá que haga una prueba (dry run) primero, ignórelo y presione: ![Confirm](../assets/SMLM5.1/bottom-confirm.png)

Esto tomará algún tiempo. Para monitorear el estado, vaya a `Events` ✈ `History` y observe el evento **Product Migration**. Una vez que su icono de estado se vuelva verde, la migración se habrá completado. Puede verificar esto navegando a `Software` ✈ `Software Channels` y confirmando que el sistema ahora está suscrito a los nuevos canales SP6.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/04-simple_and_reliable_maintenance-executing_the_upgrade.gif"/>
  </div>

<br/>

## <b class="hovereffect">Reinicio Post-Migración</b>

- Navegue de regreso a `Systems` ✈ `System List` ✈ `All`

- Note que el sistema `sles15` ahora tiene un icono de reinicio junto a él:

![Needs reboot icon](../assets/SMLM5.1/icon_needs_reboot.png)

  Esto indica que se requiere un reinicio, generalmente debido a una actualización mayor del kernel.

- Haga clic en él, veremos algo similar a esto:

![Needs reboot message](../assets/SMLM5.1/system_requires_a_reboot.png)

- Haga clic en `Schedule System Reboot` y en la siguiente pantalla haga clic en ![Reboot System](../assets/SMLM5.1/bottom-reboot_system.png)

> [!NOTE]
> El reinicio no ocurrirá inmediatamente.

<br/>


## <b class="hovereffect">La importancia de la Programación (Scheduling)</b>

Hemos programado estas acciones para que sucedan inmediatamente, pero esto no siempre es deseable. <b class="smlm">SMLM</b> soporta la creación de Ventanas de Mantenimiento (Maintenance Windows) (`Schedule` ✈ `Maintenance Windows`) lo que le permite asegurar que los eventos mayores como los reinicios solo ocurran durante esos períodos preaprobados.



La programación es especialmente útil para sistemas de producción, ya que permite cambios cuidadosamente planificados en grupos de sistemas e incluso despliegues "canario" por fases.

<br/>

> [!NOTE]
> Es posible hacer parcheo del kernel en vivo con KLP, hace posible aplicar las últimas actualizaciones de seguridad a los kernels Linux sin reiniciar.



¿Por qué es importante para [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- Las actualizaciones del sistema y otras tareas rutinarias deben ser simples y repetibles, de lo contrario, corremos el riesgo de cometer errores costosos. Con estas herramientas, podemos controlar con precisión cuándo y dónde realizamos acciones, programando el mantenimiento crítico para nuestra flota con confianza.


- Podemos controlar cuándo y dónde realizamos acciones, y programar operaciones de mantenimiento en nuestra flota en tierra.


Más información
================

- [Live kernel patching with KLP](https://documentation.suse.com/en-us/sles/15-SP7/html/SLES-all/cha-klp.html)

- [Maintenance Windows](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/maintenance-windows.html)

- [Administration Guide](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/admin-overview.html)