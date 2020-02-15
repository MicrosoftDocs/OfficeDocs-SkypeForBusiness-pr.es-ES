---
title: 'Lync Server 2013: solución de problemas del panel de control de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87ad05798dab0f324a44a4c41807e8acb6105927
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a>Solución de problemas del Panel de control de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-07-28_

En este tema se proporciona información y procedimientos que pueden ayudarle a solucionar problemas de acceso al panel de control de Lync Server 2013.

<div>

## <a name="internet-browser-requirements"></a>Requisitos del explorador de Internet

El panel de control de Lync Server requiere que esté instalada la versión 4.0.50524.0 o la versión más reciente del complemento del explorador Microsoft Silverlight. Si Silverlight no está instalado o si se ha instalado una versión anterior, siga las instrucciones del mensaje para instalar la versión requerida.

<div>


> [!NOTE]  
> Otros requisitos de software para el panel de control de Lync Server pertenecen al sistema operativo en el que se pueden instalar el panel de control de Lync Server y todas las demás herramientas administrativas de Lync Server 2013. Para obtener más información, consulte <A href="lync-server-2013-server-and-tools-operating-system-support.md">compatibilidad con sistemas operativos de servidor y herramientas en Lync Server 2013</A> en la documentación sobre compatibilidad.



</div>

Si su explorador de Internet bloquea la instalación de Silverlight por motivos de seguridad, agregue el localizador uniforme de recursos (URL) que abre el panel de control de Lync Server a la lista de sitios de confianza. En la configuración de seguridad de Internet Explorer, asegúrese de que **Ejecutar controles y complementos de ActiveX** esté **Habilitado**. Para obtener más información [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060), consulte. Además, asegúrese de que el explorador esté configurado para usar SSL 3.0.

Si el explorador de Internet está configurado para usar un servidor proxy, compruebe que el explorador esté configurado para omitir el servidor proxy en sitios detectados automáticamente como sitios internos. También puede agregar la dirección a la lista de excepciones del explorador en los valores de configuración del servidor proxy.

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>Requisitos de certificado y registro DNS para la dirección URL de acceso administrativo

Si configuró una dirección URL sencilla para acceder al panel de control de Lync Server, asegúrese de que también configuró el registro de recursos de host (A) del sistema de nombres de dominio (DNS) estático y el certificado necesario para usar esa dirección URL de acceso administrativo. Si cambia la dirección URL base en cualquier momento, asegúrese de que el cambio se refleja en el registro DNS y el certificado adecuados, y que ejecuta el *-CsComputer* en cada director y en el servidor front-end para registrar el cambio. Para obtener más información, consulte los siguientes temas en la documentación de planeación:

  - [Planeación de direcciones URL sencillas en Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

  - [Requisitos de DNS para direcciones URL sencillas en Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Requisitos de certificado para servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

Para conocer los procedimientos paso a paso para configurar la dirección URL de acceso administrativo, consulte [Editar o configurar direcciones URL sencillas en Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) en la documentación sobre implementación.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Requisitos de Internet Information Services (IIS)

El panel de control de Lync Server es uno de los componentes de Lync Server 2013 que requiere Internet Information Services (IIS). En concreto, asegúrese de que estén habilitadas las características de autenticación de Windows y de redirección HTTP, y de que se esté ejecutando el servicio de publicación World Wide Web (W3SVC).

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>Dependencia del servicio de publicación World Wide (servicio de Windows)

Cuando se detiene el servicio de publicación World Wide Web, no se puede tener acceso al panel de control de Lync Server. Puede reiniciar el servicio usando Windows Services Microsoft Management Console (MMC).

**Para iniciar el servicio de publicación World Wide Web**

1.  Inicie sesión en el equipo donde está instalado el servicio de publicación World Wide Web como parte de Internet Information Services (IIS).

2.  Haga clic en **Inicio**, haga clic en **Herramientas administrativas** y, a continuación, haga clic en **Servicios**.

3.  Haga clic con el botón secundario del mouse en **Servicio de publicación World Wide Web** y, a continuación, haga clic en **Inicio**.

</div>

<div>

## <a name="application-pool-mode"></a>Modo Grupo de aplicaciones

Configure IIS de modo que el grupo de aplicaciones CsManagementAppPool use la cuenta del servicio de red como identidad de modelo de proceso.

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>Permisos y derechos de usuario

Debe iniciar sesión en el panel de control de Lync Server con una cuenta de dominio que sea miembro del grupo CsAdministrator o con una cuenta a la que haya delegado derechos y permisos de usuario. No puede iniciar sesión en el panel de control de Lync Server con una cuenta de equipo local. Para obtener más información sobre cómo delegar tareas administrativas mediante el control de acceso basado en roles (RBAC), consulte [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) en la documentación referente a la planeación.

Si usa una dirección URL sencilla para acceder al panel de control de Lync Server, asegúrese de que los servidores Web se agregan a los grupos RTCUniversalServerAdmins y RTCUniversalUserAdmins.

</div>

<div>

## <a name="see-also"></a>Vea también


[Herramientas administrativas de Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

