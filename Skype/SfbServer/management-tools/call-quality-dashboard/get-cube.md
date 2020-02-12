---
title: Obtener cubo
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Resumen: Obtenga información sobre la operación obtener cubo, que forma parte de la API de datos para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 1d8327439d79e7d02182dc7195bc0052bf6c923c
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888829"
---
# <a name="get-cube"></a><span data-ttu-id="6c359-104">Obtener cubo</span><span class="sxs-lookup"><span data-stu-id="6c359-104">Get Cube</span></span>
 
<span data-ttu-id="6c359-105">**Resumen:** Obtenga información sobre la operación obtener cubo, que forma parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6c359-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="6c359-106">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6c359-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="6c359-107">La operación obtener cubo es parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6c359-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="6c359-108">Obtener cubo</span><span class="sxs-lookup"><span data-stu-id="6c359-108">Get Cube</span></span>

<span data-ttu-id="6c359-109">La operación obtener cubo devuelve la lista de dimensiones y medidas disponibles.</span><span class="sxs-lookup"><span data-stu-id="6c359-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="6c359-110">**Método**</span><span class="sxs-lookup"><span data-stu-id="6c359-110">**Method**</span></span>|<span data-ttu-id="6c359-111">**Solicitar URI**</span><span class="sxs-lookup"><span data-stu-id="6c359-111">**Request URI**</span></span>|<span data-ttu-id="6c359-112">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="6c359-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c359-113">Obtener</span><span class="sxs-lookup"><span data-stu-id="6c359-113">GET</span></span>  <br/> |<span data-ttu-id="6c359-114">https://\<portal\>/QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="6c359-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="6c359-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="6c359-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="6c359-116">**Parámetros de URI** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="6c359-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="6c359-117">**Solicitar encabezados** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="6c359-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6c359-118">**Solicitar cuerpo** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="6c359-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="6c359-119">**Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6c359-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="6c359-120">**Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).</span><span class="sxs-lookup"><span data-stu-id="6c359-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="6c359-121">**Encabezados de respuesta** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="6c359-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6c359-122">**Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON.</span><span class="sxs-lookup"><span data-stu-id="6c359-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6c359-123">Este ejemplo solo muestra los dos primeros elementos de cada grupo de elementos de cubo.</span><span class="sxs-lookup"><span data-stu-id="6c359-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
```json
{
"Kpis": [{
"FriendlyName": "Poor Trend Month",
"DataModelName": "[KPIValue].Poor Trend Month",
"Description": null
},
{
"FriendlyName": "Poor Rate Trend Month",
"DataModelName": "[KPIValue].Poor Rate Trend Month",
"Description": null
}],
"Dimensions": [{
"Category": "Access Location Pair",
"Attributes": [{
"FriendlyName": "Location Pair",
"DataModelName": "[Access Location Pair].[Location Pair]",
"Description": "Description of Location Pair"
}]
},
{
"Category": "Audio Bandwidth Est",
"Attributes": [{
"FriendlyName": "Metric",
"DataModelName": "[Audio Bandwidth Est].[Metric]",
"Description": "Description of Metric"
}]
}],
"Measurements": [{
"FriendlyName": "Audio Streams Count",
"DataModelName": "[Measures].[Audio Streams Count]",
"Description": "Description of Audio Streams Count"
},
{
"FriendlyName": "Audio Good Streams JPDR Count",
"DataModelName": "[Measures].[Audio Good Streams JPDR Count]",
"Description": "Description of Audio Good Streams JPDR Count"
}]
}
```

 <span data-ttu-id="6c359-124">*KPI* : reservado.</span><span class="sxs-lookup"><span data-stu-id="6c359-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="6c359-125">La sección KPI de una carga de solicitud permite que la operación ejecutar consulta devuelva valores para los KPI definidos en el cubo.</span><span class="sxs-lookup"><span data-stu-id="6c359-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="6c359-126">Aún no existe ningún KPI en el cubo de calidad.</span><span class="sxs-lookup"><span data-stu-id="6c359-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="6c359-127">*Dimensiones* : la lista de dimensiones que se pueden usar en secciones de filtros y dimensiones de una solicitud de carga para la operación ejecutar consulta.</span><span class="sxs-lookup"><span data-stu-id="6c359-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="6c359-128">Para usar una dimensión en una expresión de filtro, debe especificar un miembro de la dimensión, que se puede obtener con la operación de obtención de miembros de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="6c359-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="6c359-129">*Medidas* : la lista de medidas que se pueden usar en la sección medidas de una carga de solicitud para la operación ejecutar consulta.</span><span class="sxs-lookup"><span data-stu-id="6c359-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

