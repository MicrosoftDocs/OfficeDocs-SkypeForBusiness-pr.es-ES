---
title: 'Lync Server 2013: instalación del portal web administrativo del sistema Lync Room'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54b772311865a36ba17699fc876c32c5504214e5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534907"
---
# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Instalación del portal web administrativo del sistema Lync Room en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-04-09_

Puede descargar el portal web administrativo del sistema Microsoft Lync Room del centro de descarga de Microsoft en [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044) .

Para instalar el portal web administrativo del sistema Lync Room, siga estos pasos.

1.  Configure el puerto de aplicación de confianza mediante la ejecución del siguiente cmdlet en el shell de administración de Lync Server:
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  Para instalar el portal de la sala de reuniones, descargue **LyncRoomAdminPortal.exe** y ejecútelo como administrador.

3.  Abra el archivo de Web.config desde la siguiente ubicación:
    
    % Program Files% \\ Microsoft Lync Server 2013 \\ Web Components portal de la \\ sala de reuniones \\ \\ controlador int\\

4.  En el archivo de Web.Config, cambie PortalUserName por el nombre de usuario creado en el paso 2 en la sección "configuración de requisitos previos para Lync Room System admin portal" (el nombre recomendado en el paso es LRSApp):
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  Dado que el portal de administración LRS es una aplicación de confianza, no es necesario proporcionar la contraseña en la configuración del portal. Si este usuario usa un registrador diferente que el registrador local, debe especificar el registrador para él agregando la siguiente línea en el archivo Web.Config:
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  Si el puerto usado es distinto de 5061, agregue la siguiente línea en el archivo Web.Config:
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a>Comprobación de la instalación del portal web administrativo del sistema Lync Room

Para comprobar la instalación del portal web administrativo del sistema Lync Room, haga lo siguiente:


1.  En un servidor front-end, vaya a la siguiente dirección URL:
    
    https:// \<fe-server\> /LRS
    
    No debería ver ningún error, como se muestra en la siguiente imagen:
    
    ![Pantalla de inicio de sesión del portal de administración del sistema Lync Room](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Pantalla de inicio de sesión del portal de administración del sistema Lync Room")

2.  Si no ve ningún error, intente acceder a la siguiente dirección URL desde cualquier otro equipo de la topología:
    
    https:// \<fe-server\> /LRS
    
    Para obtener acceso a la página, deberá agregar los registros DNS como se describe en la sección "registros DNS necesarios para el inicio de sesión automático de cliente" en [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

