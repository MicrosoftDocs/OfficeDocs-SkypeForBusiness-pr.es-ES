---
title: Actualizar artículo
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Resumen: Conozca la operación de actualización elemento, que es parte del elemento de servicio. El servicio del elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 04a0ebf29537bbc2e62e6d5b35008fe9e329ab4f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="update-item"></a><span data-ttu-id="9d51c-105">Actualizar artículo</span><span class="sxs-lookup"><span data-stu-id="9d51c-105">Update Item</span></span>
 
<span data-ttu-id="9d51c-106">**Resumen:** Obtener información sobre la operación de actualización elemento, que es parte del elemento de servicio.</span><span class="sxs-lookup"><span data-stu-id="9d51c-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="9d51c-107">El servicio del elemento es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="9d51c-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="9d51c-108">Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9d51c-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9d51c-109">La operación de actualización artículo es parte del elemento de servicio en la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="9d51c-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="9d51c-110">Actualizar artículo</span><span class="sxs-lookup"><span data-stu-id="9d51c-110">Update Item</span></span>

<span data-ttu-id="9d51c-111">Elemento de actualización actualiza un elemento específico en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="9d51c-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="9d51c-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="9d51c-112">**Method**</span></span>|<span data-ttu-id="9d51c-113">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="9d51c-113">**Request URI**</span></span>|<span data-ttu-id="9d51c-114">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="9d51c-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9d51c-115">PUT</span><span class="sxs-lookup"><span data-stu-id="9d51c-115">PUT</span></span>  <br/> |<span data-ttu-id="9d51c-116">https://\<portal\>/QoERepositoryService/repository/elemento / {itemId}</span><span class="sxs-lookup"><span data-stu-id="9d51c-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="9d51c-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="9d51c-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9d51c-118">**URI parámetros** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="9d51c-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="9d51c-119">**Encabezados de solicitud** -contenido-tipo: application/json.</span><span class="sxs-lookup"><span data-stu-id="9d51c-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="9d51c-120">**Cuerpo de la solicitud** - JSON.</span><span class="sxs-lookup"><span data-stu-id="9d51c-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="9d51c-121">Carga de solicitud de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9d51c-121">Sample request payload:</span></span>
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="9d51c-122">*contenido*  JSON con formato de datos que se almacenen como el nuevo contenido de un elemento secundario existente.</span><span class="sxs-lookup"><span data-stu-id="9d51c-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="9d51c-123">Técnicamente, un repositorio puede almacenar cualquier contenido de cualquier esquema, pero cuando se utiliza para llamar al panel de calidad, debe ser un informe o una consulta.</span><span class="sxs-lookup"><span data-stu-id="9d51c-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="9d51c-124">*tipo*  Especifique siempre "application/json" para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="9d51c-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="9d51c-125">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="9d51c-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="9d51c-126">**Código de estado** - una operación correcta devuelve el código de estado 204 (sin contenido).</span><span class="sxs-lookup"><span data-stu-id="9d51c-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="9d51c-127">Si no se encuentra un identificador de elemento especificado, devuelve el código de estado 404 (no encontrado).</span><span class="sxs-lookup"><span data-stu-id="9d51c-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9d51c-128">"Sin contenido" no es un estado de error.</span><span class="sxs-lookup"><span data-stu-id="9d51c-128">"No Content" is not an error status.</span></span> <span data-ttu-id="9d51c-129">Significa que una respuesta no devolvió nada en el cuerpo (en contraste, 200 devuelve Aceptar contenido cuerpo).</span><span class="sxs-lookup"><span data-stu-id="9d51c-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="9d51c-130">Indica que el elemento se ha actualizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="9d51c-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="9d51c-131">**Encabezados de respuesta** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="9d51c-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="9d51c-132">**Cuerpo de la respuesta** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="9d51c-132">**Response Body** - None.</span></span>
  

