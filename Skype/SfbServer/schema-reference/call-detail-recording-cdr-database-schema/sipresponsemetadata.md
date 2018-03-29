---
title: Tabla SIPResponseMetaData
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: El SIPResponseMetaDataTable contiene una lista de códigos de respuesta SIP y la clasificación y la definición de cada uno de dichos códigos. Estos códigos se generan en respuesta a los eventos que afectan a los dispositivos SIP y SIP sesiones de comunicación; Por ejemplo, el código de respuesta 403 se genera cuando un dispositivo SIP realiza una solicitud, pero el servidor rechaza atender esa solicitud.
ms.openlocfilehash: a90a248837dd705746fe3b342874aad10480e8a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="9d993-104">Tabla SIPResponseMetaData</span><span class="sxs-lookup"><span data-stu-id="9d993-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="9d993-105">El SIPResponseMetaDataTable contiene una lista de códigos de respuesta SIP y la clasificación y la definición de cada uno de dichos códigos.</span><span class="sxs-lookup"><span data-stu-id="9d993-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="9d993-106">Estos códigos se generan en respuesta a los eventos que afectan a los dispositivos SIP y SIP sesiones de comunicación; Por ejemplo, el código de respuesta 403 se genera cuando un dispositivo SIP realiza una solicitud, pero el servidor rechaza atender esa solicitud.</span><span class="sxs-lookup"><span data-stu-id="9d993-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="9d993-107">Esta tabla se introdujo en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d993-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="9d993-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9d993-108">**Column**</span></span>|<span data-ttu-id="9d993-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9d993-109">**Data Type**</span></span>|<span data-ttu-id="9d993-110">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="9d993-110">**Key/Index**</span></span>|<span data-ttu-id="9d993-111">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="9d993-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9d993-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="9d993-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="9d993-113">int</span><span class="sxs-lookup"><span data-stu-id="9d993-113">int</span></span>  <br/> |<span data-ttu-id="9d993-114">Primary</span><span class="sxs-lookup"><span data-stu-id="9d993-114">Primary</span></span>  <br/> |<span data-ttu-id="9d993-115">Valor numérico que representa el código de respuesta SIP.</span><span class="sxs-lookup"><span data-stu-id="9d993-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="9d993-116">**Clase**</span><span class="sxs-lookup"><span data-stu-id="9d993-116">**Class**</span></span> <br/> |<span data-ttu-id="9d993-117">int</span><span class="sxs-lookup"><span data-stu-id="9d993-117">int</span></span>  <br/> || <span data-ttu-id="9d993-118">Criterios generales de clasificación para el código de respuesta.</span><span class="sxs-lookup"><span data-stu-id="9d993-118">General classification for the response code.</span></span> <span data-ttu-id="9d993-119">Las clasificaciones son:</span><span class="sxs-lookup"><span data-stu-id="9d993-119">Classifications include:</span></span> <br/>  <span data-ttu-id="9d993-120">1 - respuestas informativas</span><span class="sxs-lookup"><span data-stu-id="9d993-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="9d993-121">2 - correcta respuestas</span><span class="sxs-lookup"><span data-stu-id="9d993-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="9d993-122">3 - las respuestas de redirección</span><span class="sxs-lookup"><span data-stu-id="9d993-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="9d993-123">4 - respuestas de error cliente</span><span class="sxs-lookup"><span data-stu-id="9d993-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="9d993-124">5--Respuestas de error de servidor</span><span class="sxs-lookup"><span data-stu-id="9d993-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="9d993-125">6 - respuesta de error global</span><span class="sxs-lookup"><span data-stu-id="9d993-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="9d993-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9d993-126">**Description**</span></span> <br/> |<span data-ttu-id="9d993-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9d993-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="9d993-128">Descripción del código de respuesta SIP.</span><span class="sxs-lookup"><span data-stu-id="9d993-128">Description of the SIP response code.</span></span> <span data-ttu-id="9d993-129">Por ejemplo, el código de respuesta 181 tiene la siguiente descripción:</span><span class="sxs-lookup"><span data-stu-id="9d993-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="9d993-130">Llamada se está reenviando</span><span class="sxs-lookup"><span data-stu-id="9d993-130">Call Is Being Forwarded</span></span>  <br/> |
   

