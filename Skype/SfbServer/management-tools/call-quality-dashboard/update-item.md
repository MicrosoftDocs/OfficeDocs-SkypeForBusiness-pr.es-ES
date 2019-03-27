---
title: Actualizar elemento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Resumen: Obtenga información acerca de la operación Actualizar elemento, que es parte del servicio de elemento. El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 3ac56b8761f565663ffaa689c666e285b2347ed5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887952"
---
# <a name="update-item"></a><span data-ttu-id="16a03-105">Actualizar elemento</span><span class="sxs-lookup"><span data-stu-id="16a03-105">Update Item</span></span>
 
<span data-ttu-id="16a03-106">**Resumen:** Obtenga información acerca de la operación Actualizar elemento, que es parte del servicio de elemento.</span><span class="sxs-lookup"><span data-stu-id="16a03-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="16a03-107">El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="16a03-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="16a03-108">Panel de calidad de llamada es una herramienta de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="16a03-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="16a03-109">La operación Actualizar elemento es parte del servicio de elemento de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="16a03-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="16a03-110">Actualizar elemento</span><span class="sxs-lookup"><span data-stu-id="16a03-110">Update Item</span></span>

<span data-ttu-id="16a03-111">Actualizar elemento de actualiza un elemento específico en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="16a03-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="16a03-112">**(Método)**</span><span class="sxs-lookup"><span data-stu-id="16a03-112">**Method**</span></span>|<span data-ttu-id="16a03-113">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="16a03-113">**Request URI**</span></span>|<span data-ttu-id="16a03-114">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="16a03-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="16a03-115">PUT</span><span class="sxs-lookup"><span data-stu-id="16a03-115">PUT</span></span>  <br/> |<span data-ttu-id="16a03-116">https://\<portal\>/QoERepositoryService/repository/elemento / {itemId}</span><span class="sxs-lookup"><span data-stu-id="16a03-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="16a03-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="16a03-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="16a03-118">**Los parámetros URI** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="16a03-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="16a03-119">**Encabezados de solicitud** -contenido-tipo: application/json.</span><span class="sxs-lookup"><span data-stu-id="16a03-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="16a03-120">**Cuerpo de la convocatoria** - JSON.</span><span class="sxs-lookup"><span data-stu-id="16a03-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="16a03-121">Carga de solicitudes de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="16a03-121">Sample request payload:</span></span>
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="16a03-122">*contenido*  Datos se almacenen como el nuevo contenido de un elemento subcaracterística existente con formato JSON.</span><span class="sxs-lookup"><span data-stu-id="16a03-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="16a03-123">Técnicamente, un repositorio puede almacenar cualquier contenido de cualquier esquema, pero cuando se usa para llamar al panel de calidad, debe ser un informe o una consulta.</span><span class="sxs-lookup"><span data-stu-id="16a03-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="16a03-124">*tipo de*  Especifique siempre "application/json" para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="16a03-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="16a03-125">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="16a03-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="16a03-126">**Código de estado** - una operación correcta devuelve código de estado 204 (sin contenido).</span><span class="sxs-lookup"><span data-stu-id="16a03-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="16a03-127">Si no se encuentra un identificador de elemento especificado, devuelve el código de estado 404 (no encontrado).</span><span class="sxs-lookup"><span data-stu-id="16a03-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="16a03-128">"Sin contenido" no es un estado de error.</span><span class="sxs-lookup"><span data-stu-id="16a03-128">"No Content" is not an error status.</span></span> <span data-ttu-id="16a03-129">Esto significa que una respuesta no devolvió nada en el cuerpo (en contraste, 200 devuelve Aceptar el contenido de cuerpo).</span><span class="sxs-lookup"><span data-stu-id="16a03-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="16a03-130">Indica que el elemento se ha actualizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="16a03-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="16a03-131">**Encabezados de respuesta** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="16a03-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="16a03-132">**Cuerpo de la respuesta** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="16a03-132">**Response Body** - None.</span></span>
  

