---
title: Obtener elementos secundarios
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Resumen: Obtenga información acerca de la operación obtener elementos secundarios, que es parte del servicio de elemento. El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 41287978338bce49d8d8c30d1d6b91b9b2498acc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889010"
---
# <a name="get-sub-items"></a><span data-ttu-id="eb139-105">Obtener elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="eb139-105">Get Sub-Items</span></span>
 
<span data-ttu-id="eb139-106">**Resumen:** Obtenga información acerca de la operación obtener elementos secundarios, que es parte del servicio de elemento.</span><span class="sxs-lookup"><span data-stu-id="eb139-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="eb139-107">El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="eb139-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="eb139-108">Panel de calidad de llamada es una herramienta de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="eb139-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="eb139-109">La operación obtener elementos secundarios es parte del servicio de elemento de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="eb139-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="eb139-110">Obtener elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="eb139-110">Get Sub-Items</span></span>

<span data-ttu-id="eb139-111">Obtener elementos secundarios devuelve elementos secundarios de un elemento específico.</span><span class="sxs-lookup"><span data-stu-id="eb139-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="eb139-112">**(Método)**</span><span class="sxs-lookup"><span data-stu-id="eb139-112">**Method**</span></span>|<span data-ttu-id="eb139-113">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="eb139-113">**Request URI**</span></span>|<span data-ttu-id="eb139-114">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="eb139-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="eb139-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="eb139-115">GET</span></span>  <br/> |<span data-ttu-id="eb139-116">https://\<portal\>/QoERepositoryService/repository/elemento / {itemId} / subelemento</span><span class="sxs-lookup"><span data-stu-id="eb139-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="eb139-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="eb139-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="eb139-118">**Los parámetros URI** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="eb139-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="eb139-119">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="eb139-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="eb139-120">**Cuerpo de la convocatoria** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="eb139-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="eb139-121">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="eb139-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="eb139-122">**Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).</span><span class="sxs-lookup"><span data-stu-id="eb139-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="eb139-123">Si un usuario especificado que no se encuentra el identificador, devuelve el código de estado 404 (no encontrado).</span><span class="sxs-lookup"><span data-stu-id="eb139-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="eb139-124">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="eb139-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="eb139-125">**Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="eb139-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eb139-126">Se devuelve una matriz de objeto de elemento.</span><span class="sxs-lookup"><span data-stu-id="eb139-126">An array of Item object is returned.</span></span> 
  
```
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

<span data-ttu-id="eb139-127">El objeto de elemento devuelto por la operación de subelementos sólo contiene los siguientes tres campos.</span><span class="sxs-lookup"><span data-stu-id="eb139-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="eb139-128">*itemId* - identificador del elemento.</span><span class="sxs-lookup"><span data-stu-id="eb139-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="eb139-129">*userId* : identificador del usuario que es propietario de este elemento.</span><span class="sxs-lookup"><span data-stu-id="eb139-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="eb139-130">*tipo* : el tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="eb139-130">*type*  - The type of the content.</span></span> <span data-ttu-id="eb139-131">Este campo se establece por las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="eb139-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="eb139-132">`Content`y `subItems` campos no se incluyen en la respuesta a reducir la cantidad de datos que se transmiten a través de la red.</span><span class="sxs-lookup"><span data-stu-id="eb139-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

