---
title: Obtener el cubo
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Resumen: Obtenga información acerca de la operación obtener cubo, que es parte de la API de datos para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 228ebd8f9bcb6db919f418ef9809bce1b3eb7f90
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035676"
---
# <a name="get-cube"></a><span data-ttu-id="d2033-104">Obtener el cubo</span><span class="sxs-lookup"><span data-stu-id="d2033-104">Get Cube</span></span>
 
<span data-ttu-id="d2033-105">**Resumen:** Obtenga información acerca de la operación obtener cubo, que es parte de la API de datos para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="d2033-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="d2033-106">Panel de calidad de llamada es una herramienta de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="d2033-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="d2033-107">La operación obtener Cube es parte de la API de datos para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="d2033-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="d2033-108">Obtener el cubo</span><span class="sxs-lookup"><span data-stu-id="d2033-108">Get Cube</span></span>

<span data-ttu-id="d2033-109">Operación de cubo Get devuelve la lista de dimensiones disponibles y las medidas.</span><span class="sxs-lookup"><span data-stu-id="d2033-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="d2033-110">**(Método)**</span><span class="sxs-lookup"><span data-stu-id="d2033-110">**Method**</span></span>|<span data-ttu-id="d2033-111">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="d2033-111">**Request URI**</span></span>|<span data-ttu-id="d2033-112">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="d2033-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d2033-113">Obtener</span><span class="sxs-lookup"><span data-stu-id="d2033-113">GET</span></span>  <br/> |<span data-ttu-id="d2033-114">https://\<portal\>/QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="d2033-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="d2033-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="d2033-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="d2033-116">**Los parámetros URI** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="d2033-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="d2033-117">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="d2033-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d2033-118">**Cuerpo de la convocatoria** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="d2033-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="d2033-119">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="d2033-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="d2033-120">**Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).</span><span class="sxs-lookup"><span data-stu-id="d2033-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="d2033-121">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="d2033-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d2033-122">**Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON.</span><span class="sxs-lookup"><span data-stu-id="d2033-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d2033-123">En este ejemplo se muestra sólo dos primeros elementos de cada grupos de elementos de cubo.</span><span class="sxs-lookup"><span data-stu-id="d2033-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
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

 <span data-ttu-id="d2033-124">*Los KPI* - reservado</span><span class="sxs-lookup"><span data-stu-id="d2033-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="d2033-125">La sección de KPI de una carga de solicitud permite el funcionamiento de ejecutar la consulta devolver los valores para los KPI definidos en el cubo.</span><span class="sxs-lookup"><span data-stu-id="d2033-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="d2033-126">Ningún KPI aún existe en el cubo de QoE.</span><span class="sxs-lookup"><span data-stu-id="d2033-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="d2033-127">*Dimensiones* - la lista de dimensiones que se puede usar en las secciones de filtros y las dimensiones de una carga de solicitud para la operación de ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="d2033-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="d2033-128">Para usar una dimensión en una expresión de filtro, debe especificar a un miembro de dimensión, que puede obtenerse mediante la operación de obtener miembros de dimensión.</span><span class="sxs-lookup"><span data-stu-id="d2033-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="d2033-129">*Las medidas* : la lista de las medidas que pueden utilizarse en la sección de las medidas de una carga de solicitud para la operación de ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="d2033-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

