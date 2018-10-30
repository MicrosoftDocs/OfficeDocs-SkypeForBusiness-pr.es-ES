---
title: Aprobar una regla de actualización de dispositivos
TOCTitle: Aprobar una regla de actualización de dispositivos
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994053(v=OCS.15)
ms:contentKeyID: 52061737
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aprobar una regla de actualización de dispositivos

 

_**Última modificación del tema:** 2013-02-23_

Una vez que importe una regla de actualización de dispositivos, se instalará en sus dispositivos de prueba. Si el resultado de las pruebas es correcto y desea implementar la actualización en su organización, apruébela con Panel de control de Lync Server o Windows PowerShell.

## Para aprobar una regla de actualización de dispositivos con Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la página **Actualización de dispositivos**, elija entre las siguientes opciones:
    
      - Para aprobar una regla, selecciónela.
    
      - Para aprobar todas las reglas, haga clic en **Editar** y después en **Seleccionar todo**.

4.  Haga clic en **Acción** y luego en **Aprobar**.

## Aprobación de una regla de actualización de dispositivos con cmdlets de Windows PowerShell

Las reglas de actualización de dispositivos también se pueden aprobar con Windows PowerShell y el cmdlet **Approve-CsDeviceUpdateRule**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.


> [!NOTE]
> Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.



## Para aprobar una sola regla de actualización de dispositivos

  - El siguiente comando aprueba la regla de actualización de dispositivos d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 que se encuentra en el servidor web atl-cs-001.litwareinc.com:
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

## Para aprobar varias reglas de actualización de dispositivos

  - Este comando aprueba todas las reglas de actualización de dispositivos para dispositivos de marca Microsoft:
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

Para más información, consulte el tema de ayuda del cmdlet [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Approve-CsDeviceUpdateRule).

## Vea también

#### Tareas

[Importar reglas de actualización de dispositivos](lync-server-2013-import-device-update-rules.md)  
[Restaurar una regla de actualización de dispositivos](lync-server-2013-restore-a-device-update-rule.md)

