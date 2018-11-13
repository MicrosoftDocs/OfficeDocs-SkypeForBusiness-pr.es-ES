---
title: Obtener Log integración
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Resumen: Obtenga información acerca de la operación obtener Log de integración, que es parte de la API de datos para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 1b21e078578b9e198c743f77f77e4beca94ddeaf
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294835"
---
# <a name="get-integration-log"></a><span data-ttu-id="bf41f-104">Obtener Log integración</span><span class="sxs-lookup"><span data-stu-id="bf41f-104">Get Integration Log</span></span>
 
<span data-ttu-id="bf41f-105">**Resumen:** Obtenga información acerca de la operación obtener Log de integración, que es parte de la API de datos para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="bf41f-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="bf41f-106">Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bf41f-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="bf41f-107">La operación de obtener el registro de integración es parte de la API de datos para el panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="bf41f-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="bf41f-108">Obtener Log integración</span><span class="sxs-lookup"><span data-stu-id="bf41f-108">Get Integration Log</span></span>

<span data-ttu-id="bf41f-109">Obtenga la operación devuelve una lista de entradas de registro que describe las actividades en el cubo de QoE de procesamiento de registro de integración.</span><span class="sxs-lookup"><span data-stu-id="bf41f-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="bf41f-110">Esta operación está deshabilitada de forma predeterminada por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bf41f-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="bf41f-111">Cuando deshabilitado, devuelve una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="bf41f-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="bf41f-112">Para habilitar esta operación, los administradores deben configurar el archivo web.config para la aplicación web de host de la API de datos.</span><span class="sxs-lookup"><span data-stu-id="bf41f-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="bf41f-113">(Método)</span><span class="sxs-lookup"><span data-stu-id="bf41f-113">Method</span></span>|<span data-ttu-id="bf41f-114">**URI de la solicitud**</span><span class="sxs-lookup"><span data-stu-id="bf41f-114">**Request URI**</span></span>|<span data-ttu-id="bf41f-115">**Versión de HTTP**</span><span class="sxs-lookup"><span data-stu-id="bf41f-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bf41f-116">Obtener</span><span class="sxs-lookup"><span data-stu-id="bf41f-116">GET</span></span>  <br/> |<span data-ttu-id="bf41f-117">https://\<portal\>/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="bf41f-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="bf41f-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="bf41f-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="bf41f-119">**Los parámetros URI** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="bf41f-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="bf41f-120">**Encabezados de solicitud** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="bf41f-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bf41f-121">**Cuerpo de la convocatoria** - ninguno.</span><span class="sxs-lookup"><span data-stu-id="bf41f-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="bf41f-122">**Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.</span><span class="sxs-lookup"><span data-stu-id="bf41f-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="bf41f-123">**Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).</span><span class="sxs-lookup"><span data-stu-id="bf41f-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="bf41f-124">**Encabezados de respuesta** - sin encabezados adicionales.</span><span class="sxs-lookup"><span data-stu-id="bf41f-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bf41f-125">**Cuerpo de la respuesta** - a continuación es un ejemplo de estructura de entradas de registro.</span><span class="sxs-lookup"><span data-stu-id="bf41f-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


