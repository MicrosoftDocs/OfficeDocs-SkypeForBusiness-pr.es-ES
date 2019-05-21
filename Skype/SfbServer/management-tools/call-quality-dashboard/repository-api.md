---
title: API de repositorio para el panel de calidad de llamadas (CQD) en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Resumen: Obtenga información sobre la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 723b7a9340737e3f1cec47112b33ff1175597cd0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274579"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="7e2cb-104">API de repositorio para el panel de calidad de llamadas (CQD) en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="7e2cb-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="7e2cb-105">**Resumen:** Obtenga más información sobre la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="7e2cb-106">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="7e2cb-107">La API de Repository proporciona acceso mediante programación para el panel de calidad de llamadas de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="7e2cb-108">API de repositorio para panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="7e2cb-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="7e2cb-109">La API de repositorio ofrece una interfaz de acceso a datos para la base de datos del repositorio.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="7e2cb-110">El repositorio permite que el contenido se organice en una estructura de árbol o gráfico, de modo que los usuarios puedan agruparlos de la manera que tengan sentido para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="7e2cb-111">El repositorio admite dos tipos de usuarios generales: usuario del sistema, que es un usuario integrado que representa el repositorio y usuarios habituales que representan a los usuarios autorizados del repositorio.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="7e2cb-112">La API del repositorio consta de tres servicios generales:</span><span class="sxs-lookup"><span data-stu-id="7e2cb-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="7e2cb-113">[Servicio de usuario de CQD](user-service.md) : para acceder a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="7e2cb-114">[Servicio de artículos para el panel de calidad de llamadas (CQD)](item-service.md) : para obtener acceso a los elementos y el contenido almacenado en los elementos.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="7e2cb-115">[Servicio de configuración de usuario del panel de calidad de llamadas (CQD)](user-settings-service.md) : para acceder a la configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="7e2cb-116">El panel de calidad de llamadas usa la API de repositorio para administrar la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="7e2cb-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="7e2cb-117">Representación del **usuario** de los usuarios que tienen acceso al repositorio.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="7e2cb-118">**Informe** : contiene una lista de consultas, almacenadas como contenido en elementos del repositorio.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="7e2cb-119">**Consulta** : se usa para recuperar datos de la API de datos, almacenados como contenido en elementos del repositorio.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="7e2cb-120">**Configuración de usuario** : describe un comportamiento de la aplicación opcional para el usuario.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="7e2cb-121">**Compatibilidad con el uso compartido de recursos entre orígenes (CORS) para la API del repositorio**</span><span class="sxs-lookup"><span data-stu-id="7e2cb-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="7e2cb-122">La API de repositorio es compatible con el uso compartido de recursos cruzados (CORS).</span><span class="sxs-lookup"><span data-stu-id="7e2cb-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="7e2cb-123">CORS es una característica HTTP que permite que una aplicación web que se ejecuta en un dominio tenga acceso a los recursos de otro dominio.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="7e2cb-124">Los exploradores Web implementan una restricción de seguridad conocida como una directiva de mismo origen de la [Directiva](https://www.w3.org/Security/wiki/Same_Origin_Policy) de mismo origen que impide que una página web llame a las API de otro dominio.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="7e2cb-125">CORS ofrece una manera segura de permitir que un dominio (el dominio de origen) llame a las API de otro dominio.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="7e2cb-126">Consulta la [especificación de CORS](https://www.w3.org/TR/cors/) para obtener más información sobre CORS.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="7e2cb-127">**Habilitar CORS para la API del repositorio**</span><span class="sxs-lookup"><span data-stu-id="7e2cb-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="7e2cb-128">A continuación se muestra un extracto de la API del depósito Web. config, que muestra dos dominios que aparecen en la configuración de la aplicación corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="7e2cb-129">Todas las solicitudes realizadas por los scripts cargados desde estos servidores son de confianza para la API del repositorio.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="7e2cb-130">Recuerde incluir el protocolo, el nombre de host y el puerto exactos (si corresponde).</span><span class="sxs-lookup"><span data-stu-id="7e2cb-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="7e2cb-131">No coloque ningún carácter de barra diagonal (/) al final.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="7e2cb-132">Se pueden especificar varias entradas separándolas con comas.</span><span class="sxs-lookup"><span data-stu-id="7e2cb-132">Multiple entries can be specified by separating with commas.</span></span>
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


