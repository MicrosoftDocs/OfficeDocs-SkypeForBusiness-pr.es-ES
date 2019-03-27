---
title: API de datos para el panel de calidad de llamada (CQD) en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Resumen: Obtenga información sobre la API de Rata para el panel de calidad de llamada. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 8dd04971533a8631b4f95be2f13bad84e41963d7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881806"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="8c2ad-104">API de datos para el panel de calidad de llamada (CQD) en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8c2ad-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="8c2ad-105">**Resumen:** Obtenga información acerca de la API de Rata para el panel de calidad de llamada.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-105">**Summary:** Learn about the Rata API for Call Quality Dashboard.</span></span> <span data-ttu-id="8c2ad-106">Panel de calidad de llamada es una herramienta de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="8c2ad-107">La API de datos proporciona acceso mediante programación para llamar al panel de calidad de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="8c2ad-108">API de datos para el panel de calidad de llamada</span><span class="sxs-lookup"><span data-stu-id="8c2ad-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="8c2ad-109">La API de datos ofrece una interfaz de consulta para el cubo de QoE.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="8c2ad-110">La API de datos es una API de REST para trabajar con la base de datos multidimensional que proporciona agregadas métricas de QoE en función de los filtros y las dimensiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="8c2ad-111">Las operaciones de REST se incluyen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="8c2ad-112">**Operación**</span><span class="sxs-lookup"><span data-stu-id="8c2ad-112">**Operation**</span></span>|<span data-ttu-id="8c2ad-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="8c2ad-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="8c2ad-114">Obtener cubo</span><span class="sxs-lookup"><span data-stu-id="8c2ad-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="8c2ad-115">Obtener la lista de dimensiones disponibles y las medidas.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="8c2ad-116">Obtener miembros de dimensión</span><span class="sxs-lookup"><span data-stu-id="8c2ad-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="8c2ad-117">Operación de obtención de miembros de dimensión, devuelve la lista de miembros de una dimensión específica.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="8c2ad-118">También proporcionan la capacidad de filtrar la lista de miembros y obtener un subconjunto, para reducir el costo de transferencia de cable.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="8c2ad-119">Ejecutar consulta</span><span class="sxs-lookup"><span data-stu-id="8c2ad-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="8c2ad-120">Ejecutar consulta operación proporciona la capacidad de ejecutar una consulta en el cubo en función de los filtros, las medidas y dimensiones especificadas y volver atrás los datos.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="8c2ad-121">Borrar caché</span><span class="sxs-lookup"><span data-stu-id="8c2ad-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="8c2ad-122">Operación de caché borrado elimina la memoria caché en el servidor de consultas y los datos.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="8c2ad-123">Esto restablecerá la memoria caché y se va a obtener datos actualizados desde QoE cubo más adelante para nuevas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="8c2ad-124">Obtener integración de registro</span><span class="sxs-lookup"><span data-stu-id="8c2ad-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="8c2ad-125">Obtenga la operación devuelve una lista de entradas de registro que describe las actividades en el cubo de QoE de procesamiento de registro de integración.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="8c2ad-126">Obtener últimos datos de integración</span><span class="sxs-lookup"><span data-stu-id="8c2ad-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="8c2ad-127">Obtenga los últimos datos de integración del cubo.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="8c2ad-128">**Recursos de origen cruzado (CORS) compatibilidad con API de datos de uso compartido**</span><span class="sxs-lookup"><span data-stu-id="8c2ad-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="8c2ad-129">API de datos admite el uso compartido de recursos de origen cruzado (CORS).</span><span class="sxs-lookup"><span data-stu-id="8c2ad-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="8c2ad-130">CORS es una característica HTTP que permite a una aplicación web que se ejecuta en un dominio tener acceso a recursos en otro dominio.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="8c2ad-131">Los exploradores Web implementan una restricción de seguridad que se conoce como directiva del mismo origen de [Directiva del mismo origen](https://www.w3.org/Security/wiki/Same_Origin_Policy) que impide que una página web de llamar a las API en un dominio diferente.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="8c2ad-132">CORS proporciona una forma segura para permitir que un dominio (el dominio de origen) para llamar a las API en otro dominio.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="8c2ad-133">Vea la [especificación de CORS](https://www.w3.org/TR/cors/) para obtener información detallada en CORS.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="8c2ad-134">**Habilitar CORS para la API de datos**</span><span class="sxs-lookup"><span data-stu-id="8c2ad-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="8c2ad-135">El siguiente es un fragmento del archivo web.config de API de datos, que muestra dos dominios incluidos en la configuración de la aplicación corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="8c2ad-136">Todas las solicitudes realizadas por los scripts que se cargan desde estos servidores son de confianza mediante la API de datos.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="8c2ad-137">No olvide incluir el protocolo exacta, el nombre de host y el puerto (si hay alguno).</span><span class="sxs-lookup"><span data-stu-id="8c2ad-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="8c2ad-138">No para colocar cualquiera diagonal carácter (/) al final.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="8c2ad-139">Pueden especificarse varias entradas, separe con comas.</span><span class="sxs-lookup"><span data-stu-id="8c2ad-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


