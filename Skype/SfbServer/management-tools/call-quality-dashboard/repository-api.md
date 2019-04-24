---
title: API del depósito para el panel de calidad de llamada (CQD) en Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Resumen: Obtenga información sobre la API del depósito para el panel de calidad de llamada. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 9181cd1454311bb5446bb18f51af56914387e7c3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217659"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a><span data-ttu-id="373e8-104">API del depósito para el panel de calidad de llamada (CQD) en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="373e8-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server</span></span>
 
<span data-ttu-id="373e8-105">**Resumen:** Obtenga información acerca de la API del depósito para el panel de calidad de llamada.</span><span class="sxs-lookup"><span data-stu-id="373e8-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="373e8-106">Panel de calidad de llamada es una herramienta de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="373e8-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="373e8-107">La API de repositorio proporciona acceso mediante programación para llamar al panel de calidad de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="373e8-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="373e8-108">API del depósito para el panel de calidad de llamada</span><span class="sxs-lookup"><span data-stu-id="373e8-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="373e8-109">API del depósito ofrece una interfaz de acceso a datos a la base de datos de repositorio.</span><span class="sxs-lookup"><span data-stu-id="373e8-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="373e8-110">El repositorio permite que el contenido a organizarse en una estructura de árbol o gráfico de manera que los usuarios pueden agrupar en las formas que tienen sentido para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="373e8-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="373e8-111">El repositorio es compatible con dos tipos generales de los usuarios: el usuario del sistema, que es un usuario integrada que representa el repositorio y los usuarios habituales que representan a los usuarios autorizados del repositorio de.</span><span class="sxs-lookup"><span data-stu-id="373e8-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="373e8-112">API del depósito consta de tres servicios generales:</span><span class="sxs-lookup"><span data-stu-id="373e8-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="373e8-113">[Servicio de usuario para CQD](user-service.md) - para obtener acceso a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="373e8-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="373e8-114">[Elemento de servicio para el panel de calidad de llamadas (CQD)](item-service.md) : para obtener acceso a los elementos y el contenido almacenado en los elementos.</span><span class="sxs-lookup"><span data-stu-id="373e8-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="373e8-115">[Servicio de configuración de usuario para el panel de calidad de llamadas (CQD)](user-settings-service.md) : para obtener acceso a la configuración del usuario.</span><span class="sxs-lookup"><span data-stu-id="373e8-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="373e8-116">Panel de calidad de llamada usa la API de repositorio para administrar la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="373e8-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="373e8-117">**Usuario** : representación de los usuarios que tienen acceso al repositorio.</span><span class="sxs-lookup"><span data-stu-id="373e8-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="373e8-118">**Informe** - contiene una lista de consultas, que se almacenan como un contenido en elementos del repositorio.</span><span class="sxs-lookup"><span data-stu-id="373e8-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="373e8-119">**Consulta** - utilizada para recuperar datos de la API de datos, almacenados como un contenido en elementos del repositorio</span><span class="sxs-lookup"><span data-stu-id="373e8-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="373e8-120">**Configuración de usuario** - describe un comportamiento de aplicación opcional para el usuario.</span><span class="sxs-lookup"><span data-stu-id="373e8-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
  <span data-ttu-id="373e8-121">**Recursos de origen cruzado (CORS) soporte para la API del depósito de uso compartido**</span><span class="sxs-lookup"><span data-stu-id="373e8-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="373e8-122">API del depósito es compatible con el uso compartido de recursos de origen cruzado (CORS).</span><span class="sxs-lookup"><span data-stu-id="373e8-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="373e8-123">CORS es una característica HTTP que permite a una aplicación web que se ejecuta en un dominio tener acceso a recursos en otro dominio.</span><span class="sxs-lookup"><span data-stu-id="373e8-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="373e8-124">Los exploradores Web implementan una restricción de seguridad que se conoce como directiva del mismo origen de [Directiva del mismo origen](https://www.w3.org/Security/wiki/Same_Origin_Policy) que impide que una página web de llamar a las API en un dominio diferente.</span><span class="sxs-lookup"><span data-stu-id="373e8-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="373e8-125">CORS proporciona una forma segura para permitir que un dominio (el dominio de origen) para llamar a las API en otro dominio.</span><span class="sxs-lookup"><span data-stu-id="373e8-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="373e8-126">Vea la [especificación de CORS](https://www.w3.org/TR/cors/) para obtener información detallada en CORS.</span><span class="sxs-lookup"><span data-stu-id="373e8-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="373e8-127">**Habilitar CORS para la API de repositorio**</span><span class="sxs-lookup"><span data-stu-id="373e8-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="373e8-128">El siguiente es un fragmento del archivo web.config de API de repositorio, que muestra dos dominios incluidos en la configuración de la aplicación corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="373e8-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="373e8-129">Todas las solicitudes realizadas por los scripts que se cargan desde estos servidores son de confianza mediante la API de repositorio.</span><span class="sxs-lookup"><span data-stu-id="373e8-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="373e8-130">No olvide incluir el protocolo exacta, el nombre de host y el puerto (si hay alguno).</span><span class="sxs-lookup"><span data-stu-id="373e8-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="373e8-131">No para colocar cualquiera diagonal carácter (/) al final.</span><span class="sxs-lookup"><span data-stu-id="373e8-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="373e8-132">Pueden especificarse varias entradas, separe con comas.</span><span class="sxs-lookup"><span data-stu-id="373e8-132">Multiple entries can be specified by separating with commas.</span></span>
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


