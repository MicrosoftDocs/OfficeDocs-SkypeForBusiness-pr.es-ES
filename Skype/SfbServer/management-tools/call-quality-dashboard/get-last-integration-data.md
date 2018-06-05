---
title: Obtener los últimos datos de integración
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 'Resumen: Obtenga información acerca de la operación Obtener última datos de integración, que es parte de la API de datos para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: bcef1a1ad8a42f01133c45a6af093e3c7d1e3123
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19570202"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="03891-104">Obtener los últimos datos de integración</span><span class="sxs-lookup"><span data-stu-id="03891-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="03891-105">**Resumen:** Obtenga información acerca de la operación Obtener última datos de integración, que es parte de la API de datos para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="03891-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="03891-106">Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="03891-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="03891-107">La operación de obtener datos de integración de última forma parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="03891-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="03891-108">Obtener los últimos datos de integración</span><span class="sxs-lookup"><span data-stu-id="03891-108">Get Last Integration Data</span></span>

<span data-ttu-id="03891-109">Operación de datos de integración último Get devuelve la lista de los últimos 5 éxito o error de archivado y el procesamiento del cubo.</span><span class="sxs-lookup"><span data-stu-id="03891-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="03891-110">Esta característica está deshabilitada de forma predeterminada y debe habilitarse mediante la configuración de la API de datos.</span><span class="sxs-lookup"><span data-stu-id="03891-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="03891-111">**(Método)**</span><span class="sxs-lookup"><span data-stu-id="03891-111">**Method**</span></span>|<span data-ttu-id="03891-112">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="03891-112">**Request URI**</span></span>|<span data-ttu-id="03891-113">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="03891-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="03891-114">Obtener</span><span class="sxs-lookup"><span data-stu-id="03891-114">GET</span></span>  <br/> |<span data-ttu-id="03891-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span><span class="sxs-lookup"><span data-stu-id="03891-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="03891-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="03891-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="03891-117">**Los parámetros URI** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="03891-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="03891-118">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="03891-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="03891-119">**Cuerpo de la convocatoria** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="03891-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="03891-120">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="03891-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="03891-121">**Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).</span><span class="sxs-lookup"><span data-stu-id="03891-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="03891-122">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="03891-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="03891-123">**Cuerpo de la respuesta** - a continuación es un estado de registro de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="03891-123">**Response Body** - Below is a sample log status.</span></span>
  
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