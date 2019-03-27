---
title: Ejecutar consulta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Resumen: Obtenga información acerca de la operación de ejecutar la consulta, que es parte de la API de datos para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 8a1bea338039914695e16d1294f28abfe1e4b559
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899154"
---
# <a name="run-query"></a><span data-ttu-id="b9bef-104">Ejecutar consulta</span><span class="sxs-lookup"><span data-stu-id="b9bef-104">Run Query</span></span>

<span data-ttu-id="b9bef-105">**Resumen:** Obtenga información acerca de la operación de ejecutar la consulta, que es parte de la API de datos para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="b9bef-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="b9bef-106">Panel de calidad de llamada es una herramienta de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b9bef-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="b9bef-107">La operación de ejecutar la consulta forma parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b9bef-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="b9bef-108">Ejecutar consulta</span><span class="sxs-lookup"><span data-stu-id="b9bef-108">Run Query</span></span>

<span data-ttu-id="b9bef-109">Ejecutar consulta operación proporciona la capacidad de ejecutar una consulta en el cubo en función de los filtros, las medidas y dimensiones especificadas y volver atrás los datos.</span><span class="sxs-lookup"><span data-stu-id="b9bef-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="b9bef-110">**(Método)**</span><span class="sxs-lookup"><span data-stu-id="b9bef-110">**Method**</span></span>|<span data-ttu-id="b9bef-111">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="b9bef-111">**Request URI**</span></span>|<span data-ttu-id="b9bef-112">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="b9bef-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b9bef-113">Exponer</span><span class="sxs-lookup"><span data-stu-id="b9bef-113">POST</span></span>  <br/> |<span data-ttu-id="b9bef-114">https://\<portal\>/QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="b9bef-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="b9bef-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="b9bef-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="b9bef-116">**Los parámetros URI** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="b9bef-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="b9bef-117">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="b9bef-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="b9bef-118">**Cuerpo de la solicitud** - aquí es una carga de solicitud de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="b9bef-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="b9bef-119">Contiene las dimensiones, filtros y medida necesaria para una consulta.</span><span class="sxs-lookup"><span data-stu-id="b9bef-119">It contains dimensions, filters, and measurement required for a query.</span></span>

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

 <span data-ttu-id="b9bef-120">*Filtros* : una lista de expresiones de filtro que se aplique tal que el conjunto de datos resultante reflejará sólo el subconjunto de los datos que son de interés.</span><span class="sxs-lookup"><span data-stu-id="b9bef-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="b9bef-121">*Dimensiones* - una lista de las dimensiones que se usará para la agregación de los datos.</span><span class="sxs-lookup"><span data-stu-id="b9bef-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="b9bef-122">Se requiere al menos una dimensión, pero se pueden especificar varias dimensiones para obtener un nivel adicional de agregaciones subcaracterística.</span><span class="sxs-lookup"><span data-stu-id="b9bef-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="b9bef-123">*Las medidas* : una lista de las medidas, también conocido como hechos, que son las métricas que desee para agregarse según las dimensiones que especificó.</span><span class="sxs-lookup"><span data-stu-id="b9bef-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="b9bef-124">*Tendencia* - instrucciones adicionales de control para personalizar los datos de resultado.</span><span class="sxs-lookup"><span data-stu-id="b9bef-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="b9bef-125">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="b9bef-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="b9bef-126">**Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).</span><span class="sxs-lookup"><span data-stu-id="b9bef-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="b9bef-127">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="b9bef-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="b9bef-128">**Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="b9bef-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="b9bef-129">Contiene una tabla de datos que contiene los datos, también va a contener metadatos, que muestra el tiempo de ejecución de la consulta y si está o no los datos de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="b9bef-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

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

 <span data-ttu-id="b9bef-130">*Tiempo de ejecución* : el tiempo total que tardó el servidor devuelva los datos.</span><span class="sxs-lookup"><span data-stu-id="b9bef-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="b9bef-131">Esto puede o no puede implicar la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="b9bef-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="b9bef-132">*Resultado de los datos* - el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="b9bef-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="b9bef-133">Es una matriz bidimensional que contiene todas las permutaciones de miembros de las dimensiones y cada elemento que contiene los nombres de miembros de las dimensiones, así como los valores agregados de las mediciones especificados.</span><span class="sxs-lookup"><span data-stu-id="b9bef-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="b9bef-134">*Resultado es de la caché* - para diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="b9bef-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="b9bef-135">Indica si el resultado procede de la memoria caché o desde el cubo de QoE.</span><span class="sxs-lookup"><span data-stu-id="b9bef-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
