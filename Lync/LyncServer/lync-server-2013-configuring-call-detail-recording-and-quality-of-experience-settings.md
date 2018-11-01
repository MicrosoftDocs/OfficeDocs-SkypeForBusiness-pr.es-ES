---
title: "Grabación de detalles de llamada y calidad de la experiencia en Lync Server 2013"
TOCTitle: Configuración de la grabación de detalles de llamada y la calidad de la experiencia
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48274230
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de la grabación de detalles de llamada y la calidad de la experiencia en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Una vez ha asociado un almacén de supervisión con un grupo de servidores front-end, configurado el almacén de supervisión y, a continuación, instalado y configurado SQL Server Reporting Services e informes de supervisión, puede administrar la supervisión del Registro de detalles de llamadas (CDR) y la Calidad de la experiencia (QoE) mediante Shell de administración de Lync Server. Los cmdlets de Shell de administración de Lync Server le permiten habilitar y deshabilitar la supervisión de CDR y/o QoE para un sitio concreto o para su implementación de Lync Server; eso se puede realizar con un comando tan sencillo como el siguiente:

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

Al instalar Microsoft Lync Server 2013, también instalará una colección predefinida de valores de configuración global para CDR y QoE. Los valores predeterminados para algunos de los valores usados más frecuentemente por el Registro de detalles de llamadas se muestran en la siguiente tabla:


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
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>Indica si los registros del CDR se eliminarán o no periódicamente de la base de datos. Si se establece en True, los registros se eliminarán tras el período de tiempo especificado por las propiedades KeepCallDetailForDays (para registros del CDR) y KeepErrorReportForDays (para errores del CDR). Si se define como False, los registros de detalles de llamadas se conservarán indefinidamente.</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>KeepCallDetailForDays</p></td>
<td><p>Indica el número de días en que se conservarán los registros del CDR en la base de datos; los registros con mayor antigüedad que el número de días especificados se eliminarán automáticamente. Sin embargo, esto solo ocurrirá si la depuración está habilitada.</p>
<p>KeepCallDetailForDays puede definirse como cualquier valor entero entre 1 y 2562 días (aproximadamente 7 años).</p></td>
<td><p>60 días</p></td>
</tr>
<tr class="even">
<td><p>KeepErrorReportForDays</p></td>
<td><p>Indica el número de días que se conservarán los informes de errores del CDR; cualquier informe con una antigüedad superior al número de días especificado se eliminará automáticamente. Los informes de errores del CDR son informes de diagnóstico cargados por aplicaciones cliente, como Microsoft Lync 2013.</p>
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
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>Indica si los registros de QoE se eliminarán periódicamente de la base de datos. Si se establece en True, se eliminarán los registros tras el período de tiempo especificado por la propiedad KeepQoEDataForDays. Si se establece en False, los registros de QoE se mantendrán de manera indefinida.</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>KeepQoEDataForDays</p></td>
<td><p>Indica el número de días que los registros de QoE se conservarán en la base de datos; los registros de mayor antigüedad que el número de días especificados se eliminarán automáticamente. Sin embargo, esto solo ocurrirá si la depuración está habilitada.</p>
<p>KeepCallDetailForDays se puede establecer en cualquier valor entero entre 1 y 2562 días.</p></td>
<td><p>60 días</p></td>
</tr>
</tbody>
</table>


Si tiene que modificar estos valores globales puede hacerlo mediante los cmdlets Set-CsCdrConfiguration y Set-CsQoEConfiguration. Por ejemplo, este comando (ejecutado desde dentro del Shell de administración de Lync Server) deshabilita la supervisión del CDR en el ámbito global; esto se realiza estableciendo la propiedad EnableCDR en False ($False):

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

Tenga en cuenta que la deshabilitación de la supervisión no desasocia el almacén de supervisión del grupo de servidores front-end, ni desinstala o afecta de otra manera la base de datos de supervisión de back-end. Al usar Shell de administración de Lync Server para deshabilitar la supervisión de CDR o QoE todo lo que hace realmente es detener temporalmente a Lync Server para que no recopile ni archive datos de supervisión. Si desea reanudar, en este caso, la colección y el archivado de datos de CDR, todo lo que tiene que hacer es establecer la propiedad EnableCDR de nuevo en True ($True):

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

De manera similar, este comando deshabilita la depuración de los registros de QoE en el ámbito global:

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

Además de la configuración global, los valores de configuración de CDR y QoE se pueden asignar al ámbito de sitio. Esto proporciona flexibilidad de administración adicional en lo referente a la supervisión; por ejemplo, un administrador puede habilitar la supervisión de CDR para el sitio de Redmond pero deshabilitar la supervisión de CDR para el sitio de Dublín. Para crear nuevos valores de configuración de CDR en el ámbito de sitio, use un comando similar al siguiente:

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

Tenga en cuenta que los valores configurados en el ámbito del sitio tienen prioridad frente a los valores configurados en el ámbito global. Por ejemplo, supongamos que la supervisión de CDR está habilitada en el ámbito global pero deshabilitada en el ámbito de sitio (para el sitio de Redmond). Eso significa que la información de registro de detalles de llamada no se archivará para usuarios en el sitio de Redmond. Sin embargo, los usuarios de otros sitios (es decir, los usuarios administrados por los valores globales en lugar de la configuración de sitio de Redmond) tendrán su información de registro de detalle de llamada archivada.

Los nuevos valores de configuración de QoE se pueden crear en el ámbito de sitio mediante un comando como el siguiente:

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

Para obtener más información, escriba los siguientes comandos desde dentro del Shell de administración de Lync Server:

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

