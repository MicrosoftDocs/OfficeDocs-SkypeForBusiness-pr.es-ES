---
title: API del depósito para el panel de calidad de la llamada (CQD) en Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 'Resumen: Aprender sobre la API del depósito para el panel de calidad de la llamada. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 0f84e3967bd4f78f8852dbcfed8ce5d59cbe4e8c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a><span data-ttu-id="1feca-104">API del depósito para el panel de calidad de la llamada (CQD) en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1feca-104">Repository API for Call Quality Dashboard (CQD) in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1feca-105">**Resumen:** Obtenga información acerca de la API del depósito para el panel de calidad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1feca-105">**Summary:** Learn about the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="1feca-106">Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1feca-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1feca-107">La API de repositorio proporciona acceso mediante programación para llamar al panel de calidad para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1feca-107">The Repository API provides programmatic access for Call Quality Dashboard for Skype for Business Server 2015.</span></span>
  
## <a name="repository-api-for-call-quality-dashboard"></a><span data-ttu-id="1feca-108">Panel de calidad de la llamada de API del depósito</span><span class="sxs-lookup"><span data-stu-id="1feca-108">Repository API for Call Quality Dashboard</span></span>

<span data-ttu-id="1feca-109">API del depósito ofrece una interfaz de acceso a datos a la base de datos de repositorio.</span><span class="sxs-lookup"><span data-stu-id="1feca-109">Repository API offers a data access interface to repository database.</span></span> <span data-ttu-id="1feca-110">El repositorio permite el contenido organizado en una estructura de árbol o gráfico tal que los usuarios pueden agrupar en las formas que tienen sentido para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1feca-110">The repository allows the contents to be organized in a tree or graph structure such that users can group them in the ways that make sense to the users.</span></span> <span data-ttu-id="1feca-111">El repositorio es compatible con dos tipos generales de usuarios: usuario del sistema, que es un usuario integradas que representa el repositorio y los usuarios normales que representan a los usuarios autorizados del repositorio.</span><span class="sxs-lookup"><span data-stu-id="1feca-111">The repository supports two general types of users: system user, which is a built-in user representing the repository, and regular users that represent the authorized users of the repository.</span></span>
  
<span data-ttu-id="1feca-112">API del depósito está formado por tres servicios generales:</span><span class="sxs-lookup"><span data-stu-id="1feca-112">Repository API consists of three general services:</span></span> 
  
- <span data-ttu-id="1feca-113">[Servicio de usuario para CQD](user-service.md) - para tener acceso a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1feca-113">[User Service for CQD](user-service.md) - for accessing Users.</span></span>
    
- <span data-ttu-id="1feca-114">[Servicio de elementos para el panel de calidad llamar (CQD)](item-service.md) : para obtener acceso a elementos y el contenido que se almacena en los elementos.</span><span class="sxs-lookup"><span data-stu-id="1feca-114">[Item Service for Call Quality Dashboard (CQD)](item-service.md) - for accessing Items and the contents stored in Items.</span></span>
    
- <span data-ttu-id="1feca-115">[Servicio de configuración de usuario para el panel de calidad llamar (CQD)](user-settings-service.md) - para el acceso a la configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="1feca-115">[User Settings Service for Call Quality Dashboard (CQD)](user-settings-service.md) - for accessing User Settings.</span></span>
    
<span data-ttu-id="1feca-116">Panel de calidad llamada utiliza API de repositorio para gestionar la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="1feca-116">Call Quality Dashboard uses Repository API to manage the following information:</span></span> 
  
- <span data-ttu-id="1feca-117">**Usuario** : representación de los usuarios que tienen acceso al repositorio.</span><span class="sxs-lookup"><span data-stu-id="1feca-117">**User** - representation of Users who have access to the repository.</span></span>
    
- <span data-ttu-id="1feca-118">**Informe** - contiene una lista de consultas, que se almacena como un contenido en elementos del repositorio.</span><span class="sxs-lookup"><span data-stu-id="1feca-118">**Report** - contains a list of Queries, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="1feca-119">**Consulta** - utilizado para recuperar datos de la API de datos, almacenados como un contenido en elementos del repositorio</span><span class="sxs-lookup"><span data-stu-id="1feca-119">**Query** - used to retrieve data from Data API, stored as a content in repository items.</span></span>
    
- <span data-ttu-id="1feca-120">**Configuración de usuario** - describe un comportamiento de aplicación opcional para el usuario.</span><span class="sxs-lookup"><span data-stu-id="1feca-120">**User Setting** - describes an optional application behavior for the user.</span></span>
    
 <span data-ttu-id="1feca-121">**Recursos compartidos (CORS) soporte para la API del depósito de origen cruzado**</span><span class="sxs-lookup"><span data-stu-id="1feca-121">**Cross-Origin Resource Sharing (CORS) Support for Repository API**</span></span>
  
<span data-ttu-id="1feca-122">API del depósito es compatible con el uso compartido de recursos entre origen (CORS).</span><span class="sxs-lookup"><span data-stu-id="1feca-122">Repository API supports Cross-Origin Resource Sharing (CORS).</span></span> <span data-ttu-id="1feca-123">CORS es una característica HTTP que permite a una aplicación web que ejecuta en un dominio tener acceso a recursos de otro dominio.</span><span class="sxs-lookup"><span data-stu-id="1feca-123">CORS is an HTTP feature that enables a web application running under one domain to access resources in another domain.</span></span> <span data-ttu-id="1feca-124">Los exploradores Web implementan una restricción de seguridad que se conoce como directiva de mismo origen [Política del mismo origen](https://www.w3.org/Security/wiki/Same_Origin_Policy) que impide que una página web de llamar a las API en un dominio diferente.</span><span class="sxs-lookup"><span data-stu-id="1feca-124">Web browsers implement a security restriction known as [Same-Origin Policy](https://www.w3.org/Security/wiki/Same_Origin_Policy) same-origin policy that prevents a web page from calling APIs in a different domain.</span></span> <span data-ttu-id="1feca-125">CORS proporciona una forma segura para permitir un dominio (el dominio de origen) llamar a las API de otro dominio.</span><span class="sxs-lookup"><span data-stu-id="1feca-125">CORS provides a secure way to allow one domain (the origin domain) to call APIs in another domain.</span></span> <span data-ttu-id="1feca-126">Vea la [especificación de CORS](https://www.w3.org/TR/cors/) para obtener más información sobre CORS.</span><span class="sxs-lookup"><span data-stu-id="1feca-126">See the [CORS specification](https://www.w3.org/TR/cors/) for details on CORS.</span></span>
  
 <span data-ttu-id="1feca-127">**Habilitación de CORS de la API del depósito**</span><span class="sxs-lookup"><span data-stu-id="1feca-127">**Enabling CORS for Repository API**</span></span>
  
 <span data-ttu-id="1feca-128">El siguiente es un extracto del archivo web.config de API de repositorio, que muestra dos dominios enumerados en la configuración de la aplicación corsTrustedOrigin.</span><span class="sxs-lookup"><span data-stu-id="1feca-128">The following is an excerpt of Repository API web.config, showing two domains listed in corsTrustedOrigin application settings.</span></span> <span data-ttu-id="1feca-129">Todas las solicitudes realizadas por las secuencias de comandos cargados desde estos servidores son de confianza por la API del depósito.</span><span class="sxs-lookup"><span data-stu-id="1feca-129">All requests made by the scripts loaded from these servers are trusted by Repository API.</span></span>
  
<span data-ttu-id="1feca-130">Recuerde incluir el protocolo exacto, el nombre de host y el puerto (si existe).</span><span class="sxs-lookup"><span data-stu-id="1feca-130">Remember to include the exact protocol, host name, and port (if any).</span></span> <span data-ttu-id="1feca-131">No para poner cualquier diagonal carácter (/) al final.</span><span class="sxs-lookup"><span data-stu-id="1feca-131">Do not to put any forward slash character (/) at the end.</span></span> <span data-ttu-id="1feca-132">Pueden especificarse varias entradas separando con comas.</span><span class="sxs-lookup"><span data-stu-id="1feca-132">Multiple entries can be specified by separating with commas.</span></span>
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>

```


