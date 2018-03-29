---
title: Consideraciones acerca de la migración del Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Lea este tema para obtener información acerca de cómo implementar el sistema de sala de Skype en un entorno que tiene varias versiones de Skype para Business Server y Lync Server.
ms.openlocfilehash: f71c6557a8b9a98f712541c4424ba57a49536164
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="6a842-103">Consideraciones acerca de la migración del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="6a842-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="6a842-104">Lea este tema para obtener información acerca de cómo implementar el sistema de sala de Skype en un entorno que tiene varias versiones de Skype para Business Server y Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6a842-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="6a842-105">Consideraciones acerca de la migración</span><span class="sxs-lookup"><span data-stu-id="6a842-105">Migration considerations</span></span>

<span data-ttu-id="6a842-106">Esta sección proporciona instrucciones si va a implementar el sistema del sitio de Skype en un entorno de grupo de múltiples que incluye diferentes versiones de Skype para Business Server, Lync Server o Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="6a842-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, Lync Server, or Office Communications Server 2007 R2.</span></span> 
  
<span data-ttu-id="6a842-107">El componente Replicador de usuario (UR) de Lync Server obtiene objetos de usuario de Active Directory y los coloca en la base de datos de SQL Server del back-end de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6a842-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="6a842-108">Sólo la Ronda de URUGUAY en Lync Server 2013 es consciente de los objetos de sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="6a842-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="6a842-109">En anteriores versiones de Lync Server y Office Communications, el replicador de usuario no detecta los atributos de Active Directory que designan los objetos LRS y, por consiguiente, no los reconoce.</span><span class="sxs-lookup"><span data-stu-id="6a842-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="6a842-110">Si una cuenta de Skype sala sistema intenta iniciar sesión en Lync y realiza descubrimiento automático basado en el registro SRV o DNS A registro de búsqueda y seleccione las cuentas a una versión anterior de Lync Server u Office Communications Server, LRS recibirá una respuesta 404 no se encuentra en  el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="6a842-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="6a842-111">El grupo heredado no podrá redirigir el sistema del sitio de Skype a su grupo doméstico Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6a842-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="6a842-112">Puede abordar este problema con las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="6a842-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="6a842-113">Señale el registro SRV de detección automática (_sipinternaltls._tcp.contoso.com) en el grupo de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6a842-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="6a842-114">Si la primera opción no es posible, debe configurar LRS manualmente y proporcionar la dirección de grupo de Lync Server 2013 configurándolo directamente en la aplicación de consola de sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="6a842-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="6a842-115">Si se implementa el sistema de sala de Skype fuera de la red corporativa y un borde de Lync Server se ha implementado y configurado para apuntar a un director o grupo heredado, es necesario, un sitio secundario del servidor perimetral que señala al grupo de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6a842-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="6a842-116">Consulte la documentación de la implementación del servidor perimetral si desea obtener más información acerca de la implementación de un servidor perimetral secundario.</span><span class="sxs-lookup"><span data-stu-id="6a842-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="6a842-117">Sala de Skype interoperabilidad del sistema con una agrupación de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6a842-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="6a842-118">Durante la migración, si un usuario que está alojado en un grupo de Lync Server 2010 programa una reunión e invita a la cuenta de sistema del sitio de Skype, el cliente de sistema de sala de Skype tendrán una funcionalidad limitada al asistir a la reunión.</span><span class="sxs-lookup"><span data-stu-id="6a842-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="6a842-119">Cuando el cliente del sistema de sala de Skype une a una conferencia programada se ha organizado por un usuario alojados en Lync Server 2010, sistema de sala de Skype tiene las siguientes limitaciones en la reunión:</span><span class="sxs-lookup"><span data-stu-id="6a842-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="6a842-120">Sistema de sala de Skype no se puede mostrar la Galería de vídeos de múltiples vista.</span><span class="sxs-lookup"><span data-stu-id="6a842-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="6a842-121">Si el cliente del sistema de sala de Skype es el presentador, no puede aplicar bloqueo de vídeo a los participantes.</span><span class="sxs-lookup"><span data-stu-id="6a842-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="6a842-122">Sistema de sala de Skype no se puede mostrar la resolución de vídeo de 1080p (entrante o saliente), incluso si la directiva de la conferencia de Lync Server 2013 lo permite, por los motivos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6a842-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="6a842-123">Lync Server 2010 no admite una resolución de 1080p.</span><span class="sxs-lookup"><span data-stu-id="6a842-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="6a842-124">Sistema de sala de Skype está siempre limitado por la política del organizador de la conferencia para la resolución de vídeo.</span><span class="sxs-lookup"><span data-stu-id="6a842-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="6a842-125">Por lo tanto, incluso si el grupo de Lync 2010 es compatible con resolución 720p, sistema de sala de Skype no podrá aprovechar las ventajas de resolución 720p como directiva del organizador no lo admite.</span><span class="sxs-lookup"><span data-stu-id="6a842-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="6a842-p105">Los clientes de Lync 2013 detectan la presencia de LRS en la sala de reunión y desactivan el audio automáticamente para evitar eco en la sala de reunión física. Esta característica no funciona en reuniones hospedadas en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6a842-p105">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room. This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="6a842-128">Existen limitaciones en el rendimiento de escritorio compartido para reuniones hospedadas en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6a842-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="6a842-129">Los usuarios no podrán unirse a (restringidas) reuniones privadas que se hospedan en Lync 2010 con sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="6a842-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

