---
title: Obtener integración de registro
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Resumen: obtenga información sobre la operación Obtener registro de integración, que forma parte de la API de datos para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 69827fa9f3fd3f56843a41867b029a071799ba66
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832600"
---
# <a name="get-integration-log"></a><span data-ttu-id="4404a-104">Obtener integración de registro</span><span class="sxs-lookup"><span data-stu-id="4404a-104">Get Integration Log</span></span>
 
<span data-ttu-id="4404a-105">**Resumen:** Obtenga información sobre la operación Obtener registro de integración, que forma parte de la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="4404a-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="4404a-106">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4404a-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="4404a-107">La operación Obtener registro de integración forma parte de la API de datos para el panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="4404a-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="4404a-108">Obtener integración de registro</span><span class="sxs-lookup"><span data-stu-id="4404a-108">Get Integration Log</span></span>

<span data-ttu-id="4404a-109">La operación Obtener registro de integración devuelve una lista de entradas de registro que describen las actividades en el procesamiento del cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="4404a-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="4404a-110">Esta operación está deshabilitada de forma predeterminada por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4404a-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="4404a-111">Cuando se deshabilita, devuelve una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="4404a-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="4404a-112">Para habilitar esta operación, los administradores deben configurar el web.config de la aplicación web host de la API de datos.</span><span class="sxs-lookup"><span data-stu-id="4404a-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="4404a-113">Method</span><span class="sxs-lookup"><span data-stu-id="4404a-113">Method</span></span>|<span data-ttu-id="4404a-114">**URI de solicitud**</span><span class="sxs-lookup"><span data-stu-id="4404a-114">**Request URI**</span></span>|<span data-ttu-id="4404a-115">**Versión HTTP**</span><span class="sxs-lookup"><span data-stu-id="4404a-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4404a-116">GET</span><span class="sxs-lookup"><span data-stu-id="4404a-116">GET</span></span>  <br/> |<span data-ttu-id="4404a-117">https:// \<portal\> /QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="4404a-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="4404a-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="4404a-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="4404a-119">**Parámetros uri:** ninguno.</span><span class="sxs-lookup"><span data-stu-id="4404a-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="4404a-120">**Encabezados de solicitud:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="4404a-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4404a-121">**Cuerpo de la** solicitud: ninguno.</span><span class="sxs-lookup"><span data-stu-id="4404a-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="4404a-122">**Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="4404a-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="4404a-123">**Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto).</span><span class="sxs-lookup"><span data-stu-id="4404a-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="4404a-124">**Encabezados de respuesta:** no hay encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="4404a-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4404a-125">**Cuerpo de la** respuesta: a continuación se muestra una estructura de ejemplo de entradas de registro.</span><span class="sxs-lookup"><span data-stu-id="4404a-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


