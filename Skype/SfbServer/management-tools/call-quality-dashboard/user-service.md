---
title: Servicio de usuario para el CQD
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Resumen: Obtenga información sobre el servicio de usuario, que forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 439df99c1c9d66547e681fdea90b33c6295344db
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816659"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="e1d2c-104">Servicio de usuario para el CQD</span><span class="sxs-lookup"><span data-stu-id="e1d2c-104">User Service for CQD</span></span>
 
<span data-ttu-id="e1d2c-105">**Resumen:** Obtenga más información sobre el servicio de usuario, que es parte de la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="e1d2c-106">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="e1d2c-107">El servicio de usuario es parte de la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="e1d2c-108">Servicio de usuario</span><span class="sxs-lookup"><span data-stu-id="e1d2c-108">User Service</span></span>

<span data-ttu-id="e1d2c-109">La API de repositorio ofrece un modelo de administración de usuarios simplificado donde el aprovisionamiento de usuarios (la creación de nuevas cuentas de usuario) es automático e implícito.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="e1d2c-110">Cuando un usuario hace una solicitud para la API de Repository por primera vez, el repositorio crea un nuevo registro de usuario.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="e1d2c-111">El panel de calidad de llamadas también crea automáticamente un usuario específico para el nuevo usuario.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="e1d2c-112">Los nuevos elementos dedicados al usuario son clones completos de los elementos del usuario del sistema.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="e1d2c-113">De esta manera, los usuarios comienzan con sus propias copias de informes y consultas que pueden empezar a personalizar de inmediato.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e1d2c-114">Con el panel de calidad de llamadas, los usuarios pueden restablecer sus artículos dedicados en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="e1d2c-115">**Identificadores de usuario especiales**</span><span class="sxs-lookup"><span data-stu-id="e1d2c-115">**Special User IDs**</span></span>
  
<span data-ttu-id="e1d2c-116">La API de repositorio incluye URI de API de REST que espera un valor entero para especificar un usuario en particular.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="e1d2c-117">Ejemplo: `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="e1d2c-118">Aquí, {userId} debe sustituirse por un valor entero, como 0, 1, etc.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="e1d2c-119">Además, la API de repositorio aceptará dos identificadores de usuario especiales en {userId} en los URI.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="e1d2c-120">*default* : representa el usuario que está interactuando actualmente con la API.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="e1d2c-121">Esto permite que las aplicaciones tengan acceso al contenido del usuario actual sin mantener el seguimiento del valor real del identificador de usuario.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="e1d2c-122">Ejemplo: `https://<portal>/QoERepositoryService/repository/user/default`.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-122">Example: `https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="e1d2c-123">*sistema* : representa al usuario del sistema.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-123">*system*  - represents the system user.</span></span> <span data-ttu-id="e1d2c-124">Esto permite que las aplicaciones tengan acceso al contenido del usuario del sistema sin conocer el valor real del identificador de usuario.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="e1d2c-125">Ejemplo: `https://<portal>/QoERepositoryService/repository/user/system`.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="e1d2c-126">A menos que se indique lo contrario, los identificadores de usuario especiales se pueden usar en {userId} en URI.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="e1d2c-127">Las operaciones de REST se incluyen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="e1d2c-128">**Operación**</span><span class="sxs-lookup"><span data-stu-id="e1d2c-128">**Operation**</span></span>|<span data-ttu-id="e1d2c-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e1d2c-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="e1d2c-130">Obtener usuarios</span><span class="sxs-lookup"><span data-stu-id="e1d2c-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="e1d2c-131">Devuelve una lista de los usuarios del repositorio.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="e1d2c-132">Obtener usuario</span><span class="sxs-lookup"><span data-stu-id="e1d2c-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="e1d2c-133">Devuelve un registro de usuario.</span><span class="sxs-lookup"><span data-stu-id="e1d2c-133">Returns a user record.</span></span>  <br/> |
   

