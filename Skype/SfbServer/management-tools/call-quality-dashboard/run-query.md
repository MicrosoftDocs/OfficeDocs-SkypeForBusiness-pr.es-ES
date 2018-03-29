---
title: Ejecutar consulta
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Resumen: Conozca la operación Ejecutar consulta, que forma parte de la API de datos para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 6e294625e173854382e39abc098a0480871586ac
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="run-query"></a><span data-ttu-id="21688-104">Ejecutar consulta</span><span class="sxs-lookup"><span data-stu-id="21688-104">Run Query</span></span>
 
<span data-ttu-id="21688-105">**Resumen:** Obtener información sobre la operación de ejecutar consulta, que forma parte de la API de datos para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="21688-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="21688-106">Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="21688-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="21688-107">La operación de ejecutar consulta forma parte de la API de datos para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="21688-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="run-query"></a><span data-ttu-id="21688-108">Ejecutar consulta</span><span class="sxs-lookup"><span data-stu-id="21688-108">Run Query</span></span>

<span data-ttu-id="21688-109">Ejecutar consulta operación proporciona la capacidad de ejecutar una consulta en el cubo basándose en los filtros, las medidas y dimensiones especificadas y devolver los datos de nuevo.</span><span class="sxs-lookup"><span data-stu-id="21688-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>
  

|<span data-ttu-id="21688-110">**Método**</span><span class="sxs-lookup"><span data-stu-id="21688-110">**Method**</span></span>|<span data-ttu-id="21688-111">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="21688-111">**Request URI**</span></span>|<span data-ttu-id="21688-112">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="21688-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="21688-113">Exponer</span><span class="sxs-lookup"><span data-stu-id="21688-113">POST</span></span>  <br/> |<span data-ttu-id="21688-114">https://\<portal\>/QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="21688-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="21688-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="21688-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="21688-116">**URI parámetros** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="21688-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="21688-117">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="21688-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="21688-118">El **Cuerpo de la solicitud** - aquí es una carga de solicitud muestra en JSON.</span><span class="sxs-lookup"><span data-stu-id="21688-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="21688-119">Contiene dimensiones, filtros y medida necesaria para una consulta.</span><span class="sxs-lookup"><span data-stu-id="21688-119">It contains dimensions, filters, and measurement required for a query.</span></span>
  
```
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

 <span data-ttu-id="21688-120">*Filtros* : una lista de expresiones de filtro para aplicar tales que el conjunto de datos resultante se reflejan sólo el subconjunto de los datos que son de interés.</span><span class="sxs-lookup"><span data-stu-id="21688-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>
  
 <span data-ttu-id="21688-121">*Dimensiones* - una lista de las dimensiones que se utilizará para la agregación de los datos.</span><span class="sxs-lookup"><span data-stu-id="21688-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="21688-122">Se requiere al menos una dimensión pero pueden especificarse varias dimensiones para obtener un nivel adicional de agregados secundarios.</span><span class="sxs-lookup"><span data-stu-id="21688-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>
  
 <span data-ttu-id="21688-123">*Medidas* : una lista de medidas, también conocido como hechos, que son las métricas a agregarse deseadas se basan en las dimensiones que especificó.</span><span class="sxs-lookup"><span data-stu-id="21688-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>
  
 <span data-ttu-id="21688-124">*Trend* - instrucciones de control adicional para personalizar los datos de resultado.</span><span class="sxs-lookup"><span data-stu-id="21688-124">*Trend*  - Additional control instructions to customize the result data.</span></span>
  
 <span data-ttu-id="21688-125">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="21688-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="21688-126">**Código de estado** - una operación correcta devuelve el código de estado 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="21688-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="21688-127">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="21688-127">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="21688-128">**Cuerpo de la respuesta** : a continuación es una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="21688-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="21688-129">Contiene una tabla de datos que contiene los datos, también contendrá metadatos, que muestra el tiempo de ejecución de la consulta y si son o no los datos de la caché.</span><span class="sxs-lookup"><span data-stu-id="21688-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>
  
```
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

 <span data-ttu-id="21688-130">*Tiempo de ejecución* - el tiempo total que tarda el servidor devuelva los datos.</span><span class="sxs-lookup"><span data-stu-id="21688-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="21688-131">Esto puede o no puede implicar la caché.</span><span class="sxs-lookup"><span data-stu-id="21688-131">This may or may not involve cache.</span></span>
  
 <span data-ttu-id="21688-132">*Resultados de datos* - el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="21688-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="21688-133">Es una matriz bidimensional que contiene todas las permutaciones de los miembros de las dimensiones y cada elemento que contiene los nombres de miembros de las dimensiones, así como los valores agregados de las medidas especificadas.</span><span class="sxs-lookup"><span data-stu-id="21688-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>
  
 <span data-ttu-id="21688-134">*Resultado es de la caché* - para diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="21688-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="21688-135">Indica si el resultado procede de la memoria caché o del cubo de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="21688-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
  

