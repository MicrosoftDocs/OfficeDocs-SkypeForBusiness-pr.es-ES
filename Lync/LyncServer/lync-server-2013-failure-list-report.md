---
title: 'Lync Server 2013: informe de lista de errores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9cd8d15e81a54085624fab2dc751759d8196c48
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a>Informe de lista de errores en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-07-02_

El informe de lista de errores proporciona información sobre los participantes individuales que participaron en una sesión de punto a punto o de conferencia en la que se han producido errores. Esta información incluye el URI del usuario que experimentó el problema, así como el código de respuesta SIP y el identificador de diagnóstico asociado con el error.

<div>

## <a name="accessing-the-failure-list-report"></a>Acceso al informe de lista de errores

Para obtener acceso al informe de lista de errores, haga clic en cualquiera de las métricas siguientes en el [Informe de distribución de errores en Lync Server 2013](lync-server-2013-failure-distribution-report.md):

  - Motivos del diagnóstico principales (sesiones)

  - Modalidades principales (sesiones)

  - Grupos principales (sesiones)

  - Fuentes principales (sesiones)

  - Componentes principales (sesiones)

  - Usuarios de origen principales (sesiones)

  - Usuarios de destino principales (sesiones)

  - Agentes de usuarios de origen principales (sesiones)

En el informe de lista de errores, puede obtener acceso al [Informe de detalles de sesiones punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) haciendo clic en la métrica detalle de sesión para una sesión punto a punto. También puede obtener acceso al informe de detalles de conferencia haciendo clic en la métrica de conferencia de una conferencia.

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a>Cómo hacer el mejor uso del informe de lista de errores

En el informe de lista de errores, puede ver una descripción de cada código de respuesta o de cada identificador de diagnóstico simplemente manteniendo el mouse sobre ese valor. Por ejemplo, si mantiene el mouse sobre el identificador de diagnóstico 7025, verá lo siguiente en una información sobre herramientas:

Error interno del servidor al crear medios para el usuario.

Es importante tener en cuenta que el informe de lista de errores no ofrece una forma sencilla de recuperar directamente una lista de todos los usuarios que participaron en al menos una sesión con errores, ni tampoco proporciona una forma de determinar qué usuarios han participado con mayor frecuencia en un error sesión. (Por un lado, el informe de lista de errores no tiene funciones de filtrado). Sin embargo, si exporta los datos y, a continuación, los convierte en un archivo de valores separados por comas, puede usar Windows PowerShell para buscar las respuestas a preguntas como esas. Por ejemplo, supongamos que guarda los datos en un. Archivo CSV denominado C:\\Data\\Failure\_List. csv. En función de los datos guardados en ese archivo, este comando enumera todos los usuarios que participaron en al menos una sesión con errores:

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

Ese comando devolverá una lista similar a la siguiente:

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

Estos dos comandos devuelven el número total de sesiones con errores en las que cada usuario participó:

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

Devolverá unos datos similares a estos:

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a>Filtros

Ninguno. No se puede filtrar el informe de lista de errores.

</div>

<div>

## <a name="metrics"></a>Métricas

En la siguiente tabla se muestra la información proporcionada en el informe de lista de errores para cada llamada con errores.

### <a name="failure-list-report-metrics"></a>Métricas del informe de lista de errores

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
<td><p><strong>Hora de notificación</strong></p></td>
<td><p>No</p></td>
<td><p>Fecha y hora en que se registró el informe.</p></td>
</tr>
<tr class="even">
<td><p><strong>Solicitud</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo de solicitud SIP fallida. Por ejemplo, INVITE o BYE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Código de respuesta</strong></p></td>
<td><p>No</p></td>
<td><p>Código de respuesta SIP enviado cuando la conferencia ha fallado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Id. de diagnóstico</strong></p></td>
<td><p>No</p></td>
<td><p>Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tiempo de costo de combinación (MS)</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad de tiempo (en milisegundos) que necesita el usuario para unirse a la Conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Remitente</strong></p></td>
<td><p>No</p></td>
<td><p>Dirección SIP del usuario que inició la llamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente de remitente</strong></p></td>
<td><p>No</p></td>
<td><p>Software usado por el extremo del usuario que inició la llamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Destinatario</strong></p></td>
<td><p>No</p></td>
<td><p>Dirección SIP del usuario que recibió la llamada.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

