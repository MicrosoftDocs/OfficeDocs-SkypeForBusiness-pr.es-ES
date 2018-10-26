---
title: Quitar una regla de actualización de dispositivos
TOCTitle: Quitar una regla de actualización de dispositivos
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994066(v=OCS.15)
ms:contentKeyID: 52061715
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Quitar una regla de actualización de dispositivos

 

_**Última modificación del tema:** 2013-02-23_

Al quitar una regla de actualización de dispositivos, se elimina definitivamente de la cola de actualización de dispositivos.

Eliminar una regla no es lo mismo que desinstalar una actualización de los dispositivos de su implementación o de sus dispositivos de prueba. Para desinstalar una actualización aprobada de la implementación, hay que *restaurar* la regla de actualización de dispositivos. Para más información, consulte [Restaurar una regla de actualización de dispositivos](lync-server-2013-restore-a-device-update-rule.md). Para desinstalar una actualización no aprobada de los dispositivos de prueba, hay que *restablecerla*. Para más información, vea [Restablecer una regla de actualización de dispositivos](lync-server-2013-reset-a-device-update-rule.md).

Las reglas de actualización de dispositivos se pueden quitar con Panel de control de Lync Server o Windows PowerShell.

## Para quitar reglas de actualización de dispositivos con Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y luego haga clic en el botón de navegación **Actualización de dispositivos**.

4.  En la página **Actualización de dispositivos**, elija entre las siguientes opciones:
    
      - Para quitar una regla, seleccione la que desea eliminar.
    
      - Para quitar todas las reglas, haga clic en el menú **Editar** y luego haga clic en **Seleccionar todo**.

5.  Haga clic en **Editar** y después en **Eliminar**.

## Quitar reglas de actualización de dispositivos con cmdlets de Windows PowerShell

Las reglas de actualización de dispositivos también se pueden quitar con Windows PowerShell y el cmdlet **Remove-CsDeviceUpdateRule**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para quitar una sola regla de actualización de dispositivos de un servidor

  - El siguiente comando quita la regla de actualización de dispositivos d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 del servidor web atl-cs-001.litwareinc.com:
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

## Para quitar todas las reglas de actualización de dispositivos de un servidor

  - Este comando quita todas las reglas de actualización de dispositivos del servidor web en atl-cs-001.litwareinc.com:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

Para más información, consulte el tema de ayuda del cmdlet [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsDeviceUpdateRule).

## Vea también

#### Tareas

[Aprobar una regla de actualización de dispositivos](lync-server-2013-approve-a-device-update-rule.md)

