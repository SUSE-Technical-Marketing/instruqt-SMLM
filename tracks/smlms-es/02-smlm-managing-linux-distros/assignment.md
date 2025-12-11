---
slug: smlm-managing-linux-distros
id: m5gyah3o9foi
type: challenge
title: Gestionando diferentes distribuciones Linux
tabs:
- id: iii0qe9un4ad
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: bukjckiieirk
  title: Ubuntu 2404 LTS
  type: terminal
  hostname: ubuntu2404lts
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Gestionando diferentes distribuciones Linux
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

Aquí en [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]], <b class="smlmext">SUSE Multi-Linux Manager</b> es la clave para gestionar nuestra diversa flota de distribuciones Linux y arquitecturas desde un panel único. Esto nos ha ayudado a evitar las personalizaciones adicionales que solían complicar nuestro trabajo como ingenieros, lo que a su vez aumentaba el coste y el tiempo necesarios para mantener e implementar nuestras políticas del sistema.

Con esta herramienta, no estamos limitados a un solo proveedor, arquitectura o plataforma de automatización. Somos libres de elegir lo que necesitamos para nuestro entorno y gestionarlos todos de la misma manera. Imagine si para cada tipo de aeronave en nuestra flota, necesitáramos una torre de control de tráfico aéreo diferente con su propio idioma y procedimientos. La complejidad operativa sería inmanejable y los costes serían prohibitivos.

Todos sabemos que un determinado modelo de avión es mejor para una ruta específica; volar un jumbo jet para un vuelo de media hora no es rentable. Lo mismo se aplica a nuestras distribuciones Linux. Si bien las propias distribuciones de SUSE son excelentes, algunas de nuestras aplicaciones tienen requisitos específicos. <b class="smlm">SMLM</b> garantiza que nunca estemos bloqueados y siempre podamos integrar la mejor solución para la tarea en cuestión.


## <b class="hovereffect">Sus Objetivos:</b>

- Incorporar un sistema Ubuntu 24.04 LTS, un sistema especializado requerido por nuestro equipo de marketing.

- Demostrar cómo gestionamos este sistema nuevo y diferente utilizando las mismas herramientas y procedimientos de parcheo que el resto de nuestra flota.



Lab details
===========

Username:
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```

Password:
```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

<b class="smlm">SMLM</b> URL: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>


Incorporando Ubuntu
=================

Ha llegado una nueva solicitud de servicio de nuestro departamento de marketing. Sus diseñadores gráficos dependen de una suite creativa específica que solo es compatible con Ubuntu. Vamos a incorporar su sistema para que podamos gestionarlo y asegurar que cumpla con nuestros estándares de seguridad y cumplimiento, de la misma manera que lo hacemos con los demás.

Empecemos.
<br/>

- Acceda a la terminal del sistema desde la pestaña [button label="Ubuntu 2404 LTS" variant="success"](tab-1)

  Antes de realizar cualquier cambio, verifiquemos de dónde está obteniendo los paquetes:

```bash,run
grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```

Esta estación de trabajo está obteniendo software directamente de los repositorios públicos de Ubuntu. Esto presenta dos problemas: primero, no tenemos control sobre los parches que se aplican, lo cual es un problema de seguridad. Segundo, como informó el equipo de marketing, cada vez que estas estaciones de trabajo buscan actualizaciones, pueden ralentizar la conexión a Internet de la oficina, causando frustración a otros empleados.


Pongamos este sistema bajo nuestra gestión. Esto resolverá ambos problemas conectándolo a nuestra instancia interna de <b class="smlmext">SUSE Multi-Linux Manager</b> para todas las necesidades de software.

Vamos a utilizar la [button label="web UI" variant="success"](tab-0) para hacerlo:

- Bajo `Home` ✈ `Overview`, hagamos clic en `Register Systems`

- Complete los siguientes detalles:

  - **Host:**

  ```txt
  ubuntu2404lts
  ```

  - **User:**

  ```txt
  root
  ```

  - **Password:**

  ```txt
  [[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
  ```

  - **Activation Key:** <b class="highlightcopy">1-ubuntu2404</b>

- Deje el resto como está y haga clic en

<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-bootstrap.png"/>


- El proceso de registro puede tardar un par de minutos en completarse, vayamos a la [button label="terminal" variant="success"](tab-1) y ejecutemos el primer comando una vez más para ver qué ha cambiado:


```bash,run
echo 'Waiting for the registration to complete' ;while [[ ! -f /etc/apt/sources.list.d/susemanager_bootstrap.sources ]] || [[ ! -f /etc/apt/sources.list.d/susemanager:channels.sources ]]; do echo -n '.'; sleep 5; done ; sleep 60; grep -v '^#\|^Types:\|Trusted:\|Architectures:' /etc/apt/sources.list.d/*
```


Podemos ver que aparecieron nuevos archivos:

**/etc/apt/sources.list.d/susemanager:***

Apuntan el sistema a nuestros canales gestionados y controlados centralmente en <b class="smlm">SMLM</b>.


También podemos ver que el archivo original, **/etc/apt/sources.list.d/ubuntu.sources**, ha sido modificado para deshabilitar todos los repositorios públicos pero no ha sido eliminado, esto nos permitiría revertir fácilmente si lo necesitáramos.


> [!NOTE]
> Usar root vía SSH con autenticación por contraseña para registrarse es solo para fines de demostración y no se recomienda para producción.


> [!NOTE]
> Por defecto tenemos que aprobar el registro de cada sistema a través de la UI o vía línea de comandos < salt-key -A -y >, aquí <b class="smlm">SMLM</b> ha sido configurado para aprobar automáticamente.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-register_ubuntu.gif"/>
  </div>

<br/>



Ahora cambiemos a la pestaña [button label="SMLM UI" variant="success"](tab-0)


- Navegamos a `Systems` ✈ `System List` ✈ `All`

  Podemos ver el sistema que acabamos de registrar `Ubuntu2404lts`, note que por defecto se registrará bajo el nombre de host (hostname).

  Hagamos clic en él, iremos directamente a `Details` - `Overview` donde podemos ver entre otra información:

  - El estado del sistema.
  - Toda la información como nombre de host, dirección IP, tipo de virtualización, Kernel utilizado y productos instalados.
  - Los canales a los que está suscrito.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_overview.gif"/>
  </div>


<br/>

Gestionando múltiples distribuciones Linux
=====================================


Como se mencionó anteriormente, en <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b> usamos diferentes distribuciones Linux, al igual que usamos diferentes modelos de aviones y compañías. Esto nos ayuda a mantenernos por delante de la competencia utilizando el producto más adecuado para cada una de nuestras necesidades.

Con <b class="smlmext">SUSE Multi-Linux Manager</b> podemos gestionarlos todos con los mismos procedimientos, los mismos horarios, etc., utilizando la misma interfaz y mecanismos.

A continuación exploraremos cómo realizar diferentes tareas en sus sistemas, siguiendo el mismo proceso independientemente del sistema operativo que ejecuten nuestros sistemas, sin tener que crear personalizaciones innecesarias.


## <b class="hovereffect">Añadir información extra</b>


Continuemos con el sistema que acabamos de registrar, vamos a añadirle algunas configuraciones e información:

- Hagamos clic en `Properties`, donde añadiremos información extra sobre el sistema y cambiaremos algunas configuraciones.


  - Habilitar la aplicación automática de parches:

  <img style='vertical-align: middle; height: 60%; width: 60%; object-fit: contain' src="../assets/SMLM5.1/option-auto_patch_update-enabled.png"/>

    Esto parcheará automáticamente el sistema cuando haya parches relevantes.



  - Añada los siguientes detalles para el sistema:


| Field | Content                                                  |
| ---: | :-----                                                    |
| **Description** | <b class="highlightcopy">Multimedia workstation for graphics designers.</b> |
| **Facility Address** | <b class="highlightcopy">Candy eye street, 1</b> |
| **City** | <b class="highlightcopy">Aeolia</b> |
| **Building** | <b class="highlightcopy">Belem Tower 4</b> |
| **Room** | <b class="highlightcopy">Sierra nevada</b> |


<img style='padding: 0; margin:0; vertical-align: middle' src="../assets/SMLM5.1/bottom-Update_Properties.png"/>



- Veamos en qué hardware se está ejecutando:

  - Haga clic en `Details` ✈ `Hardware`


<br/>

> [!NOTE]
> Todo esto se puede automatizar a través de la API.

<br/>

Ahora vamos a añadir información extra al sistema usando claves personalizadas, esta información puede ser consumida fácilmente en sus scripts de automatización más adelante.


- Haga clic en `Details` ✈ `Custom Info`

<img style='vertical-align: top; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Create_Value.png"/>

- Haga clic en `application` y llene el **value** con lo siguiente:

```text
Logo Wings designer pro
```

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Update_Key.png"/>


<br/>

> [!NOTE]
> Ya hemos creado la clave personalizada **application** para usted, si desea crear sus propias claves es tan simple como ir a: `Systems` ✈ `Custom System Info` ✈ `Create key`

<br/><br/>

Volvamos a la lista de Systems

`Systems` ✈ `System List` ✈ `All`


Hagamos clic en cualquiera de los sistemas y vayamos a `Details` ✈ `Custom Info`.

Ya hemos poblado cada sistema con un valor,

<br/>

Ahora vaya a `Details` ✈ `Overview` y note **Installed Products** y **Subscribed Channels**, estos son diferentes a los de su sistema Ubuntu porque están ejecutando un sistema operativo diferente.



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-ubuntu_properties.gif"/>
  </div>

<br/>


## <b class="hovereffect">Ejecutar comandos en múltiples sistemas a la vez</b>


Hagamos algo en todos los sistemas que tenemos, vuelva a `Systems` ✈ `System List` ✈ `All` y seleccione todos:

<img style='vertical-align: middle; margin: 2px; height: 50%; width: 50%; object-fit: contain' src="../assets/SMLM5.1/select_all_systems.png"/>

Note la columna **Base Channel**, tenemos sistemas ejecutando tres SO diferentes.

<br/>

Habiendo seleccionado todos los sistemas que queremos operar, vayamos a realizar una acción grupal:

`Systems` ✈ `System Set Manager`

Ejecutemos un comando en todos ellos, para eso podemos ir a:

`Misc` ✈ `Remote Command`

luego complete los siguientes detalles y deje el resto con los valores por defecto:


Script:

```bash,run
cat /etc/os-release
```

No modifique el horario (schedule), queremos que se ejecute lo antes posible, haga clic en:

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/bottom-Schedule.png"/>


<br/>


<br/><br/>

Verá un aviso azul en la parte superior indicando que la tarea ha sido programada.

Vayamos a ver los resultados, para eso iremos a:

`Schedule` ✈ `Completed Actions`

Veremos una lista de acciones, en el campo **Filter by Action** escriba:

```text
Run
```
Haga clic en la entrada superior que aparece en la lista, debería ser similar a esta:

<img style='vertical-align: middle; margin: 2px; object-fit: contain' src="../assets/SMLM5.1/Select_complete_action_run.png"/>


Allí podemos ir a **Completed Systems** y examinar el resultado haciendo clic en el nombre del sistema.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/managing_different_linux_distros-multiple_systems_at_once.gif"/>
  </div>

<br/>


<br/><br/>

Con esto completamos esta parte, veremos más ejemplos de cómo podemos gestionar múltiples sistemas Linux a lo largo del workshop.



¿Por qué es importante para [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- Sin dependencia de un proveedor (vendor lock-in), mantenga la libertad de elección y la flexibilidad para reaccionar rápido a los mercados cambiantes.

- Simplifique y ahorre tiempo evitando trabajo extra en personalizaciones.

- Una UI única para gestionarlo todo reduce la complejidad y hará que la futura resolución de problemas, escalado, parcheo y automatización sean mucho más ágiles y consuman menos tiempo.



Más información
================

Para obtener una lista de las distribuciones soportadas, por favor visite:

[SMLM - Supported Clients and Features](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/client-configuration/supported-features.html)