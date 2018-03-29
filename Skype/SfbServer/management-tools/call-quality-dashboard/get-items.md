---
title: Obtener elementos
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Resumen: Conozca la operación obtener elementos, que forma parte del elemento de servicio. El servicio del elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 526d578d65ded98a6cd1a5cfc09a6749319683c3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-items"></a><span data-ttu-id="ba793-105">Obtener elementos</span><span class="sxs-lookup"><span data-stu-id="ba793-105">Get Items</span></span>
 
<span data-ttu-id="ba793-106">**Resumen:** Obtener información sobre la operación de obtener elementos, que forma parte del elemento de servicio.</span><span class="sxs-lookup"><span data-stu-id="ba793-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="ba793-107">El servicio del elemento es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="ba793-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="ba793-108">Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ba793-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ba793-109">La operación de obtener elementos forma parte del elemento de servicio en la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="ba793-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="ba793-110">Obtener elementos</span><span class="sxs-lookup"><span data-stu-id="ba793-110">Get Items</span></span>

<span data-ttu-id="ba793-111">Obtener elementos devuelve todos los elementos en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="ba793-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="ba793-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="ba793-112">**Method**</span></span>|<span data-ttu-id="ba793-113">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="ba793-113">**Request URI**</span></span>|<span data-ttu-id="ba793-114">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="ba793-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ba793-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="ba793-115">GET</span></span>  <br/> |<span data-ttu-id="ba793-116">https://\<portal\>/QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="ba793-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="ba793-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="ba793-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="ba793-118">**URI parámetros** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="ba793-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="ba793-119">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="ba793-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ba793-120">**Cuerpo de la solicitud** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="ba793-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="ba793-121">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="ba793-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="ba793-122">**Código de estado** - una operación correcta devuelve el código de estado 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="ba793-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="ba793-123">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="ba793-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ba793-124">**Cuerpo de la respuesta** : a continuación es una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="ba793-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ba793-125">Se devuelve una matriz de objetos de elemento.</span><span class="sxs-lookup"><span data-stu-id="ba793-125">An array of Item objects is returned.</span></span> <span data-ttu-id="ba793-126">Para obtener más información acerca del objeto Item, consulte obtener el elemento.</span><span class="sxs-lookup"><span data-stu-id="ba793-126">For details about Item object, see Get Item.</span></span> 
  
```
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]

```


