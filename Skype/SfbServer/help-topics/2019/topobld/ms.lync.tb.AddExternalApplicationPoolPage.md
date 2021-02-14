---
title: Agregar FQDN de grupo de servidores de aplicaciones de confianza
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para definir un nombre de dominio completo (FQDN) de grupo de aplicaciones de confianza, especifique lo siguiente:'
ms.openlocfilehash: e34c3ba68a90e292da9441465d9077112b1ce173
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811820"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="87929-103">Agregar FQDN de grupo de servidores de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="87929-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="87929-104">Para definir un nombre de dominio completo (FQDN) de grupo de aplicaciones de confianza, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="87929-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="87929-105">El nombre de dominio completo del servidor o el grupo de servidores que hospedarán las aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="87929-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="87929-106">Seleccione **Grupo de servidores de varios equipos** si va a implementar un grupo de servidores para las aplicaciones de confianza desde equilibrio de carga y alta disponibilidad; si no necesita equilibrio de carga ni alta disponibilidad, seleccione **Grupo de servidores de un solo equipo**.</span><span class="sxs-lookup"><span data-stu-id="87929-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="87929-107">Un solo servidor de aplicaciones de confianza no se puede convertir en un grupo de servidores posteriormente.</span><span class="sxs-lookup"><span data-stu-id="87929-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="87929-108">Si cree que puede necesitar un grupo en el futuro, puede implementar un grupo de varios servidores que contenga ahora un único equipo y agregar servidores cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="87929-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="87929-109">Para obtener más información sobre las aplicaciones de confianza, consulte [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="87929-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

