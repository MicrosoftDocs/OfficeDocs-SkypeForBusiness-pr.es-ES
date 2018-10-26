---
title: Restaurar una regla de actualización de dispositivos
TOCTitle: Restaurar una regla de actualización de dispositivos
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994061(v=OCS.15)
ms:contentKeyID: 52061714
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restaurar una regla de actualización de dispositivos

 

_**Última modificación del tema:** 2013-02-23_

Para desinstalar una regla de actualización de dispositivos en los dispositivos de su implementación, restáurela. Al restaurar una regla de actualización de dispositivos, se desinstala la actualización y se reinstala la versión previa de esa regla.

Las reglas de actualización de dispositivos se pueden restaurar con Panel de control de Lync Server o Windows PowerShell.

## Para restaurar reglas de actualización de dispositivos con Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y luego haga clic en el botón de navegación **Actualización de dispositivos**.

4.  En la página **Actualización de dispositivos**, elija entre las siguientes opciones:
    
      - Para restaurar una regla, selecciónela.
    
      - Para restaurar todas las reglas, haga clic en **Editar** y después en **Seleccionar todo**.

5.  Haga clic en el menú **Acción** y luego haga clic en **Restaurar**.

## Restauración de reglas de actualización de dispositivos con cmdlets de Windows PowerShell

Las reglas de actualización de dispositivos también se pueden restaurar con Windows PowerShell y el cmdlet **Restore-CsDeviceUpdateRule**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.


> [!NOTE]
> Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.



## Para restaurar una sola regla de actualización de dispositivos en un servidor

  - El siguiente comando restaura la regla de actualización de dispositivos d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 en el servidor web atl-cs-001.litwareinc.com:
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

## Para restaurar todas las reglas de actualización de dispositivos en un servidor

  - Este comando restaura todas las reglas de actualización de dispositivos en el servidor web atl-cs-001.litwareinc.com:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

Para más información, consulte el tema de ayuda del cmdlet [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Restore-CsDeviceUpdateRule).

