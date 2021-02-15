---
title: Obtener elementos secundarios
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Resumen: obtenga información sobre la operación Obtener Sub-Items, que forma parte del servicio de elementos. El servicio de elementos forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: defb0b898c5101513cbb4f6da4382a8bb43bce6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832510"
---
# <a name="get-sub-items"></a><span data-ttu-id="b676d-105">Obtener elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b676d-105">Get Sub-Items</span></span>
 
<span data-ttu-id="b676d-106">**Resumen:** Obtenga información sobre la operación Obtener Sub-Items, que forma parte del servicio de elementos.</span><span class="sxs-lookup"><span data-stu-id="b676d-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="b676d-107">El servicio de elementos forma parte de la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b676d-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="b676d-108">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b676d-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b676d-109">La operación Obtener Sub-Items forma parte del servicio de elementos en la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b676d-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="b676d-110">Obtener elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b676d-110">Get Sub-Items</span></span>

<span data-ttu-id="b676d-111">Get Sub-Items devuelve los subproybles de un elemento específico.</span><span class="sxs-lookup"><span data-stu-id="b676d-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="b676d-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="b676d-112">**Method**</span></span>|<span data-ttu-id="b676d-113">**URI de solicitud**</span><span class="sxs-lookup"><span data-stu-id="b676d-113">**Request URI**</span></span>|<span data-ttu-id="b676d-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="b676d-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b676d-115">GET</span><span class="sxs-lookup"><span data-stu-id="b676d-115">GET</span></span>  <br/> |<span data-ttu-id="b676d-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subitem</span><span class="sxs-lookup"><span data-stu-id="b676d-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="b676d-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="b676d-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="b676d-118">**Parámetros uri:** ninguno.</span><span class="sxs-lookup"><span data-stu-id="b676d-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="b676d-119">**Encabezados de solicitud:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="b676d-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b676d-120">**Cuerpo de la** solicitud: ninguno.</span><span class="sxs-lookup"><span data-stu-id="b676d-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="b676d-121">**Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="b676d-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="b676d-122">**Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto).</span><span class="sxs-lookup"><span data-stu-id="b676d-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="b676d-123">Si no se encuentra un identificador de usuario especificado, devuelve el código de estado 404 (No encontrado).</span><span class="sxs-lookup"><span data-stu-id="b676d-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="b676d-124">**Encabezados de respuesta:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="b676d-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b676d-125">**Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="b676d-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b676d-126">Se devuelve una matriz de objeto Item.</span><span class="sxs-lookup"><span data-stu-id="b676d-126">An array of Item object is returned.</span></span> 
  
```json
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

<span data-ttu-id="b676d-127">El objeto Item devuelto por Sub-Items operación sólo contiene los tres campos siguientes.</span><span class="sxs-lookup"><span data-stu-id="b676d-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="b676d-128">*itemId:*  id. del elemento.</span><span class="sxs-lookup"><span data-stu-id="b676d-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="b676d-129">*userId:*  id. del usuario propietario de este elemento.</span><span class="sxs-lookup"><span data-stu-id="b676d-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="b676d-130">*type:*  el tipo de contenido.</span><span class="sxs-lookup"><span data-stu-id="b676d-130">*type*  - The type of the content.</span></span> <span data-ttu-id="b676d-131">Este campo lo establecen las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b676d-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="b676d-132">`Content` y `subItems` los campos no se incluyen en la respuesta para reducir la cantidad de datos transmitidos a través de la red.</span><span class="sxs-lookup"><span data-stu-id="b676d-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

