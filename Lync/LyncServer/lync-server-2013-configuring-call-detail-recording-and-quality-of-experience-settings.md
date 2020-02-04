---
title: Configuración del registro detallado de llamadas y de las opciones de la calidad de la experiencia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 504c2221e9f8a3ef32e2cebbb792f5e03aef15c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a>Configuración de la grabación de detalles de llamadas y la configuración de la calidad de la experiencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-17_

Después de asociar un almacén de supervisión con un grupo de servidores front-end, configurar el almacén de supervisión y, a continuación, instalar y configurar SQL Server Reporting Services y supervisar los informes, puede administrar la grabación de detalles de llamadas (CDR) y la calidad de la experiencia (QoE). supervisión mediante el shell de administración de Lync Server. Los cmdlets del shell de administración de Lync Server le permiten habilitar y deshabilitar la supervisión de CDR o QoE para un sitio en particular o para toda la implementación de Lync Server; Esto se puede llevar a cabo con un comando tan sencillo como el siguiente:

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

Al instalar Microsoft Lync Server 2013, también instalará una colección predefinida de opciones de configuración global tanto para CDR como para QoE. En la siguiente tabla se muestran los valores predeterminados para algunos de los valores usados más frecuentemente por el registro detallado de llamadas:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Propiedad</th>
<th>Descripción</th>
<th>Valor predeterminado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableCDR</p></td>
<td><p>Indica si está habilitado o no el CDR. Si se establece en True, se recopilarán y se escribirán todos los registros del CDR en la base de datos de supervisión.</p></td>
<td><p>Verdadero</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>Indica si los registros del CDR se eliminarán o no periódicamente de la base de datos. Si se establece en True, los registros se eliminarán tras el período de tiempo especificado por las propiedades KeepCallDetailForDays (para registros del CDR) y KeepErrorReportForDays (para errores del CDR). Si se define como False, los registros detallados de llamadas se conservarán indefinidamente.</p></td>
<td><p>Verdadero</p></td>
</tr>
<tr class="odd">
<td><p>KeepCallDetailForDays</p></td>
<td><p>Indica la cantidad de días que se conservarán los registros del CDR en la base de datos; los registros con mayor antigüedad que la cantidad de días especificada se eliminarán automáticamente. Pero, esto solo ocurrirá si la depuración está habilitada.</p>
<p>KeepCallDetailForDays puede definirse como cualquier valor entero entre 1 y 2562 días (aproximadamente 7 años).</p></td>
<td><p>60 días</p></td>
</tr>
<tr class="even">
<td><p>KeepErrorReportForDays</p></td>
<td><p>Indica la cantidad de días que se conservarán los informes de errores del CDR; cualquier informe con una antigüedad superior a la cantidad de días especificada se eliminará automáticamente. Los informes de errores de CDR son informes de diagnóstico cargados por aplicaciones cliente como Microsoft Lync 2013.</p>
<p>Puede establecer esta propiedad en cualquier valor entero entre 1 y 2562 días.</p></td>
<td><p>60 días</p></td>
</tr>
</tbody>
</table>


De manera similar, los valores predeterminados para la configuración de QoE se muestran en esta tabla:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Propiedad</th>
<th>Descripción</th>
<th>Valor predeterminado</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableQoE</p></td>
<td><p>Indica si la supervisión de QoE está o no habilitada. Si se establece en True, todos los registros de QoE se recopilarán y se escribirán en la base de datos de supervisión.</p></td>
<td><p>Verdadero</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>Indica si los registros de QoE se eliminarán periódicamente de la base de datos. Si se establece en True, se eliminarán los registros tras el período de tiempo especificado por la propiedad KeepQoEDataForDays. Si se establece en False, los registros de QoE se mantendrán de manera indefinida.</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>KeepQoEDataForDays</p></td>
<td><p>Indica la cantidad de días que los registros de QoE se conservarán en la base de datos; los registros de mayor antigüedad que la cantidad de días especificada se eliminarán automáticamente. Pero, esto solo ocurrirá si la depuración está habilitada.</p>
<p>KeepCallDetailForDays se puede establecer en cualquier valor entero entre 1 y 2562 días.</p></td>
<td><p>60 días</p></td>
</tr>
</tbody>
</table>


Si tiene que modificar estos valores globales puede hacerlo con los cmdlets Set-CsCdrConfiguration y Set-CsQoEConfiguration. Por ejemplo, este comando (se ejecuta desde el shell de administración de Lync Server) deshabilita la supervisión de CDR en el ámbito global; Esto se hace estableciendo la propiedad EnableCDR en false ($False):

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

Tenga en cuenta que la deshabilitación de la supervisión no desasocia el almacén de supervisión del grupo de servidores front-end, ni desinstala o afecta de otra manera la base de datos de supervisión de back-end. Cuando usa el shell de administración de Lync Server para deshabilitar la supervisión de CDR o QoE, todo lo que realmente hace es detener temporalmente Lync Server para recopilar y archivar los datos de supervisión. Si desea reanudar, en este caso, la colección y el archivado de datos de CDR, lo único que tiene que hacer es establecer la propiedad EnableCDR de nuevo en True ($True):

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

De manera similar, este comando deshabilita la depuración de los registros de QoE en el ámbito global:

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

Además de la configuración global, los valores de configuración de CDR y QoE se pueden asignar al ámbito de sitio. Esto proporciona flexibilidad de administración adicional en lo referente a la supervisión; por ejemplo, un administrador puede habilitar la supervisión de CDR para el sitio de Redmond pero deshabilitar la supervisión de CDR para el sitio de Dublín. Para crear nuevos valores de configuración de CDR en el ámbito de sitio, use un comando similar al siguiente:

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

Tenga en cuenta que los valores configurados en el ámbito del sitio tienen prioridad frente a los valores configurados en el ámbito global. Por ejemplo, supongamos que la supervisión de CDR está habilitada en el ámbito global pero deshabilitada en el ámbito de sitio (para el sitio de Redmond). Eso significa que la información del registro detallado de llamadas no se archivará para usuarios en el sitio de Redmond. Pero, los usuarios de otros sitios (es decir, los usuarios administrados por los valores globales en lugar de la configuración de sitio de Redmond) tendrán su información del registro detallado de llamadas archivada.

Los nuevos valores de configuración de QoE se pueden crear en el ámbito de sitio con un comando como el siguiente:

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

Para obtener más información, escriba los siguientes comandos en el shell de administración de Lync Server:

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

