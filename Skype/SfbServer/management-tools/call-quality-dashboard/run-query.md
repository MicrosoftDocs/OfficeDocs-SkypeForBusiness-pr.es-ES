---
title: Ejecutar consulta
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
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Resumen: obtenga información sobre la operación Ejecutar consulta, que forma parte de la API de datos para el Panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: bff24ca5a4d651ba276b4b0d795afabce3c6d0dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803120"
---
# <a name="run-query"></a><span data-ttu-id="6103b-104">Ejecutar consulta</span><span class="sxs-lookup"><span data-stu-id="6103b-104">Run Query</span></span>

<span data-ttu-id="6103b-105">**Resumen:** Obtenga información sobre la operación Ejecutar consulta, que forma parte de la API de datos para el Panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6103b-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="6103b-106">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6103b-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="6103b-107">La operación Ejecutar consulta forma parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6103b-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="6103b-108">Ejecutar consulta</span><span class="sxs-lookup"><span data-stu-id="6103b-108">Run Query</span></span>

<span data-ttu-id="6103b-109">La operación Ejecutar consulta permite ejecutar una consulta en el cubo en función de las dimensiones, medidas y filtros especificados y devolver los datos.</span><span class="sxs-lookup"><span data-stu-id="6103b-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="6103b-110">**Método**</span><span class="sxs-lookup"><span data-stu-id="6103b-110">**Method**</span></span>|<span data-ttu-id="6103b-111">**URI de solicitud**</span><span class="sxs-lookup"><span data-stu-id="6103b-111">**Request URI**</span></span>|<span data-ttu-id="6103b-112">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="6103b-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6103b-113">PUBLICAR</span><span class="sxs-lookup"><span data-stu-id="6103b-113">POST</span></span>  <br/> |<span data-ttu-id="6103b-114">https:// \<portal\> /QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="6103b-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="6103b-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="6103b-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="6103b-116">**Parámetros uri:** ninguno.</span><span class="sxs-lookup"><span data-stu-id="6103b-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="6103b-117">**Encabezados de solicitud:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="6103b-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="6103b-118">**Cuerpo de la** solicitud: esta es una carga de solicitud de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="6103b-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="6103b-119">Contiene dimensiones, filtros y medidas necesarias para una consulta.</span><span class="sxs-lookup"><span data-stu-id="6103b-119">It contains dimensions, filters, and measurement required for a query.</span></span>

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

 <span data-ttu-id="6103b-120">*Filtros:*  una lista de expresiones de filtro que se aplicarán de manera que el conjunto de datos resultante refleje solo el subconjunto de los datos que son de interés.</span><span class="sxs-lookup"><span data-stu-id="6103b-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="6103b-121">*Dimensiones:*  una lista de dimensiones que se usará para agregar los datos.</span><span class="sxs-lookup"><span data-stu-id="6103b-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="6103b-122">Se requiere al menos una dimensión, pero se pueden especificar varias dimensiones para obtener un nivel adicional de subamendas.</span><span class="sxs-lookup"><span data-stu-id="6103b-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="6103b-123">*Medidas:*  una lista de medidas, también conocidas como hechos, que son las métricas deseadas que se agregarán en función de las dimensiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="6103b-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="6103b-124">*Tendencia:*  instrucciones de control adicionales para personalizar los datos de resultados.</span><span class="sxs-lookup"><span data-stu-id="6103b-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="6103b-125">**Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6103b-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="6103b-126">**Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto).</span><span class="sxs-lookup"><span data-stu-id="6103b-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="6103b-127">**Encabezados de respuesta:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="6103b-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="6103b-128">**Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="6103b-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="6103b-129">Contiene una tabla de datos que contiene los datos, además de un metadatos, que muestra el tiempo de ejecución de la consulta y si los datos son o no de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="6103b-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

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

 <span data-ttu-id="6103b-130">*Tiempo de*  ejecución: tiempo total que tardó el servidor en devolver los datos.</span><span class="sxs-lookup"><span data-stu-id="6103b-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="6103b-131">Esto puede implicar o no la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="6103b-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="6103b-132">*Resultado de los*  datos: el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="6103b-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="6103b-133">Es una matriz bidimensional que contiene todas las permutaciones de los miembros de las dimensiones y cada elemento que contiene los nombres de los miembros de las dimensiones, así como los valores agregados de las medidas especificadas.</span><span class="sxs-lookup"><span data-stu-id="6103b-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="6103b-134">*El resultado es de la memoria*  caché: para diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="6103b-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="6103b-135">Indica si el resultado provenía de la memoria caché o del cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="6103b-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
