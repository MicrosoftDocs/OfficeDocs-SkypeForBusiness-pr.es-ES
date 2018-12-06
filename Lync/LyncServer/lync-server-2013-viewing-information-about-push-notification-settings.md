---
title: Visualización de información sobre la configuración de notificaciones push
TOCTitle: Visualización de información sobre la configuración de notificaciones push
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49889659
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Visualización de información sobre la configuración de notificaciones push

 

_**Última modificación del tema:** 2013-02-23_

Las notificaciones de inserción, en la forma de distintivos, iconos o alertas, se pueden enviar a un dispositivo móvil aunque la aplicación móvil se encuentre inactiva. Las notificaciones de inserción notifican a un usuario eventos como correo de voz o invitaciones de mensajería instantánea nuevas o perdidas. Puede ver información sobre la configuración de las notificaciones de inserción para los dispositivos móviles a través de Panel de control de Lync Server 2013 o Shell de administración de Lync Server 2013.

## Para ver información sobre las notificaciones de inserción desde Panel de control de Lync Server:

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y en el botón de navegación **Configuración de notificación de inserción**.

4.  En la página **Configuración de notificación de inserción**, haga clic en el sitio que desea ver, en el menú **Editar** y en **Mostrar detalles**.

## Para ver información sobre la configuración de las notificaciones de inserción con los cmdlets de Windows PowerShell:

También puede ver los valores de configuración de las notificaciones de inserción a través de Shell de administración de Lync Server y el cmdlet **Get-CsPushNotificationConfiguration**. Ejecute este cmdlet desde Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para ver información sobre la configuración de las notificaciones de inserción:

  - Para ver información sobre todos los valores de configuración de las notificaciones de inserción, escriba el comando siguiente en Shell de administración de Lync Server y presione Entrar:
    
        Get-CsPushNotificationConfiguration
    
    Aparecerá información similar a esta:
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

Para más información, consulte el tema de Ayuda del cmdlet [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPushNotificationConfiguration).

## Vea también

#### Tareas

[Configurar las notificaciones de inserción en Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)

