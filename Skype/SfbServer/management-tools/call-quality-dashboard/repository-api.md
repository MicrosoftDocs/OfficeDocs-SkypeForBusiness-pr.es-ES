---
title: API de repositorio para panel de calidad de llamadas (CQD) en Skype Empresarial Server
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
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Resumen: obtenga información sobre la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 982ec0932f0a57958e1929a6ae2413ada0b5c9fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803130"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="b1893-104">API de repositorio para panel de calidad de llamadas (CQD) en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b1893-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="b1893-105">**Resumen:** Obtenga información sobre la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b1893-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="b1893-106">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b1893-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b1893-107">La API de repositorio proporciona acceso mediante programación para el Panel de calidad de llamadas para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b1893-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="b1893-108">API de repositorio para panel de calidad de llamadas</span><span class="sxs-lookup"><span data-stu-id="b1893-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="b1893-109">La API de repositorio ofrece una interfaz de acceso a datos a la base de datos del repositorio.</span><span class="sxs-lookup"><span data-stu-id="b1893-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="b1893-110">El repositorio permite que el contenido se organice en una estructura de gráfico o árbol, de modo que los usuarios puedan agruparlos de la manera que tienen sentido para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b1893-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="b1893-111">El repositorio admite dos tipos generales de usuarios: usuario del sistema, que es un usuario integrado que representa el repositorio, y usuarios normales que representan a los usuarios autorizados del repositorio.</span><span class="sxs-lookup"><span data-stu-id="b1893-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="b1893-112">La API de repositorio consta de tres servicios generales:</span><span class="sxs-lookup"><span data-stu-id="b1893-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="b1893-113">[Servicio de usuario para CQD:](user-service.md) para obtener acceso a usuarios.</span><span class="sxs-lookup"><span data-stu-id="b1893-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="b1893-114">Servicio de elementos para el Panel de calidad de [llamadas (CQD):](item-service.md) para obtener acceso a elementos y el contenido almacenado en elementos.</span><span class="sxs-lookup"><span data-stu-id="b1893-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="b1893-115">[Servicio de configuración de usuario para el Panel de calidad de llamadas (CQD):](user-settings-service.md) para obtener acceso a La configuración del usuario.</span><span class="sxs-lookup"><span data-stu-id="b1893-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="b1893-116">El Panel de calidad de llamadas usa la API de repositorio para administrar la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="b1893-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="b1893-117">**Usuario:** representación de los usuarios que tienen acceso al repositorio.</span><span class="sxs-lookup"><span data-stu-id="b1893-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="b1893-118">**Informe:** contiene una lista de consultas, almacenadas como contenido en elementos del repositorio.</span><span class="sxs-lookup"><span data-stu-id="b1893-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="b1893-119">**Consulta:** se usa para recuperar datos de la API de datos, almacenados como contenido en elementos del repositorio.</span><span class="sxs-lookup"><span data-stu-id="b1893-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="b1893-120">**Configuración de** usuario: describe un comportamiento opcional de la aplicación para el usuario.</span><span class="sxs-lookup"><span data-stu-id="b1893-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="b1893-121">**Compatibilidad con el uso compartido de recursos entre orígenes (CORS) para la API de repositorio**</span><span class="sxs-lookup"><span data-stu-id="b1893-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="b1893-122">La API de repositorio admite el uso compartido de recursos entre orígenes (CORS).</span><span class="sxs-lookup"><span data-stu-id="b1893-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="b1893-123">CORS es una característica HTTP que permite que una aplicación web que se ejecuta en un dominio obtenga acceso a los recursos de otro dominio.</span><span class="sxs-lookup"><span data-stu-id="b1893-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="b1893-124">Los exploradores web implementan [](https://www.w3.org/Security/wiki/Same_Origin_Policy) una restricción de seguridad conocida como directiva de mismo origen que impide que una página web llame a las API de un dominio diferente.</span><span class="sxs-lookup"><span data-stu-id="b1893-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="b1893-125">CORS proporciona una forma segura de permitir que un dominio (el dominio de origen) llame a las API de otro dominio.</span><span class="sxs-lookup"><span data-stu-id="b1893-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="b1893-126">Consulta la [especificación de CORS](https://www.w3.org/TR/cors/) para obtener más información sobre CORS.</span><span class="sxs-lookup"><span data-stu-id="b1893-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="b1893-127">**Habilitar CORS para la API de repositorio**</span><span class="sxs-lookup"><span data-stu-id="b1893-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="b1893-128">A continuación se muestra un extracto de la API de repositorio web.config que muestra dos dominios enumerados en la configuración de la aplicación corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="b1893-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="b1893-129">Todas las solicitudes realizadas por los scripts cargados desde estos servidores son de confianza para la API de repositorio.</span><span class="sxs-lookup"><span data-stu-id="b1893-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="b1893-130">Recuerde incluir el protocolo, el nombre de host y el puerto exactos (si los hay).</span><span class="sxs-lookup"><span data-stu-id="b1893-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="b1893-131">No coloque ningún carácter de barra diagonal (/) al final.</span><span class="sxs-lookup"><span data-stu-id="b1893-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="b1893-132">Se pueden especificar varias entradas separándose con comas.</span><span class="sxs-lookup"><span data-stu-id="b1893-132">Multiple entries can be specified by separating with commas.</span></span>
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


