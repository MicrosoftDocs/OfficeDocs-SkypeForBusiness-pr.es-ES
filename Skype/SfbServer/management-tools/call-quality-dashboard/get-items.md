---
title: Obtener elementos
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
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Resumen: obtenga información sobre la operación Obtener elementos, que forma parte del servicio de elementos. El servicio de elementos forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 7da3ba77e782abe44896a7c1eb51a458d9a7e0b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832540"
---
# <a name="get-items"></a><span data-ttu-id="db2ff-105">Obtener elementos</span><span class="sxs-lookup"><span data-stu-id="db2ff-105">Get Items</span></span>
 
<span data-ttu-id="db2ff-106">**Resumen:** Obtenga información sobre la operación Obtener elementos, que forma parte del servicio de elementos.</span><span class="sxs-lookup"><span data-stu-id="db2ff-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="db2ff-107">El servicio de elementos forma parte de la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="db2ff-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="db2ff-108">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="db2ff-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="db2ff-109">La operación Obtener elementos forma parte del servicio de elementos en la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="db2ff-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="db2ff-110">Obtener elementos</span><span class="sxs-lookup"><span data-stu-id="db2ff-110">Get Items</span></span>

<span data-ttu-id="db2ff-111">Get Items devuelve todos los elementos del repositorio.</span><span class="sxs-lookup"><span data-stu-id="db2ff-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="db2ff-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="db2ff-112">**Method**</span></span>|<span data-ttu-id="db2ff-113">**URI de solicitud**</span><span class="sxs-lookup"><span data-stu-id="db2ff-113">**Request URI**</span></span>|<span data-ttu-id="db2ff-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="db2ff-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="db2ff-115">GET</span><span class="sxs-lookup"><span data-stu-id="db2ff-115">GET</span></span>  <br/> |<span data-ttu-id="db2ff-116">https:// \<portal\> /QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="db2ff-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="db2ff-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="db2ff-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="db2ff-118">**Parámetros de URI:** ninguno.</span><span class="sxs-lookup"><span data-stu-id="db2ff-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="db2ff-119">**Encabezados de solicitud:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="db2ff-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="db2ff-120">**Cuerpo de la** solicitud: ninguno.</span><span class="sxs-lookup"><span data-stu-id="db2ff-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="db2ff-121">**Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="db2ff-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="db2ff-122">**Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto).</span><span class="sxs-lookup"><span data-stu-id="db2ff-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="db2ff-123">**Encabezados de respuesta:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="db2ff-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="db2ff-124">**Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="db2ff-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="db2ff-125">Se devuelve una matriz de objetos Item.</span><span class="sxs-lookup"><span data-stu-id="db2ff-125">An array of Item objects is returned.</span></span> <span data-ttu-id="db2ff-126">Para obtener más información acerca del objeto Item, vea Obtener elemento.</span><span class="sxs-lookup"><span data-stu-id="db2ff-126">For details about Item object, see Get Item.</span></span> 
  
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
