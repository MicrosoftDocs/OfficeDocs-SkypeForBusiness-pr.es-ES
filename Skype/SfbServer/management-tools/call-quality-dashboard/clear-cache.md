---
title: Borrar caché
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Resumen: Obtenga información acerca de la operación Borrar caché, que es parte de la API de datos para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: c2371a7f99eb37e8e01be919bf6c31b0c9a452cb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32195554"
---
# <a name="clear-cache"></a><span data-ttu-id="3d0e6-104">Borrar caché</span><span class="sxs-lookup"><span data-stu-id="3d0e6-104">Clear Cache</span></span>
 
<span data-ttu-id="3d0e6-105">**Resumen:** Obtenga información acerca de la operación Borrar caché, que es parte de la API de datos para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="3d0e6-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="3d0e6-106">Panel de calidad de llamada es una herramienta de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="3d0e6-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="3d0e6-107">La operación Borrar caché es parte de la API de datos para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="3d0e6-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="3d0e6-108">Borrar caché</span><span class="sxs-lookup"><span data-stu-id="3d0e6-108">Clear Cache</span></span>

<span data-ttu-id="3d0e6-109">Operación de caché borrado elimina la memoria caché en el servidor de consultas y los datos.</span><span class="sxs-lookup"><span data-stu-id="3d0e6-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="3d0e6-110">Esto restablecerá la memoria caché y se va a obtener datos actualizados desde QoE cubo más adelante para nuevas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="3d0e6-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="3d0e6-111">**(Método)**</span><span class="sxs-lookup"><span data-stu-id="3d0e6-111">**Method**</span></span>|<span data-ttu-id="3d0e6-112">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="3d0e6-112">**Request URI**</span></span>|<span data-ttu-id="3d0e6-113">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="3d0e6-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3d0e6-114">Exponer</span><span class="sxs-lookup"><span data-stu-id="3d0e6-114">POST</span></span>  <br/> |<span data-ttu-id="3d0e6-115">https://\<portal\>/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="3d0e6-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="3d0e6-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="3d0e6-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="3d0e6-117">**Los parámetros URI** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="3d0e6-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="3d0e6-118">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="3d0e6-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="3d0e6-119">**Cuerpo de la convocatoria** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="3d0e6-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="3d0e6-120">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="3d0e6-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="3d0e6-121">**Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).</span><span class="sxs-lookup"><span data-stu-id="3d0e6-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="3d0e6-122">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="3d0e6-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="3d0e6-123">**Cuerpo de la respuesta** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="3d0e6-123">**Response Body** - None.</span></span>
  

