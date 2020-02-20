---
title: 'Lync Server 2013: modificar la configuración de los archivos de registro de actualización de dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0734050b050c00a8f7a0a262e69451a223dfb6fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a>Modificar la configuración de los archivos de registro de actualización de dispositivos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Puede cambiar la configuración de la información de actualización de dispositivos que se registra en la organización mediante el panel de control de Lync Server o el shell de administración de Lync Server. En la siguiente tabla se muestran los valores que se pueden modificar y las herramientas que se usan para modificar la configuración.

La configuración del registro se puede cambiar y aplicar globalmente o por sitio.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Para cambiar</th>
<th>Utilice</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tamaño máximo (en bytes) de un archivo de registro</p></td>
<td><p>Panel de Control de Lync Server</p>
<p>O bien,</p>
<p>Shell de administración de Communications Server</p></td>
</tr>
<tr class="even">
<td><p>La cantidad máxima de información (en bytes) que se puede almacenar en la memoria caché</p></td>
<td><p>Panel de Control de Lync Server</p>
<p>O bien,</p>
<p>Shell de administración de Communications Server</p></td>
</tr>
<tr class="odd">
<td><p>Frecuencia (en minutos) con la que se escribe la información almacenada en caché en el archivo de registro</p></td>
<td><p>Panel de Control de Lync Server</p>
<p>O bien,</p>
<p>Shell de administración de Communications Server</p></td>
</tr>
<tr class="even">
<td><p>Tiempo (en días) que se conservarán los archivos de registro</p></td>
<td><p>Panel de Control de Lync Server</p>
<p>O bien,</p>
<p>Shell de administración de Communications Server</p></td>
</tr>
<tr class="odd">
<td><p>Cuándo (hora del día) para comprobar si hay archivos expirados que deben eliminarse</p></td>
<td><p>Shell de administración de Communications Server</p></td>
</tr>
<tr class="even">
<td><p>Qué extensiones de archivo de registro se permiten</p></td>
<td><p>Shell de administración de Communications Server</p></td>
</tr>
<tr class="odd">
<td><p>Qué tipos de archivos de registro se deben conservar</p></td>
<td><p>Shell de administración de Communications Server</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a>Para cambiar la configuración de registro mediante el panel de control de Lync Server

1.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en **Configuración de registros de dispositivos**.

3.  En la página **Configuración de registros de dispositivos**, haga doble clic en la configuración que desea cambiar.

4.  En el cuadro de diálogo **Editar configuración del registro** , cambie cualquiera de las siguientes opciones de configuración:
    
      - **Tamaño máximo de archivo (bytes)**   especifica el tamaño máximo que puede tener un archivo de registro antes de ser purgado. El valor predeterminado es 1.024.000 (1 MB).
    
      - **Tamaño máximo de la memoria caché (bytes)**   especifica la cantidad máxima de información (en bytes) que se puede conservar en la memoria caché de archivos de registro antes de que se borre dicha memoria caché y se escriban los datos en un archivo de registro. El valor predeterminado es 512.000 (0,5 MB).
    
      - **Número de minutos para vaciar la memoria caché (1-60)**   indica la frecuencia con la que la información almacenada en la memoria caché del archivo de registro se escribe en el archivo de registro real. Una vez se ha registrado la información, la memoria caché se borra. El valor predeterminado es cinco minutos.
    
      - **Número de días que se conservarán los archivos de registro (1-365)**   especifica el número de días que se conservan los archivos de registro antes de que se purguen. El valor predeterminado es 10 días.

5.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a>Cambio de la configuración de registro mediante cmdlets de Windows PowerShell

La configuración del archivo de registro de actualización de dispositivos se puede modificar mediante Windows PowerShell y el cmdlet **set-CsDeviceUpdateConfiguration** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.

<div>


> [!NOTE]  
> Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 mediante PowerShell remoto" en.



</div>

En los ejemplos siguientes se muestra un par de las formas en las que puede usar **set-CsDeviceUpdateConfiguration** para modificar la configuración.

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a>Para modificar el tamaño máximo del archivo de registro y el intervalo de limpieza del registro

  - El siguiente comando modifica la configuración del registro de actualización de dispositivos que se aplica al sitio de Redmond. En este ejemplo, el tamaño máximo del archivo de registro está establecido en 204800 bytes y el intervalo de limpieza de registro se establece en 14 días.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a>Para modificar el tiempo de limpieza del registro del día

  - Este comando establece el tiempo de limpieza de registro del sitio Redmond en 3:00 A.M.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

Para obtener más información, consulte el tema de ayuda del cmdlet [set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

