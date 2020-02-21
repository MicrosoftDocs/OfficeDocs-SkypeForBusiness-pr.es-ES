---
title: 'Lync Server 2013: requisitos previos para la integración con Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3ea70be8c4d431b6231b1cf8e8dc252581643b6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Requisitos previos para integrar Microsoft Lync Server 2013 y Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-04-22_

Para poder integrar Microsoft Lync Server 2013 y Microsoft Exchange Server 2013, debe asegurarse de que se han completado todos los pasos de requisitos previos. Como cabría esperar, la integración no puede llevarse a cabo hasta que Exchange 2013 y Lync Server 2013 estén completamente instalados y en funcionamiento. Para más información sobre la instalación de Exchange, consulte la documentación de planeación [https://go.microsoft.com/fwlink/p/?LinkId=268539](https://go.microsoft.com/fwlink/p/?linkid=268539)e implementación de Exchange 2013 en. Para obtener más información sobre la instalación de Lync Server 2013, consulte la documentación [https://go.microsoft.com/fwlink/p/?LinkId=254806](https://go.microsoft.com/fwlink/p/?linkid=254806)de planeación e implementación en.

Una vez que los servidores estén en funcionamiento, debe asignar certificados de autenticación de servidor a servidor tanto en Lync Server 2013 como en Exchange 2013; Estos certificados permiten que Lync Server y Exchange puedan intercambiar información y comunicarse entre sí. Al instalar Exchange 2013, se creará automáticamente un certificado autofirmado con el nombre certificado de autenticación de Microsoft Exchange Server. Este certificado, que puede encontrarse en el almacén de certificados del equipo local, debe usarse para la autenticación de servidor a servidor en Exchange 2013. Para obtener más información acerca de la asignación de certificados en Exchange 2013, consulte "configurar el flujo de correo [https://go.microsoft.com/fwlink/p/?LinkId=268540](https://go.microsoft.com/fwlink/p/?linkid=268540)y el acceso de cliente" en.

Para Lync Server 2013 puede usar un certificado de Lync Server existente como certificado de autenticación de servidor a servidor; por ejemplo, el certificado predeterminado también puede usarse como certificado OAuthTokenIssuer. Lync Server 2013 permite usar cualquier certificado de servidor web como certificado para la autenticación de servidor a servidor, siempre que:

  - El certificado incluya el nombre del dominio SIP en el campo Asunto.

  - Ese mismo certificado se haya configurado como certificado OAuthTokenIssuer en todos los servidores front-end.

  - El certificado tenga una longitud de al menos 2048 bits.

Para obtener más información acerca de los certificados de autenticación de servidor a servidor para Microsoft Lync Server 2013, consulte [asignar un certificado de autenticación de servidor a servidor a Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).

Después de que se hayan asignado los certificados, debe configurar el servicio Detección automática en Exchange 2013. En Exchange 2013, el servicio de detección automática configura perfiles de usuario y proporciona acceso a los servicios de Exchange cuando los usuarios inician sesión en el sistema. Los usuarios presentan el servicio de detección automática con su dirección de correo electrónico y contraseña; a su vez, los servicios proporcionan al usuario información como la siguiente:

  - Información de conexión para la conectividad interna y externa a Exchange 2013.

  - La ubicación del servidor de Buzón de correo del usuario.

  - Direcciones URL de las características de Outlook como información de libre u ocupado, Mensajería unificada y la libreta de direcciones sin conexión.

  - Configuración del servidor Outlook Anywhere.

El servicio Detección automática debe estar configurado para poder integrar Lync Server 2013 y Exchange 2013. Para comprobar si el servicio de detección automática se ha configurado o no, ejecute el siguiente comando desde el shell de administración de Exchange y compruebe el valor de la propiedad AutoDiscoverServiceInternalUri:

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

Si este valor está en blanco, deberá asignar un URI al servicio de detección automática. Por lo general, este URI será similar al siguiente:

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

Puede asignar el URI de detección automática ejecutando un comando similar al siguiente:

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

Para obtener más información sobre el servicio de detección automática, consulte "Descripción del servicio detección [https://go.microsoft.com/fwlink/p/?LinkId=268542](https://go.microsoft.com/fwlink/p/?linkid=268542)automática" en.

Una vez configurado el servicio de detección automática, debe modificar las opciones de configuración de OAuth de Lync Server; Esto garantiza que Lync Server sepa dónde encontrar el servicio Detección automática. Para modificar las opciones de configuración de OAuth en Lync Server 2013, ejecute el siguiente comando desde el shell de administración de Lync Server. Al ejecutar este comando, asegúrese de especificar el URI para el servicio de detección automática que se está ejecutando en el servidor de Exchange y de que usa **Autodiscover. SVC** para apuntar a la ubicación del servicio en lugar de **Autodiscover. XML** (que apunta al archivo XML usado por el servicio):

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> El parámetro Identity en el comando anterior es opcional; Esto se debe a que Lync Server solo permite tener una única colección global de opciones de configuración de OAuth. Entre otras cosas, esto significa que puede configurar la dirección URL del servicio de detección automática usando este comando un poco más simple:<BR>Set-CsOAuthConfiguration – ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"<BR>Si no conoce bien esta tecnología, OAuth es un protocolo de autorización estándar que usan muchos de los principales sitios web. Con OAuth, las credenciales y las contraseñas de usuario no se pasan de un equipo a otro. En lugar de eso, la autenticación y la autorización se basan en el intercambio de tokens de seguridad. Estos tokens conceden acceso a un conjunto concreto de recursos durante un período de tiempo concreto.



</div>

Además de configurar el servicio Detección automática, también debe crear un registro DNS para el servicio que apunta al servidor Exchange. Por ejemplo, si el servicio de detección automática está ubicado en autodiscover.litwareinc.com, deberá crear un registro DNS para autodiscover.litwareinc.com que se resuelva en el nombre de dominio completo del servidor Exchange (por ejemplo, atl-exchange-001.litwareinc.com).

</div>

<span> </span>

</div>

</div>

</div>

