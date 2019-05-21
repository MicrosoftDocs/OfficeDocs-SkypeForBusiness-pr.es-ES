---
title: Actualizar elemento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Resumen: Obtenga información sobre la operación de actualización de elementos, que es parte del servicio de elementos. El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: aa46be0babf5998fcf2fabea797cb7a769914f8e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274537"
---
# <a name="update-item"></a><span data-ttu-id="eb8f5-105">Actualizar elemento</span><span class="sxs-lookup"><span data-stu-id="eb8f5-105">Update Item</span></span>
 
<span data-ttu-id="eb8f5-106">**Resumen:** Obtenga más información sobre la operación de actualización de elementos, que es parte del servicio de elementos.</span><span class="sxs-lookup"><span data-stu-id="eb8f5-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="eb8f5-107">El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="eb8f5-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="eb8f5-108">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="eb8f5-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="eb8f5-109">La operación actualizar elemento forma parte del servicio de elemento en la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="eb8f5-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="eb8f5-110">Actualizar elemento</span><span class="sxs-lookup"><span data-stu-id="eb8f5-110">Update Item</span></span>

<span data-ttu-id="eb8f5-111">Actualizar elemento actualiza un elemento específico en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="eb8f5-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="eb8f5-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="eb8f5-112">**Method**</span></span>|<span data-ttu-id="eb8f5-113">**Solicitar URI**</span><span class="sxs-lookup"><span data-stu-id="eb8f5-113">**Request URI**</span></span>|<span data-ttu-id="eb8f5-114">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="eb8f5-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="eb8f5-115">CORRER</span><span class="sxs-lookup"><span data-stu-id="eb8f5-115">PUT</span></span>  <br/> |<span data-ttu-id="eb8f5-116">https://\<portal\>/QoERepositoryService/Repository/Item/{Itemid}</span><span class="sxs-lookup"><span data-stu-id="eb8f5-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="eb8f5-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="eb8f5-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="eb8f5-118">**Parámetros de URI** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="eb8f5-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="eb8f5-119">**Solicitar encabezados** -tipo de contenido: aplicación/JSON.</span><span class="sxs-lookup"><span data-stu-id="eb8f5-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="eb8f5-120">**Solicitar cuerpo** : JSON.</span><span class="sxs-lookup"><span data-stu-id="eb8f5-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="eb8f5-121">Carga de solicitud de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="eb8f5-121">Sample request payload:</span></span>
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="eb8f5-122">*contenido*  Datos con formato JSON que se almacenan como el nuevo contenido de un elemento secundario existente.</span><span class="sxs-lookup"><span data-stu-id="eb8f5-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="eb8f5-123">Técnicamente, un repositorio puede almacenar cualquier contenido de cualquier esquema, pero cuando se usa para el panel de calidad de llamadas, debe ser un informe o una consulta.</span><span class="sxs-lookup"><span data-stu-id="eb8f5-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="eb8f5-124">*Escriba*  Especifica siempre "Application/JSON" para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="eb8f5-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="eb8f5-125">**Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="eb8f5-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="eb8f5-126">**Código de estado** : una operación correcta devuelve el código de estado 204 (sin contenido).</span><span class="sxs-lookup"><span data-stu-id="eb8f5-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="eb8f5-127">Si no se encuentra un identificador de elemento especificado, devuelve el código de estado 404 (no se encontró).</span><span class="sxs-lookup"><span data-stu-id="eb8f5-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="eb8f5-128">"Sin contenido" no es un estado de error.</span><span class="sxs-lookup"><span data-stu-id="eb8f5-128">"No Content" is not an error status.</span></span> <span data-ttu-id="eb8f5-129">Significa que una respuesta no devolvió nada en el cuerpo (por el contrario, 200 aceptar devuelve contenido en cuerpo).</span><span class="sxs-lookup"><span data-stu-id="eb8f5-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="eb8f5-130">Indica que el elemento se ha actualizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="eb8f5-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="eb8f5-131">**Encabezados de respuesta** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="eb8f5-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="eb8f5-132">**Cuerpo** de la respuesta: ninguno.</span><span class="sxs-lookup"><span data-stu-id="eb8f5-132">**Response Body** - None.</span></span>
  

