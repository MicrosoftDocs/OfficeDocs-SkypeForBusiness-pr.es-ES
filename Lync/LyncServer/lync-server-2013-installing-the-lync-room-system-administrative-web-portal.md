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
ms.openlocfilehash: 24757a87279f64dd903ed4fdfb26169b606f899c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Instalación del portal web administrativo del sistema Lync Room en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-04-09_

Puede descargar el portal web administrativo del sistema Microsoft Lync Room del centro de descarga de Microsoft [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044)en.

Para instalar el portal web administrativo del sistema Lync Room, siga estos pasos.

1.  Configure el puerto de aplicación de confianza mediante la ejecución del siguiente cmdlet en el shell de administración de Lync Server:
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  Para instalar el portal de la sala de reuniones, descargue **LyncRoomAdminPortal. exe** y, a continuación, ejecútelo como administrador.

3.  Abra el archivo Web. config desde la siguiente ubicación:
    
    % Program Files\\% Microsoft Lync Server\\2013 Web\\Components portal\\de\\la sala de reuniones controlador int\\

4.  En el archivo Web. config, cambie PortalUserName por el nombre de usuario creado en el paso 2 en la sección "configuración de requisitos previos para Lync Room System admin portal" (el nombre recomendado en el paso es LRSApp):
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  Dado que el portal de administración LRS es una aplicación de confianza, no es necesario proporcionar la contraseña en la configuración del portal. Si este usuario usa un registrador diferente que el registrador local, debe especificar el registrador para él agregando la siguiente línea en el archivo Web. config:
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  Si el puerto usado es distinto de 5061, agregue la siguiente línea en el archivo Web. config:
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a>Comprobación de la instalación del portal web administrativo del sistema Lync Room

Para comprobar la instalación del portal web administrativo del sistema Lync Room, haga lo siguiente:


1.  En un servidor front-end, vaya a la siguiente dirección URL:
    
    https://\<fe-servidor\>/LRS
    
    No debería ver ningún error, como se muestra en la siguiente imagen:
    
    ![Pantalla de inicio de sesión del portal de administración del sistema Lync Room](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Pantalla de inicio de sesión del portal de administración del sistema Lync Room")

2.  Si no ve ningún error, intente acceder a la siguiente dirección URL desde cualquier otro equipo de la topología:
    
    https://\<fe-servidor\>/LRS
    
    Para obtener acceso a la página, deberá agregar los registros DNS como se describe en la sección "registros DNS necesarios para el inicio de sesión automático [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056)de cliente" en.

</div>

</div>

<span> </span>

</div>

</div>

</div>

