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
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Puede crear un nuevo servidor de chat persistente o grupo de servidores de chat persistente con el asistente definir nuevo grupo de chat persistente. Seleccione un Grupo de servidores de varios equipos o un Grupo de servidores de un solo equipo. Si selecciona un grupo de un solo equipo y posteriormente necesita un grupo de varios equipos, tendrá que quitar el grupo de servidores de un solo equipo y, a continuación, definir un grupo de varios equipos.
ms.openlocfilehash: 61851656b70b85db47fdad01dff0101217262dda
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217560"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="d89fd-105">Definir FQDN de chat persistente</span><span class="sxs-lookup"><span data-stu-id="d89fd-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="d89fd-106">Puede crear un nuevo servidor de chat persistente o grupo de servidores de chat persistente con el asistente **definir nuevo grupo de chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="d89fd-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="d89fd-107">Seleccione un **Grupo de servidores de varios equipos** o un **Grupo de servidores de un solo equipo**.</span><span class="sxs-lookup"><span data-stu-id="d89fd-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="d89fd-108">Si selecciona un grupo de un solo equipo y posteriormente necesita un grupo de varios equipos, tendrá que quitar el grupo de servidores de un solo equipo y, a continuación, definir un grupo de varios equipos.</span><span class="sxs-lookup"><span data-stu-id="d89fd-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="d89fd-109">También debe definir un **FQDN de grupo** de servidores para el servidor de chat persistente o el grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d89fd-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="d89fd-110">El nombre de dominio completo (FQDN) de grupo de servidores para el grupo de servidores de un solo equipo debe coincidir con el FQDN del equipo que forma el único grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="d89fd-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="d89fd-111">En el caso de un grupo de servidores de varios equipos, el FQDN debe ser el nombre que elija para representar a este grupo de servidores de varios equipos y define en DNS por un registro de host A (y AAAA s se utiliza IPv6).</span><span class="sxs-lookup"><span data-stu-id="d89fd-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d89fd-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d89fd-112">See also</span></span>

[<span data-ttu-id="d89fd-113">Planeación del servidor de chat persistente en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d89fd-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="d89fd-114">Agregar un servidor de chat persistente a la topología de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d89fd-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
