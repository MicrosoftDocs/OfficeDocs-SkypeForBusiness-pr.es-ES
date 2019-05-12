---
title: Servicio de usuario para CQD
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Resumen: Información sobre el servicio de usuario, que forma parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 631ccfefe7a4503f325c288ef1bf27d4366869e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915083"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="d0ecc-104">Servicio de usuario para CQD</span><span class="sxs-lookup"><span data-stu-id="d0ecc-104">User Service for CQD</span></span>
 
<span data-ttu-id="d0ecc-105">**Resumen:** Obtenga información sobre el servicio de usuario, que forma parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="d0ecc-106">Panel de calidad de llamada es una herramienta de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="d0ecc-107">El servicio de usuario es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="d0ecc-108">Servicio de usuario</span><span class="sxs-lookup"><span data-stu-id="d0ecc-108">User Service</span></span>

<span data-ttu-id="d0ecc-109">Repositorio de API proporciona un modelo de administración de usuario simplificada donde aprovisionamiento (creación de nuevas cuentas de usuario) del usuario es automática e implícita.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="d0ecc-110">Cuando un usuario realiza una solicitud de la API de repositorio por primera vez, el repositorio crea un nuevo registro de usuario.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="d0ecc-111">Panel de calidad también crea automáticamente un usuario de llamada dedicado elementos para el nuevo usuario.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="d0ecc-112">Los nuevos elementos de usuario dedicada sean copias completados de los elementos del usuario del sistema.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="d0ecc-113">De este modo, los usuarios comienzan con sus propias copias de los informes y las consultas que puede iniciar inmediatamente personalización.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d0ecc-114">Con el panel de calidad de llamadas, los usuarios pueden restablecer sus elementos dedicados en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="d0ecc-115">**Identificadores de usuario especiales**</span><span class="sxs-lookup"><span data-stu-id="d0ecc-115">**Special User IDs**</span></span>
  
<span data-ttu-id="d0ecc-116">API del depósito incluye a REST API URIs que espera un valor entero para especificar un usuario en particular.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="d0ecc-117">Ejemplo: `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="d0ecc-118">En este caso, {userId} debe reemplazarse por un valor entero como 0, 1, etcetera.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="d0ecc-119">Además, API de repositorio aceptará dos identificadores de usuario especial en {userId} en los URI.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="d0ecc-120">*predeterminado* - representa el usuario que actualmente está interactuando con la API.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="d0ecc-121">Esto permite a las aplicaciones tener acceso a contenido del usuario actual sin seguimiento del valor de identificador de usuario real.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="d0ecc-122">Ejemplo: ` https://<portal>/QoERepositoryService/repository/user/default`.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-122">Example: ` https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="d0ecc-123">*sistema* - representa el usuario del sistema.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-123">*system*  - represents the system user.</span></span> <span data-ttu-id="d0ecc-124">Esto permite a las aplicaciones tener acceso a contenido del usuario del sistema sin necesidad de conocer el valor de identificador de usuario real.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="d0ecc-125">Ejemplo: `https://<portal>/QoERepositoryService/repository/user/system`.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="d0ecc-126">A menos que se indique lo contrario, se pueden usar los identificadores de usuario especial en {userId} en los URI.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="d0ecc-127">Las operaciones de REST se incluyen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="d0ecc-128">**Operación**</span><span class="sxs-lookup"><span data-stu-id="d0ecc-128">**Operation**</span></span>|<span data-ttu-id="d0ecc-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d0ecc-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="d0ecc-130">Obtener usuarios</span><span class="sxs-lookup"><span data-stu-id="d0ecc-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="d0ecc-131">Devuelve una lista de los usuarios en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="d0ecc-132">Obtener usuario</span><span class="sxs-lookup"><span data-stu-id="d0ecc-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="d0ecc-133">Devuelve un registro de usuario.</span><span class="sxs-lookup"><span data-stu-id="d0ecc-133">Returns a user record.</span></span>  <br/> |
   

