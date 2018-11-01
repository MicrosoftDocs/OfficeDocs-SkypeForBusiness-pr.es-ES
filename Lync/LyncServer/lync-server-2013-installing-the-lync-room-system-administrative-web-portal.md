---
title: Instalar el portal web administrativo del sistema Lync Room
TOCTitle: Instalar el portal web administrativo del sistema Lync Room
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn436326(v=OCS.15)
ms:contentKeyID: 59602830
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalar el portal web administrativo del sistema Lync Room

 

_**Última modificación del tema:** 2016-12-08_

El portal web administrativo de sistema Lync Room de Microsoft puede descargarse desde el Centro de descarga de Microsoft, en [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044).

Para instalar este portal, haga lo siguiente:

1.  Configure el puerto de la aplicación de confianza. Para ello, ejecute el cmdlet siguiente en Shell de administración de Lync Server:
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  Para instalar el portal de salas de reuniones, descargue **LyncRoomAdminPortal.exe** y ejecútelo como administrador.

3.  Abra el archivo Web.config desde la ubicación siguiente:
    
    %Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler\\

4.  En este archivo, cambie PortalUserName por el nombre de usuario que se ha creado en el paso 2, bajo la sección “Configuración de requisitos previos para el portal administrativo del sistema Lync Room” (se recomienda el nombre de LRSApp):
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  El portal administrativo de LRS es una aplicación de confianza, por lo que no es necesario especificar una contraseña durante su configuración. Si el usuario usa un registrador distinto del registrador local, deberá especificarse de qué registrador se trata. Para ello, agregue la línea siguiente al archivo Web.Config:
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  Si se usa un puerto distinto del 5061, agregue la línea siguiente al archivo Web.Config:
    
        <add key="PortalUserRegistrarPort" value="5061" />

## Comprobar la instalación del portal web administrativo del sistema Lync Room

Para comprobar la instalación del portal web administrativo del sistema Lync Room, haga lo siguiente:


1.  En un servidor front-end, busque la dirección URL:
    
    https://\<fe-server\>/lrs
    
    No debe aparecer ningún error, tal como muestra la imagen siguiente:
    
    ![Pantalla de inicio de sesión en el portal de administración del sistema Lync Room](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Pantalla de inicio de sesión en el portal de administración del sistema Lync Room")

2.  Si no se muestra ningún error, intente acceder a la dirección URL siguiente desde otro equipo de la topología:
    
    https://\<fe-server\>/lrs
    
    Para acceder a la página deberá agregar los registros DNS conforme a lo descrito en “Registros DNS necesarios para el inicio de sesión de clientes automático”, en [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056).

