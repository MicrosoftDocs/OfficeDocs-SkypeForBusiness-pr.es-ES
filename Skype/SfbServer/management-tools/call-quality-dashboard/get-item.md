---
title: Obtener elemento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Resumen: Obtenga información sobre la operación obtener elemento, que forma parte del servicio de artículo. El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 208ad3d1852ab58b7fcd0d01eeb440097328f733
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992677"
---
# <a name="get-item"></a><span data-ttu-id="b5cf9-105">Obtener elemento</span><span class="sxs-lookup"><span data-stu-id="b5cf9-105">Get Item</span></span>
 
<span data-ttu-id="b5cf9-106">**Resumen:** Obtenga más información sobre la operación obtener elemento, que es parte del servicio de artículos.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="b5cf9-107">El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="b5cf9-108">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b5cf9-109">La operación obtener elemento forma parte del servicio de elemento en la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="b5cf9-110">Obtener elemento</span><span class="sxs-lookup"><span data-stu-id="b5cf9-110">Get Item</span></span>

<span data-ttu-id="b5cf9-111">Obtener elemento devuelve un elemento específico del repositorio.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="b5cf9-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="b5cf9-112">**Method**</span></span>|<span data-ttu-id="b5cf9-113">**Solicitar URI**</span><span class="sxs-lookup"><span data-stu-id="b5cf9-113">**Request URI**</span></span>|<span data-ttu-id="b5cf9-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="b5cf9-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b5cf9-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="b5cf9-115">GET</span></span>  <br/> |<span data-ttu-id="b5cf9-116">https://\<portal\>/QoERepositoryService/Repository/Item/{Itemid}</span><span class="sxs-lookup"><span data-stu-id="b5cf9-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="b5cf9-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="b5cf9-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="b5cf9-118">**Parámetros de URI** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="b5cf9-119">**Solicitar encabezados** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b5cf9-120">**Solicitar cuerpo** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="b5cf9-121">**Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="b5cf9-122">**Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).</span><span class="sxs-lookup"><span data-stu-id="b5cf9-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="b5cf9-123">Si no se encuentra un identificador de elemento especificado, devuelve el código de estado 404 (no se encontró).</span><span class="sxs-lookup"><span data-stu-id="b5cf9-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="b5cf9-124">**Encabezados de respuesta** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b5cf9-125">**Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="b5cf9-126">*Itemid* -ID del elemento.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="b5cf9-127">identificador *de usuario* del usuario que es el propietario de este elemento.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="b5cf9-128">*contenido* : el contenido específico de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="b5cf9-129">*Type* : el tipo del contenido.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-129">*type*  - The type of the content.</span></span> <span data-ttu-id="b5cf9-130">Este campo lo establecen las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="b5cf9-131">*subItemIds* : los identificadores de subelementos, si los hay.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="b5cf9-132">Este es un cortocircuito de la operación de obtención de subelementos para guardar una llamada.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="b5cf9-133">Las aplicaciones también pueden obtener la misma información mediante la operación de obtención de subelementos.</span><span class="sxs-lookup"><span data-stu-id="b5cf9-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

