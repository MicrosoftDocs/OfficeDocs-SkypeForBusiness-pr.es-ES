---
title: Obtener elemento
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Resumen: Conozca la operación de obtener el elemento, que es parte del elemento de servicio. El servicio del elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 6e4ba82c804937025b72da2d443c2a828d92d98a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-item"></a><span data-ttu-id="b0f96-105">Obtener elemento</span><span class="sxs-lookup"><span data-stu-id="b0f96-105">Get Item</span></span>
 
<span data-ttu-id="b0f96-106">**Resumen:** Obtener información sobre la operación de obtener el elemento, que es parte del elemento de servicio.</span><span class="sxs-lookup"><span data-stu-id="b0f96-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="b0f96-107">El servicio del elemento es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="b0f96-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="b0f96-108">Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b0f96-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b0f96-109">La operación de obtener el elemento forma parte del elemento de servicio en la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="b0f96-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="b0f96-110">Obtener elemento</span><span class="sxs-lookup"><span data-stu-id="b0f96-110">Get Item</span></span>

<span data-ttu-id="b0f96-111">Obtener un elemento específico de devoluciones de artículos en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="b0f96-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="b0f96-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="b0f96-112">**Method**</span></span>|<span data-ttu-id="b0f96-113">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="b0f96-113">**Request URI**</span></span>|<span data-ttu-id="b0f96-114">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="b0f96-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b0f96-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="b0f96-115">GET</span></span>  <br/> |<span data-ttu-id="b0f96-116">https://\<portal\>/QoERepositoryService/repository/elemento / {itemId}</span><span class="sxs-lookup"><span data-stu-id="b0f96-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="b0f96-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="b0f96-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="b0f96-118">**URI parámetros** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="b0f96-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="b0f96-119">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="b0f96-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b0f96-120">**Cuerpo de la solicitud** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="b0f96-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="b0f96-121">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="b0f96-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="b0f96-122">**Código de estado** - una operación correcta devuelve el código de estado 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="b0f96-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="b0f96-123">Si no se encuentra un identificador de elemento especificado, devuelve el código de estado 404 (no encontrado).</span><span class="sxs-lookup"><span data-stu-id="b0f96-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="b0f96-124">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="b0f96-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b0f96-125">**Cuerpo de la respuesta** : a continuación es una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="b0f96-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}

```

 <span data-ttu-id="b0f96-126">*itemId* - ID del elemento.</span><span class="sxs-lookup"><span data-stu-id="b0f96-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="b0f96-127">*userId* : identificador del usuario que es propietario de este elemento.</span><span class="sxs-lookup"><span data-stu-id="b0f96-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="b0f96-128">*contenido* : el contenido específico de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b0f96-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="b0f96-129">*tipo* : el tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="b0f96-129">*type*  - The type of the content.</span></span> <span data-ttu-id="b0f96-130">Este campo está definido por las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b0f96-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="b0f96-131">*subItemIds* : los identificadores de elementos secundarios, si existe alguno.</span><span class="sxs-lookup"><span data-stu-id="b0f96-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="b0f96-132">Se trata de un cortocircuito de operación obtener elementos secundarios para guardar una llamada.</span><span class="sxs-lookup"><span data-stu-id="b0f96-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="b0f96-133">Aplicaciones también pueden obtener la misma información mediante la operación de obtener elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="b0f96-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

