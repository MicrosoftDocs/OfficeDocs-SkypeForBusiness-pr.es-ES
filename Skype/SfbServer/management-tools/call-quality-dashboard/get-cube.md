---
title: Obtener cubo
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Resumen: obtenga información sobre la operación Obtener cubo, que forma parte de la API de datos para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: a3527f21bc1751c23bba088ae06c3e6702cb8c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832630"
---
# <a name="get-cube"></a><span data-ttu-id="6fb39-104">Obtener cubo</span><span class="sxs-lookup"><span data-stu-id="6fb39-104">Get Cube</span></span>
 
<span data-ttu-id="6fb39-105">**Resumen:** Obtenga información sobre la operación Obtener cubo, que forma parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6fb39-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="6fb39-106">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6fb39-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="6fb39-107">La operación Obtener cubo forma parte de la API de datos para el Panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6fb39-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="6fb39-108">Obtener cubo</span><span class="sxs-lookup"><span data-stu-id="6fb39-108">Get Cube</span></span>

<span data-ttu-id="6fb39-109">La operación Obtener cubo devuelve la lista de dimensiones y medidas disponibles.</span><span class="sxs-lookup"><span data-stu-id="6fb39-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="6fb39-110">**Método**</span><span class="sxs-lookup"><span data-stu-id="6fb39-110">**Method**</span></span>|<span data-ttu-id="6fb39-111">**URI de solicitud**</span><span class="sxs-lookup"><span data-stu-id="6fb39-111">**Request URI**</span></span>|<span data-ttu-id="6fb39-112">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="6fb39-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6fb39-113">GET</span><span class="sxs-lookup"><span data-stu-id="6fb39-113">GET</span></span>  <br/> |<span data-ttu-id="6fb39-114">https:// \<portal\> /QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="6fb39-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="6fb39-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="6fb39-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="6fb39-116">**Parámetros uri:** ninguno.</span><span class="sxs-lookup"><span data-stu-id="6fb39-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="6fb39-117">**Encabezados de solicitud:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="6fb39-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6fb39-118">**Cuerpo de la** solicitud: ninguno.</span><span class="sxs-lookup"><span data-stu-id="6fb39-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="6fb39-119">**Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="6fb39-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="6fb39-120">**Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto).</span><span class="sxs-lookup"><span data-stu-id="6fb39-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="6fb39-121">**Encabezados de respuesta:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="6fb39-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6fb39-122">**Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="6fb39-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6fb39-123">En este ejemplo solo se muestran los dos primeros elementos de cada grupo de elementos Cube.</span><span class="sxs-lookup"><span data-stu-id="6fb39-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
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

 <span data-ttu-id="6fb39-124">*KPI:*  reservados.</span><span class="sxs-lookup"><span data-stu-id="6fb39-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="6fb39-125">La sección KPI de una carga de solicitud permite que la operación Ejecutar consulta devuelva valores para los KPI definidos en el cubo.</span><span class="sxs-lookup"><span data-stu-id="6fb39-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="6fb39-126">Todavía no existe ningún KPI en el cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="6fb39-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="6fb39-127">*Dimensiones: lista*  de dimensiones que se pueden usar en las secciones Filtros y Dimensiones de una carga de solicitud para la operación Ejecutar consulta.</span><span class="sxs-lookup"><span data-stu-id="6fb39-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="6fb39-128">Para usar una dimensión en una expresión de filtro, debe especificar un miembro de dimensión, que se puede obtener mediante la operación Obtener miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="6fb39-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="6fb39-129">*Medidas:*  lista de medidas que se pueden usar en la sección Medidas de una carga de solicitud para la operación Ejecutar consulta.</span><span class="sxs-lookup"><span data-stu-id="6fb39-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

