---
title: 'Lync Server 2013: informe de inventario de teléfono IP'
description: 'Lync Server 2013: informe de inventario de teléfono IP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP Phone Inventory Report
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48185044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bc05017775ad64e0e18f876215aa2c6b3882bd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575026"
---
# <a name="ip-phone-inventory-report-in-lync-server-2013"></a>Informe de inventario de teléfono IP en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-12_

El informe de inventario de teléfono IP ofrece información sobre los teléfonos IP que la organización usa actualmente. El informe proporciona una lista detallada de los teléfonos IP que realmente se usaron durante el período de informes especificado. Entre otros datos, este informe permite que los administradores conozcan si aún hay teléfonos antiguos obsoletos en uso que se deben reemplazar. También puede advertir a los administradores sobre la presencia de teléfonos costosos que casi no se usan en la organización. Ese tipo de información puede resultar valiosa en el momento de comprar teléfonos nuevos o de redistribuir los teléfonos existentes. (Por ejemplo, se le puede pedir a un usuario que rara vez usa su costoso teléfono que lo intercambie con un usuario que usa el suyo con mucha más frecuencia).

Debe tenerse en cuenta que este informe presenta algunas limitaciones cuando se usa como un informe de inventario real. Por un lado, el informe de teléfono IP se limita a enumerar todos los teléfonos que iniciaron sesión en Lync Server durante el período de tiempo especificado, ordenados por la hora de último inicio de sesión. Si un teléfono no inició sesión durante el período especificado, no aparecerá en el informe de inventario. Eso incluye los teléfonos que iniciaron sesión antes de que comenzara el período y que seguían conectados durante el intervalo especificado. Por ejemplo, supongamos que desea ver el inventario de teléfonos completo de julio de 2012. Supongamos, además, que varios teléfonos iniciaron sesión en Lync Server el 30 de junio de 2012 y que todavía iniciaron sesión a partir del 1 de julio. Esos teléfonos no se mostrarán en el informe de inventario del 1 de julio.

También es importante tener en cuenta que el informe de inventario puede incluir teléfonos que la organización ya no usa. Por ejemplo, supongamos que diferentes teléfonos de Fabrikam iniciaron sesión en el sistema el 1 de julio de 2012. Cinco días después, la organización se deshizo de todos esos teléfonos de Fabrikam y los reemplazó por un modelo más nuevo de Contoso. Los teléfonos de Fabrikam seguirán apareciendo en el informe de "inventario" porque iniciaron sesión en el sistema durante el mes de julio.

Además, el informe de inventario de teléfono IP no proporciona información sobre los totales de resumen de los diferentes tipos de teléfonos. Por ejemplo, supongamos que tiene 105 teléfonos Polycom CX600. El informe no indicará que tiene 105 teléfonos de ese tipo; en cambio, simplemente se visualizarán 105 entradas independientes para Polycom CX600. La única forma de saber que existen 105 entradas para Polycom CX600 sería contar cada una de esas entradas manualmente.

<div>


> [!WARNING]  
> O bien, exportar los datos y usar Microsoft Excel o Windows PowerShell para que hagan el recuento automáticamente.



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a>Obtener acceso al informe de inventario de teléfono IP

Se puede tener acceso al informe de inventario de teléfono IP desde la página principal de informes de supervisión. Si hace clic en la métrica URI de usuario, podrá tener acceso al informe de actividad de usuario. Si hace clic en la métrica Última actividad para una llamada punto a punto, podrá ver el informe de detalles de sesiones punto a punto o el informe de detalles de conferencia, si hace clic en la misma métrica para una conferencia.

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>Aprovechar al máximo el informe de inventario de teléfono IP

Si solo le interesa la información de uso de un tipo de teléfono en particular (por ejemplo, "¿con qué frecuencia usan los usuarios un teléfono Polycom CX600?"), puede obtener esa información directamente del informe de inventario de teléfono IP filtrando para ese tipo de teléfono en particular. Sin embargo, si desea obtener información resumida de todos los teléfonos (cuántas personas usan un Polycom CX600, cuántos están usando un LG-Nortel IP8540, etc.), tendrá que exportar los datos y usar otra aplicación (como Windows PowerShell) para realizar ese tipo de análisis. Por ejemplo, supongamos que exporta los datos a un archivo de valores separados por comas (C: \\ Data \\ IP \_ Phone \_ Inventory \_Report.csv). En ese caso, podría usar estos dos comandos para proporcionar datos de resumen para todos los teléfonos:

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

Se devolverán datos similares a estos:

    Count    Name
    -----    ----
      267    POLYCOM, CX700
      267    POLYCOM, CX600
      166    POLYCOM, C
       68    Microsoft, CPE
       64    LG-Nortel, IP8540
       59    Aastra, 6725ip
       37    LG-Nortel, IP
       22    POLYCOM, CX3000
       11    Microsoft, CPE_A
        9    POLYCOM, CX500
        7    Aastra, 6721ip

De modo similar, estos dos comandos indican qué teléfonos iniciaron sesión en el sistema, pero nunca se usaron en realidad para hacer llamadas (el valor de la métrica Última actividad está en blanco, lo que indica que no hubo ninguna actividad reciente):

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

Se devuelven datos similares a estos para cada teléfono que no se usó:

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

Otra forma interesante de usar el informe de inventario de teléfono IP es la siguiente: si tiene la dirección MAC de un teléfono IP, puede conocer quién usó el teléfono por última vez con solo escribir esa dirección en el cuadro de texto Dirección MAC. El informe luego mostrará, entre otros datos, la dirección SIP del usuario que inició sesión con ese teléfono por última vez. También puede escribir la dirección SIP de un usuario (en el cuadro Prefijo de URI de usuario) para conocer todos los teléfonos que usó ese determinado usuario.

</div>

<div>

## <a name="filters"></a>Filtros

Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas. Por ejemplo, el inventario de teléfonos IP le permite ver solo los teléfonos fabricados por una empresa concreta, o incluso una versión concreta de dichos teléfonos. También se puede elegir cómo agrupar los datos. En este caso, los registros se agrupan por hora, día, semana o mes.

En la siguiente tabla verá una lista de los filtros que puede usar con el informe de inventario de teléfono IP.

### <a name="ip-phone-inventory-report-filters"></a>Filtros del informe de inventario de teléfono IP

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</p>
<p>7/7/2012 1:00 PM</p>
<p>Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</p>
<p>7/7/2012 1:00 PM</p>
<p>Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</p>
<p>7/7/2012</p>
<p>Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</p>
<p>7/3/2012</p>
<p>Las semanas siempre van del domingo al sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Manufacturer</strong></p></td>
<td><p>Nombre de la empresa que fabricó el teléfono IP. Los valores de este filtro se rellenan automáticamente a partir de los teléfonos IP que hay actualmente en la base de datos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Versión de hardware</strong></p></td>
<td><p>Número de versión del teléfono IP; mediante el uso del fabricante y los filtros de versión de hardware puede identificar de manera única un tipo de teléfono en particular. Los valores de este filtro se rellenan automáticamente a partir de los teléfonos IP que hay actualmente en la base de datos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente de usuario</strong></p></td>
<td><p>Identificador del software del teléfono IP. Los valores de este filtro se rellenan automáticamente a partir de los teléfonos IP que hay actualmente en la base de datos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dirección MAC</strong></p></td>
<td><p>Identificador único de la interfaz de red del teléfono IP. La dirección Media Access Control (MAC) suele asignarse en el momento de fabricar el teléfono y está preprogramada en el hardware del dispositivo.</p>
<p>Para buscar registros correspondientes a una dirección MAC concreta, basta con escribir esa dirección. Por ejemplo:</p>
<p>00-08-5D-16-16-48</p>
<p>Debe escribir la dirección completa. Si escribe parte de una dirección (por ejemplo, 00-08-5D), no obtendrá ningún resultado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Días anteriores a la última actividad</strong></p></td>
<td><p>Seleccione uno de los siguientes valores:</p>
<ul>
<li><p>Todos</p></li>
<li><p>10  </p></li>
<li><p>20</p></li>
<li><p>semestre</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Días anteriores a la hora del último cierre de sesión</strong></p></td>
<td><p>Seleccione uno de los siguientes valores:</p>
<ul>
<li><p>Todos</p></li>
<li><p>10  </p></li>
<li><p>20</p></li>
<li><p>semestre</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Prefijo de URI de usuario</strong></p></td>
<td><p>Dirección SIP del usuario que usó el teléfono IP.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

En la tabla siguiente se muestra la información proporcionada en el informe de inventario de teléfono IP.

### <a name="ip-phone-inventory-report-metrics"></a>Métricas del informe de inventario de teléfono IP

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>¿Se pueden ordenar los datos en este elemento?</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Manufacturer</strong></p></td>
<td><p>Sí</p></td>
<td><p>Nombre de la empresa que fabricó el teléfono IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Versión de hardware</strong></p></td>
<td><p>Sí</p></td>
<td><p>Número de versión del teléfono IP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Dirección MAC</strong></p></td>
<td><p>Sí</p></td>
<td><p>Identificador único de la interfaz de red del teléfono IP. La dirección MAC suele asignarse en el momento de fabricar el teléfono y está preprogramada en el hardware del dispositivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI de usuario</strong></p></td>
<td><p>Sí</p></td>
<td><p>Dirección SIP del usuario que usó el teléfono IP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente de usuario</strong></p></td>
<td><p>Sí</p></td>
<td><p>Identificador del software del teléfono IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hora de último inicio de sesión</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en que el teléfono IP inició sesión por última vez en Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hora de último cierre de sesión</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en que el teléfono IP cerró sesión por última vez en Lync Server.</p></td>
</tr>
<tr class="even">
<td><p><strong>Última actividad</strong></p></td>
<td><p>Sí</p></td>
<td><p>Fecha y hora en que se usó por última vez el teléfono IP.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

