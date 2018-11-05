---
title: Eliminar los archivos de registro de actualización de dispositivos
TOCTitle: Eliminar los archivos de registro de actualización de dispositivos
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994039(v=OCS.15)
ms:contentKeyID: 52061642
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Eliminar los archivos de registro de actualización de dispositivos

 

_**Última modificación del tema:** 2013-02-23_

La Servicio web de actualización de dispositivos mantiene una amplia colección de archivos de registro. Esta colección incluye tanto registros de auditoría ejecutados por el propio servicio como archivos de registro cargados desde dispositivos cliente. Para evitar que el servidor se llene de registros del servicio de Servicio web de actualización de dispositivos, le resultará conveniente borrar los archivos de registro que ya se han guardado por un número específico de días. Establezca este número en función de la actividad de actualización y la cantidad de dispositivos cliente en la organización, y mediante Panel de control de Lync Server o Shell de administración de Lync Server.

## Para borrar el registro de actualización de dispositivos mediante Panel de control de Lync Server

1.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en **Configuración de registros de dispositivos**.

3.  En la página **Configuración de registros de dispositivos**, haga doble clic en la configuración que desea cambiar.

4.  En el cuadro de diálogo **Editar configuración de registros**, en **Número de días que mantener los archivos de registros (1-365)**, especifique un número de días.

5.  Haga clic en **Confirmar**. Todos los archivos que han estado en el servidor por más del número de días especificado se borrarán. Este valor se aplicará a esta configuración hasta que lo modifique.

## Borrar el registro de actualización de dispositivos mediante los cmdlets de Windows PowerShell

Puede borrar los registros de actualización de dispositivos mediante Windows PowerShell y el cmdlet **Clear-CsDeviceUpdateLog**. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.


> [!NOTE]
> Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.



## Para borrar los registros de actualización de dispositivos en un servidor

  - El siguiente comando borra el registro de actualización de dispositivos en el servidor web atl-cs-001.litwareinc.com. Todas las entradas del registro guardadas por más de diez días (el valor especificado por el parámetro DaysBack) se quitarán del registro.
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

## Para borrar todos los registros de actualización de dispositivos

  - Este comando quita las entradas caducadas (en este ejemplo, entradas guardadas por más de diez días) de todos los registros de actualización de dispositivos que se usan actualmente en la organización.
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

Para obtener información detallada, consulte el tema de Ayuda acerca del cmdlet [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/en-us/powershell/module/skype/Clear-CsDeviceUpdateLog).

