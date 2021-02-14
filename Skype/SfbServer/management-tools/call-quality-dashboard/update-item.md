---
title: Actualizar elemento
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Resumen: obtenga información sobre la operación Actualizar elemento, que forma parte del servicio de elementos. El servicio de elementos forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 78da2fa414b4ba266f9e6aba4feac5ff73150062
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803090"
---
# <a name="update-item"></a><span data-ttu-id="8c610-105">Actualizar elemento</span><span class="sxs-lookup"><span data-stu-id="8c610-105">Update Item</span></span>
 
<span data-ttu-id="8c610-106">**Resumen:** Obtenga información sobre la operación Actualizar elemento, que forma parte del servicio de elementos.</span><span class="sxs-lookup"><span data-stu-id="8c610-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="8c610-107">El servicio de elementos forma parte de la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8c610-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="8c610-108">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8c610-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="8c610-109">La operación Actualizar elemento forma parte del servicio de elementos en la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8c610-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="8c610-110">Actualizar elemento</span><span class="sxs-lookup"><span data-stu-id="8c610-110">Update Item</span></span>

<span data-ttu-id="8c610-111">Actualizar elemento actualiza un elemento específico en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="8c610-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="8c610-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="8c610-112">**Method**</span></span>|<span data-ttu-id="8c610-113">**URI de solicitud**</span><span class="sxs-lookup"><span data-stu-id="8c610-113">**Request URI**</span></span>|<span data-ttu-id="8c610-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="8c610-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8c610-115">PUT</span><span class="sxs-lookup"><span data-stu-id="8c610-115">PUT</span></span>  <br/> |<span data-ttu-id="8c610-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="8c610-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="8c610-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="8c610-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="8c610-118">**Parámetros uri:** ninguno.</span><span class="sxs-lookup"><span data-stu-id="8c610-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="8c610-119">**Encabezados de** solicitud -Content-Type: application/json.</span><span class="sxs-lookup"><span data-stu-id="8c610-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="8c610-120">**Cuerpo de la** solicitud: JSON.</span><span class="sxs-lookup"><span data-stu-id="8c610-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="8c610-121">Carga de solicitud de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8c610-121">Sample request payload:</span></span>
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="8c610-122">*content*  Datos con formato JSON que se almacenarán como el nuevo contenido de un sub item existente.</span><span class="sxs-lookup"><span data-stu-id="8c610-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="8c610-123">Técnicamente, un repositorio puede almacenar cualquier contenido de cualquier esquema, pero cuando se usa para el Panel de calidad de llamadas, debe ser un informe o una consulta.</span><span class="sxs-lookup"><span data-stu-id="8c610-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="8c610-124">*type*  Especifique siempre "application/json" para el Panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8c610-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="8c610-125">**Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="8c610-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="8c610-126">**Código de estado:** una operación correcta devuelve el código de estado 204 (sin contenido).</span><span class="sxs-lookup"><span data-stu-id="8c610-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="8c610-127">Si no se encuentra un identificador de elemento especificado, devuelve el código de estado 404 (No encontrado).</span><span class="sxs-lookup"><span data-stu-id="8c610-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8c610-128">"Sin contenido" no es un estado de error.</span><span class="sxs-lookup"><span data-stu-id="8c610-128">"No Content" is not an error status.</span></span> <span data-ttu-id="8c610-129">Esto significa que una respuesta no deseó nada en el cuerpo (en cambio, 200 OK devuelve contenido en Body).</span><span class="sxs-lookup"><span data-stu-id="8c610-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="8c610-130">Indica que el elemento se actualizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="8c610-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="8c610-131">**Encabezados de respuesta:** ninguno.</span><span class="sxs-lookup"><span data-stu-id="8c610-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="8c610-132">**Cuerpo de la** respuesta: ninguno.</span><span class="sxs-lookup"><span data-stu-id="8c610-132">**Response Body** - None.</span></span>
  

