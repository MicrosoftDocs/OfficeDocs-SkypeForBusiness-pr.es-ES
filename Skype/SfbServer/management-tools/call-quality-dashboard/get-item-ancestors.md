---
title: Obtener predecesores del elemento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Resumen: Obtenga información sobre la operación obtener elementos antecesores de elemento, que es parte del servicio de elemento. El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 77fb5f46ada278bcb172a51620317182fe5d61b0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274733"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="9700d-105">Obtener predecesores del elemento</span><span class="sxs-lookup"><span data-stu-id="9700d-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="9700d-106">**Resumen:** Obtenga más información sobre la operación obtener elementos antecesores de elemento, que es parte del servicio de elemento.</span><span class="sxs-lookup"><span data-stu-id="9700d-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="9700d-107">El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="9700d-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="9700d-108">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9700d-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="9700d-109">La operación obtener elementos antecesores del elemento es parte del servicio de elemento en la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="9700d-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="9700d-110">Obtener predecesores del elemento</span><span class="sxs-lookup"><span data-stu-id="9700d-110">Get Item Ancestors</span></span>

<span data-ttu-id="9700d-111">Obtener elementos antecesores del elemento devuelve los elementos antecesores específicos del repositorio.</span><span class="sxs-lookup"><span data-stu-id="9700d-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="9700d-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="9700d-112">**Method**</span></span>|<span data-ttu-id="9700d-113">**Solicitar URI**</span><span class="sxs-lookup"><span data-stu-id="9700d-113">**Request URI**</span></span>|<span data-ttu-id="9700d-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="9700d-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9700d-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="9700d-115">GET</span></span>  <br/> |<span data-ttu-id="9700d-116">https://\<portal\>/QoERepositoryService/Repository/itemAncestors/{Itemid}</span><span class="sxs-lookup"><span data-stu-id="9700d-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="9700d-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="9700d-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9700d-118">**Parámetros de URI** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="9700d-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="9700d-119">**Solicitar encabezados** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="9700d-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9700d-120">**Solicitar cuerpo** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="9700d-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="9700d-121">**Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="9700d-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="9700d-122">**Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).</span><span class="sxs-lookup"><span data-stu-id="9700d-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="9700d-123">Si no se encuentra un identificador de usuario especificado, devuelve el código de estado 404 (no se encontró).</span><span class="sxs-lookup"><span data-stu-id="9700d-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="9700d-124">**Encabezados de respuesta** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="9700d-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9700d-125">**Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON.</span><span class="sxs-lookup"><span data-stu-id="9700d-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
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

 <span data-ttu-id="9700d-126">*Item1* -ID del elemento.</span><span class="sxs-lookup"><span data-stu-id="9700d-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="9700d-127">*Item2* -profundidad es la distancia desde el elemento.</span><span class="sxs-lookup"><span data-stu-id="9700d-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="9700d-128">0 es el elemento primario inmediato.</span><span class="sxs-lookup"><span data-stu-id="9700d-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="9700d-129">*Item3* : título del elemento.</span><span class="sxs-lookup"><span data-stu-id="9700d-129">*Item3*  - Title of the item.</span></span>
  

