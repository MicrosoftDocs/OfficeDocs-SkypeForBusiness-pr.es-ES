---
title: Consideraciones sobre la migración del Sistema de sala de Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Lea este tema para obtener información sobre cómo implementar el Sistema de sala de Skype en un entorno que tiene varias versiones de Skype Empresarial Server y Lync Server.
ms.openlocfilehash: 30b2a4733ea2e2e42b8a879914a2e0e3c4903c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805790"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="7ff97-103">Consideraciones sobre la migración del Sistema de sala de Skype</span><span class="sxs-lookup"><span data-stu-id="7ff97-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="7ff97-104">Lea este tema para obtener información sobre cómo implementar el Sistema de sala de Skype en un entorno que tiene varias versiones de Skype Empresarial Server y Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7ff97-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="7ff97-105">Consideraciones de migración</span><span class="sxs-lookup"><span data-stu-id="7ff97-105">Migration considerations</span></span>

<span data-ttu-id="7ff97-106">En esta sección se proporcionan instrucciones para implementar el Sistema de sala de Skype en un entorno de varios grupos de servidores que incluya diferentes versiones de Skype Empresarial Server o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7ff97-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="7ff97-107">El componente replicador de usuarios (UR) de Lync Server obtiene objetos de usuario de Active Directory y los coloca en la base de datos back-end SQL Server lync Server.</span><span class="sxs-lookup"><span data-stu-id="7ff97-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="7ff97-108">Solo la UR de Lync Server 2013 es consciente de los objetos del Sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="7ff97-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="7ff97-109">El UR de versiones anteriores de Lync Server y Office Communications Server no detecta los atributos de Active Directory que designan objetos LRS y, por lo tanto, no los conocía.</span><span class="sxs-lookup"><span data-stu-id="7ff97-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="7ff97-110">Si una cuenta del Sistema de sala de Skype intenta iniciar sesión en Lync y realiza la detección automática en función del registro SRV o del registro A de DNS, y si esas cuentas apuntan a una versión anterior de Lync Server u Office Communications Server, LRS recibirá una respuesta 404 No encontrado del grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="7ff97-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="7ff97-111">El grupo heredado no podrá redirigir el Sistema de sala de Skype a su grupo principal de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ff97-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="7ff97-112">Puede solucionar este problema con las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="7ff97-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="7ff97-113">Apunte el registro SRV de detección automática (_sipinternaltls._tcp.contoso.com) al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ff97-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="7ff97-114">Si la primera opción no es posible, debe configurar manualmente LRS y proporcionar la dirección del grupo de lync Server 2013 configurándose directamente en la aplicación de consola del Sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="7ff97-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="7ff97-115">Si el Sistema de sala de Skype se implementa fuera de la red corporativa y se ha implementado y configurado un servidor perimetral de Lync para que apunte a un grupo o director heredado, se requiere un sitio secundario del servidor perimetral, que apunta al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ff97-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="7ff97-116">Consulte la documentación de implementación del servidor perimetral para obtener más información acerca de la implementación de un servidor perimetral secundario.</span><span class="sxs-lookup"><span data-stu-id="7ff97-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="7ff97-117">Interoperabilidad del sistema de sala de Skype con un grupo de servidores de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7ff97-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="7ff97-118">Durante la migración, si un usuario que se encuentra en un grupo de Lync Server 2010 programa una reunión e invita a la cuenta del Sistema de salas de Skype, el cliente del Sistema de salas de Skype tendrá una funcionalidad limitada mientras asiste a la reunión.</span><span class="sxs-lookup"><span data-stu-id="7ff97-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="7ff97-119">Cuando el cliente del Sistema de salas de Skype se une a una llamada de conferencia programada organizada por un usuario que se encuentra en Lync Server 2010, el Sistema de salas de Skype tiene las siguientes limitaciones en la reunión:</span><span class="sxs-lookup"><span data-stu-id="7ff97-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="7ff97-120">El Sistema de sala de Skype no puede mostrar la galería de vídeos de varias vistas.</span><span class="sxs-lookup"><span data-stu-id="7ff97-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="7ff97-121">Si el cliente del Sistema de sala de Skype es el moderador, no puede aplicar bloqueo de vídeo a los participantes.</span><span class="sxs-lookup"><span data-stu-id="7ff97-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="7ff97-122">El Sistema de sala de Skype no puede mostrar una resolución de vídeo de 1080p (entrante o saliente), incluso si la directiva de conferencia de Lync Server 2013 lo permite, debido a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ff97-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="7ff97-123">Lync Server 2010 no admite la resolución de 1080p.</span><span class="sxs-lookup"><span data-stu-id="7ff97-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="7ff97-124">El Sistema de sala de Skype siempre está limitado por la directiva de conferencias del organizador para la resolución de vídeo.</span><span class="sxs-lookup"><span data-stu-id="7ff97-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="7ff97-125">Por lo tanto, incluso si el grupo de Lync 2010 admite una resolución de 720p, el Sistema de sala de Skype no podrá aprovechar la resolución de 720p siempre que la directiva del organizador no la admita.</span><span class="sxs-lookup"><span data-stu-id="7ff97-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="7ff97-126">Los clientes de Lync 2013 detectan la presencia de LRS en la sala de reuniones y se silencian automáticamente para evitar eco en la sala de reuniones física.</span><span class="sxs-lookup"><span data-stu-id="7ff97-126">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room.</span></span> <span data-ttu-id="7ff97-127">Esta característica no funciona en reuniones hospedadas en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7ff97-127">This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="7ff97-128">Existen limitaciones en el rendimiento del uso compartido de escritorio para las reuniones hospedadas en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7ff97-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="7ff97-129">Los usuarios no podrán unirse a reuniones privadas (restringidas) hospedadas en Lync 2010 con el Sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="7ff97-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

