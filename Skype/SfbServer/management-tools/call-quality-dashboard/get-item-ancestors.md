---
title: Obtener elemento antecesores
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Resumen: Obtenga información acerca de la operación obtener antecesores del elemento, que es parte del servicio de elemento. El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: e9e23c32aada4c609f9deb43004385b389a533bf
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532594"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="e28d2-105">Obtener elemento antecesores</span><span class="sxs-lookup"><span data-stu-id="e28d2-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="e28d2-106">**Resumen:** Obtenga información acerca de la operación obtener antecesores del elemento, que es parte del servicio de elemento.</span><span class="sxs-lookup"><span data-stu-id="e28d2-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="e28d2-107">El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="e28d2-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="e28d2-108">Panel de calidad de llamada es una herramienta de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e28d2-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="e28d2-109">La operación obtener elemento antecesores es parte del servicio de elemento de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="e28d2-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="e28d2-110">Obtener elemento antecesores</span><span class="sxs-lookup"><span data-stu-id="e28d2-110">Get Item Ancestors</span></span>

<span data-ttu-id="e28d2-111">Get elemento antecesores devuelve a un antecesores elementos específicos del repositorio.</span><span class="sxs-lookup"><span data-stu-id="e28d2-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="e28d2-112">**(Método)**</span><span class="sxs-lookup"><span data-stu-id="e28d2-112">**Method**</span></span>|<span data-ttu-id="e28d2-113">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="e28d2-113">**Request URI**</span></span>|<span data-ttu-id="e28d2-114">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="e28d2-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e28d2-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="e28d2-115">GET</span></span>  <br/> |<span data-ttu-id="e28d2-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors / {itemId}</span><span class="sxs-lookup"><span data-stu-id="e28d2-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="e28d2-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="e28d2-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="e28d2-118">**Los parámetros URI** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="e28d2-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="e28d2-119">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="e28d2-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="e28d2-120">**Cuerpo de la convocatoria** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="e28d2-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="e28d2-121">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="e28d2-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="e28d2-122">**Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).</span><span class="sxs-lookup"><span data-stu-id="e28d2-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="e28d2-123">Si un usuario especificado que no se encuentra el identificador, devuelve el código de estado 404 (no encontrado).</span><span class="sxs-lookup"><span data-stu-id="e28d2-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="e28d2-124">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="e28d2-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="e28d2-125">**Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="e28d2-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
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

 <span data-ttu-id="e28d2-126">*Item1* - identificador del elemento.</span><span class="sxs-lookup"><span data-stu-id="e28d2-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="e28d2-127">*Item2* - profundidad es la distancia desde el elemento.</span><span class="sxs-lookup"><span data-stu-id="e28d2-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="e28d2-128">0 es el objeto primario inmediato.</span><span class="sxs-lookup"><span data-stu-id="e28d2-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="e28d2-129">*Item3* - título del elemento.</span><span class="sxs-lookup"><span data-stu-id="e28d2-129">*Item3*  - Title of the item.</span></span>
  

