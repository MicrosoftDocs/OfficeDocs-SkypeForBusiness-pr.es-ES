---
title: Tabla SIPResponseMetaData
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable contiene una lista de los códigos de respuesta SIP y la clasificación y definición de cada uno de estos códigos. Estos códigos se generan como respuesta a los eventos que afectan a los dispositivos SIP y a las sesiones de comunicación SIP; por ejemplo, se genera el código de respuesta 403 cuando un dispositivo SIP realiza una solicitud, pero el servidor rechaza responderla.
ms.openlocfilehash: 3d6714e9c5b5c154d19381fad33821b02ec8a73e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809930"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="ad9d2-104">Tabla SIPResponseMetaData</span><span class="sxs-lookup"><span data-stu-id="ad9d2-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="ad9d2-p102">SIPResponseMetaDataTable contiene una lista de los códigos de respuesta SIP y la clasificación y definición de cada uno de estos códigos. Estos códigos se generan como respuesta a los eventos que afectan a los dispositivos SIP y a las sesiones de comunicación SIP; por ejemplo, se genera el código de respuesta 403 cuando un dispositivo SIP realiza una solicitud, pero el servidor rechaza responderla.</span><span class="sxs-lookup"><span data-stu-id="ad9d2-p102">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes. These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="ad9d2-107">Esta tabla se introdujo en Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ad9d2-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="ad9d2-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ad9d2-108">**Column**</span></span>|<span data-ttu-id="ad9d2-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="ad9d2-109">**Data Type**</span></span>|<span data-ttu-id="ad9d2-110">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="ad9d2-110">**Key/Index**</span></span>|<span data-ttu-id="ad9d2-111">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="ad9d2-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ad9d2-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="ad9d2-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="ad9d2-113">entero</span><span class="sxs-lookup"><span data-stu-id="ad9d2-113">int</span></span>  <br/> |<span data-ttu-id="ad9d2-114">Principal</span><span class="sxs-lookup"><span data-stu-id="ad9d2-114">Primary</span></span>  <br/> |<span data-ttu-id="ad9d2-115">Valor numérico que representa el código de respuesta SIP.</span><span class="sxs-lookup"><span data-stu-id="ad9d2-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="ad9d2-116">**Class**</span><span class="sxs-lookup"><span data-stu-id="ad9d2-116">**Class**</span></span> <br/> |<span data-ttu-id="ad9d2-117">entero</span><span class="sxs-lookup"><span data-stu-id="ad9d2-117">int</span></span>  <br/> || <span data-ttu-id="ad9d2-p103">Clasificación general para el código de respuesta. Las clasificaciones incluyen:</span><span class="sxs-lookup"><span data-stu-id="ad9d2-p103">General classification for the response code. Classifications include:</span></span> <br/>  <span data-ttu-id="ad9d2-120">1- Respuestas informativos</span><span class="sxs-lookup"><span data-stu-id="ad9d2-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="ad9d2-121">2- Respuestas correctas</span><span class="sxs-lookup"><span data-stu-id="ad9d2-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="ad9d2-122">3- Respuestas de redirección</span><span class="sxs-lookup"><span data-stu-id="ad9d2-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="ad9d2-123">4- Respuestas de error de cliente</span><span class="sxs-lookup"><span data-stu-id="ad9d2-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="ad9d2-124">5-- Respuestas de error del servidor</span><span class="sxs-lookup"><span data-stu-id="ad9d2-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="ad9d2-125">6- Respuesta de error global</span><span class="sxs-lookup"><span data-stu-id="ad9d2-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="ad9d2-126">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ad9d2-126">**Description**</span></span> <br/> |<span data-ttu-id="ad9d2-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ad9d2-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="ad9d2-p104">Descripción del código de respuesta SIP. Por ejemplo, el código de respuesta 181 tiene la siguiente descripción:</span><span class="sxs-lookup"><span data-stu-id="ad9d2-p104">Description of the SIP response code. For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="ad9d2-130">Se está desviando la llamada</span><span class="sxs-lookup"><span data-stu-id="ad9d2-130">Call Is Being Forwarded</span></span>  <br/> |
   

