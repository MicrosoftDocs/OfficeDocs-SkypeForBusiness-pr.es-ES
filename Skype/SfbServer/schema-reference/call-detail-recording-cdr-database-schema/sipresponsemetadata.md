---
title: Tabla SIPResponseMetaData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: El SIPResponseMetaDataTable contiene una lista de códigos de respuesta SIP, así como la clasificación y la definición de cada uno de esos códigos. Estos códigos se generan en respuesta a los eventos que afectan a los dispositivos SIP y a las sesiones de comunicación SIP; por ejemplo, el código de respuesta 403 se genera cuando un dispositivo SIP realiza una solicitud, pero el servidor no acepta la solicitud.
ms.openlocfilehash: 2c302793dc9f9c53d445d231a261bf43a0c385df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814898"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="0ed8f-104">Tabla SIPResponseMetaData</span><span class="sxs-lookup"><span data-stu-id="0ed8f-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="0ed8f-105">El SIPResponseMetaDataTable contiene una lista de códigos de respuesta SIP, así como la clasificación y la definición de cada uno de esos códigos.</span><span class="sxs-lookup"><span data-stu-id="0ed8f-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="0ed8f-106">Estos códigos se generan en respuesta a los eventos que afectan a los dispositivos SIP y a las sesiones de comunicación SIP; por ejemplo, el código de respuesta 403 se genera cuando un dispositivo SIP realiza una solicitud, pero el servidor no acepta la solicitud.</span><span class="sxs-lookup"><span data-stu-id="0ed8f-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="0ed8f-107">Esta tabla fue introducida en Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0ed8f-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="0ed8f-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="0ed8f-108">**Column**</span></span>|<span data-ttu-id="0ed8f-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0ed8f-109">**Data Type**</span></span>|<span data-ttu-id="0ed8f-110">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="0ed8f-110">**Key/Index**</span></span>|<span data-ttu-id="0ed8f-111">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="0ed8f-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0ed8f-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="0ed8f-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="0ed8f-113">int</span><span class="sxs-lookup"><span data-stu-id="0ed8f-113">int</span></span>  <br/> |<span data-ttu-id="0ed8f-114">Primary</span><span class="sxs-lookup"><span data-stu-id="0ed8f-114">Primary</span></span>  <br/> |<span data-ttu-id="0ed8f-115">Valor numérico que representa el código de respuesta SIP.</span><span class="sxs-lookup"><span data-stu-id="0ed8f-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="0ed8f-116">**Las**</span><span class="sxs-lookup"><span data-stu-id="0ed8f-116">**Class**</span></span> <br/> |<span data-ttu-id="0ed8f-117">int</span><span class="sxs-lookup"><span data-stu-id="0ed8f-117">int</span></span>  <br/> || <span data-ttu-id="0ed8f-118">Clasificación general para el código de respuesta.</span><span class="sxs-lookup"><span data-stu-id="0ed8f-118">General classification for the response code.</span></span> <span data-ttu-id="0ed8f-119">Las clasificaciones incluyen:</span><span class="sxs-lookup"><span data-stu-id="0ed8f-119">Classifications include:</span></span> <br/>  <span data-ttu-id="0ed8f-120">1-respuestas informativas</span><span class="sxs-lookup"><span data-stu-id="0ed8f-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="0ed8f-121">2-respuestas correctas</span><span class="sxs-lookup"><span data-stu-id="0ed8f-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="0ed8f-122">3-respuestas de redireccionamiento</span><span class="sxs-lookup"><span data-stu-id="0ed8f-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="0ed8f-123">4-respuestas de error de cliente</span><span class="sxs-lookup"><span data-stu-id="0ed8f-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="0ed8f-124">5--respuestas de error de servidor</span><span class="sxs-lookup"><span data-stu-id="0ed8f-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="0ed8f-125">6-respuesta de error global</span><span class="sxs-lookup"><span data-stu-id="0ed8f-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="0ed8f-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0ed8f-126">**Description**</span></span> <br/> |<span data-ttu-id="0ed8f-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0ed8f-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="0ed8f-128">Descripción del código de respuesta SIP.</span><span class="sxs-lookup"><span data-stu-id="0ed8f-128">Description of the SIP response code.</span></span> <span data-ttu-id="0ed8f-129">Por ejemplo, el código de respuesta 181 tiene la siguiente descripción:</span><span class="sxs-lookup"><span data-stu-id="0ed8f-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="0ed8f-130">La llamada se está reenviando</span><span class="sxs-lookup"><span data-stu-id="0ed8f-130">Call Is Being Forwarded</span></span>  <br/> |
   

