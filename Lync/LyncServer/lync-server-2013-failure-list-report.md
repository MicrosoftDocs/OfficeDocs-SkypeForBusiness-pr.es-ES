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
ms.openlocfilehash: 3fc3d74e6613f54f346e00328f1fae929f7def27
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a><span data-ttu-id="c6d1c-102">Informe de lista de errores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6d1c-102">Failure List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6d1c-103">_**Última modificación del tema:** 2012-07-02_</span><span class="sxs-lookup"><span data-stu-id="c6d1c-103">_**Topic Last Modified:** 2012-07-02_</span></span>

<span data-ttu-id="c6d1c-104">El informe de lista de errores proporciona información sobre los participantes individuales que participaron en una sesión de punto a punto o de conferencia en la que se han producido errores.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-104">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session.</span></span> <span data-ttu-id="c6d1c-105">Esta información incluye el URI del usuario que experimentó el problema, así como el código de respuesta SIP y el identificador de diagnóstico asociado con el error.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-105">This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>

<div>

## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="c6d1c-106">Acceso al informe de lista de errores</span><span class="sxs-lookup"><span data-stu-id="c6d1c-106">Accessing the Failure List Report</span></span>

<span data-ttu-id="c6d1c-107">Para obtener acceso al informe de lista de errores, haga clic en cualquiera de las métricas siguientes en el [Informe de distribución de errores en Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span><span class="sxs-lookup"><span data-stu-id="c6d1c-107">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span></span>

  - <span data-ttu-id="c6d1c-108">Motivos del diagnóstico principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="c6d1c-108">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="c6d1c-109">Modalidades principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="c6d1c-109">Top modalities (sessions)</span></span>

  - <span data-ttu-id="c6d1c-110">Grupos principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="c6d1c-110">Top pools (sessions)</span></span>

  - <span data-ttu-id="c6d1c-111">Fuentes principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="c6d1c-111">Top sources (sessions)</span></span>

  - <span data-ttu-id="c6d1c-112">Componentes principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="c6d1c-112">Top components (sessions)</span></span>

  - <span data-ttu-id="c6d1c-113">Usuarios de origen principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="c6d1c-113">Top from users (sessions)</span></span>

  - <span data-ttu-id="c6d1c-114">Usuarios de destino principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="c6d1c-114">Top to users (sessions)</span></span>

  - <span data-ttu-id="c6d1c-115">Agentes de usuarios de origen principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="c6d1c-115">Top from user agents (sessions)</span></span>

<span data-ttu-id="c6d1c-116">En el informe de lista de errores, puede obtener acceso al [Informe de detalles de sesiones punto a punto en Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) haciendo clic en la métrica detalle de sesión para una sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-116">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="c6d1c-117">También puede obtener acceso al informe de detalles de conferencia haciendo clic en la métrica de conferencia de una conferencia.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-117">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="c6d1c-118">Cómo hacer el mejor uso del informe de lista de errores</span><span class="sxs-lookup"><span data-stu-id="c6d1c-118">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="c6d1c-119">En el informe de lista de errores, puede ver una descripción de cada código de respuesta o de cada identificador de diagnóstico simplemente manteniendo el mouse sobre ese valor.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-119">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value.</span></span> <span data-ttu-id="c6d1c-120">Por ejemplo, si mantiene el mouse sobre el identificador de diagnóstico 7025, verá lo siguiente en una información sobre herramientas:</span><span class="sxs-lookup"><span data-stu-id="c6d1c-120">For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>

<span data-ttu-id="c6d1c-121">Error interno del servidor al crear medios para el usuario.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-121">Internal server error creating media for user.</span></span>

<span data-ttu-id="c6d1c-122">Es importante tener en cuenta que el informe de lista de errores no ofrece una forma sencilla de recuperar directamente una lista de todos los usuarios que participaron en al menos una sesión con errores, ni tampoco proporciona una forma de determinar qué usuarios han participado con mayor frecuencia en un error sesión.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-122">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="c6d1c-123">(Por un lado, el informe de lista de errores no tiene funciones de filtrado). Sin embargo, si exporta los datos y, a continuación, los convierte en un archivo de valores separados por comas, puede usar Windows PowerShell para buscar las respuestas a preguntas como esas.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-123">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="c6d1c-124">Por ejemplo, supongamos que guarda los datos en un. Archivo CSV denominado C:\\Data\\Failure\_List. csv.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-124">For example, suppose you save the data to a .CSV file named C:\\Data\\Failure\_List.csv.</span></span> <span data-ttu-id="c6d1c-125">En función de los datos guardados en ese archivo, este comando enumera todos los usuarios que participaron en al menos una sesión con errores:</span><span class="sxs-lookup"><span data-stu-id="c6d1c-125">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span>

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

<span data-ttu-id="c6d1c-126">Ese comando devolverá una lista similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="c6d1c-126">That command will return a list similar to this:</span></span>

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

<span data-ttu-id="c6d1c-127">Estos dos comandos devuelven el número total de sesiones con errores en las que cada usuario participó:</span><span class="sxs-lookup"><span data-stu-id="c6d1c-127">These two commands report back the total number of failed sessions that each user was involved in:</span></span>

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

<span data-ttu-id="c6d1c-128">Devolverá unos datos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="c6d1c-128">That will return data similar to this:</span></span>

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c6d1c-129">Filtros</span><span class="sxs-lookup"><span data-stu-id="c6d1c-129">Filters</span></span>

<span data-ttu-id="c6d1c-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-130">None.</span></span> <span data-ttu-id="c6d1c-131">No se puede filtrar el informe de lista de errores.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-131">You cannot filter the Failure List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="c6d1c-132">Métricas</span><span class="sxs-lookup"><span data-stu-id="c6d1c-132">Metrics</span></span>

<span data-ttu-id="c6d1c-133">En la siguiente tabla se muestra la información proporcionada en el informe de lista de errores para cada llamada con errores.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-133">The following table lists the information provided in the Failure List Report for each failed call.</span></span>

### <a name="failure-list-report-metrics"></a><span data-ttu-id="c6d1c-134">Métricas del informe de lista de errores</span><span class="sxs-lookup"><span data-stu-id="c6d1c-134">Failure List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6d1c-135">Nombre</span><span class="sxs-lookup"><span data-stu-id="c6d1c-135">Name</span></span></th>
<th><span data-ttu-id="c6d1c-136">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="c6d1c-136">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c6d1c-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="c6d1c-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6d1c-138"><strong>Hora de notificación</strong></span><span class="sxs-lookup"><span data-stu-id="c6d1c-138"><strong>Reported time</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d1c-139">No</span><span class="sxs-lookup"><span data-stu-id="c6d1c-139">No</span></span></p></td>
<td><p><span data-ttu-id="c6d1c-140">Fecha y hora en que se registró el informe.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-140">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d1c-141"><strong>Solicitud</strong></span><span class="sxs-lookup"><span data-stu-id="c6d1c-141"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d1c-142">No</span><span class="sxs-lookup"><span data-stu-id="c6d1c-142">No</span></span></p></td>
<td><p><span data-ttu-id="c6d1c-143">Tipo de solicitud SIP fallida.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-143">SIP request type that failed.</span></span> <span data-ttu-id="c6d1c-144">Por ejemplo, INVITE o BYE.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-144">For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d1c-145"><strong>Código de respuesta</strong></span><span class="sxs-lookup"><span data-stu-id="c6d1c-145"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d1c-146">No</span><span class="sxs-lookup"><span data-stu-id="c6d1c-146">No</span></span></p></td>
<td><p><span data-ttu-id="c6d1c-147">Código de respuesta SIP enviado cuando la conferencia ha fallado.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-147">SIP response code sent when the conference failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d1c-148"><strong>Id. de diagnóstico</strong></span><span class="sxs-lookup"><span data-stu-id="c6d1c-148"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d1c-149">No</span><span class="sxs-lookup"><span data-stu-id="c6d1c-149">No</span></span></p></td>
<td><p><span data-ttu-id="c6d1c-150">Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-150">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d1c-151"><strong>Tiempo de costo de combinación (MS)</strong></span><span class="sxs-lookup"><span data-stu-id="c6d1c-151"><strong>Join cost time (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d1c-152">No</span><span class="sxs-lookup"><span data-stu-id="c6d1c-152">No</span></span></p></td>
<td><p><span data-ttu-id="c6d1c-153">Cantidad de tiempo (en milisegundos) que necesita el usuario para unirse a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-153">Amount of time (in milliseconds) required for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d1c-154"><strong>Remitente</strong></span><span class="sxs-lookup"><span data-stu-id="c6d1c-154"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d1c-155">No</span><span class="sxs-lookup"><span data-stu-id="c6d1c-155">No</span></span></p></td>
<td><p><span data-ttu-id="c6d1c-156">Dirección SIP del usuario que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-156">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d1c-157"><strong>Agente de remitente</strong></span><span class="sxs-lookup"><span data-stu-id="c6d1c-157"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d1c-158">No</span><span class="sxs-lookup"><span data-stu-id="c6d1c-158">No</span></span></p></td>
<td><p><span data-ttu-id="c6d1c-159">Software usado por el extremo del usuario que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-159">Software used by the endpoint of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d1c-160"><strong>Destinatario</strong></span><span class="sxs-lookup"><span data-stu-id="c6d1c-160"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d1c-161">No</span><span class="sxs-lookup"><span data-stu-id="c6d1c-161">No</span></span></p></td>
<td><p><span data-ttu-id="c6d1c-162">Dirección SIP del usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="c6d1c-162">SIP address of the user who was being called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

