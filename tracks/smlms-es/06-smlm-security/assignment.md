---
slug: smlm-security
id: 4idwkrfipylc
type: challenge
title: Seguridad y parches
tabs:
- id: 4mntvmce5pza
  title: SMLM UI
  type: browser
  hostname: smlm-www
difficulty: basic
timelimit: 6000
enhanced_loading: null
---

🌌 Seguridad y parches
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



En este laboratorio, abordaremos una de las responsabilidades más importantes que tenemos: garantizar la seguridad de toda nuestra flota digital. Exploraremos cómo <b class="smlmext">SUSE Multi-Linux Manager</b> nos permite responder a las amenazas de seguridad con la velocidad y precisión requeridas por una aerolínea de clase mundial.




## <b class="hovereffect">Sus Objetivos:</b>

- Realizar una auditoría de cumplimiento de seguridad en sus sistemas utilizando OpenSCAP.

- Identificar los sistemas afectados por vulnerabilidades de seguridad relevantes.

- Aplicar los parches necesarios a todos los sistemas afectados simultáneamente.



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




Audite sus sistemas
==================

Queremos auditar nuestros sistemas de producción para asegurarnos de que cumplen con las normas.

Ya hemos verificado que los siguientes paquetes están instalados:

- openscap-utils
- scap-security-guide


Seleccione el grupo de producción

- Vayamos a `Systems` ✈ `System Groups`
- Encuentre el grupo **prod** y haga clic en `Use in SSM`
![Next](../assets/SMLM5.1/prod_group_selection.png)

Seremos dirigidos a la página **System Set Manager Overview**, como vimos anteriormente, desde aquí podemos aplicar acciones a múltiples sistemas a la vez.

- Vaya a la pestaña `Audit`
- Bajo `OpenSCAP` complete el formulario con los siguientes detalles, deje el resto con los valores predeterminados:
  - **Command-line Arguments:** <b class="highlightcopy">--profile xccdf_org.ssgproject.content_profile_stig</b>
  - **Path to XCCDF document:** <b class="highlightcopy">/usr/share/xml/scap/ssg/content/ssg-sle15-ds.xml</b>
- Presione


<p style="margin: 1px; padding: 1px; vertical-align: middle; display:inline-block; align:left;">
</p>
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:left;">
<img style="margin: 1px; padding: 1px; vertical-align: middle; display:block; align:left;" src="../assets/SMLM5.1/bottom-Schedule.png"/>
</p> ✈
<p style="margin: 1px; padding: 1px;vertical-align: middle; display:inline-block; align:center;">
<img style="margin: 1px; padding: 1px;vertical-align: middle; display:block; align:center;" src="../assets/SMLM5.1/bottom-confirm.png"/>
</p>



Esto tomará un par de minutos.


Para ver los resultados, vayamos a `Audit` ✈ `OpenSCAP` ✈ `All Scans`

![OpenSCAP Results](../assets/SMLM5.1/openscap_results.png)

Si hacemos clic en uno de estos resultados, podemos ver un desglose más detallado.

- Al hacer clic en **report.html**, puede ver una versión más agradable del informe que fue generado por OpenSCAP.

![Detailed OpenSCAP Results](../assets/SMLM5.1/openscap_results_detailed.png)


No se preocupe por los problemas reportados.


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-audit_your_system.gif"/>
  </div>

<br/>



Identificar sistemas afectados por vulnerabilidades
============================================

Queremos ver qué sistemas están afectados por vulnerabilidades.

- Ahora, naveguemos a `Patches` ✈ `Patch List` ✈ `Relevant`

  Aquí podemos ver una lista de todos los parches relevantes disponibles para nuestros sistemas, miremos los **Security Patches** (Parches de Seguridad).

- Al hacer clic en el nombre de un **Advisory** (Aviso), puede ver una página detallada que muestra qué paquetes y sistemas afecta, entre otros detalles.

- En el lado derecho de la lista, la columna **CVEs** proporciona enlaces directos a los informes oficiales de vulnerabilidad.

  También es posible crear nuestros propios parches, pero no cubriremos eso en esta sección, para más información por favor consulte los enlaces al final.



## <b class="hovereffect">Parchear sistemas afectados</b>

Parchear nuestros sistemas es tan simple como seguir estos pasos:

- Vaya a `Systems` ✈ `System Set Manager`
- Navegue a la pestaña `Patches` ✈ seleccione **Security Advisory** en la lista desplegable, y haga clic en `Show`

![Select Security Advisory](../assets/SMLM5.1/show_only_security_advisories.png)

- Haga clic en `Select All` ✈ `Apply Patches` ✈ ![Confirm](../assets/SMLM5.1/bottom-confirm.png)


  <div style='align: middle; margin: 15px;'>
    <img class="animatedgif" src="../assets/SMLM5.1/videos/06-security_and_patching-indentify_vulnerabilities.gif"/>
  </div>

<br/>


¿Por qué es importante para [[ Instruqt-Var key="COMPANY_NAME" hostname="zbastion" ]]?
=================================================================================


- Al ser capaces de actuar rápido, estamos reduciendo la ventana de exposición. Cuando se descubre una nueva vulnerabilidad, comienza una carrera entre nosotros y los actores maliciosos que intentan explotarla. Un proceso de parcheo complejo y manual deja nuestros sistemas críticos expuestos durante demasiado tiempo.

- <b class="smlmext">SUSE Multi-Linux Manager</b> proporciona una vista única y unificada de la postura de seguridad de toda nuestra flota y nos permite remediar amenazas con un proceso consistente y confiable.

- Ser capaces de verificar fácilmente el cumplimiento de nuestros sistemas con diferentes marcos de seguridad nos permite implementar medidas correctivas más rápido y adherirnos a regulaciones estrictas de la industria.


Más información
================


* [Auditoría](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/auditing.html)
* [Seguridad de SUSE](https://www.suse.com/support/security/)
* [Seguridad del Sistema con OpenSCAP](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/openscap.html)
* [Gestionar Parches](https://documentation.suse.com/multi-linux-manager/5.1/en/docs/administration/patch-management.html)