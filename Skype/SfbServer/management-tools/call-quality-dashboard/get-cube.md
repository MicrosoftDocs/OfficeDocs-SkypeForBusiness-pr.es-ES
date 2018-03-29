---
title: Obtener el cubo
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Resumen: Conozca la operación de obtener el cubo, que forma parte de la API de datos para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: e39a88e249dc807b201b08d966285d93ae7f82a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-cube"></a><span data-ttu-id="4af7b-104">Obtener el cubo</span><span class="sxs-lookup"><span data-stu-id="4af7b-104">Get Cube</span></span>
 
<span data-ttu-id="4af7b-105">**Resumen:** Obtener información sobre la operación de obtener el cubo, que forma parte de la API de datos para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="4af7b-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="4af7b-106">Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4af7b-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4af7b-107">La operación Get Cube es parte de la API de datos para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="4af7b-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="4af7b-108">Obtener el cubo</span><span class="sxs-lookup"><span data-stu-id="4af7b-108">Get Cube</span></span>

<span data-ttu-id="4af7b-109">Operación de cubo Get devuelve la lista de medidas y dimensiones disponibles.</span><span class="sxs-lookup"><span data-stu-id="4af7b-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="4af7b-110">**Método**</span><span class="sxs-lookup"><span data-stu-id="4af7b-110">**Method**</span></span>|<span data-ttu-id="4af7b-111">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="4af7b-111">**Request URI**</span></span>|<span data-ttu-id="4af7b-112">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="4af7b-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4af7b-113">Obtener</span><span class="sxs-lookup"><span data-stu-id="4af7b-113">GET</span></span>  <br/> |<span data-ttu-id="4af7b-114">https://\<portal\>/QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="4af7b-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="4af7b-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="4af7b-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="4af7b-116">**URI parámetros** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="4af7b-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="4af7b-117">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="4af7b-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4af7b-118">**Cuerpo de la solicitud** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="4af7b-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="4af7b-119">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="4af7b-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="4af7b-120">**Código de estado** - una operación correcta devuelve el código de estado 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="4af7b-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="4af7b-121">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="4af7b-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4af7b-122">**Cuerpo de la respuesta** : a continuación es una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="4af7b-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4af7b-123">En este ejemplo sólo muestra dos primeros elementos de cada grupo de elementos del cubo.</span><span class="sxs-lookup"><span data-stu-id="4af7b-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
```
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

 <span data-ttu-id="4af7b-124">*KPI* - reservado</span><span class="sxs-lookup"><span data-stu-id="4af7b-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="4af7b-125">La sección de KPI de una carga de solicitud permite ejecutar consulta devolver los valores de los KPI definidos en el cubo.</span><span class="sxs-lookup"><span data-stu-id="4af7b-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="4af7b-126">No hay KPI aún existe en el cubo de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="4af7b-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="4af7b-127">*Dimensiones* - la lista de dimensiones que pueden utilizarse en las secciones de filtros y las dimensiones de una carga de solicitud para la operación de ejecutar consulta.</span><span class="sxs-lookup"><span data-stu-id="4af7b-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="4af7b-128">Para utilizar una dimensión en una expresión de filtro, debe especificar a un miembro de dimensión, que puede obtenerse mediante la operación de obtener miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="4af7b-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="4af7b-129">*Mediciones* : la lista de medidas que pueden utilizarse en la sección de mediciones de una carga de solicitud para la operación de ejecutar consulta.</span><span class="sxs-lookup"><span data-stu-id="4af7b-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

