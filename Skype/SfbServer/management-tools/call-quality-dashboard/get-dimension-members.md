---
title: Obtener miembros de dimensión
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Resumen: obtenga información sobre la operación Obtener miembros de dimensión. La operación Obtener miembros de dimensión forma parte de la API de datos para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: ffec3b02a3c876a003adb679a28b0e8f2edb91c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832640"
---
# <a name="get-dimension-members"></a><span data-ttu-id="da24f-105">Obtener miembros de dimensión</span><span class="sxs-lookup"><span data-stu-id="da24f-105">Get Dimension Members</span></span>
 
<span data-ttu-id="da24f-106">**Resumen:** Obtenga información sobre la operación Obtener miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="da24f-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="da24f-107">La operación Obtener miembros de dimensión forma parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="da24f-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="da24f-108">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="da24f-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="da24f-109">La operación Obtener miembros de dimensión forma parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="da24f-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="da24f-110">Obtener miembros de dimensión</span><span class="sxs-lookup"><span data-stu-id="da24f-110">Get Dimension Members</span></span>

<span data-ttu-id="da24f-111">La operación Obtener miembros de dimensión devuelve la lista de miembros de una dimensión específica.</span><span class="sxs-lookup"><span data-stu-id="da24f-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="da24f-112">También permite filtrar la lista de miembros y obtener un subconjunto para reducir el costo de transferencia bancaria.</span><span class="sxs-lookup"><span data-stu-id="da24f-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="da24f-113">**Método**</span><span class="sxs-lookup"><span data-stu-id="da24f-113">**Method**</span></span>|<span data-ttu-id="da24f-114">**URI de solicitud**</span><span class="sxs-lookup"><span data-stu-id="da24f-114">**Request URI**</span></span>|<span data-ttu-id="da24f-115">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="da24f-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="da24f-116">PUBLICAR</span><span class="sxs-lookup"><span data-stu-id="da24f-116">POST</span></span>  <br/> |<span data-ttu-id="da24f-117">https:// \<portal\> /QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="da24f-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="da24f-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="da24f-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="da24f-119">**Parámetros uri:** ninguno.</span><span class="sxs-lookup"><span data-stu-id="da24f-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="da24f-120">**Encabezados de solicitud:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="da24f-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="da24f-121">**Cuerpo de** la solicitud: contiene el nombre de la dimensión para la que queremos los miembros.</span><span class="sxs-lookup"><span data-stu-id="da24f-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="da24f-122">También el número máximo de miembros devueltos, además de especificar algún filtrado para limitar los miembros devueltos.</span><span class="sxs-lookup"><span data-stu-id="da24f-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 <span data-ttu-id="da24f-123">**Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="da24f-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="da24f-124">**Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto).</span><span class="sxs-lookup"><span data-stu-id="da24f-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="da24f-125">**Encabezados de respuesta:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="da24f-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="da24f-126">**Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON en respuesta a una solicitud de "[StartDate]. Dimensión [Mes]".</span><span class="sxs-lookup"><span data-stu-id="da24f-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="da24f-127">La lista solo muestra una pequeña parte de la lista.</span><span class="sxs-lookup"><span data-stu-id="da24f-127">The list is only showing a small portion of the list.</span></span> 
  
```json
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}
```
