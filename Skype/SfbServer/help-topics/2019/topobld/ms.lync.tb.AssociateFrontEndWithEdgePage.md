---
title: Asociar front-end con servidor perimetral
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
ROBOTS: NOINDEX, NOFOLLOW
description: Cada grupo de servidores front-end solo puede tener asociado un servidor perimetral o un grupo de servidores perimetrales. Al habilitar el acceso de usuarios externos para un sitio, puede proporcionar compatibilidad con usuarios remotos. También puede habilitar la compatibilidad con usuarios federados, que puede incluir compatibilidad con usuarios de proveedores de conectividad de mensajería instantánea (MI) públicos específicos (como Windows Live) y compatibilidad con usuarios anónimos.
ms.openlocfilehash: a70949bc72684aa5896c09bab39bc77b405bd206
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122641"
---
# <a name="associate-front-end-with-edge"></a><span data-ttu-id="6b2e4-105">Asociar front-end con servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="6b2e4-105">Associate Front End With Edge</span></span>

<span data-ttu-id="6b2e4-106">Cada grupo de servidores front-end solo puede tener asociado un servidor perimetral o un grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="6b2e4-106">Each Front End pool can have only one Edge Server or Edge pool associated with it.</span></span> <span data-ttu-id="6b2e4-107">Al habilitar el acceso de usuarios externos para un sitio, puede proporcionar compatibilidad con usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="6b2e4-107">When you enable external user access for a site, you can provide support for remote users.</span></span> <span data-ttu-id="6b2e4-108">También puede habilitar la compatibilidad con usuarios federados, que puede incluir compatibilidad con usuarios de proveedores de conectividad de mensajería instantánea (MI) públicos específicos (como Windows Live) y compatibilidad con usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="6b2e4-108">You can also enable support for federated users, which can include support for users of specific public instant messaging (IM) connectivity providers (such as Windows Live), and support for anonymous users.</span></span>

<span data-ttu-id="6b2e4-109">Todos los grupos de servidores de un sitio y los grupos de varios sitios centrales pueden usar el mismo servidor perimetral, si el uso no supera la capacidad del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="6b2e4-109">All pools at a site, and the pools of multiple central sites, can use the same Edge Server, if usage does not exceed the capacity of the Edge Server.</span></span> <span data-ttu-id="6b2e4-110">Para obtener más información sobre supervisión y escala, consulte [Planear el acceso de usuarios externos](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access) en la documentación sobre planeación.</span><span class="sxs-lookup"><span data-stu-id="6b2e4-110">For details about monitoring, including scaling, see [Planning for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access) in the Planning documentation.</span></span> <span data-ttu-id="6b2e4-111">Para obtener más información sobre cómo diseñar una topología que permita el acceso de usuarios externos, consulte[Definir la topología perimetral](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="6b2e4-111">For details about designing a topology to support external user access, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) in the Deployment documentation.</span></span>