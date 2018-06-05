---
title: Obtener elemento antecesores
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Resumen: Obtenga información acerca de la operación obtener antecesores del elemento, que es parte del servicio de elemento. El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 60d77ff1fd14a994d55a42516cd686891a56595f
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569204"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="8852b-105">Obtener elemento antecesores</span><span class="sxs-lookup"><span data-stu-id="8852b-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="8852b-106">**Resumen:** Obtenga información acerca de la operación obtener antecesores del elemento, que es parte del servicio de elemento.</span><span class="sxs-lookup"><span data-stu-id="8852b-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="8852b-107">El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="8852b-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="8852b-108">Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8852b-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8852b-109">La operación obtener elemento antecesores es parte del servicio de elemento de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="8852b-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="8852b-110">Obtener elemento antecesores</span><span class="sxs-lookup"><span data-stu-id="8852b-110">Get Item Ancestors</span></span>

<span data-ttu-id="8852b-111">Get elemento antecesores devuelve a un antecesores elementos específicos del repositorio.</span><span class="sxs-lookup"><span data-stu-id="8852b-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="8852b-112">**(Método)**</span><span class="sxs-lookup"><span data-stu-id="8852b-112">**Method**</span></span>|<span data-ttu-id="8852b-113">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="8852b-113">**Request URI**</span></span>|<span data-ttu-id="8852b-114">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="8852b-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8852b-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="8852b-115">GET</span></span>  <br/> |<span data-ttu-id="8852b-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors / {itemId}</span><span class="sxs-lookup"><span data-stu-id="8852b-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="8852b-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="8852b-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="8852b-118">**Los parámetros URI** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="8852b-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="8852b-119">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="8852b-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8852b-120">**Cuerpo de la convocatoria** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="8852b-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="8852b-121">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="8852b-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="8852b-122">**Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).</span><span class="sxs-lookup"><span data-stu-id="8852b-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="8852b-123">Si un usuario especificado que no se encuentra el identificador, devuelve el código de estado 404 (no encontrado).</span><span class="sxs-lookup"><span data-stu-id="8852b-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="8852b-124">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="8852b-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8852b-125">**Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="8852b-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
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

 <span data-ttu-id="8852b-126">*Item1* - identificador del elemento.</span><span class="sxs-lookup"><span data-stu-id="8852b-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="8852b-127">*Item2* - profundidad es la distancia desde el elemento.</span><span class="sxs-lookup"><span data-stu-id="8852b-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="8852b-128">0 es el objeto primario inmediato.</span><span class="sxs-lookup"><span data-stu-id="8852b-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="8852b-129">*Item3* - título del elemento.</span><span class="sxs-lookup"><span data-stu-id="8852b-129">*Item3*  - Title of the item.</span></span>
  

