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
ms.openlocfilehash: 370008a5b33cc7eb45802fb02bdd9a873184ed5a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a>Informe lista de errores en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-07-02_

El informe de lista de errores proporciona información sobre los usuarios que participaron de una sesión punto a punto o de conferencia con errores. Esta información incluye el URI del usuario que experimentó el problema, además del código de respuesta SIP y el identificador de diagnóstico asociado al error.

<div>

## <a name="accessing-the-failure-list-report"></a>Obtener acceso al informe de lista de errores

Para obtener acceso al informe de la lista de errores, haga clic en cualquiera de las siguientes métricas del [Informe de distribución de errores en Lync Server 2013](lync-server-2013-failure-distribution-report.md):

  - Principales motivos del diagnóstico (sesiones)

  - Principales modalidades (sesiones)

  - Principales grupos de servidores (sesiones)

  - Principales orígenes (sesiones)

  - Principales componentes (sesiones)

  - Principales remitentes (sesiones)

  - Principales destinatarios (sesiones)

  - Principales agentes de remitente (sesiones)

En el informe de la lista de errores, puede obtener acceso al [informe detallado de la sesión de punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) haciendo clic en la métrica de detalle de la sesión para una sesión de punto a punto. También puede tener acceso al informe de detalles de conferencia si hace clic en la métrica Conferencia para una conferencia.

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a>Aprovechar al máximo el informe de lista de errores

En el informe de lista de errores, puede ver una descripción de cada código de respuesta o cada identificador de diagnóstico. Para ello, simplemente mantenga el mouse sobre ese valor. Por ejemplo, si coloca el mouse sobre el identificador de diagnóstico 7025, verá un mensaje similar al siguiente como información sobre herramientas:

Error interno del servidor al crear medios para el usuario.

Es importante tener en cuenta que el informe de lista de errores no ofrece una manera directa de recuperar una lista de todos los usuarios que participaron de al menos una sesión con errores, ni tampoco permite determinar qué usuarios participaron con más frecuencia en sesiones con errores. (Por un elemento, el informe de la lista de errores no tiene funciones de filtrado). Sin embargo, si exporta los datos y, a continuación, los convierte en un archivo de valores separados por comas, puede usar Windows PowerShell para buscar las respuestas a preguntas como estas. Por ejemplo, supongamos que guarda los datos en un. Archivo CSV denominado C:\\Data\\Failure\_List. csv. De acuerdo con los datos guardados en ese archivo, este comando muestra todos los usuarios que participaron de al menos una sesión con errores:

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

Ese comando devolverá una lista similar a esta:

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

Estos dos comandos ofrecen información sobre el número total de sesiones con errores de las que participó cada usuario:

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

Se devolverán datos similares a estos:

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

En la siguiente tabla se detalla la información proporcionada en el informe de lista de errores para cada llamada con errores.

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
<th>¿Se pueden ordenar los datos por este elemento?</th>
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
<td><p>Tipo de solicitud SIP que presentó errores. Por ejemplo, INVITE o BYE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Código de respuesta</strong></p></td>
<td><p>No</p></td>
<td><p>Código de respuesta SIP enviado cuando se produjo un error en la conferencia.</p></td>
</tr>
<tr class="even">
<td><p><strong>Id. de diagnóstico</strong></p></td>
<td><p>No</p></td>
<td><p>Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tiempo coste de conexión (ms)</strong></p></td>
<td><p>No</p></td>
<td><p>Cantidad de tiempo (en milisegundos) que necesitó el usuario para unirse a la conferencia.</p></td>
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

