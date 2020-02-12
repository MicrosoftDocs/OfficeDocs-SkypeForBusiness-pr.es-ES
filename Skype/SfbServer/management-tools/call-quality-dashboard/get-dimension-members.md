---
title: Obtener miembros de dimensión
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Resumen: Obtenga información sobre la operación obtener miembros de dimensión. La operación obtener miembros de dimensión forma parte de la API de datos para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 40e5ac8b95c24c3a8cb759da99f7d7aeaa391576
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888819"
---
# <a name="get-dimension-members"></a><span data-ttu-id="77a24-105">Obtener miembros de dimensión</span><span class="sxs-lookup"><span data-stu-id="77a24-105">Get Dimension Members</span></span>
 
<span data-ttu-id="77a24-106">**Resumen:** Obtenga más información sobre la operación obtener miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="77a24-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="77a24-107">La operación obtener miembros de dimensión forma parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="77a24-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="77a24-108">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="77a24-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="77a24-109">La operación obtener miembros de dimensión forma parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="77a24-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="77a24-110">Obtener miembros de dimensión</span><span class="sxs-lookup"><span data-stu-id="77a24-110">Get Dimension Members</span></span>

<span data-ttu-id="77a24-111">Operación de obtención de miembros de dimensión devuelve la lista de miembros de una dimensión específica.</span><span class="sxs-lookup"><span data-stu-id="77a24-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="77a24-112">También ofrece la posibilidad de filtrar la lista de miembros y obtener un subconjunto, para reducir el coste de la transferencia bancaria.</span><span class="sxs-lookup"><span data-stu-id="77a24-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="77a24-113">**Método**</span><span class="sxs-lookup"><span data-stu-id="77a24-113">**Method**</span></span>|<span data-ttu-id="77a24-114">**Solicitar URI**</span><span class="sxs-lookup"><span data-stu-id="77a24-114">**Request URI**</span></span>|<span data-ttu-id="77a24-115">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="77a24-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="77a24-116">Exponer</span><span class="sxs-lookup"><span data-stu-id="77a24-116">POST</span></span>  <br/> |<span data-ttu-id="77a24-117">https://\<portal\>/QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="77a24-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="77a24-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="77a24-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="77a24-119">**Parámetros de URI** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="77a24-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="77a24-120">**Solicitar encabezados** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="77a24-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="77a24-121">**Solicitar cuerpo** : contiene el nombre de la dimensión para la que deseamos los miembros.</span><span class="sxs-lookup"><span data-stu-id="77a24-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="77a24-122">También se devuelve un número máximo de miembros, junto a usted puede especificar algunos filtros para limitar los miembros devueltos.</span><span class="sxs-lookup"><span data-stu-id="77a24-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
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

 <span data-ttu-id="77a24-123">**Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="77a24-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="77a24-124">**Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).</span><span class="sxs-lookup"><span data-stu-id="77a24-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="77a24-125">**Encabezados de respuesta** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="77a24-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="77a24-126">**Cuerpo de respuesta** : a continuación se muestra una carga de respuesta de ejemplo en JSON en respuesta a una solicitud de "[fechainicio]. [Month] "dimensión.</span><span class="sxs-lookup"><span data-stu-id="77a24-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="77a24-127">La lista solo muestra una pequeña parte de la lista.</span><span class="sxs-lookup"><span data-stu-id="77a24-127">The list is only showing a small portion of the list.</span></span> 
  
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
