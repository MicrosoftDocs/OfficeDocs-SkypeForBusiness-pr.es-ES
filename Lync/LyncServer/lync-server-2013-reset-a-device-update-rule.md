---
title: Restablecer una regla de actualización de dispositivos
TOCTitle: Restablecer una regla de actualización de dispositivos
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994069(v=OCS.15)
ms:contentKeyID: 52061766
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restablecer una regla de actualización de dispositivos

 

_**Última modificación del tema:** 2013-02-23_

Si no le gusta el modo en que una actualización funciona en sus dispositivos de prueba, puede restablecer la regla de actualización del dispositivo, por la que se quita el estado pendiente de la regla y se desinstala la actualización de los dispositivos de prueba.

Una regla de actualización del dispositivo se puede quitar por medio del Panel de control de Lync Server o de Windows PowerShell.


> [!NOTE]
> Para desinstalar una regla que ya está aprobada (es decir, implantada), restáurela. Para ver detalles, consulte <A href="lync-server-2013-restore-a-device-update-rule.md">Restaurar una regla de actualización de dispositivos</A>.



## Para restablecer una regla de actualización de dispositivo mediante el Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, después, en el botón de navegación **Actualización de dispositivo**.

4.  En la página **Actualización de dispositivo**, realice alguna de las operaciones siguientes:
    
      - Para restablecer una regla, seleccione la regla en cuestión.
    
      - Para restablecer todas las reglas, haga clic en **Seleccionar todo** en el menú **Editar**.
    
      - Para restablecer todas las reglas para una marca, use el menú de columna **Marca**.

5.  Haga clic en **Acción** y, después, en **Cancelar actualizaciones pendientes**.
    
    > [!TIP]  
    > Si está completamente seguro de que no va a querer volver implantar la regla o reglas de actualización de dispositivo que ha cancelado, puede que prefiera eliminarlas. Para conocer los detalles, consulte <a href="lync-server-2013-remove-a-device-update-rule.md">Quitar una regla de actualización de dispositivos</a>.
    


## Restablecer una regla de actualización de dispositivo con cmdlets de Windows PowerShell

Las reglas de actualización de dispositivo también se pueden restablecer a través de Windows PowerShell y el cmdlet **Reset-CsDeviceUpdateRule**. Este cmdlet se ejecuta desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.


> [!NOTE]
> Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.



## Para restablecer una regla de actualización de dispositivo específica en un servidor

  - Con el siguiente comando se restablece la regla de actualización de dispositivo d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 en el servidor web atl-cs-001.litwareinc.com:
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

## Para restablecer todas las reglas de actualización de dispositivo en un servidor

  - Con este comando se restablecen todas las reglas de actualización de dispositivo en el servidor web atl-cs-001.litwareinc.com:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

## Para restablecer todas las reglas de actualización de dispositivo que tienen una marca específica

  - En este ejemplo, se restablecen todas las reglas de actualización de dispositivo de la organización que tienen la marca Microsoft:
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

Para más información detallada, vea el tema de ayuda relativo al cmdlet [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Reset-CsDeviceUpdateRule).

## Vea también

#### Tareas

[Aprobar una regla de actualización de dispositivos](lync-server-2013-approve-a-device-update-rule.md)

