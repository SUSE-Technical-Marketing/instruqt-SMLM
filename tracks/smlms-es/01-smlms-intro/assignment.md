---
slug: smlms-intro
id: 5lg1n5pv2y7a
type: challenge
title: ¡Bienvenido al SUSE Multi-Linux Hands-on Workshop!
teaser: ¡Bienvenido al SUSE Multi-Linux Hands-on Workshop! En esta sección le presentaremos
  el taller y sus componentes principales.
notes:
- type: text
  contents: |
    # ¡Bienvenido al SUSE Multi-Linux Hands-on Workshop!
    Por favor, espere mientras configuramos su entorno de laboratorio.
    <img class="logos" src="../assets/logos/suse_logo.svg"/>
tabs:
- id: ny4l1mqx0cx2
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: ""
enhanced_loading: null
---

Bienvenido al <b style="font-family: suse; src: url('[https://fonts.google.com/specimen/SUSE](https://fonts.google.com/specimen/SUSE)'); color: #30ba78">SUSE</b> Multi-Linux Hands-on Workshop
==================================================================

<link  rel="stylesheet" href="[https://raw.githubusercontent.com/SUSE-Technical-Marketing/lab-setup/refs/heads/develop/web/css/instruqt.css](https://raw.githubusercontent.com/SUSE-Technical-Marketing/lab-setup/refs/heads/develop/web/css/instruqt.css)" type="text/css" crossorigin="anonymous" fetchpriority="high" />

<style type="text/css">

  @import url("[https://raw.githubusercontent.com/SUSE-Technical-Marketing/lab-setup/refs/heads/develop/web/css/instruqt.css](https://raw.githubusercontent.com/SUSE-Technical-Marketing/lab-setup/refs/heads/develop/web/css/instruqt.css)");
  @import "[https://raw.githubusercontent.com/SUSE-Technical-Marketing/lab-setup/refs/heads/develop/web/css/instruqt.css](https://raw.githubusercontent.com/SUSE-Technical-Marketing/lab-setup/refs/heads/develop/web/css/instruqt.css)";

  * {
    font-family: suse;
    src: url('[https://fonts.google.com/specimen/SUSE](https://fonts.google.com/specimen/SUSE)');
/* background-color: #30ba78; */
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

En este taller explorará parte de la magia que <b class="smlmext">SUSE Multi-Linux Manager</b> (<b class="smlm">SMLM</b>) puede hacer; es la solución de <b class="suse">SUSE</b> para gestionar múltiples distribuciones de Linux a escala desde una interfaz unificada. También descubrirá cómo mantener sus servidores de producción heredados (legacy) con soporte gracias a <b class="smlsext">SUSE Multi-Linux Support</b> (<b class="smls">SMLS</b>), nuestra solución de soporte profesional y fiable para sistemas Linux.

&emsp;&emsp; Usted adoptará el rol de un **ingeniero** en <b class="companyname">[[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]</b>, una aerolínea donde cada avión tiene un servidor Linux a bordo.

&emsp;&emsp; Al igual que con cualquier componente de un avión, es crítico que esos servidores permanezcan estables y fiables, sin importar si están ubicados en tierra en algún centro de datos o volando sobre las nubes ☁ ☁ ☁


&emsp;&emsp; Algunos modelos de avión requerirán un "sabor" de Linux diferente, o una arquitectura de CPU distinta. Esto no es un problema para <b class="smlm">SMLM</b>; usted es libre de elegir la distribución de Linux y la arquitectura de CPU que mejor se adapte a sus necesidades sin tener que renunciar a una estandarización y gestión sencillas.


&emsp;&emsp; Como ingeniero responsable de gestionar el panorama de Linux, recorrerá algunas de las soluciones que <b class="smlm">SMLM</b> y <b class="smls">SMLS</b> le ofrecen para facilitar y automatizar la gestión de sistemas y resolver problemas excepcionales que puedan ocurrir.


A lo largo de los diferentes desafíos tendrá disponibles las siguientes herramientas:

 ✈ **SUSE Multi-Linux Manager**:
   El panel único de gestión para administrar toda su pila de Linux.

 ✈ **Centos 7**:
   Una distribución heredada (legacy) todavía en uso en algunos aviones antiguos y sistemas terrestres.

 ✈ **Ubuntu 24**: Una distribución de Linux específica requerida por nuestro departamento de marketing para ejecutar sus aplicaciones de diseño gráfico.

 ✈ **SLES 15**: La distribución de Linux altamente fiable, estable y segura de <b class="suse">SUSE</b> que forma la columna vertebral de nuestros sistemas más críticos.




## <b class="smlmext hovereffect">SUSE Multi-Linux Manager</b>

Es la mejor solución de gestión de infraestructura de código abierto de su clase para su infraestructura definida por software.

&emsp;&emsp; <b class="smlmext">SUSE Multi-Linux Manager</b> fue diseñado para ayudar a sus equipos de DevOps y Operaciones de TI empresariales a reducir la complejidad y recuperar el control de sus activos de TI; una herramienta única pero muy potente para gestionar sistemas Linux a través de una variedad de arquitecturas de hardware, hipervisores, así como plataformas de contenedores, IoT y nube.

&emsp;&emsp; Automatiza el aprovisionamiento de servidores Linux y dispositivos IoT, la aplicación de parches y la configuración para un despliegue de servidores más rápido, consistente y repetible, ayudando a optimizar operaciones y reducir costos. Y con la monitorización, seguimiento, auditoría e informes automatizados de sus sistemas, máquinas virtuales y contenedores en sus entornos de desarrollo, prueba y producción, puede garantizar el cumplimiento de las políticas de seguridad internas y las regulaciones externas.


## <b class="smlsext hovereffect">SUSE Multi-Linux Support</b>


Es una oferta de servicio integral que ofrece asistencia técnica y mantenimiento para varias distribuciones de Linux, incluyendo su Red Hat Enterprise Linux (RHEL) existente, CentOS, <b class="liberty">SUSE Liberty Linux</b> y <b class="sles">SUSE Linux Enterprise Server</b> (<b class="sles">SLES</b>), dependiendo de la oferta.

&emsp;&emsp; Permite a las organizaciones gestionar entornos mixtos de Linux de manera eficiente bajo un único marco de soporte.
Dependiendo del paquete adquirido, <b class="smlsext">SUSE Multi-Linux Support</b> también puede incluir <b class="smlmext">SUSE Multi-Linux Manager</b>, una herramienta de gestión multi-Linux para administrar estas distribuciones.



 🌅 Explorar la Interfaz de Usuario de Instruqt
=======================
Antes de comenzar nuestra primera tarea, tomémonos un momento para observar la Interfaz de Usuario (UI) de Instruqt.

+ El **lado derecho** de la pantalla le proporciona estas instrucciones y los controles de navegación.

+ El **lado izquierdo** le da acceso a las diversas máquinas y servicios que componen nuestro entorno de laboratorio.

Dentro de la UI de Instruqt puede alternar entre la [button label="SMLM UI" variant="success"](tab-0) y las [button label="terminales" variant="success"](tab-1) disponibles haciendo clic en las pestañas en la parte superior del panel izquierdo.


> [!NOTE]
> No hay recarga automática en la interfaz web; en algunos casos puede que tenga que recargar el navegador interno de Instruqt para ver las actualizaciones.


🛫 Iniciar sesión en <b class="smlmext">SUSE Multi-Linux Manager</b> 🛫
========================================

Vamos a familiarizarle con el entorno.

- Abra <b class="smlmext">SUSE Multi-Linux Manager</b> dentro del laboratorio desde la pestaña [button label="SMLM UI" variant="success"](tab-0)


- Inicie sesión con las siguientes credenciales:

  - Usuario (Username):
```txt
[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]
```
  - Contraseña (Password):

```txt
[[ Instruqt-Var key="UNIVERSAL_PWD" hostname="zbastion" ]]
```

Si todo ha ido bien, debería ver la página de **Overview** en la interfaz de <b class="smlmext">SUSE Multi-Linux Manager</b> con la sesión iniciada como el usuario `[[ Instruqt-Var key="SMLM_USERNAME" hostname="zbastion" ]]`.

> [!NOTE]
> Si desea acceder a la UI de <b class="smlmext">SUSE Multi-Linux Manager</b> directamente a través de su navegador, también puede hacerlo:

URL de <b class="smlm">SMLM</b>: <a href="[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]">[[ Instruqt-Var key="SMLM_URL" hostname="zbastion" ]]</a>


> [!NOTE]
> Si la página no carga correctamente, es posible que deba actualizar la pestaña del navegador después de que el entorno del laboratorio haya terminado de iniciarse.


🗺 Explorar <b class="smlmext">SUSE Multi-Linux Manager</b> 🗺
======================================

Antes de despegar, familiaricémonos con los controles. Esto no pretende ser un recorrido exhaustivo, sino una breve visión general de los instrumentos clave que utilizaremos a lo largo del taller. Le animamos a ser curioso y explorar.


Comencemos.


- **Menú Systems** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_systems.png"/>

  En el panel de la izquierda, haga clic en `systems`. Esta es la visión general de nuestra flota, mostrando cada servidor registrado. La lista es pequeña ahora, pero crecerá a medida que completemos nuestros ejercicios.

   - **System Lists**

     Esta sección proporciona vistas convenientes y pre-filtradas. Por ejemplo, la lista `Out of Date` le muestra instantáneamente qué servidores requieren actualizaciones, ahorrándole tener que realizar una búsqueda manual.

  <br/>

  - **System Groups**

    Para organizar nuestra flota lógicamente, usamos `System Groups`. Puede categorizarlos basándose en cualquier criterio; al hacerlo puede ahorrar tiempo al aplicar acciones o definir políticas. Una vez creados, puede adjuntar sistemas automáticamente a uno o múltiples grupos, p. ej. usando `activation keys`.


    Siéntase libre de intentar crear uno ahora haciendo clic en `+ Create Group`.

  <br/>

  - **Operaciones por lotes (Batch operations)**

    `System Set Manager` proporciona una forma potente de realizar acciones en múltiples sistemas simultáneamente.


    En lugar de aplicar cambios uno por uno, puede seleccionar una colección de sistemas, ya sea individualmente desde la `System List` o aprovechando los `System Groups` existentes, y luego ejecutar tareas en todos ellos en una sola operación.

  <br/>

  - **Aprovisionamiento (Provisioning)**

    <b class="smlmext">SUSE Multi-Linux Manager</b> proporciona herramientas integrales para el aprovisionamiento de nuevos sistemas y el re-aprovisionamiento de los existentes. Esta capacidad le ayuda a establecer un proceso estandarizado y repetible para el despliegue de sistemas.


    Por ejemplo, dentro de la sección `Autoinstallation` puede definir distribuciones y perfiles Kickstart/AutoYaST, lo que le permite especificar cómo deben desplegarse sus sistemas, qué software tendrán instalado, cómo se distribuirá el espacio de almacenamiento y más.


    Todos estos mecanismos de automatización sencillos de configurar pueden combinarse con soluciones de automatización complejas pero más potentes como Salt o Ansible, manteniendo su libertad para elegir la mejor solución para cada desafío.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_systems.gif"/>
  </div>

<br/>



- **Menú Patches** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_patches.png"/>

  - **Patching**

    Una de las tareas más comunes en TI es mantener los sistemas actualizados y, de vez en cuando, aplicar parches de seguridad con urgencia.
    Con SMLM podemos ver fácilmente una lista de parches **relevantes**, clasificados por tipo, y provistos con toda la información que pueda necesitar saber, incluyendo todos los sistemas y paquetes a los que afectan.

    Más allá de los parches suministrados por el proveedor, también podemos crear nuestros propios parches. Más adelante exploraremos las diferentes opciones que tenemos para gestionar el parcheo y las actualizaciones regulares en toda nuestra flota.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_patches.gif"/>
  </div>

<br/>


- **Software channels** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_software.png"/>

  En `Channel List` podemos ver todos los canales/repositorios/streams de paquetes disponibles para consumo; también puede crear nuevos canales de software para organizar su software o cargar sus propios paquetes.

  Todos los canales que ve actualmente han sido recuperados por SMLM de las fuentes oficiales y pueden mantenerse sincronizados fácilmente.

  En `Package Search` somos capaces de buscar paquetes específicos e inspeccionar su contenido y metadatos.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_software.gif"/>
  </div>

<br/>

- **Configuration** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_configuration.png"/>

  También es posible gestionar y aplicar configuraciones específicas a los sistemas, al momento del registro o posteriormente; para ello podemos inspeccionar la sección `Configuration`.

  SMLM proporciona una manera fácil de gestionar revisiones, desplegar y comparar archivos de configuración entre sistemas. Y todo puede agruparse fácilmente en canales de configuración.

  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/introduction_configuration.gif"/>
  </div>

<br/>

- **Scheduling** <img class="bottoms" src="../assets/SMLM5.1/left_column_-_schedule.png"/>

  En `Schedule` podemos observar y gestionar acciones programadas, definir ventanas de mantenimiento específicas. Esto es especialmente útil para automatizar operaciones regulares o realizar despliegues "canary" (canarios) cuando se gestionan muchos sistemas. Veremos esto en acción más adelante durante el taller.

<br/>
<br/>

SUSE Multi-Linux Manager ofrece muchas posibilidades para gestionar sus sistemas, no podemos cubrirlas todas en este taller pero, como siempre, siéntase libre de hacer preguntas y explorar.

> [!NOTE]
> Su usuario tiene privilegios completos de administrador, por lo que recomendamos realizar cambios solo después de haber terminado los ejercicios.
