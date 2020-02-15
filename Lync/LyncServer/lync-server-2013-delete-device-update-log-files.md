---
title: 'Lync Server 2013: eliminar archivos de registro de actualización de dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f5b8ed6d087bb7b80ba93aead7c3ab530c82000
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a>Eliminar los archivos de registro de actualización de dispositivos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

El servicio Web Device Update mantiene una amplia colección de archivos de registro. Esta colección incluye tanto los registros de auditoría realizados por el propio servicio como los archivos de registro cargados desde los dispositivos cliente. Para evitar que el servidor se rellene con los registros del servicio Web de actualización de dispositivos, probablemente querrá eliminar los archivos de registro que han estado en el plazo de un determinado número de días. Establezca este número de días en función de la actividad de actualización y del número de dispositivos cliente de la organización, mediante el uso del panel de control de Lync Server o el shell de administración de Lync Server.

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a>Para borrar el registro de actualización de dispositivos mediante el panel de control de Lync Server

1.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en **Configuración de registros de dispositivos**.

3.  En la página **Configuración de registros de dispositivos**, haga doble clic en la configuración que desea cambiar.

4.  En el cuadro de diálogo **Editar configuración de registro** , en **número de días que se mantendrán los archivos de registro (1-365)**, especifique un número de días.

5.  Haga clic en **Confirmar**. Se eliminan todos los archivos que han estado en el servidor durante un número de días mayor que el especificado. Esta configuración se aplicará a esta configuración hasta que la cambie.

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a>Borrado del registro de actualización de dispositivos con los cmdlets de Windows PowerShell

Puede borrar los registros de actualización de dispositivos con Windows PowerShell y el cmdlet **Clear-CsDeviceUpdateLog** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.

<div>


> [!NOTE]  
> Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 mediante PowerShell remoto" en.



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a>Para borrar los registros de actualización de dispositivos en un servidor

  - El siguiente comando borra el registro de actualización de dispositivos en el servidor Web atl-cs-001.litwareinc.com. Todas las entradas de registro que tengan más de 10 días de antigüedad (el valor especificado por el parámetro DaysBack) se quitarán del registro.
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a>Para borrar todos los registros de actualización de dispositivos

  - Este comando quita las entradas obsoletas (en este ejemplo, las entradas de más de 10 días de antigüedad) de todos los registros de actualización de dispositivos que se usan actualmente en la organización.
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

