---
title: Definir FQDN de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Para crear un nuevo servidor de chat persistente o un grupo de servidores de chat persistente, use el asistente definir nuevo grupo de chats persistentes. Seleccione un Grupo de varios equipos o un Grupo de un solo equipo. Si selecciona un grupo de un solo equipo y, más adelante, necesita uno de varios equipos, deberá eliminar el grupo de un solo equipo y definir uno de varios equipos.
ms.openlocfilehash: 12b5a648de211086d33624afad56ce069493b135
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820202"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="92765-105">Definir FQDN de chat persistente</span><span class="sxs-lookup"><span data-stu-id="92765-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="92765-106">Para crear un nuevo servidor de chat persistente o un grupo de servidores de chat persistente, use el asistente **definir nuevo grupo de chats persistentes** .</span><span class="sxs-lookup"><span data-stu-id="92765-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="92765-107">Seleccione un **Grupo de varios equipos** o un **Grupo de un solo equipo**.</span><span class="sxs-lookup"><span data-stu-id="92765-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="92765-108">Si selecciona un grupo de un solo equipo y, más adelante, necesita uno de varios equipos, deberá eliminar el grupo de un solo equipo y definir uno de varios equipos.</span><span class="sxs-lookup"><span data-stu-id="92765-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="92765-109">También debe definir un **FQDN de grupo** para el servidor de chat persistente o el grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="92765-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="92765-110">El nombre de dominio completo (FQDN) del grupo de un solo equipo debe coincidir con el FQDN del equipo que forma el único grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="92765-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="92765-111">En el caso de un grupo de varios equipos, el FQDN debe ser el nombre que elija para representar a este grupo de varios equipos y que se define en DNS mediante un registro de host A (y AAAA si se usa IPv6).</span><span class="sxs-lookup"><span data-stu-id="92765-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="92765-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="92765-112">See also</span></span>

[<span data-ttu-id="92765-113">Planificar el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="92765-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="92765-114">Agregar un servidor de chat persistente a su topología de 2015 de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="92765-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
