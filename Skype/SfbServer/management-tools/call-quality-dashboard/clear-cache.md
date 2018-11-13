---
title: Borrar caché
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Resumen: Obtenga información acerca de la operación Borrar caché, que es parte de la API de datos para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 64873e7257877859ff8b16c504cee93d3287f9ed
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294514"
---
# <a name="clear-cache"></a><span data-ttu-id="33471-104">Borrar caché</span><span class="sxs-lookup"><span data-stu-id="33471-104">Clear Cache</span></span>
 
<span data-ttu-id="33471-105">**Resumen:** Obtenga información acerca de la operación Borrar caché, que es parte de la API de datos para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="33471-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="33471-106">Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="33471-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="33471-107">La operación Borrar caché es parte de la API de datos para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="33471-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="33471-108">Borrar caché</span><span class="sxs-lookup"><span data-stu-id="33471-108">Clear Cache</span></span>

<span data-ttu-id="33471-109">Operación de caché borrado elimina la memoria caché en el servidor de consultas y los datos.</span><span class="sxs-lookup"><span data-stu-id="33471-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="33471-110">Esto restablecerá la memoria caché y se va a obtener datos actualizados desde QoE cubo más adelante para nuevas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="33471-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="33471-111">**(Método)**</span><span class="sxs-lookup"><span data-stu-id="33471-111">**Method**</span></span>|<span data-ttu-id="33471-112">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="33471-112">**Request URI**</span></span>|<span data-ttu-id="33471-113">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="33471-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="33471-114">Exponer</span><span class="sxs-lookup"><span data-stu-id="33471-114">POST</span></span>  <br/> |<span data-ttu-id="33471-115">https://\<portal\>/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="33471-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="33471-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="33471-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="33471-117">**Los parámetros URI** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="33471-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="33471-118">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="33471-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="33471-119">**Cuerpo de la convocatoria** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="33471-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="33471-120">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="33471-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="33471-121">**Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).</span><span class="sxs-lookup"><span data-stu-id="33471-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="33471-122">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="33471-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="33471-123">**Cuerpo de la respuesta** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="33471-123">**Response Body** - None.</span></span>
  

