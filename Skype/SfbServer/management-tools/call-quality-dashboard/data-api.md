---
title: API de datos para panel de calidad de llamadas (CQD) en Skype Empresarial Server
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
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Resumen: obtenga información sobre la API de datos para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 367aa1bf1103863fff37fbcd4f8d9fa379de7c1d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832700"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="57e64-104">API de datos para panel de calidad de llamadas (CQD) en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="57e64-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="57e64-105">**Resumen:** Obtenga información sobre la API de datos para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="57e64-105">**Summary:** Learn about the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="57e64-106">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="57e64-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="57e64-107">La API de datos proporciona acceso mediante programación para el Panel de calidad de llamadas para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="57e64-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="57e64-108">API de datos para panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="57e64-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="57e64-109">La API de datos ofrece una interfaz de consulta para el cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="57e64-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="57e64-110">La API de datos es una API de REST para trabajar con una base de datos multidimensional que proporciona métricas de QoE agregadas basadas en filtros y dimensiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="57e64-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="57e64-111">Las operaciones rest se incluyen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="57e64-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="57e64-112">**Operación**</span><span class="sxs-lookup"><span data-stu-id="57e64-112">**Operation**</span></span>|<span data-ttu-id="57e64-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="57e64-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="57e64-114">Obtener cubo</span><span class="sxs-lookup"><span data-stu-id="57e64-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="57e64-115">Obtiene la lista de dimensiones y medidas disponibles.</span><span class="sxs-lookup"><span data-stu-id="57e64-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="57e64-116">Obtener miembros de dimensión</span><span class="sxs-lookup"><span data-stu-id="57e64-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="57e64-117">La operación Obtener miembros de dimensión devuelve la lista de miembros de una dimensión específica.</span><span class="sxs-lookup"><span data-stu-id="57e64-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="57e64-118">También permite filtrar la lista de miembros y obtener un subconjunto para reducir el costo de transferencia bancaria.</span><span class="sxs-lookup"><span data-stu-id="57e64-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="57e64-119">Ejecutar consulta</span><span class="sxs-lookup"><span data-stu-id="57e64-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="57e64-120">La operación Ejecutar consulta permite ejecutar una consulta en el cubo en función de las dimensiones, medidas y filtros especificados y devolver los datos.</span><span class="sxs-lookup"><span data-stu-id="57e64-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="57e64-121">Borrar caché</span><span class="sxs-lookup"><span data-stu-id="57e64-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="57e64-122">La operación Borrar caché elimina la memoria caché del servidor para consultas y datos.</span><span class="sxs-lookup"><span data-stu-id="57e64-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="57e64-123">Esto restablecerá la memoria caché y se recibirán datos nuevos del cubo QoE posteriormente para las nuevas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="57e64-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="57e64-124">Obtener integración de registro</span><span class="sxs-lookup"><span data-stu-id="57e64-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="57e64-125">La operación Obtener registro de integración devuelve una lista de entradas de registro que describen las actividades en el procesamiento del cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="57e64-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="57e64-126">Obtener últimos datos de integración</span><span class="sxs-lookup"><span data-stu-id="57e64-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="57e64-127">Obtenga los últimos datos de integración del cubo.</span><span class="sxs-lookup"><span data-stu-id="57e64-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="57e64-128">**Compatibilidad con uso compartido de recursos entre orígenes (CORS) para API de datos**</span><span class="sxs-lookup"><span data-stu-id="57e64-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="57e64-129">La API de datos admite el uso compartido de recursos entre orígenes (CORS).</span><span class="sxs-lookup"><span data-stu-id="57e64-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="57e64-130">CORS es una característica HTTP que permite que una aplicación web que se ejecuta en un dominio obtenga acceso a los recursos de otro dominio.</span><span class="sxs-lookup"><span data-stu-id="57e64-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="57e64-131">Los exploradores web implementan [](https://www.w3.org/Security/wiki/Same_Origin_Policy) una restricción de seguridad conocida como directiva de mismo origen que impide que una página web llame a las API de un dominio diferente.</span><span class="sxs-lookup"><span data-stu-id="57e64-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="57e64-132">CORS proporciona una forma segura de permitir que un dominio (el dominio de origen) llame a las API de otro dominio.</span><span class="sxs-lookup"><span data-stu-id="57e64-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="57e64-133">Consulta la [especificación de CORS](https://www.w3.org/TR/cors/) para obtener más información sobre CORS.</span><span class="sxs-lookup"><span data-stu-id="57e64-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="57e64-134">**Habilitar CORS para la API de datos**</span><span class="sxs-lookup"><span data-stu-id="57e64-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="57e64-135">A continuación se muestra un extracto de la API de web.config, que muestra dos dominios enumerados en la configuración de la aplicación corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="57e64-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="57e64-136">Todas las solicitudes realizadas por los scripts cargados desde estos servidores son de confianza para la API de datos.</span><span class="sxs-lookup"><span data-stu-id="57e64-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="57e64-137">Recuerde incluir el protocolo, el nombre de host y el puerto exactos (si los hay).</span><span class="sxs-lookup"><span data-stu-id="57e64-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="57e64-138">No coloque ningún carácter de barra diagonal (/) al final.</span><span class="sxs-lookup"><span data-stu-id="57e64-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="57e64-139">Se pueden especificar varias entradas separándose con comas.</span><span class="sxs-lookup"><span data-stu-id="57e64-139">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


