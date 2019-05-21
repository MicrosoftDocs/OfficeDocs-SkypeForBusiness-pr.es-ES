---
title: Obtener últimos datos de integración
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 'Resumen: Obtenga información sobre la operación obtener datos de la última integración, que forma parte de la API de datos para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: d110bdc1fe88a9fe7f77abe7f7b9ed47a3324eb0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274698"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="19116-104">Obtener últimos datos de integración</span><span class="sxs-lookup"><span data-stu-id="19116-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="19116-105">**Resumen:** Obtenga más información sobre la operación obtener datos de la última integración, que forma parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="19116-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="19116-106">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="19116-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="19116-107">La operación obtener datos de la última integración es parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="19116-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="19116-108">Obtener últimos datos de integración</span><span class="sxs-lookup"><span data-stu-id="19116-108">Get Last Integration Data</span></span>

<span data-ttu-id="19116-109">Obtener la operación de datos de la última integración devuelve la lista de los 5 últimos resultados de archivado y procesamiento de cubo.</span><span class="sxs-lookup"><span data-stu-id="19116-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="19116-110">Esta característica está deshabilitada de forma predeterminada y debe habilitarse mediante la configuración de la API de datos.</span><span class="sxs-lookup"><span data-stu-id="19116-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="19116-111">**Método**</span><span class="sxs-lookup"><span data-stu-id="19116-111">**Method**</span></span>|<span data-ttu-id="19116-112">**Solicitar URI**</span><span class="sxs-lookup"><span data-stu-id="19116-112">**Request URI**</span></span>|<span data-ttu-id="19116-113">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="19116-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="19116-114">Obtener</span><span class="sxs-lookup"><span data-stu-id="19116-114">GET</span></span>  <br/> |<span data-ttu-id="19116-115">https://\<portal\>/QoEDataService/IntegrationLog/status</span><span class="sxs-lookup"><span data-stu-id="19116-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="19116-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="19116-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="19116-117">**Parámetros de URI** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="19116-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="19116-118">**Solicitar encabezados** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="19116-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="19116-119">**Solicitar cuerpo** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="19116-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="19116-120">**Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="19116-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="19116-121">**Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).</span><span class="sxs-lookup"><span data-stu-id="19116-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="19116-122">**Encabezados de respuesta** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="19116-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="19116-123">**Cuerpo de respuesta** : a continuación se muestra un ejemplo de registro.</span><span class="sxs-lookup"><span data-stu-id="19116-123">**Response Body** - Below is a sample log status.</span></span>
  
```
{
"LastSuccessIntegrations": ["01/18/2015 10:30:13",
"01/18/2015 10:28:29",
"01/17/2015 15:15:17",
"01/17/2015 15:00:17",
"01/17/2015 14:45:13"],
"LastSuccessCubeProcessings": ["01/17/2015 15:16:40",
"01/17/2015 15:01:41",
"01/17/2015 14:47:19",
"01/17/2015 14:31:40",
"01/17/2015 14:17:01"],
"LastFailedIntegrations":  ,
"LastFailedCubeProcessings": ["01/18/2015 10:30:58",
"01/18/2015 10:29:28",
"01/17/2015 10:02:20",
"01/15/2015 20:01:56",
"01/15/2015 19:45:50"],
"LastDataIntegrationStart": null,
"LastCubeProcessingStart": "01/18/2015 10:30:16"
}
```
