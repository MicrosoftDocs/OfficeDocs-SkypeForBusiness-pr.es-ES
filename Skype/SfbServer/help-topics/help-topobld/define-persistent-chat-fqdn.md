---
title: Definir FQDN de chat persistente
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Crear un nuevo servidor de Chat persistente o el grupo de servidores de Chat persistente mediante el Asistente para definir nuevo grupo de Chat persistente. Seleccione un Grupo de varios equipos o un Grupo de un solo equipo. Si selecciona un grupo de un solo equipo y, más adelante, necesita uno de varios equipos, deberá eliminar el grupo de un solo equipo y definir uno de varios equipos.
ms.openlocfilehash: 9de27a5b64c9fa13effa9396798cb67083a407e5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880927"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="a7793-105">Definir FQDN de chat persistente</span><span class="sxs-lookup"><span data-stu-id="a7793-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="a7793-106">Crear un nuevo servidor de Chat persistente o el grupo de servidores de Chat persistente mediante el Asistente para **Definir nuevo grupo de Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="a7793-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="a7793-107">Seleccione un **Grupo de varios equipos** o un **Grupo de un solo equipo**.</span><span class="sxs-lookup"><span data-stu-id="a7793-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="a7793-108">Si selecciona un grupo de un solo equipo y, más adelante, necesita uno de varios equipos, deberá eliminar el grupo de un solo equipo y definir uno de varios equipos.</span><span class="sxs-lookup"><span data-stu-id="a7793-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="a7793-109">También debe definir un **FQDN del grupo de servidores** para el servidor de Chat persistente o grupo de servidores de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a7793-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="a7793-110">El nombre de dominio completo (FQDN) del grupo de un solo equipo debe coincidir con el FQDN del equipo que forma el único grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="a7793-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="a7793-111">En el caso de un grupo de varios equipos, el FQDN debe ser el nombre que elija para representar a este grupo de varios equipos y que se define en DNS mediante un registro de host A (y AAAA si se usa IPv6).</span><span class="sxs-lookup"><span data-stu-id="a7793-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a7793-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a7793-112">See also</span></span>

[<span data-ttu-id="a7793-113">Planificar el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="a7793-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="a7793-114">Agregar servidor de Chat persistente a su Skype para topología empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="a7793-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
