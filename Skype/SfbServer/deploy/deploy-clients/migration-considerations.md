---
title: Consideraciones acerca de la migración del Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Lea este tema para obtener información sobre cómo implementar el sistema de salas de Skype en un entorno con varias versiones de Skype empresarial Server y Lync Server.
ms.openlocfilehash: f5da7f92c7ab947d5e6d68c19823d227f8ae3ca3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234213"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="2a30f-103">Consideraciones acerca de la migración del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="2a30f-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="2a30f-104">Lea este tema para obtener información sobre cómo implementar el sistema de salas de Skype en un entorno con varias versiones de Skype empresarial Server y Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a30f-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="2a30f-105">Consideraciones acerca de la migración</span><span class="sxs-lookup"><span data-stu-id="2a30f-105">Migration considerations</span></span>

<span data-ttu-id="2a30f-106">Esta sección le proporciona instrucciones si va a implementar el sistema de salas de Skype en un entorno de varios grupos que incluye distintas versiones de Skype empresarial Server o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a30f-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="2a30f-107">El componente Replicador de usuario (UR) de Lync Server obtiene objetos de usuario de Active Directory y los coloca en la base de datos de SQL Server del back-end de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a30f-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="2a30f-108">Solo el UR de Lync Server 2013 tiene constancia de los objetos de sistema de la sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="2a30f-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="2a30f-109">En anteriores versiones de Lync Server y Office Communications, el replicador de usuario no detecta los atributos de Active Directory que designan los objetos LRS y, por consiguiente, no los reconoce.</span><span class="sxs-lookup"><span data-stu-id="2a30f-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="2a30f-110">Si una cuenta del sistema de Skype Room intenta iniciar sesión en Lync y realiza un descubrimiento automático basado en un registro SRV o DNS búsqueda de registros, y si esas cuentas apuntan a una versión anterior de Lync Server o de Office Communications Server, LRS recibirá una respuesta 404 no encontrada de  Grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="2a30f-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="2a30f-111">El grupo heredado no podrá redirigir el sistema de la sala de Skype a su grupo de inicio de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2a30f-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="2a30f-112">Puede abordar este problema con las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2a30f-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="2a30f-113">Señale el registro SRV de detección automática (_sipinternaltls._tcp.contoso.com) en el grupo de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2a30f-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="2a30f-114">Si la primera opción no es posible, debe configurar manualmente LRS y proporcionar la dirección de la agrupación de Lync Server 2013, configurándolo directamente en la aplicación de consola del sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="2a30f-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="2a30f-115">Si el sistema de salas de Skype se implementa fuera de la red corporativa y se ha implementado y configurado un servidor perimetral de Lync para apuntar a un grupo o director heredado, se necesita un sitio de servidor perimetral secundario, que apunta al grupo de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a30f-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="2a30f-116">Consulte la documentación de la implementación del servidor perimetral si desea obtener más información acerca de la implementación de un servidor perimetral secundario.</span><span class="sxs-lookup"><span data-stu-id="2a30f-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="2a30f-117">Interoperabilidad de sistemas de salas de Skype con un grupo de 2010 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="2a30f-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="2a30f-118">Durante la migración, si un usuario alojado en un grupo de servidores de Lync Server 2010 programa una reunión e invita a la cuenta del sistema de salas de Skype, el cliente del sistema de la sala de Skype dispondrá de una funcionalidad limitada mientras asiste a la reunión.</span><span class="sxs-lookup"><span data-stu-id="2a30f-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="2a30f-119">Cuando el cliente del sistema de salas de Skype se une a una llamada de conferencia programada que ha sido organizada por un usuario alojado en Lync Server 2010, el sistema de salas de Skype tiene las siguientes limitaciones de la reunión:</span><span class="sxs-lookup"><span data-stu-id="2a30f-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="2a30f-120">El sistema de salas de Skype no puede mostrar la galería de vídeos de varias vistas.</span><span class="sxs-lookup"><span data-stu-id="2a30f-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="2a30f-121">Si el cliente del sistema de Skype Room es el moderador, no puede aplicar el bloqueo de video a los participantes.</span><span class="sxs-lookup"><span data-stu-id="2a30f-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="2a30f-122">El sistema de salas de Skype no puede mostrar resolución de video 1080p (entrante o saliente), incluso si la Directiva de conferencia de Lync Server 2013 lo permite, debido a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2a30f-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="2a30f-123">Lync Server 2010 no admite la resolución de 1080p.</span><span class="sxs-lookup"><span data-stu-id="2a30f-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="2a30f-124">El sistema de salas de Skype siempre está limitado por la política de conferencia del organizador para la resolución de video.</span><span class="sxs-lookup"><span data-stu-id="2a30f-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="2a30f-125">Por lo tanto, incluso si el grupo de Lync 2010 admite la resolución 720p, el sistema de salas de Skype no podrá aprovechar la resolución de 720p mientras la Directiva del organizador no lo admita.</span><span class="sxs-lookup"><span data-stu-id="2a30f-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="2a30f-p105">Los clientes de Lync 2013 detectan la presencia de LRS en la sala de reunión y desactivan el audio automáticamente para evitar eco en la sala de reunión física. Esta característica no funciona en reuniones hospedadas en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a30f-p105">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room. This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="2a30f-128">Existen limitaciones en el rendimiento de escritorio compartido para reuniones hospedadas en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2a30f-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="2a30f-129">Los usuarios no podrán unirse a reuniones privadas (restringidas) hospedadas en Lync 2010 con el sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="2a30f-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

