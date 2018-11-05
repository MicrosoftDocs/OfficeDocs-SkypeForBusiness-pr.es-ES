---
title: Solución de problemas del Panel de control de Lync Server 2013
TOCTitle: Solución de problemas del Panel de control de Lync Server 2013
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48275292
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Solución de problemas del Panel de control de Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Este tema proporciona información y procedimientos que le pueden ayudar a solucionar problemas de acceso a Panel de control de Lync Server 2013.

## Requisitos del explorador de Internet

Panel de control de Lync Server necesita que esté instalada la versión 4.0.50524.0 o la versión más reciente de Complemento de explorador Microsoft Silverlight. Si Silverlight no está instalada o si está instalada una versión anterior, siga las instrucciones del mensaje para instalar la versión necesaria.


> [!NOTE]
> Otros requisitos de software de Panel de control de Lync Server corresponden al sistema operativo en el que se pueden instalar Panel de control de Lync Server y todas las demás herramientas administrativas de Lync Server 2013. Para más información, consulte <A href="lync-server-2013-server-and-tools-operating-system-support.md">Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013</A> en la documentación de compatibilidad.



Si su explorador de Internet bloquea la instalación de Silverlight por razones de seguridad, agregue el localizador uniforme de recursos (URL) que abre Panel de control de Lync Server a la lista de sitios de confianza. En la configuración de seguridad de Internet Explorer, asegúrese de que **Ejecutar controles y complementos de ActiveX** esté **Habilitado**. Para información, vea [http://go.microsoft.com/fwlink/?linkid=214060\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=214060%26clcid=0xc0a). Además, asegúrese de que el explorador esté configurado para usar SSL 3.0.

Si el explorador de Internet está configurado para usar un servidor proxy, compruebe que el explorador esté configurado para omitir el servidor proxy en sitios detectados automáticamente como sitios internos. También puede agregar la dirección a la lista de excepciones del explorador en los valores de configuración del servidor proxy.

## Requisitos de certificado y registro DNS para la dirección URL de acceso administrativo

Si configuró una sola URL para obtener acceso a Panel de control de Lync Server, asegúrese de haber configurado también el certificado y el registro de recursos de host (A) de sistema de nombres de dominio (DNS) estático necesarios para usar esa dirección URL de acceso administrativo. Si cambia la URL base en cualquier momento, asegúrese de que el cambio se refleje en el certificado y registro DNS correspondientes y de ejecutar *Enable-CsComputer* en cada Director y Servidor front-end para registrar el cambio. Para más información, vea los siguientes temas en la documentación de planificación:

  - [Planeación de las direcciones URL simples en Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

  - [Requisitos de DNS para direcciones URL simples en Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Requisitos de certificado para Servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

Para consultar paso a paso los procedimientos de configuración de la dirección URL de acceso administrativo, consulte [Editar o configurar direcciones URL sencillas en Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) en la documentación de implementación.


> [!NOTE]
> Si tiene más de un adaptador de red en el servidor web, debe configurar el DNS manualmente para cada adaptador de red adicional con el fin de que la resolución DNS funcione correctamente.



## Requisitos de Internet Information Services (IIS)

Panel de control de Lync Server es uno de los componentes de Lync Server 2013 que necesita Servicios de Internet Information Server (IIS). En concreto, asegúrese de que estén habilitadas las características de autenticación de Windows y de redirección HTTP, y de que se esté ejecutando el servicio de publicación World Wide Web (W3SVC).

## Dependencia del servicio de publicación World Wide (servicio de Windows)

Cuando se detiene el servicio de publicación World Wide Web, no puede obtener acceso a Panel de control de Lync Server. Puede reiniciar el servicio usando Windows Services Microsoft Management Console (MMC).

**Para iniciar el servicio de publicación World Wide Web**

1.  Inicie sesión en el equipo en el que está instalado el servicio de publicación World Wide Web como parte de Servicios de Internet Information Server (IIS).

2.  Haga clic en **Inicio**, haga clic en **Herramientas administrativas** y, a continuación, haga clic en **Servicios**.

3.  Haga clic con el botón secundario del mouse en **Servicio de publicación World Wide Web** y, a continuación, haga clic en **Inicio**.

## Modo Grupo de aplicaciones

Configure IIS de modo que el grupo de aplicaciones CsManagementAppPool use la cuenta del servicio de red como identidad de modelo de proceso.

## Permisos y derechos de usuario

Debe iniciar sesión en Panel de control de Lync Server usando una cuenta de dominio que pertenezca al grupo CsAdministrator o usando una cuenta a la que haya delegado permisos y derechos de usuario. No puede iniciar sesión en Panel de control de Lync Server usando una cuenta del equipo local. Para más información sobre cómo delegar tareas administrativas a través del control de acceso basado en roles (RBAC), consulte [Planeación del control de acceso basado en roles en Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) en la documentación de planeación.

Si usa una sola URL para obtener acceso al Panel de control de Lync Server, asegúrese de agregar servidores web a los grupos RTCUniversalServerAdmins y RTCUniversalUserAdmins.

## Vea también

#### Conceptos

[Herramientas administrativas de Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)

