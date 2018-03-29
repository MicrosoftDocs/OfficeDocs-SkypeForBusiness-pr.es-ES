---
title: Borrar caché
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Resumen: Conozca la operación Borrar caché, que forma parte de la API de datos para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 2356997facfa0057f90ea3d6c8b4cda06add2615
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="clear-cache"></a><span data-ttu-id="5f386-104">Borrar caché</span><span class="sxs-lookup"><span data-stu-id="5f386-104">Clear Cache</span></span>
 
<span data-ttu-id="5f386-105">**Resumen:** Obtener información sobre la operación de borrar la caché, que forma parte de la API de datos para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="5f386-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="5f386-106">Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5f386-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5f386-107">La operación Borrar caché forma parte de la API de datos para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="5f386-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="5f386-108">Borrar caché</span><span class="sxs-lookup"><span data-stu-id="5f386-108">Clear Cache</span></span>

<span data-ttu-id="5f386-109">Operación de caché borrado elimina la caché en el servidor para consultas y datos.</span><span class="sxs-lookup"><span data-stu-id="5f386-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="5f386-110">Esto restablecerá la caché y le facilitaremos datos nuevos de cubo QoE posteriormente para las nuevas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="5f386-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="5f386-111">**Método**</span><span class="sxs-lookup"><span data-stu-id="5f386-111">**Method**</span></span>|<span data-ttu-id="5f386-112">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="5f386-112">**Request URI**</span></span>|<span data-ttu-id="5f386-113">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="5f386-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5f386-114">Exponer</span><span class="sxs-lookup"><span data-stu-id="5f386-114">POST</span></span>  <br/> |<span data-ttu-id="5f386-115">https://\<portal\>/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="5f386-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="5f386-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="5f386-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="5f386-117">**URI parámetros** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="5f386-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="5f386-118">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="5f386-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="5f386-119">**Cuerpo de la solicitud** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="5f386-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="5f386-120">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="5f386-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="5f386-121">**Código de estado** - una operación correcta devuelve el código de estado 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="5f386-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="5f386-122">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="5f386-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="5f386-123">**Cuerpo de la respuesta** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="5f386-123">**Response Body** - None.</span></span>
  

