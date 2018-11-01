---
title: Habilitar o deshabilitar notificaciones push para iPhones
TOCTitle: Habilitar o deshabilitar notificaciones push para iPhones
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49889365
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar o deshabilitar notificaciones push para iPhones

 

_**Última modificación del tema:** 2013-02-23_

Las notificaciones de inserción, en forma de distintivos, iconos o alertas, se pueden enviar a un iPhone aunque la aplicación móvil esté inactiva. Las notificaciones de inserción notifican a un usuario eventos como una invitación de mensajería instantánea nueva o perdida, o el correo de voz. Puede habilitar o deshabilitar las notificaciones de inserción para iPhone mediante Panel de control de Lync Server 2013 o Shell de administración de Lync Server 2013.

## Para habilitar las notificaciones de inserción para iPhone desde Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Configuración de notificaciones de inserción**.

4.  En la página **Configuración de notificaciones de inserción**, haga clic en el sitio que desee editar, haga clic en el menú **Editar** y, después, haga clic en **Mostrar detalles**.

5.  Haga clic en la casilla **Habilitar notificaciones de inserción de Apple**.

6.  Haga clic en **Confirmar**.

## Para deshabilitar las notificaciones de inserción para iPhone desde Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Configuración de notificaciones de inserción**.

4.  En la página **Configuración de notificaciones de inserción**, haga clic en el sitio que desee editar, haga clic en el menú **Editar** y, después, haga clic en **Mostrar detalles**.

5.  Desactive la casilla **Habilitar notificaciones de inserción de Apple**.

6.  Haga clic en **Confirmar**.

## Para habilitar o deshabilitar las notificaciones de inserción a iPhone mediante los cmdlets de Windows PowerShell

Las notificaciones de iPhone de Apple se pueden habilitar o deshabilitar mediante el cmdlet de **Set-CsPushNotificationConfiguration**. Puede ejecutar este cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para habilitar las notificaciones de inserción para iPhone

  - Para habilitar las notificaciones de inserción para iPhone, establezca el valor de la propiedad EnableApplePushNotificationService como True ($True). Por ejemplo:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

## Para deshabilitar las notificaciones de inserción para iPhone

  - Para deshabilitar las notificaciones de inserción para iPhone, establezca el valor de la propiedad EnableApplePushNotificationService como False ($False). Por ejemplo:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

Si desea obtener más información, consulte el tema de ayuda del cmdlet [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPushNotificationConfiguration).

## Vea también

#### Tareas

[Configurar las notificaciones de inserción en Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)

