---
title: 'Lync Server 2013: crear o modificar una colección de opciones de configuración de CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 582df13f3bcd7c1d25e8bf15ce1534992ba6aeeb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514797"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Crear o modificar una colección de opciones de configuración de CDR en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas de conferencia. Estos datos de uso contienen información sobre quién llamó a quién, cuándo se realizó la llamada y la duración de la misma.

Al instalar Microsoft Lync Server 2013, se creará una única colección global de opciones de configuración de CDR. Los administradores pueden también crear una configuración personalizada en el ámbito de sitio. Cuando se usa esta configuración en el ámbito del sitio, predomina sobre la configuración global. Por ejemplo, si crea una configuración cuyo ámbito es el sitio para el sitio de Redmond, se usará dicha configuración (en lugar de la configuración global) para administrar el CDR de Redmond.

Puede crear opciones de configuración de CDR con el panel de control de Lync Server o con el cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) . Puede usar el panel de control de Lync Server o el cmdlet [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) para modificar la configuración existente. Si usa el panel de control de Lync Server para crear o modificar la configuración, estarán disponibles las siguientes opciones:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Valor de IU</th>
<th>Parámetro de PowerShell</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>Identidad</p></td>
<td><p>Identificador único de los valores de configuración del CDR que se crean. Estos parámetros solo se pueden crear en el ámbito del sitio.</p></td>
</tr>
<tr class="even">
<td><p>Habilitar supervisión del CDR</p></td>
<td><p>EnableCDR</p></td>
<td><p>Indica si está o no habilitado el CDR.</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar depuración de registros de detalles de llamadas (CDR)</p></td>
<td><p>EnablePurging</p></td>
<td><p>Indica si los registros del CDR se eliminarán periódicamente de su base de datos correspondiente.</p></td>
</tr>
<tr class="even">
<td><p>Conservar registros de detalles de llamadas durante un máximo de (días)</p></td>
<td><p>KeepCallDetailForDays</p></td>
<td><p>Indica el número de días que los registros del CDR se conservarán en su base de datos correspondiente. Los registros con una antigüedad superior al número de días especificado se eliminarán automáticamente. Tenga en cuenta que debe habilitar la purga para que pueda completarse.</p></td>
</tr>
<tr class="odd">
<td><p>Conservar los datos de los informes de errores durante el período de duración máximo (días)</p></td>
<td><p>KeepErrorReportForDays</p></td>
<td><p>Indica el número de días que se conservarán los informes de errores del CDR. Cualquier informe con una antigüedad superior al número de días especificado se eliminará automáticamente. Los informes de errores del CDR son informes de diagnóstico que se cargan desde las aplicaciones cliente.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Los cmdlets New-CsCdrConfiguration y Set-CsCdrConfiguration incluyen opciones adicionales que no están disponibles en el panel de control de Lync Server. Vea los temas de ayuda de <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> y <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">set-CsCdrConfiguration</A> para obtener más información.



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a>Para crear opciones de configuración de CDR mediante el panel de control de Lync Server

1.  En el panel de control de Lync Server, haga clic en **supervisión y archivado**.

2.  En la pestaña **registro detallado de llamadas** , haga clic en **nuevo**.

3.  En el cuadro de diálogo **Seleccionar un sitio**, seleccione el sitio donde desea crear los nuevo valores de configuración. Si el cuadro de diálogo está vacío, significa que ya se han asignado valores de configuración del CDR a todos los sitios (cada sitio solo puede tener una colección de valores). En tal caso, elimine o vuelva a crear la configuración, o simplemente modifique la configuración actual.

4.  En el cuadro de diálogo **Nueva configuración de registro detallado de llamadas (CDR)**, elija las opciones que desee y haga clic en **Confirmar**.

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a>Para modificar las opciones de configuración de CDR existentes mediante el panel de control de Lync Server

1.  En el panel de control de Lync Server, haga clic en **supervisión y archivado**.

2.  Haga doble clic en la colección de valores que desea modificar, o seleccione la colección, y haga clic en **Editar** y en **Mostrar detalles**. Tenga en cuenta que solo puede modificar una colección a la vez. Para realizar los mismos cambios en varias colecciones, use el shell de administración de Lync Server en su lugar.

3.  En el cuadro de diálogo **Editar configuración de registro detallado de llamadas (CDR)**, elija las opciones que desee y haga clic en **Confirmar**.

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creación de opciones de configuración de CDR con los cmdlets de Windows PowerShell

Puede crear opciones de configuración de CDR también mediante Windows PowerShell y el cmdlet **New-CsCdrConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>Para crear una nueva colección de valores de configuración del CDR:

  - Este comando crea una nueva colección de valores de configuración del CDR para el sitio de Redmond:
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>Para crear una colección de valores de configuración del CDR que deshabiliten el registro detallado de llamadas:

  - Dado que, en el comando anterior, no se especificaron parámetros (además del parámetro de identidad obligatorio), la nueva colección de valores de configuración usará los valores predeterminados para todas sus propiedades. Para crear una configuración que use otros valores de propiedad, basta con incluir el parámetro y el valor correspondiente adecuados. Por ejemplo, para crear una colección de parámetros de configuración de detalle de llamadas que, de forma predeterminada, permita el registro detallado de llamadas, use solo un comando como este:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>Para especificar varios valores de propiedad al crear una nueva colección de valores de configuración del CDR:

  - Puede incluir varios parámetros para modificar varios valores de propiedad. Por ejemplo, este comando configura los nuevos valores para conservar los registros detallados de llamadas durante 30 días y los informes de error durante 90 días:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

Para obtener más información, consulte el tema de ayuda del cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

