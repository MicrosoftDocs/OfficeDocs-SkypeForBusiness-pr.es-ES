---
title: Consideraciones acerca de la migración del Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Lea este tema para obtener más información acerca de cómo implementar el sistema de sala de Skype en un entorno que tiene varias versiones de Skype para Business Server y Lync Server.
ms.openlocfilehash: 24015d85ef82b3a175564f92504d7c0ca46e9d54
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20982751"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="f0c29-103">Consideraciones acerca de la migración del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="f0c29-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="f0c29-104">Lea este tema para obtener más información acerca de cómo implementar el sistema de sala de Skype en un entorno que tiene varias versiones de Skype para Business Server y Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0c29-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="f0c29-105">Consideraciones acerca de la migración</span><span class="sxs-lookup"><span data-stu-id="f0c29-105">Migration considerations</span></span>

<span data-ttu-id="f0c29-106">En esta sección se proporciona instrucciones si va a implementar el sistema de sala de Skype en un entorno de grupo de varios servidores que incluya las diferentes versiones de Skype para Business Server, Lync Server u Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f0c29-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, Lync Server, or Office Communications Server 2007 R2.</span></span> 
  
<span data-ttu-id="f0c29-107">El componente Replicador de usuario (UR) de Lync Server obtiene objetos de usuario de Active Directory y los coloca en la base de datos de SQL Server del back-end de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0c29-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="f0c29-108">Sólo el Replicador de usuarios en Lync Server 2013 está al tanto de objetos del sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="f0c29-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="f0c29-109">En anteriores versiones de Lync Server y Office Communications, el replicador de usuario no detecta los atributos de Active Directory que designan los objetos LRS y, por consiguiente, no los reconoce.</span><span class="sxs-lookup"><span data-stu-id="f0c29-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="f0c29-110">Si una cuenta de sistema de salas de Skype intenta iniciar sesión en Lync y realiza la detección automática en función de registro SRV o el aspecto de registro DNS A copia de seguridad, y si los puntos de esas cuentas a una versión anterior de Lync Server u Office Communications Server, LRS recibirá una respuesta 404 no se encuentra en  el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="f0c29-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="f0c29-111">El grupo heredado no podrán redirigir del sistema de sala de Skype a su grupo de servidores principal de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0c29-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="f0c29-112">Puede abordar este problema con las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f0c29-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="f0c29-113">Señale el registro SRV de detección automática (_sipinternaltls._tcp.contoso.com) en el grupo de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0c29-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="f0c29-114">Si la primera opción no es posible, debe configurar LRS manualmente y proporcione la dirección de grupo de servidores de Lync Server 2013 mediante su configuración directamente en la aplicación de consola del sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="f0c29-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="f0c29-115">Si el sistema de sala de Skype se implementa fuera de la red corporativa y un servidor perimetral de Lync ha implementado y configurado para que apunte a un grupo de servidores heredado o director, un sitio secundario del servidor perimetral es necesario, que apunta al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0c29-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="f0c29-116">Consulte la documentación de la implementación del servidor perimetral si desea obtener más información acerca de la implementación de un servidor perimetral secundario.</span><span class="sxs-lookup"><span data-stu-id="f0c29-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="f0c29-117">Interoperabilidad del sistema de salas de Skype con un grupo de servidores de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f0c29-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="f0c29-118">Durante la migración, si un usuario alojado en un grupo de servidores de Lync Server 2010 programa una reunión y se invita a la cuenta del sistema de salas de Skype, el cliente del sistema de salas de Skype tendrán una funcionalidad limitada al asistir a la reunión.</span><span class="sxs-lookup"><span data-stu-id="f0c29-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="f0c29-119">Cuando el cliente del sistema de salas de Skype se une a una llamada de conferencia programada que se ha organizado por un usuario alojado en Lync Server 2010, sistema de sala de Skype tiene las siguientes limitaciones en la reunión:</span><span class="sxs-lookup"><span data-stu-id="f0c29-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="f0c29-120">Sistema de sala de Skype no se puede mostrar la Galería de vídeo de varias vista.</span><span class="sxs-lookup"><span data-stu-id="f0c29-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="f0c29-121">Si el cliente del sistema de salas de Skype es el moderador, no se aplican bloqueo de vídeo en los participantes.</span><span class="sxs-lookup"><span data-stu-id="f0c29-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="f0c29-122">Sistema de sala de Skype no se puede mostrar la resolución de vídeo de 1080p (entrante o saliente), incluso si la directiva de conferencia de Lync Server 2013 lo permite, debido a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0c29-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="f0c29-123">Lync Server 2010 no es compatible con resolución 1080p.</span><span class="sxs-lookup"><span data-stu-id="f0c29-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="f0c29-124">Sistema de sala de Skype siempre está limitado por la directiva del organizador de la conferencia para la resolución de vídeo.</span><span class="sxs-lookup"><span data-stu-id="f0c29-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="f0c29-125">Por lo tanto, incluso si el grupo de servidores de Lync 2010 es compatible con la resolución 720p, sistema de sala de Skype no podrán aprovechar las ventajas de resolución 720p como la directiva del organizador no lo admite.</span><span class="sxs-lookup"><span data-stu-id="f0c29-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="f0c29-p105">Los clientes de Lync 2013 detectan la presencia de LRS en la sala de reunión y desactivan el audio automáticamente para evitar eco en la sala de reunión física. Esta característica no funciona en reuniones hospedadas en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f0c29-p105">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room. This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="f0c29-128">Existen limitaciones en el rendimiento de escritorio compartido para reuniones hospedadas en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f0c29-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="f0c29-129">Los usuarios no podrán unirse a privada reuniones (restringidas) a las que se hospedan en Lync 2010 con el sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="f0c29-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

