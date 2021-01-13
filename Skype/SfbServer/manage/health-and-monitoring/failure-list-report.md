---
title: Informe de lista de errores en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Resumen: obtenga información sobre el informe de lista de errores en Skype Empresarial Server.'
ms.openlocfilehash: 48654ee827f0d7efcb50bcccc4e1d2f3fdb5422e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816850"
---
# <a name="failure-list-report-in-skype-for-business-server"></a><span data-ttu-id="cf899-103">Informe de lista de errores en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="cf899-103">Failure List Report in Skype for Business Server</span></span> 
 
<span data-ttu-id="cf899-104">**Resumen:** Obtenga información sobre el informe de lista de errores en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="cf899-104">**Summary:** Learn about the Failure List Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="cf899-105">El informe de lista de errores proporciona información sobre los participantes individuales que participaron en una sesión punto a punto o de conferencia con errores.</span><span class="sxs-lookup"><span data-stu-id="cf899-105">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session.</span></span> <span data-ttu-id="cf899-106">Esta información incluye el URI del usuario que experimentó el problema, así como el código de respuesta SIP y el id. de diagnóstico asociado al error.</span><span class="sxs-lookup"><span data-stu-id="cf899-106">This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>
  
## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="cf899-107">Acceso al informe de lista de errores</span><span class="sxs-lookup"><span data-stu-id="cf899-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="cf899-108">Para obtener acceso al informe de lista de errores, haga clic en cualquiera de las métricas siguientes en el informe de distribución de errores [de Skype Empresarial Server:](failure-distribution-report.md)</span><span class="sxs-lookup"><span data-stu-id="cf899-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Skype for Business Server](failure-distribution-report.md):</span></span>
  
- <span data-ttu-id="cf899-109">Motivos del diagnóstico principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="cf899-109">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="cf899-110">Modalidades principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="cf899-110">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="cf899-111">Grupos principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="cf899-111">Top pools (sessions)</span></span>
    
- <span data-ttu-id="cf899-112">Fuentes principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="cf899-112">Top sources (sessions)</span></span>
    
- <span data-ttu-id="cf899-113">Componentes principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="cf899-113">Top components (sessions)</span></span>
    
- <span data-ttu-id="cf899-114">Usuarios de origen principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="cf899-114">Top from users (sessions)</span></span>
    
- <span data-ttu-id="cf899-115">Usuarios de destino principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="cf899-115">Top to users (sessions)</span></span>
    
- <span data-ttu-id="cf899-116">Agentes de usuarios de origen principales (sesiones)</span><span class="sxs-lookup"><span data-stu-id="cf899-116">Top from user agents (sessions)</span></span>
    
<span data-ttu-id="cf899-117">Desde el informe de lista de errores puede obtener acceso al informe de detalles de sesiones punto a punto en [Skype Empresarial Server](peer-to-peer-session-detail-report.md) haciendo clic en la métrica de detalles de sesión de una sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="cf899-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="cf899-118">También puede obtener acceso al Informe de detalles de conferencia haciendo clic en la métrica Conferencia de una conferencia.</span><span class="sxs-lookup"><span data-stu-id="cf899-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>
  
## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="cf899-119">Aprovechar al máximo el informe de lista de errores</span><span class="sxs-lookup"><span data-stu-id="cf899-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="cf899-120">En el Informe de lista de errores, puede ver una descripción de cada código de respuesta o cada identificador de diagnóstico simplemente manteniendo el mouse sobre ese valor.</span><span class="sxs-lookup"><span data-stu-id="cf899-120">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value.</span></span> <span data-ttu-id="cf899-121">Por ejemplo, si mantienes el mouse sobre el Identificador de diagnóstico 7025, verás lo siguiente en una información sobre herramientas:</span><span class="sxs-lookup"><span data-stu-id="cf899-121">For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>
  
<span data-ttu-id="cf899-122">Error interno del servidor al crear medios para el usuario.</span><span class="sxs-lookup"><span data-stu-id="cf899-122">Internal server error creating media for user.</span></span>
  
<span data-ttu-id="cf899-123">Es importante tener en cuenta que el informe de lista de errores no proporciona una forma sencilla de recuperar directamente una lista de todos los usuarios que participaron en al menos una sesión con errores, ni proporciona una forma de determinar qué usuarios participaron con más frecuencia en una sesión con errores.</span><span class="sxs-lookup"><span data-stu-id="cf899-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="cf899-124">(Por un lado, el informe de lista de errores no tiene capacidades de filtrado). Sin embargo, si exporta los datos y los convierte en un archivo de valores separados por comas, puede usar Windows PowerShell para encontrar las respuestas a preguntas como estas.</span><span class="sxs-lookup"><span data-stu-id="cf899-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="cf899-125">Por ejemplo, supongamos que guarda los datos en un archivo . Archivo CSV denominado C:\Data\Failure_List.csv.</span><span class="sxs-lookup"><span data-stu-id="cf899-125">For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv.</span></span> <span data-ttu-id="cf899-126">En función de los datos guardados en ese archivo, este comando enumera todos los usuarios que participaron en al menos una sesión con errores:</span><span class="sxs-lookup"><span data-stu-id="cf899-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span> 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

<span data-ttu-id="cf899-127">Ese comando devolverá una lista similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf899-127">That command will return a list similar to this:</span></span>
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

<span data-ttu-id="cf899-128">Estos dos comandos informan del número total de sesiones con errores en las que participó cada usuario:</span><span class="sxs-lookup"><span data-stu-id="cf899-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

<span data-ttu-id="cf899-129">Devolverá unos datos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="cf899-129">That will return data similar to this:</span></span>
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a><span data-ttu-id="cf899-130">Filtros</span><span class="sxs-lookup"><span data-stu-id="cf899-130">Filters</span></span>

<span data-ttu-id="cf899-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cf899-131">None.</span></span> <span data-ttu-id="cf899-132">No puede filtrar el informe de lista de errores.</span><span class="sxs-lookup"><span data-stu-id="cf899-132">You cannot filter the Failure List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="cf899-133">Métricas</span><span class="sxs-lookup"><span data-stu-id="cf899-133">Metrics</span></span>

<span data-ttu-id="cf899-134">En la tabla siguiente se muestra la información proporcionada en el informe de lista de errores para cada llamada con errores.</span><span class="sxs-lookup"><span data-stu-id="cf899-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>
  
<span data-ttu-id="cf899-135">**Métricas del informe de lista de errores**</span><span class="sxs-lookup"><span data-stu-id="cf899-135">**Failure List Report Metrics**</span></span>

|<span data-ttu-id="cf899-136">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="cf899-136">**Name**</span></span>|<span data-ttu-id="cf899-137">**¿Se pueden ordenar los datos en este elemento?**</span><span class="sxs-lookup"><span data-stu-id="cf899-137">**Can you sort on this item?**</span></span>|<span data-ttu-id="cf899-138">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="cf899-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cf899-139">**Hora notificada**</span><span class="sxs-lookup"><span data-stu-id="cf899-139">**Reported time**</span></span> <br/> |<span data-ttu-id="cf899-140">No</span><span class="sxs-lookup"><span data-stu-id="cf899-140">No</span></span>  <br/> |<span data-ttu-id="cf899-141">Fecha y hora en que se registró el informe.</span><span class="sxs-lookup"><span data-stu-id="cf899-141">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="cf899-142">**Solicitud**</span><span class="sxs-lookup"><span data-stu-id="cf899-142">**Request**</span></span> <br/> |<span data-ttu-id="cf899-143">No</span><span class="sxs-lookup"><span data-stu-id="cf899-143">No</span></span>  <br/> |<span data-ttu-id="cf899-144">Tipo de solicitud SIP con error.</span><span class="sxs-lookup"><span data-stu-id="cf899-144">SIP request type that failed.</span></span> <span data-ttu-id="cf899-145">Por ejemplo, INVITE o BYE.</span><span class="sxs-lookup"><span data-stu-id="cf899-145">For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="cf899-146">**Código de respuesta**</span><span class="sxs-lookup"><span data-stu-id="cf899-146">**Response code**</span></span> <br/> |<span data-ttu-id="cf899-147">No</span><span class="sxs-lookup"><span data-stu-id="cf899-147">No</span></span>  <br/> |<span data-ttu-id="cf899-148">Código de respuesta SIP enviado cuando la conferencia ha fallado.</span><span class="sxs-lookup"><span data-stu-id="cf899-148">SIP response code sent when the conference failed.</span></span>  <br/> |
|<span data-ttu-id="cf899-149">**Id. de diagnóstico**</span><span class="sxs-lookup"><span data-stu-id="cf899-149">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="cf899-150">No</span><span class="sxs-lookup"><span data-stu-id="cf899-150">No</span></span>  <br/> |<span data-ttu-id="cf899-151">Identificador único (con formato de encabezado de ms-diagnostics) adjunto a un mensaje SIP que a menudo aporta información útil para solucionar errores.</span><span class="sxs-lookup"><span data-stu-id="cf899-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="cf899-152">**Tiempo de costo de unión (ms)**</span><span class="sxs-lookup"><span data-stu-id="cf899-152">**Join cost time (ms)**</span></span> <br/> |<span data-ttu-id="cf899-153">No</span><span class="sxs-lookup"><span data-stu-id="cf899-153">No</span></span>  <br/> |<span data-ttu-id="cf899-154">Cantidad de tiempo (en milisegundos) necesario para que el usuario se una a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="cf899-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="cf899-155">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="cf899-155">**From user**</span></span> <br/> |<span data-ttu-id="cf899-156">No</span><span class="sxs-lookup"><span data-stu-id="cf899-156">No</span></span>  <br/> |<span data-ttu-id="cf899-157">Dirección SIP del usuario que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="cf899-157">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="cf899-158">**Agente de remitente**</span><span class="sxs-lookup"><span data-stu-id="cf899-158">**From user agent**</span></span> <br/> |<span data-ttu-id="cf899-159">No</span><span class="sxs-lookup"><span data-stu-id="cf899-159">No</span></span>  <br/> |<span data-ttu-id="cf899-160">Software usado por el punto de conexión del usuario que inició la llamada.</span><span class="sxs-lookup"><span data-stu-id="cf899-160">Software used by the endpoint of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="cf899-161">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="cf899-161">**To user**</span></span> <br/> |<span data-ttu-id="cf899-162">No</span><span class="sxs-lookup"><span data-stu-id="cf899-162">No</span></span>  <br/> |<span data-ttu-id="cf899-163">Dirección SIP del usuario al que se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="cf899-163">SIP address of the user who was being called.</span></span>  <br/> |
   

