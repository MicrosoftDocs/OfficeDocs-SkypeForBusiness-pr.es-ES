---
title: Servicio de usuario para CQD
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Resumen: Conozca el servicio de usuario, que forma parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: c4bb2395ea3fa4541140a7966bbfb554ef53c168
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="ff9da-104">Servicio de usuario para CQD</span><span class="sxs-lookup"><span data-stu-id="ff9da-104">User Service for CQD</span></span>
 
<span data-ttu-id="ff9da-105">**Resumen:** Obtenga información acerca del servicio de usuario, que forma parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="ff9da-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="ff9da-106">Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ff9da-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ff9da-107">El servicio de usuario forma parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="ff9da-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="ff9da-108">Servicio de usuario</span><span class="sxs-lookup"><span data-stu-id="ff9da-108">User Service</span></span>

<span data-ttu-id="ff9da-109">API del depósito proporciona un modelo de administración de usuario simplificado donde usuario provisioning (creación de nuevas cuentas de usuario) es implícita y automática.</span><span class="sxs-lookup"><span data-stu-id="ff9da-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="ff9da-110">Cuando un usuario realiza una solicitud de la API del depósito por primera vez, el repositorio crea un nuevo registro de usuario.</span><span class="sxs-lookup"><span data-stu-id="ff9da-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="ff9da-111">Panel de calidad también crea automáticamente un usuario de llamada dedicado elementos para el nuevo usuario.</span><span class="sxs-lookup"><span data-stu-id="ff9da-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="ff9da-112">Los nuevos elementos de usuario dedicado son clones completos de los elementos del usuario del sistema.</span><span class="sxs-lookup"><span data-stu-id="ff9da-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="ff9da-113">De este modo, los usuarios comienzan con sus propias copias de informes y consultas que pueden iniciar inmediatamente personalizar.</span><span class="sxs-lookup"><span data-stu-id="ff9da-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ff9da-114">Con llamar al panel de calidad, los usuarios pueden restablecer sus elementos dedicados en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="ff9da-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="ff9da-115">**Identificadores de usuario especial**</span><span class="sxs-lookup"><span data-stu-id="ff9da-115">**Special User IDs**</span></span>
  
<span data-ttu-id="ff9da-116">API del depósito incluye a resto API URIs que espera un valor entero para especificar un usuario en particular.</span><span class="sxs-lookup"><span data-stu-id="ff9da-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="ff9da-117">Ejemplo: `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span><span class="sxs-lookup"><span data-stu-id="ff9da-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="ff9da-118">En este caso, {ID} debe reemplazarse por un valor entero como 0, 1, etcetera.</span><span class="sxs-lookup"><span data-stu-id="ff9da-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="ff9da-119">Por otra parte, API de repositorio aceptará dos identificadores de usuario especial en {ID} de URI.</span><span class="sxs-lookup"><span data-stu-id="ff9da-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="ff9da-120">*predeterminado* - representa el usuario que actualmente está interactuando con la API.</span><span class="sxs-lookup"><span data-stu-id="ff9da-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="ff9da-121">Esto permite que las aplicaciones tengan acceso a contenido del usuario actual sin seguimiento del valor de ID de usuario real.</span><span class="sxs-lookup"><span data-stu-id="ff9da-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="ff9da-122">Ejemplo: ` https://<portal>/QoERepositoryService/repository/user/default`.</span><span class="sxs-lookup"><span data-stu-id="ff9da-122">Example: ` https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="ff9da-123">*sistema* - representa el usuario del sistema.</span><span class="sxs-lookup"><span data-stu-id="ff9da-123">*system*  - represents the system user.</span></span> <span data-ttu-id="ff9da-124">Esto permite que las aplicaciones tengan acceso a contenido del usuario del sistema sin conocer el valor de ID de usuario real.</span><span class="sxs-lookup"><span data-stu-id="ff9da-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="ff9da-125">Ejemplo: `https://<portal>/QoERepositoryService/repository/user/system`.</span><span class="sxs-lookup"><span data-stu-id="ff9da-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="ff9da-126">A menos que se indique lo contrario, se pueden utilizar los identificadores de usuario especial en {ID} en identificadores URI.</span><span class="sxs-lookup"><span data-stu-id="ff9da-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="ff9da-127">Las operaciones de resto se incluyen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ff9da-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="ff9da-128">**Operación**</span><span class="sxs-lookup"><span data-stu-id="ff9da-128">**Operation**</span></span>|<span data-ttu-id="ff9da-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ff9da-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ff9da-130">Conseguir que los usuarios</span><span class="sxs-lookup"><span data-stu-id="ff9da-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="ff9da-131">Devuelve una lista de usuarios del repositorio.</span><span class="sxs-lookup"><span data-stu-id="ff9da-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="ff9da-132">Obtener usuario</span><span class="sxs-lookup"><span data-stu-id="ff9da-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="ff9da-133">Devuelve un registro de usuario.</span><span class="sxs-lookup"><span data-stu-id="ff9da-133">Returns a user record.</span></span>  <br/> |
   

