---
slug: smls-extended-support
id: jvmvyogygp8z
type: challenge
title: Soporte extendido para sistemas legacy
tabs:
- id: hqtojer6yykw
  title: SMLM UI
  type: browser
  hostname: smlm-www
- id: phwtdcjwflq0
  title: CentOS 7 QA
  type: terminal
  hostname: centos7
- id: 3ny9jkdxvs0i
  title: CentOS 7 Prod
  type: terminal
  hostname: zzcentos7
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Soporte extendido para sistemas legacy
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

# Extendiendo la vida útil de nuestra flota heredada

En cualquier aerolínea, tienes aviones más antiguos y fiables que te han servido durante años pero para los cuales aún no tienes reemplazo. Para nosotros, una parte de esa flota heredada son nuestros sistemas CentOS 7. Son estables pero están al final de su vida útil (end-of-life), lo que significa que ya no reciben actualizaciones de seguridad críticas de su fabricante original. Para una aerolínea, volar sin soporte es un riesgo que simplemente no podemos correr.

La solución tradicional sería un reemplazo completo y costoso de cada uno de ellos.
Pero, ¿y si pudiéramos realizar una actualización de extensión de vida, modernizándolos in situ con una interrupción mínima? Esa es precisamente la misión de este desafío. Usaremos el poder de <b class="smlmext">SUSE Multi-Linux Manager</b> junto con <b class="smlsext">SUSE Multi-Linux Support</b> para realizar una transición segura de estos sistemas y mantenerlos en servicio hasta que podamos reemplazarlos con un sistema operativo más moderno.



## <b class="hovereffect">Nuestro plan de vuelo:</b>

- Examinar los sistemas legacy actuales que ejecutan Centos 7

- Incorporar (Onboard) el sistema de QA y aplicar los parches disponibles

- Identificar y aplicar actualizaciones si las hay.

- Liberar el sistema con la fórmula liberate.

- Observar qué ha cambiado entre ambos sistemas

- Identificar si esto es una migración.

<br/>

## <b class="hovereffect">Nuestros aviones</b>

- CentOS 7 QA ✈ Nuestro servidor de prueba y desarrollo.

- CentOS 7 Prod ✈ Nuestro servidor de producción ya registrado en <b class="smlm">SMLM</b>

<br/><br/>


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



Incorporación de Centos 7 QA (Onboarding Centos 7 QA)
======================



## <b class="hovereffect">Examinando los sistemas legacy</b>

Acceda a la terminal del sistema desde la pestaña [button label="Centos 7 QA" variant="success"](tab-1)

Verifique la versión actual del sistema:

```bash,run
rpm -qi centos-release centos-logos
```


Ahora ejecute el siguiente comando para registrar el sistema en <b class="smlm">SMLM</b>:


```bash,run
curl -Sks "smlm.${_SANDBOX_ID}.instruqt.io"/pub/bootstrap/generic_bootstrap.sh | SMLM_DNS="smlm.${_SANDBOX_ID}.instruqt.io" ACTIVATION_KEYS=1-liberty7ltss PROFILENAME='airco-dh4a-qa' bash ; echo "Let's wait 2 minutes for all the background processes to finish"; sleep 120
```


Esto es similar al que usamos para incorporar Ubuntu en el laboratorio anterior, lo que cambia es:

- **Activation key** (Clave de activación): Es una referencia a la configuración que se aplicará al sistema por defecto, en este caso ha sido creada para indicar solo a qué canales de software se registrará el sistema.

- **Profile name** (Nombre de perfil): Si no lo especificamos usará el nombre de host (hostname), pero en este caso queremos que tenga un nombre más significativo con la misma convención de nomenclatura que usamos con Centos 7 Prod.


**Opcional:** Si tenemos curiosidad y queremos ver qué sucede cuando actualizamos y ejecutamos la fórmula Liberate, podemos ejecutar el siguiente comando en ambos sistemas ( [button label="Centos 7 QA" variant="success"](tab-1) y [button label="Centos 7 Prod" variant="success"](tab-2) ):


```bash,run
journalctl -f
```

Y ver los registros (logs) apareciendo en las terminales.


<br/><br/>


## <b class="hovereffect">Identificar y aplicar actualizaciones de los repositorios <b class="liberty">Liberty</b></b>

Estos sistemas Centos 7 vienen con los últimos paquetes proporcionados upstream, queremos asegurarnos de que los nuevos errores se corrijan y tener una persona de soporte amigable que nos ayude cuando haya problemas, ahora ya hemos suscrito los sistemas Centos 7 a los repositorios de software proporcionados por SUSE durante el proceso de registro, así que parcheémoslos todos:



Ahora cambiemos a la pestaña [button label="SMLM UI" variant="success"](tab-0)


- Vaya a `Systems` ✈ `System List` en el menú de la izquierda.

- Encuentre su host **airco-dh4a-qa** y haga clic en él.

- Seleccione `Software` ✈ `Packages`

- Haga clic en `Update Packages List`, esto tardará aproximadamente un minuto en completarse

- Seleccione `Software` ✈ `Patches`

- Verá una lista de parches disponibles.

Haga clic en `Select All`, luego en `Apply Patches` en la parte superior derecha y finalmente en `Confirm`. <b class="smlmext">SUSE Multi-Linux Manager</b> ahora programará y realizará el procedimiento de actualización en el sistema CentOS.


> [!NOTE]
> Puede tardar un par de minutos obtener la lista de paquetes antes de que pueda ver la lista de parches que se pueden aplicar al sistema.


Dado que esto puede tardar un poco, veamos qué sucede bajo el capó.
Vaya a la pestaña `Events`, luego a `History`, debería ver una lista de eventos que han sucedido desde que el sistema se registró en <b class="smlm">SMLM</b>, en las primeras filas deberíamos poder encontrar un evento que contenga algo similar a *Combined Patch*.


Si hacemos clic en él podemos ver todos los detalles, siéntase libre de echar un vistazo, de lo contrario espere hasta que el icono esté verde:

![Successfully patched](../assets/SMLM5.1/successfully_updated_system.png)

Acabamos de aplicar parches que corrigen errores a los paquetes existentes, estos paquetes parcheados provienen directamente de SUSE, esto no es una migración.

<br/>

Comparémoslo con el sistema de producción que aún no hemos actualizado.

Por favor vaya a `Software` ✈ `Packages` ✈ `Profiles`

Seleccione el sistema `airco-dh4a-prod`, que es la versión de producción, luego haga clic en:

![Compare](../assets/SMLM5.1/bottom-compare.png)


Podemos ver que la mayoría de las versiones de los paquetes no han cambiado, siguen siendo la misma versión ( **X.X.X**-xyz ) pero con un parche aplicado ( X.X.X-**xyz** ).

Antes de pasar a la siguiente sección, creemos un perfil almacenado, esto nos ayudará a ver las diferencias más claramente después de aplicar la fórmula liberate en la siguiente sección.


Por favor vaya a `Software` ✈ `Packages` ✈ `Profile` y haga clic en `Create System Profile`. Para el nombre puede llamarlo:

```txt
before_liberation
```


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-identify_and_apply_updates.gif"/>
  </div>


<br/><br/>


Liberar el sistema (opcional)
==============================

Este es un paso **opcional** y no se requiere para obtener soporte.

Ahora liberemos el sistema:

- Vaya a la pestaña `Formulas`, busque **Liberate**, y una vez encontrado, selecciónelo y haga clic en `Save` en la parte superior derecha.

Verá un mensaje en azul en la parte superior de la pantalla, desplácese hacia arriba si no puede verlo:

![Formula saved](../assets/SMLM5.1/formula_saved.png)


Haga clic donde dice `Highstate`, será dirigido a otra pestaña (`States` ✈ `Highstate`).

Puede ver en el resumen en la parte inferior que la fórmula liberate está listada.

Para iniciar el proceso de liberación, haga clic en:

![Formula saved](../assets/SMLM5.1/bottom-apply_highstates.png)

Esto tomará algún tiempo, por favor verifique `Events` -> `History`, debería ver un evento llamado **Apply highstate scheduled**

Esperemos un par de minutos para que termine, mientras tanto puede observar lo que está sucediendo mirando la terminal [button label="Centos 7 QA" variant="success"](tab-1).


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-liberate.gif"/>
  </div>

<br/><br/>

## <b class="hovereffect">Observar qué ha cambiado</b>


Una vez completado, comparemos el sistema nuevamente para ver la diferencia, si aún no estamos allí, hagamos clic en el nombre del sistema `airco-dh4a-qa`.

Luego vaya a `Software` ✈ `Packages` ✈ `Profile`

Bajo **Compare to Stored Profile** haga clic en: ![Compare](../assets/SMLM5.1/bottom-compare.png)

Podemos ver que lo único que ha cambiado son los siguientes paquetes:

- **centos-logos**, reemplazado por **sles_es-logos**

- **centos-release**, reemplazado por **sles_es-release-server**

El resto permanece igual pero ahora tiene todo el soporte, actualizaciones y parches proporcionados por <b class="suse">SUSE</b> para <b class="liberty">Liberty Linux</b>.

Lo mismo se aplica a versiones más modernas de CentOS y RHEL, puede transformarlas a <b class="liberty">Liberty</b> y tenerlas soportadas por <b class="suse">SUSE</b> sin tener que realizar ningún cambio en el software y las bibliotecas reales.



  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/03-extended_support-what_changed.gif"/>
  </div>

<br/>



Liberar el servidor de producción (opcional)
=========================================

Hemos visto cómo parchear y Liberar nuestro antiguo servidor Centos 7 en QA, ahora es el momento de hacer lo mismo con el sistema de producción, pero esta vez lo haremos en un orden diferente.

- Primero, aplicaremos la fórmula **Liberate**

  Vayamos a nuestro servidor de producción `airco-dh4a-prod` y `Create System Profile`

  Después apliquemos la fórmula **Liberate** como lo hicimos con el sistema QA.

- Una vez completado, comparemos el sistema con el perfil que acabamos de crear, como podemos ver, el único cambio ha sido los paquetes **centos-logos** y **centos-release**, el resto permanece exactamente igual.


¿Es una migración?
==================

Una migración implica construir un servidor completamente nuevo, reinstalar todas las aplicaciones desde cero y mover cuidadosamente los datos, un proceso que consume tiempo, es costoso y está lleno de riesgos.

Lo que hicimos fue mucho más elegante. Realizamos una actualización in situ (in-place upgrade).

La identidad del servidor, el nombre de host, las aplicaciones y los datos del usuario permanecieron completamente intactos. Simplemente cambiamos su fuente subyacente para actualizaciones, y esos componentes al final de su vida útil ahora son componentes totalmente soportados que reciben parches.

Hemos extendido con éxito la vida de nuestro sistema, lo hemos devuelto al cumplimiento de seguridad y lo hicimos todo sin la interrupción de una migración completa. Esa es la eficiencia que mantiene a [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] volando alto.




¿Por qué es importante para [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================

- Permite a [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]] mantener sus sistemas en ejecución con soporte, otorgándoles tiempo para migrar dependiendo de sus necesidades comerciales en lugar de las necesidades del proveedor.

- Mitiga el riesgo que implica tener sistemas sin soporte ofreciendo soporte extendido. Este enfoque evita la necesidad de una migración inmediata, todo funciona como de costumbre pero ahora hay un grupo de expertos que pueden responder a sus llamadas.

- Le da la libertad de cambiar de proveedor de soporte sin pasar por migraciones largas, y le permite hacerlo a escala.



Más información
================

- [Registrando RHEL 7 o CentOS Linux 7 con SUSE Manager](https://documentation.suse.com/liberty/7/html/suma-quickstart/art-suma-quickstart.html)
- [Ejecutando escaneos de cumplimiento OpenSCAP para SUSE Multi-Linux Support 7](https://documentation.suse.com/liberty/7/html/compliance-scans/art-compliance-scans.html)
- [Registrando CentOS Linux 7 con el SUSE Customer Center](https://documentation.suse.com/liberty/7/html/quickstart-scc/art-quickstart-scc.html)
- [SUSE Multi-Linux Support 9](https://documentation.suse.com/liberty/9/)