---
title: Definir FQDN de chat persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Puede crear un nuevo servidor de chat persistente o un grupo de servidores de chat persistente mediante el Asistente para definir nuevo grupo de chat persistente. Seleccione un Grupo de servidores de varios equipos o un Grupo de servidores de un solo equipo. Si selecciona un grupo de servidores de un solo equipo y, posteriormente, necesita un grupo de varios equipos, deberá quitar el grupo de un solo equipo y, a continuación, definir un grupo de varios equipos.
ms.openlocfilehash: e96cc1f3c71dee7bab50d3101281596c17084207
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818450"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="03a1f-105">Definir FQDN de chat persistente</span><span class="sxs-lookup"><span data-stu-id="03a1f-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="03a1f-106">Puede crear un nuevo servidor de chat persistente o un grupo de servidores de chat persistente mediante el Asistente para definir nuevo grupo **de chat persistente.**</span><span class="sxs-lookup"><span data-stu-id="03a1f-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="03a1f-107">Seleccione un **Grupo de servidores de varios equipos** o un **Grupo de servidores de un solo equipo**.</span><span class="sxs-lookup"><span data-stu-id="03a1f-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="03a1f-108">Si selecciona un grupo de servidores de un solo equipo y, posteriormente, necesita un grupo de varios equipos, deberá quitar el grupo de un solo equipo y, a continuación, definir un grupo de varios equipos.</span><span class="sxs-lookup"><span data-stu-id="03a1f-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="03a1f-109">También debe definir un **FQDN de grupo para** el servidor de chat persistente o el grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="03a1f-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="03a1f-110">El nombre de dominio completo (FQDN) de grupo de servidores para el grupo de servidores de un solo equipo debe coincidir con el FQDN del equipo que forma el único grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="03a1f-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="03a1f-111">En el caso de un grupo de servidores de varios equipos, el FQDN debe ser el nombre que elija para representar a este grupo de servidores de varios equipos y define en DNS por un registro de host A (y AAAA s se utiliza IPv6).</span><span class="sxs-lookup"><span data-stu-id="03a1f-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="03a1f-112">Ver también</span><span class="sxs-lookup"><span data-stu-id="03a1f-112">See also</span></span>

[<span data-ttu-id="03a1f-113">Planear el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="03a1f-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="03a1f-114">Agregar un servidor de chat persistente a la topología de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="03a1f-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
