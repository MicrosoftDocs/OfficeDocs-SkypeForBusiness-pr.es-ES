---
title: Informe de lista de errores en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Resumen: Información sobre el informe de lista de errores en Skype para Business Server.'
ms.openlocfilehash: f286dfe288b82b1e8ab0f5b4956c4f75c5bd72a2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899613"
---
# <a name="failure-list-report-in-skype-for-business-server"></a><span data-ttu-id="5286d-103">Informe de lista de errores en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="5286d-103">Failure List Report in Skype for Business Server</span></span> 
 
<span data-ttu-id="5286d-104">**Resumen:** Obtenga información sobre el informe de lista de errores en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="5286d-104">**Summary:** Learn about the Failure List Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="5286d-p101">El informe de lista de errores proporciona información sobre los usuarios que participaron de una sesión punto a punto o de conferencia con errores. Esta información incluye el URI del usuario que experimentó el problema, además del código de respuesta SIP y el identificador de diagnóstico asociado al error.</span><span class="sxs-lookup"><span data-stu-id="5286d-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>
  
## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="5286d-107">Obtener acceso al informe de lista de errores</span><span class="sxs-lookup"><span data-stu-id="5286d-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="5286d-108">El informe de lista de errores se tiene acceso haciendo clic en cualquiera de las siguientes métricas en el [Informe de distribución de errores en Skype para Business Server](failure-distribution-report.md):</span><span class="sxs-lookup"><span data-stu-id="5286d-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Skype for Business Server](failure-distribution-report.md):</span></span>
  
- <span data-ttu-id="5286d-109">Principales motivos del diagnóstico (sesiones)</span><span class="sxs-lookup"><span data-stu-id="5286d-109">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="5286d-110">Principales modalidades (sesiones)</span><span class="sxs-lookup"><span data-stu-id="5286d-110">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="5286d-111">Principales grupos de servidores (sesiones)</span><span class="sxs-lookup"><span data-stu-id="5286d-111">Top pools (sessions)</span></span>
    
- <span data-ttu-id="5286d-112">Principales orígenes (sesiones)</span><span class="sxs-lookup"><span data-stu-id="5286d-112">Top sources (sessions)</span></span>
    
- <span data-ttu-id="5286d-113">Principales componentes (sesiones)</span><span class="sxs-lookup"><span data-stu-id="5286d-113">Top components (sessions)</span></span>
    
- <span data-ttu-id="5286d-114">Principales remitentes (sesiones)</span><span class="sxs-lookup"><span data-stu-id="5286d-114">Top from users (sessions)</span></span>
    
- <span data-ttu-id="5286d-115">Principales destinatarios (sesiones)</span><span class="sxs-lookup"><span data-stu-id="5286d-115">Top to users (sessions)</span></span>
    
- <span data-ttu-id="5286d-116">Principales agentes de remitente (sesiones)</span><span class="sxs-lookup"><span data-stu-id="5286d-116">Top from user agents (sessions)</span></span>
    
<span data-ttu-id="5286d-117">Desde el informe de lista de errores, puede acceder al [informe de detalles de la sesión de punto a punto en Skype para Business Server](peer-to-peer-session-detail-report.md) haciendo clic en la métrica de todos los detalles de la sesión de una sesión de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="5286d-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="5286d-118">También puede tener acceso al informe de detalles de conferencia si hace clic en la métrica Conferencia para una conferencia.</span><span class="sxs-lookup"><span data-stu-id="5286d-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>
  
## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="5286d-119">Aprovechar al máximo el informe de lista de errores</span><span class="sxs-lookup"><span data-stu-id="5286d-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="5286d-p103">En el informe de lista de errores, puede ver una descripción de cada código de respuesta o cada identificador de diagnóstico. Para ello, simplemente mantenga el mouse sobre ese valor. Por ejemplo, si coloca el mouse sobre el identificador de diagnóstico 7025, verá un mensaje similar al siguiente como información sobre herramientas:</span><span class="sxs-lookup"><span data-stu-id="5286d-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>
  
<span data-ttu-id="5286d-122">Error interno del servidor al crear medios para el usuario.</span><span class="sxs-lookup"><span data-stu-id="5286d-122">Internal server error creating media for user.</span></span>
  
<span data-ttu-id="5286d-123">Es importante tener en cuenta que el informe de lista de errores no ofrece una manera directa de recuperar una lista de todos los usuarios que participaron de al menos una sesión con errores, ni tampoco permite determinar qué usuarios participaron con más frecuencia en sesiones con errores.</span><span class="sxs-lookup"><span data-stu-id="5286d-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="5286d-124">(En primer lugar, el informe de lista de errores no tiene capacidad de filtrado). Sin embargo, si exporta los datos y, a continuación, se convierta en un archivo de valores separados por comas, se puede usar Windows PowerShell para encontrar las respuestas a preguntas como las.</span><span class="sxs-lookup"><span data-stu-id="5286d-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="5286d-125">Por ejemplo, supongamos que guarda los datos en un archivo .CSV con el nombre C:\Data\Failure_List.csv.</span><span class="sxs-lookup"><span data-stu-id="5286d-125">For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv.</span></span> <span data-ttu-id="5286d-126">De acuerdo con los datos guardados en ese archivo, este comando muestra todos los usuarios que participaron de al menos una sesión con errores:</span><span class="sxs-lookup"><span data-stu-id="5286d-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span> 
  
```
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

<span data-ttu-id="5286d-127">Ese comando devolverá una lista similar a esta:</span><span class="sxs-lookup"><span data-stu-id="5286d-127">That command will return a list similar to this:</span></span>
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

<span data-ttu-id="5286d-128">Estos dos comandos ofrecen información sobre el número total de sesiones con errores de las que participó cada usuario:</span><span class="sxs-lookup"><span data-stu-id="5286d-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>
  
```
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

<span data-ttu-id="5286d-129">Se devolverán datos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="5286d-129">That will return data similar to this:</span></span>
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a><span data-ttu-id="5286d-130">Filtros</span><span class="sxs-lookup"><span data-stu-id="5286d-130">Filters</span></span>

<span data-ttu-id="5286d-p105">Ninguno. No se puede filtrar el informe de lista de errores.</span><span class="sxs-lookup"><span data-stu-id="5286d-p105">None. You cannot filter the Failure List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="5286d-133">Métricas</span><span class="sxs-lookup"><span data-stu-id="5286d-133">Metrics</span></span>

<span data-ttu-id="5286d-134">En la siguiente tabla se detalla la información proporcionada en el informe de lista de errores para cada llamada con errores.</span><span class="sxs-lookup"><span data-stu-id="5286d-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>
  
<span data-ttu-id="5286d-135">**Métricas del informe de lista de errores**</span><span class="sxs-lookup"><span data-stu-id="5286d-135">**Failure List Report Metrics**</span></span>

|<span data-ttu-id="5286d-136">**Nombre.**</span><span class="sxs-lookup"><span data-stu-id="5286d-136">**Name**</span></span>|<span data-ttu-id="5286d-137">**¿Se pueden ordenar los datos por este elemento?**</span><span class="sxs-lookup"><span data-stu-id="5286d-137">**Can you sort on this item?**</span></span>|<span data-ttu-id="5286d-138">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5286d-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5286d-139">**Hora de notificación**</span><span class="sxs-lookup"><span data-stu-id="5286d-139">**Reported time**</span></span> <br/> |<span data-ttu-id="5286d-140">No</span><span class="sxs-lookup"><span data-stu-id="5286d-140">No</span></span>  <br/> |<span data-ttu-id="5286d-141">Fecha y hora en que se registró el informe.</span><span class="sxs-lookup"><span data-stu-id="5286d-141">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="5286d-142">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="5286d-142">**Request**</span></span> <br/> |<span data-ttu-id="5286d-143">No</span><span class="sxs-lookup"><span data-stu-id="5286d-143">No</span></span>  <br/> |<span data-ttu-id="5286d-p106">Tipo de solicitud SIP que presentó errores. Por ejemplo, INVITE o BYE.</span><span class="sxs-lookup"><span data-stu-id="5286d-p106">SIP request type that failed. For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="5286d-146">**Código de respuesta**</span><span class="sxs-lookup"><span data-stu-id="5286d-146">**Response code**</span></span> <br/> |<span data-ttu-id="5286d-147">No</span><span class="sxs-lookup"><span data-stu-id="5286d-147">No</span></span>  <br/> |<span data-ttu-id="5286d-148">Código de respuesta SIP enviado cuando se produjo un error en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="5286d-148">SIP response code sent when the conference failed.</span></span>  <br/> |
|<span data-ttu-id="5286d-149">**Id. de diagnóstico**</span><span class="sxs-lookup"><span data-stu-id="5286d-149">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="5286d-150">No</span><span class="sxs-lookup"><span data-stu-id="5286d-150">No</span></span>  <br/> |<span data-ttu-id="5286d-151">Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores.</span><span class="sxs-lookup"><span data-stu-id="5286d-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="5286d-152">**Tiempo coste de conexión (ms)**</span><span class="sxs-lookup"><span data-stu-id="5286d-152">**Join cost time (ms)**</span></span> <br/> |<span data-ttu-id="5286d-153">No</span><span class="sxs-lookup"><span data-stu-id="5286d-153">No</span></span>  <br/> |<span data-ttu-id="5286d-154">Cantidad de tiempo (en milisegundos) que necesitó el usuario para unirse a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="5286d-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="5286d-155">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="5286d-155">**From user**</span></span> <br/> |<span data-ttu-id="5286d-156">No</span><span class="sxs-lookup"><span data-stu-id="5286d-156">No</span></span>  <br/> |<span data-ttu-id="5286d-157">Dirección SIP del usuario que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="5286d-157">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="5286d-158">**Agente de remitente**</span><span class="sxs-lookup"><span data-stu-id="5286d-158">**From user agent**</span></span> <br/> |<span data-ttu-id="5286d-159">No</span><span class="sxs-lookup"><span data-stu-id="5286d-159">No</span></span>  <br/> |<span data-ttu-id="5286d-160">Software usado por el extremo del usuario que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="5286d-160">Software used by the endpoint of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="5286d-161">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="5286d-161">**To user**</span></span> <br/> |<span data-ttu-id="5286d-162">No</span><span class="sxs-lookup"><span data-stu-id="5286d-162">No</span></span>  <br/> |<span data-ttu-id="5286d-163">Dirección SIP del usuario que recibió la llamada.</span><span class="sxs-lookup"><span data-stu-id="5286d-163">SIP address of the user who was being called.</span></span>  <br/> |
   

