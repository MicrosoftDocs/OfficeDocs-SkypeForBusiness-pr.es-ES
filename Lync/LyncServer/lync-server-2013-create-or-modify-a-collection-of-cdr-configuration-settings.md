---
title: "Créa. ou mo. d’une coll. de par. de con. de l’enr. des détails des appels"
TOCTitle: "Créa. ou mo. d’une coll. de par. de con. de l’enr. des détails des appels"
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49889679
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Creación o modificación de un conjunto de opciones de configuración de CDR

 

_**Última modificación del tema:** 2015-03-09_

El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas de conferencia. Estos datos de uso contienen información sobre quién llamó a quién, cuándo se realizó la llamada y la duración de la misma.

Cuando se instala Microsoft Lync Server 2013, se crea de forma predeterminada una colección global y única de valores de configuración del CDR. Los administradores pueden también crear una configuración personalizada en el ámbito de sitio. Cuando se usa esta configuración en el ámbito del sitio, predomina sobre la configuración global. Por ejemplo, si crea una configuración cuyo ámbito es el sitio para el sitio de Redmond, se usará dicha configuración (en lugar de la configuración global) para administrar el CDR de Redmond.

Puede crear los valores de configuración del CDR con Panel de control de Lync Server, o con el cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration). También puede usar Panel de control de Lync Server o el cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration) para modificar la configuración actual. Si usa Panel de control de Lync Server para crear o modificar la configuración, puede escoger entre las opciones siguientes:


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
<td><p>Nombre</p></td>
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



> [!NOTE]
> Los cmdlets New-CsCdrConfiguration y Set-CsCdrConfiguration incluyen otras opciones no disponibles en Panel de control de Lync Server. Para más información, consulte los temas de Ayuda <A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> y <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A>.



## Para crear valores de configuración del CDR con Panel de control de Lync Server:

1.  En Panel de control de Lync Server, haga clic en **Supervisión y archivado**.

2.  En la pestaña **Registro detallado de llamadas**, haga clic en **Nuevo**.

3.  En el cuadro de diálogo **Seleccionar un sitio**, seleccione el sitio donde desea crear los nuevo valores de configuración. Si el cuadro de diálogo está vacío, significa que ya se han asignado valores de configuración del CDR a todos los sitios (cada sitio solo puede tener una colección de valores). En tal caso, elimine o vuelva a crear la configuración, o simplemente modifique la configuración actual.

4.  En el cuadro de diálogo **Nueva configuración de registro detallado de llamadas (CDR)**, elija las opciones que desee y haga clic en **Confirmar**.

## Para modificar los valores de configuración actuales del CDR con Panel de control de Lync Server:

1.  En Panel de control de Lync Server, haga clic en **Supervisión y archivado**.

2.  Haga doble clic en la colección de valores que desea modificar, o seleccione la colección, y haga clic en **Editar** y en **Mostrar detalles**. Tenga en cuenta que solo puede modificar una colección a la vez. Para hacer cambios a varias colecciones, use Shell de administración de Lync Server.

3.  En el cuadro de diálogo **Editar configuración de registro detallado de llamadas (CDR)**, elija las opciones que desee y haga clic en **Confirmar**.

## Para crear valores de configuración del CDR con los cmdlets de Shell de administración de Lync Server:

Los valores de configuración del CDR también pueden crearse con Windows PowerShell y con el cmdlet **New-CsCdrConfiguration**. Ejecute este cmdlet desde Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para crear una nueva colección de valores de configuración del CDR:

  - Este comando crea una nueva colección de valores de configuración del CDR para el sitio de Redmond:
    
        New-CsCdrConfiguration -Identity "site:Redmond"

## Para crear una colección de valores de configuración del CDR que deshabiliten el registro detallado de llamadas:

  - Dado que, en el comando anterior, no se especificaron parámetros (además del parámetro de identidad obligatorio), la nueva colección de valores de configuración usará los valores predeterminados para todas sus propiedades. Para crear una configuración que use otros valores de propiedad, basta con incluir el parámetro y el valor correspondiente adecuados. Por ejemplo, para crear una colección de parámetros de configuración de detalle de llamadas que, de forma predeterminada, permita el registro detallado de llamadas, use solo un comando como este:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

## Para especificar varios valores de propiedad al crear una nueva colección de valores de configuración del CDR:

  - Puede incluir varios parámetros para modificar varios valores de propiedad. Por ejemplo, este comando configura los nuevos valores para conservar los registros detallados de llamadas durante 30 días y los informes de error durante 90 días:
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

Para más información, consulte el tema de Ayuda del cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration).

