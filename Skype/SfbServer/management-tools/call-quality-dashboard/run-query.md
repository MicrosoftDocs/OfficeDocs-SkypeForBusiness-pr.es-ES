---
title: Ejecutar consulta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Resumen: Obtenga información sobre la operación ejecutar consulta, que forma parte de la API de datos para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 8d31ea4c597ea3353fdd5da3e863938aababe819
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991405"
---
# <a name="run-query"></a><span data-ttu-id="d5ae1-104">Ejecutar consulta</span><span class="sxs-lookup"><span data-stu-id="d5ae1-104">Run Query</span></span>

<span data-ttu-id="d5ae1-105">**Resumen:** Obtenga información sobre la operación ejecutar consulta, que forma parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="d5ae1-106">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="d5ae1-107">La operación ejecutar consulta forma parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="d5ae1-108">Ejecutar consulta</span><span class="sxs-lookup"><span data-stu-id="d5ae1-108">Run Query</span></span>

<span data-ttu-id="d5ae1-109">Ejecutar la operación de consulta proporciona la capacidad de ejecutar una consulta en el cubo basándose en las dimensiones, medidas y filtros especificados y devolver los datos.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="d5ae1-110">**Método**</span><span class="sxs-lookup"><span data-stu-id="d5ae1-110">**Method**</span></span>|<span data-ttu-id="d5ae1-111">**Solicitar URI**</span><span class="sxs-lookup"><span data-stu-id="d5ae1-111">**Request URI**</span></span>|<span data-ttu-id="d5ae1-112">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="d5ae1-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d5ae1-113">Exponer</span><span class="sxs-lookup"><span data-stu-id="d5ae1-113">POST</span></span>  <br/> |<span data-ttu-id="d5ae1-114">https://\<portal\>/QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="d5ae1-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="d5ae1-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="d5ae1-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="d5ae1-116">**Parámetros de URI** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="d5ae1-117">**Solicitar encabezados** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="d5ae1-118">**Solicitar cuerpo** : aquí es una carga de solicitud de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="d5ae1-119">Contiene dimensiones, filtros y medidas necesarias para una consulta.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-119">It contains dimensions, filters, and measurement required for a query.</span></span>

```json
{
"Filters": [{
"DataModelName": "[StartDate].[Month]",
"Caption": "July 2013",
"Value": "[2015-03-01T00:00:00]",
"Operand": 0,
"UnionGroup": ""
}],
"Dimensions": [{
"DataModelName": "[StartDate].[Month]"
}],
"Measurements": [{
"DataModelName": "[Measures].[Audio Good Streams Count]"
},
{
"DataModelName": "[Measures].[Audio UnClassified Streams Count]"
},
{
"DataModelName": "[Measures].[Audio Poor Streams Count]"
},
{
"DataModelName": "[Measures].[AudioPoorPercentage]"
}],
"Trend": {
"EnableTrend": true,
"SpanCount": 7,
"TrendDate": "2015-3",
"Type": 0
}
}
```

 <span data-ttu-id="d5ae1-120">*Filtros* : una lista de expresiones de filtro que se aplicarán de tal modo que el conjunto de datos resultante solo reflejará el subconjunto de datos que son de interés.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="d5ae1-121">*Dimensiones* : una lista de las dimensiones que se usarán para agregar los datos.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="d5ae1-122">Se necesita al menos una dimensión, pero se pueden especificar varias dimensiones para obtener el nivel adicional de subagregaciones.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="d5ae1-123">*Medidas* : una lista de medidas, también conocidas como hechos, que son las métricas que se desean agregar según las dimensiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="d5ae1-124">*Tendencia* : instrucciones de control adicionales para personalizar los datos de resultado.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="d5ae1-125">**Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="d5ae1-126">**Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).</span><span class="sxs-lookup"><span data-stu-id="d5ae1-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="d5ae1-127">**Encabezados de respuesta** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="d5ae1-128">**Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="d5ae1-129">Contiene una tabla de datos que contiene los datos; también contendrá un metadatos, que muestra el tiempo de ejecución de la consulta y si los datos proceden o no de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

```json
{
"ExecutionTime": "00:00:00.2102630",
"DataResult": [["September 2014",
        1792,
        34,
        78,
        4.171],
        ["October 2014",
        37017,
        1731,
        3305,
        8.197],
        ["November 2014",
        79184,
        3033,
        5556,
        6.557],
        ["December 2014",
        122253,
        4050,
        5444,
        4.263],
        ["January 2015",
        31246,
        1069,
        1342,
        4.118]],
"ResultIsFromCache": false,
"ErrorType": 0
}
```

 <span data-ttu-id="d5ae1-130">*Tiempo de ejecución* : el tiempo total que ha tardado el servidor en devolver los datos.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="d5ae1-131">Esto puede o no implicar caché.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="d5ae1-132">*Resultado de datos* : resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="d5ae1-133">Se trata de una matriz bidimensional que contiene todas las permutaciones de los miembros de las dimensiones, y cada elemento que contiene los nombres de los miembros de las dimensiones, así como los valores agregados de las medidas especificadas.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="d5ae1-134">El *resultado es de la caché* , para diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="d5ae1-135">Indica si el resultado procede de la caché o del cubo de calidad.</span><span class="sxs-lookup"><span data-stu-id="d5ae1-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
