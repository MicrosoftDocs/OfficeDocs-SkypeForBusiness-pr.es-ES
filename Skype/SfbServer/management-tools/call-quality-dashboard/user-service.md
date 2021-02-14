---
title: Servicio de usuario para CQD
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
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Resumen: obtenga información sobre el servicio de usuario, que forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: d9f4b771a1bf5efeece4f8fb87195d8567f0426e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803080"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="606cd-104">Servicio de usuario para CQD</span><span class="sxs-lookup"><span data-stu-id="606cd-104">User Service for CQD</span></span>
 
<span data-ttu-id="606cd-105">**Resumen:** Obtenga información sobre el servicio de usuario, que forma parte de la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="606cd-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="606cd-106">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="606cd-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="606cd-107">El servicio de usuario forma parte de la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="606cd-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="606cd-108">Servicio de usuario</span><span class="sxs-lookup"><span data-stu-id="606cd-108">User Service</span></span>

<span data-ttu-id="606cd-109">La API de repositorio proporciona un modelo de administración de usuarios simplificado en el que el aprovisionamiento de usuarios (creación de nuevas cuentas de usuario) es automático e implícito.</span><span class="sxs-lookup"><span data-stu-id="606cd-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="606cd-110">Cuando un usuario realiza una solicitud a la API de repositorio por primera vez, el repositorio crea un nuevo registro de usuario.</span><span class="sxs-lookup"><span data-stu-id="606cd-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="606cd-111">El Panel de calidad de llamadas también crea automáticamente elementos dedicados para el nuevo usuario.</span><span class="sxs-lookup"><span data-stu-id="606cd-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="606cd-112">Los nuevos elementos dedicados del usuario son clones completos de los elementos del usuario del sistema.</span><span class="sxs-lookup"><span data-stu-id="606cd-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="606cd-113">De esta forma, los usuarios empiezan con sus propias copias de informes y consultas que pueden empezar a personalizar inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="606cd-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="606cd-114">Con el Panel de calidad de llamadas, los usuarios pueden restablecer sus elementos dedicados en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="606cd-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="606cd-115">**Id. de usuario especiales**</span><span class="sxs-lookup"><span data-stu-id="606cd-115">**Special User IDs**</span></span>
  
<span data-ttu-id="606cd-116">La API de repositorio incluye URI de API de REST que espera que un valor entero especifique un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="606cd-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="606cd-117">Ejemplo:  `https://<portal>/QoERepositoryService/repository/user/{userId}` .</span><span class="sxs-lookup"><span data-stu-id="606cd-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="606cd-118">Aquí, {userId} debe reemplazarse por un valor entero como 0, 1, etc.</span><span class="sxs-lookup"><span data-stu-id="606cd-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="606cd-119">Además, la API de repositorio aceptará dos id. de usuario especiales en {userId} en URI.</span><span class="sxs-lookup"><span data-stu-id="606cd-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="606cd-120">*predeterminado:*  representa el usuario que está interactuando actualmente con la API.</span><span class="sxs-lookup"><span data-stu-id="606cd-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="606cd-121">Esto permite que las aplicaciones accedan al contenido del usuario actual sin realizar un seguimiento del valor real del identificador de usuario.</span><span class="sxs-lookup"><span data-stu-id="606cd-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="606cd-122">Ejemplo: `https://<portal>/QoERepositoryService/repository/user/default`.</span><span class="sxs-lookup"><span data-stu-id="606cd-122">Example: `https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="606cd-123">*system:*  representa al usuario del sistema.</span><span class="sxs-lookup"><span data-stu-id="606cd-123">*system*  - represents the system user.</span></span> <span data-ttu-id="606cd-124">Esto permite que las aplicaciones obtengan acceso al contenido del usuario del sistema sin conocer el valor real del identificador de usuario.</span><span class="sxs-lookup"><span data-stu-id="606cd-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="606cd-125">Ejemplo: `https://<portal>/QoERepositoryService/repository/user/system`.</span><span class="sxs-lookup"><span data-stu-id="606cd-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="606cd-126">A menos que se indique lo contrario, los id. de usuario especiales se pueden usar en {userId} en URI.</span><span class="sxs-lookup"><span data-stu-id="606cd-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="606cd-127">Las operaciones rest se incluyen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="606cd-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="606cd-128">**Operación**</span><span class="sxs-lookup"><span data-stu-id="606cd-128">**Operation**</span></span>|<span data-ttu-id="606cd-129">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="606cd-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="606cd-130">Obtener usuarios</span><span class="sxs-lookup"><span data-stu-id="606cd-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="606cd-131">Devuelve una lista de usuarios en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="606cd-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="606cd-132">Obtener usuario</span><span class="sxs-lookup"><span data-stu-id="606cd-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="606cd-133">Devuelve un registro de usuario.</span><span class="sxs-lookup"><span data-stu-id="606cd-133">Returns a user record.</span></span>  <br/> |
   

