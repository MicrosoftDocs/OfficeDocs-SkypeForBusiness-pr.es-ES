---
title: Obtener elementos secundarios
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Resumen: Obtenga información sobre la operación de obtención de subelementos, que es parte del servicio de elementos. El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 523a6050065680550685337dabfec72c87f30bf7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816769"
---
# <a name="get-sub-items"></a><span data-ttu-id="86c5b-105">Obtener elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="86c5b-105">Get Sub-Items</span></span>
 
<span data-ttu-id="86c5b-106">**Resumen:** Obtenga más información sobre la operación obtener subelementos, que es parte del servicio de artículos.</span><span class="sxs-lookup"><span data-stu-id="86c5b-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="86c5b-107">El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="86c5b-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="86c5b-108">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="86c5b-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="86c5b-109">La operación obtener subelementos es parte del servicio de elemento en la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="86c5b-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="86c5b-110">Obtener elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="86c5b-110">Get Sub-Items</span></span>

<span data-ttu-id="86c5b-111">Obtener subelementos devuelve los subelementos de un elemento específico.</span><span class="sxs-lookup"><span data-stu-id="86c5b-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="86c5b-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="86c5b-112">**Method**</span></span>|<span data-ttu-id="86c5b-113">**Solicitar URI**</span><span class="sxs-lookup"><span data-stu-id="86c5b-113">**Request URI**</span></span>|<span data-ttu-id="86c5b-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="86c5b-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="86c5b-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="86c5b-115">GET</span></span>  <br/> |<span data-ttu-id="86c5b-116">https://\<portal\>/QoERepositoryService/Repository/Item/{Itemid}/SubItem</span><span class="sxs-lookup"><span data-stu-id="86c5b-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="86c5b-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="86c5b-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="86c5b-118">**Parámetros de URI** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="86c5b-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="86c5b-119">**Solicitar encabezados** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="86c5b-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="86c5b-120">**Solicitar cuerpo** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="86c5b-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="86c5b-121">**Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="86c5b-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="86c5b-122">**Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).</span><span class="sxs-lookup"><span data-stu-id="86c5b-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="86c5b-123">Si no se encuentra un identificador de usuario especificado, devuelve el código de estado 404 (no se encontró).</span><span class="sxs-lookup"><span data-stu-id="86c5b-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="86c5b-124">**Encabezados de respuesta** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="86c5b-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="86c5b-125">**Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON.</span><span class="sxs-lookup"><span data-stu-id="86c5b-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="86c5b-126">Se devuelve una matriz de objetos de elemento.</span><span class="sxs-lookup"><span data-stu-id="86c5b-126">An array of Item object is returned.</span></span> 
  
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

<span data-ttu-id="86c5b-127">El objeto de elemento devuelto por la operación SubItems solo contiene los tres campos siguientes.</span><span class="sxs-lookup"><span data-stu-id="86c5b-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="86c5b-128">*Itemid* -ID del elemento.</span><span class="sxs-lookup"><span data-stu-id="86c5b-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="86c5b-129">identificador *de usuario* del usuario que es el propietario de este elemento.</span><span class="sxs-lookup"><span data-stu-id="86c5b-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="86c5b-130">*Type* : el tipo del contenido.</span><span class="sxs-lookup"><span data-stu-id="86c5b-130">*type*  - The type of the content.</span></span> <span data-ttu-id="86c5b-131">Este campo lo establecen las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="86c5b-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="86c5b-132">`Content`y `subItems` los campos no se incluyen en la respuesta para reducir la cantidad de datos que se transmiten a través de la red.</span><span class="sxs-lookup"><span data-stu-id="86c5b-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

