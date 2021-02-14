---
title: Borrar caché
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
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Resumen: obtenga información sobre la operación Borrar caché, que forma parte de la API de datos para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: c9b966bb1e35a5a6255cd75ea6c685daaf220a09
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806420"
---
# <a name="clear-cache"></a><span data-ttu-id="a1fe6-104">Borrar caché</span><span class="sxs-lookup"><span data-stu-id="a1fe6-104">Clear Cache</span></span>
 
<span data-ttu-id="a1fe6-105">**Resumen:** Obtenga información sobre la operación Borrar caché, que forma parte de la API de datos para el Panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a1fe6-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="a1fe6-106">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a1fe6-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a1fe6-107">La operación Borrar caché forma parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a1fe6-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="a1fe6-108">Borrar caché</span><span class="sxs-lookup"><span data-stu-id="a1fe6-108">Clear Cache</span></span>

<span data-ttu-id="a1fe6-109">La operación Borrar caché elimina la memoria caché del servidor para consultas y datos.</span><span class="sxs-lookup"><span data-stu-id="a1fe6-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="a1fe6-110">Esto restablecerá la memoria caché y se recibirán datos nuevos del cubo QoE posteriormente para las nuevas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="a1fe6-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="a1fe6-111">**Método**</span><span class="sxs-lookup"><span data-stu-id="a1fe6-111">**Method**</span></span>|<span data-ttu-id="a1fe6-112">**URI de solicitud**</span><span class="sxs-lookup"><span data-stu-id="a1fe6-112">**Request URI**</span></span>|<span data-ttu-id="a1fe6-113">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="a1fe6-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a1fe6-114">PUBLICAR</span><span class="sxs-lookup"><span data-stu-id="a1fe6-114">POST</span></span>  <br/> |<span data-ttu-id="a1fe6-115">https:// \<portal\> /QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="a1fe6-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="a1fe6-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="a1fe6-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="a1fe6-117">**Parámetros uri:** ninguno.</span><span class="sxs-lookup"><span data-stu-id="a1fe6-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="a1fe6-118">**Encabezados de solicitud:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="a1fe6-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a1fe6-119">**Cuerpo de la** solicitud: ninguno.</span><span class="sxs-lookup"><span data-stu-id="a1fe6-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="a1fe6-120">**Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="a1fe6-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="a1fe6-121">**Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto).</span><span class="sxs-lookup"><span data-stu-id="a1fe6-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="a1fe6-122">**Encabezados de respuesta:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="a1fe6-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a1fe6-123">**Cuerpo de la** respuesta: ninguno.</span><span class="sxs-lookup"><span data-stu-id="a1fe6-123">**Response Body** - None.</span></span>
  

