---
title: Obtener a miembros de dimensión
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Resumen: Obtenga información acerca de la operación obtener miembros de dimensión. La operación de obtener miembros de dimensión forma parte de la API de datos para el panel de calidad de llamadas. Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: e15f63d5ad52c9fbc52d692fd5bbb0480a41a50a
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569281"
---
# <a name="get-dimension-members"></a><span data-ttu-id="ede30-105">Obtener a miembros de dimensión</span><span class="sxs-lookup"><span data-stu-id="ede30-105">Get Dimension Members</span></span>
 
<span data-ttu-id="ede30-106">**Resumen:** Obtenga información acerca de la operación obtener miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="ede30-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="ede30-107">La operación de obtener miembros de dimensión forma parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ede30-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="ede30-108">Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ede30-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ede30-109">La operación de obtener miembros de dimensión forma parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ede30-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="ede30-110">Obtener a miembros de dimensión</span><span class="sxs-lookup"><span data-stu-id="ede30-110">Get Dimension Members</span></span>

<span data-ttu-id="ede30-111">Operación de obtención de miembros de dimensión, devuelve la lista de miembros de una dimensión específica.</span><span class="sxs-lookup"><span data-stu-id="ede30-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="ede30-112">También proporcionan la capacidad de filtrar la lista de miembros y obtener un subconjunto, para reducir el costo de transferencia de cable.</span><span class="sxs-lookup"><span data-stu-id="ede30-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="ede30-113">**(Método)**</span><span class="sxs-lookup"><span data-stu-id="ede30-113">**Method**</span></span>|<span data-ttu-id="ede30-114">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="ede30-114">**Request URI**</span></span>|<span data-ttu-id="ede30-115">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="ede30-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ede30-116">Exponer</span><span class="sxs-lookup"><span data-stu-id="ede30-116">POST</span></span>  <br/> |<span data-ttu-id="ede30-117">https://\<portal\>/QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="ede30-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="ede30-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="ede30-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="ede30-119">**Los parámetros URI** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="ede30-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="ede30-120">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="ede30-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ede30-121">**Cuerpo de la solicitud** - contiene el nombre de dimensión que se desea que los miembros de.</span><span class="sxs-lookup"><span data-stu-id="ede30-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="ede30-122">También se devuelve el número máximo de miembros, junto a puede especificar algunos filtrado para limitar a los miembros devueltos.</span><span class="sxs-lookup"><span data-stu-id="ede30-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
```
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 <span data-ttu-id="ede30-123">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="ede30-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="ede30-124">**Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).</span><span class="sxs-lookup"><span data-stu-id="ede30-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="ede30-125">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="ede30-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ede30-126">**Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON en respuesta a una solicitud de "[StartDate]. [Mes] "dimensión.</span><span class="sxs-lookup"><span data-stu-id="ede30-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ede30-127">La lista muestra sólo una pequeña parte de la lista.</span><span class="sxs-lookup"><span data-stu-id="ede30-127">The list is only showing a small portion of the list.</span></span> 
  
```
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