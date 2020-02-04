---
title: 'Lync Server 2013: instalar el portal web administrativo del sistema Lync Room'
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
ms.openlocfilehash: dcfc78429ef021afcb0ed286ad86a39e63bfbf62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Installing the Lync Room System Administrative Web Portal in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-04-09_

Puede descargar el portal web administrativo del sistema de Microsoft Lync Room en el centro de descarga [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044)de Microsoft en.

Para instalar el portal web administrativo del sistema de Lync Room, siga estos pasos.

1.  Configure el puerto de la aplicación de confianza ejecutando el siguiente cmdlet en el shell de administración de Lync Server:
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  Para instalar el portal sala de reuniones, descargue **LyncRoomAdminPortal. exe** y, a continuación, ejecútelo como administrador.

3.  Abra el archivo Web.config, que se encuentra en la siguiente ubicación:
    
    % Archivos de programa\\% Microsoft Lync Server\\2013 Web\\Components portal\\sala\\de reuniones controlador int\\

4.  En el archivo Web. config, cambie PortalUserName por el nombre de usuario creado en el paso 2, en la sección "configuración de los requisitos previos para Lync Room System admin System" (el nombre recomendado en el paso es LRSApp):
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  Dado que el portal de administración de LRS es una aplicación de confianza, no es necesario que proporcione la contraseña en la configuración del portal. Si este usuario utiliza un registrador diferente del local, deberá especificar el registrador que utilizará agregando la siguiente línea en el archivo Web.Config:
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  Si utiliza un puerto diferente de 5061, agregue la siguiente línea en el archivo Web.Config: 
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a>Comprobar la instalación del portal web administrativo del sistema Lync Room

Para comprobar la instalación del portal web administrativo del sistema de Lync Room, haga lo siguiente:


1.  En un servidor front-end, vaya a la siguiente URL:
    
    https://\<fe: servidor\>/LRS
    
    No debería ver ningún error, como se muestra en la imagen siguiente:
    
    ![Pantalla de inicio de sesión en el portal de administración del sistema Lync Room](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Pantalla de inicio de sesión en el portal de administración del sistema Lync Room")

2.  Si no ve ningún error, intente acceder a la siguiente URL desde cualquier otro equipo de la topología:
    
    https://\<fe: servidor\>/LRS
    
    Para obtener acceso a la página, tendrá que agregar los registros DNS tal y como se describe en "registros DNS necesarios para el inicio de sesión [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056)de cliente automático" en.

</div>

</div>

<span> </span>

</div>

</div>

</div>

