---
title: Obtener elemento
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
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Resumen: obtenga información sobre la operación Obtener elemento, que forma parte del servicio de elementos. El servicio de elementos forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 896540c4572fb3991356ce055f01690ed702c6f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832570"
---
# <a name="get-item"></a><span data-ttu-id="33a3c-105">Obtener elemento</span><span class="sxs-lookup"><span data-stu-id="33a3c-105">Get Item</span></span>
 
<span data-ttu-id="33a3c-106">**Resumen:** Obtenga información sobre la operación Obtener elemento, que forma parte del servicio de elementos.</span><span class="sxs-lookup"><span data-stu-id="33a3c-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="33a3c-107">El servicio de elementos forma parte de la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="33a3c-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="33a3c-108">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="33a3c-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="33a3c-109">La operación Obtener elemento forma parte del servicio de elementos en la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="33a3c-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="33a3c-110">Obtener elemento</span><span class="sxs-lookup"><span data-stu-id="33a3c-110">Get Item</span></span>

<span data-ttu-id="33a3c-111">Obtener elemento devuelve un elemento específico en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="33a3c-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="33a3c-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="33a3c-112">**Method**</span></span>|<span data-ttu-id="33a3c-113">**URI de solicitud**</span><span class="sxs-lookup"><span data-stu-id="33a3c-113">**Request URI**</span></span>|<span data-ttu-id="33a3c-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="33a3c-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="33a3c-115">GET</span><span class="sxs-lookup"><span data-stu-id="33a3c-115">GET</span></span>  <br/> |<span data-ttu-id="33a3c-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="33a3c-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="33a3c-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="33a3c-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="33a3c-118">**Parámetros uri:** ninguno.</span><span class="sxs-lookup"><span data-stu-id="33a3c-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="33a3c-119">**Encabezados de solicitud:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="33a3c-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="33a3c-120">**Cuerpo de la** solicitud: ninguno.</span><span class="sxs-lookup"><span data-stu-id="33a3c-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="33a3c-121">**Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="33a3c-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="33a3c-122">**Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto).</span><span class="sxs-lookup"><span data-stu-id="33a3c-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="33a3c-123">Si no se encuentra un identificador de elemento especificado, devuelve el código de estado 404 (No encontrado).</span><span class="sxs-lookup"><span data-stu-id="33a3c-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="33a3c-124">**Encabezados de respuesta:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="33a3c-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="33a3c-125">**Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="33a3c-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="33a3c-126">*itemId:*  id. del elemento.</span><span class="sxs-lookup"><span data-stu-id="33a3c-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="33a3c-127">*userId:*  identificador del usuario propietario de este elemento.</span><span class="sxs-lookup"><span data-stu-id="33a3c-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="33a3c-128">*contenido:*  contenido específico de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="33a3c-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="33a3c-129">*type:*  el tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="33a3c-129">*type*  - The type of the content.</span></span> <span data-ttu-id="33a3c-130">Las aplicaciones establecen este campo.</span><span class="sxs-lookup"><span data-stu-id="33a3c-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="33a3c-131">*subItemIds:*  los id. de los subelementos, si los hay.</span><span class="sxs-lookup"><span data-stu-id="33a3c-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="33a3c-132">Se trata de un corto circuito de la operación Get Sub-Items para guardar una llamada.</span><span class="sxs-lookup"><span data-stu-id="33a3c-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="33a3c-133">Las aplicaciones también pueden obtener la misma información mediante la operación Get Sub-Items.</span><span class="sxs-lookup"><span data-stu-id="33a3c-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

