---
title: Borrar caché
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Resumen: Obtenga información sobre la operación Borrar caché, que forma parte de la API de datos para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 38648e1a910f93a30bd6da8807321acad0330e62
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274838"
---
# <a name="clear-cache"></a><span data-ttu-id="926a0-104">Borrar caché</span><span class="sxs-lookup"><span data-stu-id="926a0-104">Clear Cache</span></span>
 
<span data-ttu-id="926a0-105">**Resumen:** Obtenga información sobre la operación Borrar caché, que forma parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="926a0-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="926a0-106">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="926a0-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="926a0-107">La operación Borrar caché es parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="926a0-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="926a0-108">Borrar caché</span><span class="sxs-lookup"><span data-stu-id="926a0-108">Clear Cache</span></span>

<span data-ttu-id="926a0-109">Operación de borrar caché elimina la caché del servidor de consultas y datos.</span><span class="sxs-lookup"><span data-stu-id="926a0-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="926a0-110">Esto restablecerá la memoria caché y recibirá datos nuevos de la actualización del cubo de QoE después para solicitudes nuevas.</span><span class="sxs-lookup"><span data-stu-id="926a0-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="926a0-111">**Método**</span><span class="sxs-lookup"><span data-stu-id="926a0-111">**Method**</span></span>|<span data-ttu-id="926a0-112">**Solicitar URI**</span><span class="sxs-lookup"><span data-stu-id="926a0-112">**Request URI**</span></span>|<span data-ttu-id="926a0-113">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="926a0-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="926a0-114">Exponer</span><span class="sxs-lookup"><span data-stu-id="926a0-114">POST</span></span>  <br/> |<span data-ttu-id="926a0-115">https://\<portal\>/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="926a0-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="926a0-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="926a0-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="926a0-117">**Parámetros de URI** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="926a0-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="926a0-118">**Solicitar encabezados** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="926a0-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="926a0-119">**Solicitar cuerpo** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="926a0-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="926a0-120">**Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="926a0-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="926a0-121">**Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).</span><span class="sxs-lookup"><span data-stu-id="926a0-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="926a0-122">**Encabezados de respuesta** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="926a0-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="926a0-123">**Cuerpo** de la respuesta: ninguno.</span><span class="sxs-lookup"><span data-stu-id="926a0-123">**Response Body** - None.</span></span>
  

