---
title: Tabla SIPResponseMetaData
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: El SIPResponseMetaDataTable contiene una lista de los códigos de respuesta SIP y la clasificación y la definición de cada uno de estos códigos. Estos códigos se generan en respuesta a eventos que ello afecte a los dispositivos SIP y SIP sesiones de comunicación; Por ejemplo, se genera el código de respuesta 403 cuando un dispositivo SIP realiza una solicitud, pero el servidor no acepta aceptar dicha solicitud.
ms.openlocfilehash: 7b60ffff90434c341fcf15fb75ddc93ac9f26201
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878213"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="2a20b-104">Tabla SIPResponseMetaData</span><span class="sxs-lookup"><span data-stu-id="2a20b-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="2a20b-105">El SIPResponseMetaDataTable contiene una lista de los códigos de respuesta SIP y la clasificación y la definición de cada uno de estos códigos.</span><span class="sxs-lookup"><span data-stu-id="2a20b-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="2a20b-106">Estos códigos se generan en respuesta a eventos que ello afecte a los dispositivos SIP y SIP sesiones de comunicación; Por ejemplo, se genera el código de respuesta 403 cuando un dispositivo SIP realiza una solicitud, pero el servidor no acepta aceptar dicha solicitud.</span><span class="sxs-lookup"><span data-stu-id="2a20b-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="2a20b-107">En esta tabla se introdujo en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2a20b-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="2a20b-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="2a20b-108">**Column**</span></span>|<span data-ttu-id="2a20b-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="2a20b-109">**Data Type**</span></span>|<span data-ttu-id="2a20b-110">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="2a20b-110">**Key/Index**</span></span>|<span data-ttu-id="2a20b-111">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="2a20b-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2a20b-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="2a20b-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="2a20b-113">int</span><span class="sxs-lookup"><span data-stu-id="2a20b-113">int</span></span>  <br/> |<span data-ttu-id="2a20b-114">Primary</span><span class="sxs-lookup"><span data-stu-id="2a20b-114">Primary</span></span>  <br/> |<span data-ttu-id="2a20b-115">Valor numérico que representa el código de respuesta SIP.</span><span class="sxs-lookup"><span data-stu-id="2a20b-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="2a20b-116">**Clase**</span><span class="sxs-lookup"><span data-stu-id="2a20b-116">**Class**</span></span> <br/> |<span data-ttu-id="2a20b-117">int</span><span class="sxs-lookup"><span data-stu-id="2a20b-117">int</span></span>  <br/> || <span data-ttu-id="2a20b-118">Criterios generales de clasificación para el código de respuesta.</span><span class="sxs-lookup"><span data-stu-id="2a20b-118">General classification for the response code.</span></span> <span data-ttu-id="2a20b-119">Clasificaciones de incluyen:</span><span class="sxs-lookup"><span data-stu-id="2a20b-119">Classifications include:</span></span> <br/>  <span data-ttu-id="2a20b-120">1 - respuestas de tipo informativo</span><span class="sxs-lookup"><span data-stu-id="2a20b-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="2a20b-121">2 - respuestas correctas</span><span class="sxs-lookup"><span data-stu-id="2a20b-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="2a20b-122">3 - las respuestas de redirección</span><span class="sxs-lookup"><span data-stu-id="2a20b-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="2a20b-123">4 - respuestas de error cliente</span><span class="sxs-lookup"><span data-stu-id="2a20b-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="2a20b-124">5--Respuestas de error de servidor</span><span class="sxs-lookup"><span data-stu-id="2a20b-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="2a20b-125">6 - respuesta de error global</span><span class="sxs-lookup"><span data-stu-id="2a20b-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="2a20b-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2a20b-126">**Description**</span></span> <br/> |<span data-ttu-id="2a20b-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2a20b-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="2a20b-128">Descripción del código de respuesta SIP.</span><span class="sxs-lookup"><span data-stu-id="2a20b-128">Description of the SIP response code.</span></span> <span data-ttu-id="2a20b-129">Por ejemplo, el código de respuesta 181 tiene la siguiente descripción:</span><span class="sxs-lookup"><span data-stu-id="2a20b-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="2a20b-130">Se está desviando la llamada</span><span class="sxs-lookup"><span data-stu-id="2a20b-130">Call Is Being Forwarded</span></span>  <br/> |
   

