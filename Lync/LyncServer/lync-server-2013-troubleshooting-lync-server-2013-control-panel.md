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
ms.openlocfilehash: ff82a1e63a064d0053fc77614d6a9b5fa818c23e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a>Solución de problemas del panel de control de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-07-28_

Este tema proporciona información y procedimientos que pueden ayudarle a solucionar problemas de acceso al panel de control de Lync Server 2013.

<div>

## <a name="internet-browser-requirements"></a>Requisitos del explorador de Internet

El panel de control de Lync Server requiere que se haya instalado la versión 4.0.50524.0 o la versión más reciente del complemento de Microsoft Silverlight. Si Silverlight no está instalado o si se ha instalado una versión anterior, siga las instrucciones del mensaje para instalar la versión requerida.

<div>


> [!NOTE]  
> Otros requisitos de software para Lync Server panel de control pertenecen al sistema operativo en el que se pueden instalar el panel de control de Lync Server y todas las demás herramientas administrativas de Lync Server 2013. Para obtener más información, vea <A href="lync-server-2013-server-and-tools-operating-system-support.md">compatibilidad del sistema operativo servidor y herramientas de Lync Server 2013</A> en la documentación de soporte técnico.



</div>

Si su explorador de Internet bloquea la instalación de Silverlight debido a consideraciones de seguridad, agregue el localizador de recursos uniforme (URL) que abre el panel de control de Lync Server a la lista de sitios de confianza. En la configuración de seguridad de Internet Explorer, asegúrese de que **la opción ejecutar controles y complementos de ActiveX** esté establecida en **habilitado**. Para obtener más información [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060), consulte. Además, asegúrese de que el explorador esté configurado para usar SSL 3,0.

Si el explorador de Internet está configurado para usar un servidor proxy, compruebe que el explorador esté configurado para omitir el servidor proxy para los sitios que se detectan automáticamente como sitios internos. O bien, agregue la dirección a la lista de excepciones del explorador en los valores de configuración del servidor proxy.

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>Requisitos de registro DNS y certificado para la dirección URL de acceso administrativo

Si ha configurado una dirección URL sencilla para obtener acceso al panel de control de Lync Server, asegúrese de haber configurado también el registro de recursos (A) del sistema de nombres de dominio (DNS) estático y el certificado necesario para usar esa dirección URL de acceso administrativo. Si cambia la dirección URL base en cualquier momento, asegúrese de que el cambio se refleja en el registro DNS y el certificado apropiados, y de que ejecuta la opción *enable-CsComputer* en cada director y en el servidor front-end para registrar el cambio. Para obtener más información, vea los siguientes temas en la documentación de planificación:

  - [Planeación de las direcciones URL simples en Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)

  - [Requisitos de DNS para direcciones URL simples en Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Requisitos de certificado para Servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

Para obtener los procedimientos paso a paso para configurar la dirección URL de acceso administrativo, vea [Editar o configurar direcciones URL simples en Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) en la documentación de implementación.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Requisitos de servicios de Internet Information Server (IIS)

El panel de control de Lync Server es uno de los componentes de Lync Server 2013 que requiere Internet Information Services (IIS). En particular, asegúrese de que las características de autenticación HTTP y autenticación de Windows estén habilitadas y que el servicio de publicación World Wide Web (W3SVC) se esté ejecutando.

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>Dependencia del servicio de publicación internacional (servicio de Windows)

Si el servicio de publicación World Wide Web se detiene, no puede obtener acceso al panel de control de Lync Server. Puede reiniciar el servicio mediante Microsoft Management Console (MMC) de servicios de Windows.

**Para iniciar el servicio de publicación World Wide Web**

1.  Inicie sesión en el equipo donde está instalado el servicio de publicación World Wide Web como parte de servicios de Internet Information Server (IIS).

2.  Haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **servicios**.

3.  Haga clic con el botón secundario en **servicio de publicación World Wide Web**y, a continuación, haga clic en **iniciar**.

</div>

<div>

## <a name="application-pool-mode"></a>Modo de grupo de aplicaciones

Configure IIS para que el grupo de aplicaciones de CsManagementAppPool use la cuenta de servicio de red como su identidad de modelo de proceso.

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>Derechos y permisos de usuario

Debe iniciar sesión en el panel de control de Lync Server usando una cuenta de dominio que sea miembro del grupo CsAdministrator o usando una cuenta a la que haya delegado derechos de usuario y permisos. No puede iniciar sesión en el panel de control de Lync Server mediante una cuenta de equipo local. Para obtener más información sobre cómo delegar tareas administrativas mediante el control de acceso basado en roles (RBAC), consulte [planear el control de acceso basado en roles en Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) en la documentación de planeación.

Si usa una dirección URL sencilla para obtener acceso al panel de control de Lync Server, asegúrese de que los servidores Web se agregan a los grupos RTCUniversalServerAdmins y RTCUniversalUserAdmins.

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

