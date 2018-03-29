---
title: API de datos de llamada Quality Dashboard (CQD) en Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: 'Resumen: Conozca la Rata API para panel de calidad de la llamada. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 038324064177c110c0736092985e9da1b330ea8b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a><span data-ttu-id="b1697-104">API de datos de llamada Quality Dashboard (CQD) en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b1697-104">Data API for Call Quality Dashboard (CQD) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b1697-105">**Resumen:** Conozca la Rata API para panel de calidad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b1697-105">**Summary:** Learn about the Rata API for Call Quality Dashboard.</span></span> <span data-ttu-id="b1697-106">Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b1697-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b1697-107">La API de datos proporciona acceso mediante programación para llamar al panel de calidad para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b1697-107">The Data API provides programmatic access for Call Quality Dashboard for Skype for Business Server 2015.</span></span>
  
## <a name="data-api-for-call-quality-dashboard"></a><span data-ttu-id="b1697-108">API de datos para el panel de calidad de la llamada</span><span class="sxs-lookup"><span data-stu-id="b1697-108">Data API for Call Quality Dashboard</span></span>

<span data-ttu-id="b1697-109">La API de datos ofrece una interfaz de consulta al cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="b1697-109">The Data API offers a query interface to the QoE Cube.</span></span> <span data-ttu-id="b1697-110">La API de datos es una API de REST para trabajar con una base de datos multidimensional que proporciona métricas de calidad agregados basados en los filtros y las dimensiones especificadas.</span><span class="sxs-lookup"><span data-stu-id="b1697-110">The Data API is a REST API for working with multi-dimensional database that provides aggregated QoE metrics based on specified dimensions and filters.</span></span>
  
<span data-ttu-id="b1697-111">Las operaciones de resto se incluyen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="b1697-111">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="b1697-112">**Operación**</span><span class="sxs-lookup"><span data-stu-id="b1697-112">**Operation**</span></span>|<span data-ttu-id="b1697-113">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b1697-113">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b1697-114">Obtener el cubo</span><span class="sxs-lookup"><span data-stu-id="b1697-114">Get Cube</span></span>](get-cube.md) <br/> |<span data-ttu-id="b1697-115">Obtener la lista de medidas y dimensiones disponibles.</span><span class="sxs-lookup"><span data-stu-id="b1697-115">Get the list of available dimensions and measurements.</span></span>  <br/> |
|[<span data-ttu-id="b1697-116">Los miembros de dimensión</span><span class="sxs-lookup"><span data-stu-id="b1697-116">Get Dimension Members</span></span>](get-dimension-members.md) <br/> |<span data-ttu-id="b1697-117">Operación de obtención de miembros de dimensión, devuelve la lista de miembros de una dimensión específica.</span><span class="sxs-lookup"><span data-stu-id="b1697-117">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="b1697-118">También proporcionan la capacidad para filtrar la lista de miembros y obtener un subconjunto, para reducir el costo de la transferencia de alambre.</span><span class="sxs-lookup"><span data-stu-id="b1697-118">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>  <br/> |
|[<span data-ttu-id="b1697-119">Ejecutar consulta</span><span class="sxs-lookup"><span data-stu-id="b1697-119">Run Query</span></span>](run-query.md) <br/> |<span data-ttu-id="b1697-120">Ejecutar consulta operación proporciona la capacidad de ejecutar una consulta en el cubo basándose en los filtros, las medidas y dimensiones especificadas y devolver los datos de nuevo.</span><span class="sxs-lookup"><span data-stu-id="b1697-120">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>  <br/> |
|[<span data-ttu-id="b1697-121">Borrar caché</span><span class="sxs-lookup"><span data-stu-id="b1697-121">Clear Cache</span></span>](clear-cache.md) <br/> |<span data-ttu-id="b1697-122">Operación de caché borrado elimina la caché en el servidor para consultas y datos.</span><span class="sxs-lookup"><span data-stu-id="b1697-122">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="b1697-123">Esto restablecerá la caché y le facilitaremos datos nuevos de cubo QoE posteriormente para las nuevas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="b1697-123">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>  <br/> |
|[<span data-ttu-id="b1697-124">Obtener Log integración</span><span class="sxs-lookup"><span data-stu-id="b1697-124">Get Integration Log</span></span>](get-integration-log.md) <br/> |<span data-ttu-id="b1697-125">Obtener Log integración operación devuelve una lista de entradas del registro que describe las actividades en el cubo de la calidad de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="b1697-125">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>  <br/> |
|[<span data-ttu-id="b1697-126">Obtener los últimos datos de integración</span><span class="sxs-lookup"><span data-stu-id="b1697-126">Get Last Integration Data</span></span>](get-last-integration-data.md) <br/> |<span data-ttu-id="b1697-127">Obtener los últimos datos de integración del cubo.</span><span class="sxs-lookup"><span data-stu-id="b1697-127">Get the last integration data from the cube.</span></span>  <br/> |
   
 <span data-ttu-id="b1697-128">**Recursos compartidos (CORS) admite API de datos de origen cruzado**</span><span class="sxs-lookup"><span data-stu-id="b1697-128">**Cross-Origin Resource Sharing (CORS) Support for Data API**</span></span>
  
<span data-ttu-id="b1697-129">API de datos admiten el uso compartido de recursos entre origen (CORS).</span><span class="sxs-lookup"><span data-stu-id="b1697-129">Data API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="b1697-130">CORS es una característica HTTP que permite a una aplicación web que ejecuta en un dominio tener acceso a recursos de otro dominio.</span><span class="sxs-lookup"><span data-stu-id="b1697-130">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="b1697-131">Los exploradores Web implementan una restricción de seguridad que se conoce como directiva de mismo origen [Política del mismo origen](https://www.w3.org/Security/wiki/Same_Origin_Policy) que impide que una página web de llamar a las API en un dominio diferente.</span><span class="sxs-lookup"><span data-stu-id="b1697-131">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="b1697-132">CORS proporciona una forma segura para permitir un dominio (el dominio de origen) llamar a las API de otro dominio.</span><span class="sxs-lookup"><span data-stu-id="b1697-132">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="b1697-133">Vea la [especificación de CORS](https://www.w3.org/TR/cors/) para obtener más información sobre CORS.</span><span class="sxs-lookup"><span data-stu-id="b1697-133">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="b1697-134">**Habilitación de CORS para datos de API**</span><span class="sxs-lookup"><span data-stu-id="b1697-134">**Enabling CORS for Data API**</span></span>
  
 <span data-ttu-id="b1697-135">El siguiente es un extracto del archivo web.config de datos API, que muestra dos dominios enumerados en la configuración de la aplicación corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="b1697-135">The following is an excerpt of Data API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="b1697-136">Todas las solicitudes realizadas por las secuencias de comandos cargados desde estos servidores son de confianza por la API de datos.</span><span class="sxs-lookup"><span data-stu-id="b1697-136">All requests made by the scripts loaded from these servers are trusted by Data API.</span></span>
  
<span data-ttu-id="b1697-137">Recuerde incluir el protocolo exacto, el nombre de host y el puerto (si existe).</span><span class="sxs-lookup"><span data-stu-id="b1697-137">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="b1697-138">No para poner cualquier diagonal carácter (/) al final.</span><span class="sxs-lookup"><span data-stu-id="b1697-138">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="b1697-139">Pueden especificarse varias entradas separando con comas.</span><span class="sxs-lookup"><span data-stu-id="b1697-139">Multiple entries can be specified by separating with commas.</span></span>
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>

```


