---
title: Habilitar o deshabilitar las notificaciones push para Windows Phones
TOCTitle: Habilitar o deshabilitar las notificaciones push para Windows Phones
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49889517
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar o deshabilitar las notificaciones push para Windows Phones

 

_**Última modificación del tema:** 2013-02-23_

Las notificaciones de inserción, en forma de distintivos, iconos o alertas, se pueden enviar a un Windows Phone aunque la aplicación móvil esté inactiva. Las notificaciones de inserción notifican a un usuario eventos como una invitación de mensajería instantánea nueva o perdida y correo de voz. Puede habilitar o deshabilitar las notificaciones de inserción para dispositivos Windows Phone usando Panel de control de Lync Server 2013 o Shell de administración de Lync Server 2013.

## Para habilitar las notificaciones de inserción de Windows Phone desde Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Configuración de notificaciones de inserción**.

4.  En la página **Configuración de notificaciones de inserción**, haga clic en el sitio que desee editar, luego en el menú **Editar** y, por último, en **Mostrar detalles**.

5.  Active la casilla **Habilitar notificaciones de inserción Microsoft**.

6.  Haga clic en **Confirmar**.

## Para deshabilitar las notificaciones de inserción de Windows Phone desde Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Configuración de notificaciones de inserción**.

4.  En la página **Configuración de notificaciones de inserción**, haga clic en el sitio que desee editar, luego en el menú **Editar** y, por último, en **Mostrar detalles**.

5.  Desactive la casilla **Habilitar notificaciones de inserción Microsoft**.

6.  Haga clic en **Confirmar**.

## Para habilitar o deshabilitar las notificaciones de inserción de Windows Phone mediante los cmdlets de Windows PowerShell

Puede habilitar o deshabilitar las notificaciones de inserción de Windows Phone mediante los cmdlets de **Set-CsPushNotificationConfiguration**. Puede ejecutar este cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para habilitar las notificaciones de inserción de Windows Phone

  - Para habilitar las notificaciones de inserción de Windows Phone, establezca en la propiedad EnableMicrosoftPushNotificationService el valor True ($True). Por ejemplo:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

## Para deshabilitar las notificaciones de inserción de Windows Phone

  - Para deshabilitar las notificaciones de inserción de Windows Phone, establezca en la propiedad EnableMicrosoftPushNotificationService el valor False ($False). Por ejemplo:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

Para obtener más información, consulte el tema de ayuda correspondiente al cmdlet [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPushNotificationConfiguration).

## Vea también

#### Tareas

[Configurar las notificaciones de inserción en Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)

