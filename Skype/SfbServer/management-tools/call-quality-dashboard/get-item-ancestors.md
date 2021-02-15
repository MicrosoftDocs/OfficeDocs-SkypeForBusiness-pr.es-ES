---
title: Obtener predecesores del elemento
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
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Resumen: obtenga información sobre la operación Obtener antecesores de elemento, que forma parte del servicio de elementos. El servicio de elementos forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 59fcd10f620b32151346e8732e67ae6151a258ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832580"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="6c561-105">Obtener predecesores del elemento</span><span class="sxs-lookup"><span data-stu-id="6c561-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="6c561-106">**Resumen:** Obtenga información sobre la operación Obtener antecesores de elemento, que forma parte del servicio de elementos.</span><span class="sxs-lookup"><span data-stu-id="6c561-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="6c561-107">El servicio de elementos forma parte de la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6c561-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="6c561-108">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6c561-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="6c561-109">La operación Obtener antecesores de elemento forma parte del servicio de elementos en la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6c561-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="6c561-110">Obtener predecesores del elemento</span><span class="sxs-lookup"><span data-stu-id="6c561-110">Get Item Ancestors</span></span>

<span data-ttu-id="6c561-111">Obtener antecesores de elemento devuelve un elemento específico antecesor del repositorio.</span><span class="sxs-lookup"><span data-stu-id="6c561-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="6c561-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="6c561-112">**Method**</span></span>|<span data-ttu-id="6c561-113">**URI de solicitud**</span><span class="sxs-lookup"><span data-stu-id="6c561-113">**Request URI**</span></span>|<span data-ttu-id="6c561-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="6c561-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c561-115">GET</span><span class="sxs-lookup"><span data-stu-id="6c561-115">GET</span></span>  <br/> |<span data-ttu-id="6c561-116">https:// \<portal\> /QoERepositoryService/repository/itemAncestors/{itemId}</span><span class="sxs-lookup"><span data-stu-id="6c561-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="6c561-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="6c561-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="6c561-118">**Parámetros uri:** ninguno.</span><span class="sxs-lookup"><span data-stu-id="6c561-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="6c561-119">**Encabezados de solicitud:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="6c561-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6c561-120">**Cuerpo de la** solicitud: ninguno.</span><span class="sxs-lookup"><span data-stu-id="6c561-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="6c561-121">**Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6c561-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="6c561-122">**Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto).</span><span class="sxs-lookup"><span data-stu-id="6c561-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="6c561-123">Si no se encuentra un identificador de usuario especificado, devuelve el código de estado 404 (No encontrado).</span><span class="sxs-lookup"><span data-stu-id="6c561-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="6c561-124">**Encabezados de respuesta:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="6c561-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6c561-125">**Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="6c561-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 <span data-ttu-id="6c561-126">*Item1:*  id. del elemento.</span><span class="sxs-lookup"><span data-stu-id="6c561-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="6c561-127">*Item2:*  profundidad es la distancia desde el elemento.</span><span class="sxs-lookup"><span data-stu-id="6c561-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="6c561-128">0 es el elemento primario inmediato.</span><span class="sxs-lookup"><span data-stu-id="6c561-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="6c561-129">*Item3:*  título del elemento.</span><span class="sxs-lookup"><span data-stu-id="6c561-129">*Item3*  - Title of the item.</span></span>
  

