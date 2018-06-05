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
description: 'Resumen: Obtenga información acerca de la operación obtener elemento, que es parte del servicio de elemento. El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 29811f7f760644d257a2600dea08e54e1a53421b
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569155"
---
# <a name="get-item"></a><span data-ttu-id="3b7f8-105">Obtener elemento</span><span class="sxs-lookup"><span data-stu-id="3b7f8-105">Get Item</span></span>
 
<span data-ttu-id="3b7f8-106">**Resumen:** Obtenga información acerca de la operación obtener elemento, que es parte del servicio de elemento.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="3b7f8-107">El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="3b7f8-108">Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="3b7f8-109">La operación obtener elemento es parte del servicio de elemento de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="3b7f8-110">Obtener elemento</span><span class="sxs-lookup"><span data-stu-id="3b7f8-110">Get Item</span></span>

<span data-ttu-id="3b7f8-111">Obtener elemento devuelve un elemento específico en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="3b7f8-112">**(Método)**</span><span class="sxs-lookup"><span data-stu-id="3b7f8-112">**Method**</span></span>|<span data-ttu-id="3b7f8-113">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="3b7f8-113">**Request URI**</span></span>|<span data-ttu-id="3b7f8-114">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="3b7f8-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3b7f8-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="3b7f8-115">GET</span></span>  <br/> |<span data-ttu-id="3b7f8-116">https://\<portal\>/QoERepositoryService/repository/elemento / {itemId}</span><span class="sxs-lookup"><span data-stu-id="3b7f8-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="3b7f8-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="3b7f8-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="3b7f8-118">**Los parámetros URI** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="3b7f8-119">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="3b7f8-120">**Cuerpo de la convocatoria** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="3b7f8-121">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="3b7f8-122">**Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).</span><span class="sxs-lookup"><span data-stu-id="3b7f8-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="3b7f8-123">Si no se encuentra un identificador de elemento especificado, devuelve el código de estado 404 (no encontrado).</span><span class="sxs-lookup"><span data-stu-id="3b7f8-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="3b7f8-124">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="3b7f8-125">**Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="3b7f8-126">*itemId* - identificador del elemento.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="3b7f8-127">*userId* : identificador del usuario que es propietario de este elemento.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="3b7f8-128">*contenido* : el contenido específico de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="3b7f8-129">*tipo* : el tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-129">*type*  - The type of the content.</span></span> <span data-ttu-id="3b7f8-130">Este campo se establece por las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="3b7f8-131">*subItemIds* - los identificadores de elementos secundarios, si hay alguno.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="3b7f8-132">Se trata de un máximo de operación obtener elementos secundarios para guardar una llamada.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="3b7f8-133">Las aplicaciones o bien pueden obtener la misma información de uso de la operación obtener elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="3b7f8-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

