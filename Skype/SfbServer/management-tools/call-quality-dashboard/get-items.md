---
title: Obtener elementos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Resumen: Obtenga información sobre la operación obtener elementos, que es parte del servicio de elementos. El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: be93e16750c1a977a6bc3cfc9651e78a043ef563
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992667"
---
# <a name="get-items"></a><span data-ttu-id="ea849-105">Obtener elementos</span><span class="sxs-lookup"><span data-stu-id="ea849-105">Get Items</span></span>
 
<span data-ttu-id="ea849-106">**Resumen:** Obtenga más información sobre la operación obtener elementos, que es parte del servicio de elemento.</span><span class="sxs-lookup"><span data-stu-id="ea849-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="ea849-107">El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ea849-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="ea849-108">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ea849-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="ea849-109">La operación obtener elementos forma parte del servicio de elemento en la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ea849-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="ea849-110">Obtener elementos</span><span class="sxs-lookup"><span data-stu-id="ea849-110">Get Items</span></span>

<span data-ttu-id="ea849-111">Obtener elementos devuelve todos los elementos del repositorio.</span><span class="sxs-lookup"><span data-stu-id="ea849-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="ea849-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="ea849-112">**Method**</span></span>|<span data-ttu-id="ea849-113">**Solicitar URI**</span><span class="sxs-lookup"><span data-stu-id="ea849-113">**Request URI**</span></span>|<span data-ttu-id="ea849-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="ea849-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ea849-115">Obtener</span><span class="sxs-lookup"><span data-stu-id="ea849-115">GET</span></span>  <br/> |<span data-ttu-id="ea849-116">https://\<portal\>/QoERepositoryService/Repository/Item</span><span class="sxs-lookup"><span data-stu-id="ea849-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="ea849-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="ea849-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="ea849-118">**Parámetros de URI** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="ea849-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="ea849-119">**Solicitar encabezados** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="ea849-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ea849-120">**Solicitar cuerpo** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="ea849-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="ea849-121">**Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="ea849-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="ea849-122">**Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).</span><span class="sxs-lookup"><span data-stu-id="ea849-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="ea849-123">**Encabezados de respuesta** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="ea849-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ea849-124">**Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON.</span><span class="sxs-lookup"><span data-stu-id="ea849-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ea849-125">Se devuelve una matriz de objetos de elemento.</span><span class="sxs-lookup"><span data-stu-id="ea849-125">An array of Item objects is returned.</span></span> <span data-ttu-id="ea849-126">Para obtener más información sobre el objeto de elemento, vea obtener elemento.</span><span class="sxs-lookup"><span data-stu-id="ea849-126">For details about Item object, see Get Item.</span></span> 
  
```json
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
