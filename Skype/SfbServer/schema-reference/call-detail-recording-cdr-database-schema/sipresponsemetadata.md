---
title: Tabla SIPResponseMetaData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: El SIPResponseMetaDataTable contiene una lista de los códigos de respuesta SIP y la clasificación y la definición de cada uno de estos códigos. Estos códigos se generan en respuesta a eventos que ello afecte a los dispositivos SIP y SIP sesiones de comunicación; Por ejemplo, se genera el código de respuesta 403 cuando un dispositivo SIP realiza una solicitud, pero el servidor no acepta aceptar dicha solicitud.
ms.openlocfilehash: edd1f4e60376b367f701864ff15d334c4d971e47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930292"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="e5246-104">Tabla SIPResponseMetaData</span><span class="sxs-lookup"><span data-stu-id="e5246-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="e5246-105">El SIPResponseMetaDataTable contiene una lista de los códigos de respuesta SIP y la clasificación y la definición de cada uno de estos códigos.</span><span class="sxs-lookup"><span data-stu-id="e5246-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="e5246-106">Estos códigos se generan en respuesta a eventos que ello afecte a los dispositivos SIP y SIP sesiones de comunicación; Por ejemplo, se genera el código de respuesta 403 cuando un dispositivo SIP realiza una solicitud, pero el servidor no acepta aceptar dicha solicitud.</span><span class="sxs-lookup"><span data-stu-id="e5246-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="e5246-107">En esta tabla se introdujo en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e5246-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="e5246-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e5246-108">**Column**</span></span>|<span data-ttu-id="e5246-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e5246-109">**Data Type**</span></span>|<span data-ttu-id="e5246-110">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="e5246-110">**Key/Index**</span></span>|<span data-ttu-id="e5246-111">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="e5246-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e5246-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="e5246-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="e5246-113">int</span><span class="sxs-lookup"><span data-stu-id="e5246-113">int</span></span>  <br/> |<span data-ttu-id="e5246-114">Primary</span><span class="sxs-lookup"><span data-stu-id="e5246-114">Primary</span></span>  <br/> |<span data-ttu-id="e5246-115">Valor numérico que representa el código de respuesta SIP.</span><span class="sxs-lookup"><span data-stu-id="e5246-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="e5246-116">**Clase**</span><span class="sxs-lookup"><span data-stu-id="e5246-116">**Class**</span></span> <br/> |<span data-ttu-id="e5246-117">int</span><span class="sxs-lookup"><span data-stu-id="e5246-117">int</span></span>  <br/> || <span data-ttu-id="e5246-118">Criterios generales de clasificación para el código de respuesta.</span><span class="sxs-lookup"><span data-stu-id="e5246-118">General classification for the response code.</span></span> <span data-ttu-id="e5246-119">Clasificaciones de incluyen:</span><span class="sxs-lookup"><span data-stu-id="e5246-119">Classifications include:</span></span> <br/>  <span data-ttu-id="e5246-120">1 - respuestas de tipo informativo</span><span class="sxs-lookup"><span data-stu-id="e5246-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="e5246-121">2 - respuestas correctas</span><span class="sxs-lookup"><span data-stu-id="e5246-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="e5246-122">3 - las respuestas de redirección</span><span class="sxs-lookup"><span data-stu-id="e5246-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="e5246-123">4 - respuestas de error cliente</span><span class="sxs-lookup"><span data-stu-id="e5246-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="e5246-124">5--Respuestas de error de servidor</span><span class="sxs-lookup"><span data-stu-id="e5246-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="e5246-125">6 - respuesta de error global</span><span class="sxs-lookup"><span data-stu-id="e5246-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="e5246-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e5246-126">**Description**</span></span> <br/> |<span data-ttu-id="e5246-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5246-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="e5246-128">Descripción del código de respuesta SIP.</span><span class="sxs-lookup"><span data-stu-id="e5246-128">Description of the SIP response code.</span></span> <span data-ttu-id="e5246-129">Por ejemplo, el código de respuesta 181 tiene la siguiente descripción:</span><span class="sxs-lookup"><span data-stu-id="e5246-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="e5246-130">Se está desviando la llamada</span><span class="sxs-lookup"><span data-stu-id="e5246-130">Call Is Being Forwarded</span></span>  <br/> |
   

