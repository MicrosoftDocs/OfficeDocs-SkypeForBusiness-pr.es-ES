---
title: Obtener integración de registro
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Resumen: Obtenga información sobre la operación obtener registro de integración, que forma parte de la API de datos para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 58be983ff3b282c94a4b42619a6c37c6270afcb5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274761"
---
# <a name="get-integration-log"></a><span data-ttu-id="d60db-104">Obtener integración de registro</span><span class="sxs-lookup"><span data-stu-id="d60db-104">Get Integration Log</span></span>
 
<span data-ttu-id="d60db-105">**Resumen:** Obtenga más información sobre la operación obtener registro de integración, que forma parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d60db-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="d60db-106">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d60db-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="d60db-107">La operación obtener registro de integración es parte de la API de datos para el panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="d60db-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="d60db-108">Obtener integración de registro</span><span class="sxs-lookup"><span data-stu-id="d60db-108">Get Integration Log</span></span>

<span data-ttu-id="d60db-109">La operación obtener registro de integración devuelve una lista de entradas de registro que describen las actividades en el procesamiento del cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="d60db-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="d60db-110">Esta operación está deshabilitada de forma predeterminada por razones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d60db-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="d60db-111">Cuando se deshabilita, devuelve una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="d60db-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="d60db-112">Para habilitar esta operación, los administradores deben configurar el archivo Web. config para la aplicación Web de host de la API de datos.</span><span class="sxs-lookup"><span data-stu-id="d60db-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="d60db-113">Método</span><span class="sxs-lookup"><span data-stu-id="d60db-113">Method</span></span>|<span data-ttu-id="d60db-114">**Solicitar URI**</span><span class="sxs-lookup"><span data-stu-id="d60db-114">**Request URI**</span></span>|<span data-ttu-id="d60db-115">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="d60db-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d60db-116">Obtener</span><span class="sxs-lookup"><span data-stu-id="d60db-116">GET</span></span>  <br/> |<span data-ttu-id="d60db-117">https://\<portal\>/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="d60db-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="d60db-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="d60db-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="d60db-119">**Parámetros de URI** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="d60db-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="d60db-120">**Solicitar encabezados** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="d60db-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d60db-121">**Solicitar cuerpo** : ninguno.</span><span class="sxs-lookup"><span data-stu-id="d60db-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="d60db-122">**Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="d60db-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="d60db-123">**Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).</span><span class="sxs-lookup"><span data-stu-id="d60db-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="d60db-124">**Encabezados de respuesta** : no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="d60db-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d60db-125">**Cuerpo de respuesta** : a continuación se muestra una estructura de ejemplo de entradas de registro.</span><span class="sxs-lookup"><span data-stu-id="d60db-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


