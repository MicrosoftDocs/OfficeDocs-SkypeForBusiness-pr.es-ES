---
title: Agregar el FQDN del grupo de aplicaciones de confianza
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 'Para definir un nombre de dominio completo del grupo de servidores de aplicaciones de confianza (FQDN), especifique lo siguiente:'
ms.openlocfilehash: af21ab09797a5b81f2071a37a2668d556f0a4012
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="1b358-103">Agregar el FQDN del grupo de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="1b358-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="1b358-104">Para definir un nombre de dominio completo del grupo de servidores de aplicaciones de confianza (FQDN), especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1b358-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="1b358-105">Un nombre de dominio completo del servidor o grupo de servidores que se va a hospedar las aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="1b358-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="1b358-106">Si va a implementar un grupo de servidores para las aplicaciones de confianza de equilibrio de carga y alta disponibilidad, o seleccione el **grupo de servidores de un solo equipo** si no necesita disponibilidad alta o equilibrio de carga, seleccione **el grupo de servidores de varios equipos** .</span><span class="sxs-lookup"><span data-stu-id="1b358-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1b358-107">Un único servidor de aplicaciones de confianza no se puede convertir a un grupo de servidores más adelante.</span><span class="sxs-lookup"><span data-stu-id="1b358-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="1b358-108">Si piensa que es posible que necesite un grupo de servidores en el futuro, puede implementar un grupo de servidores de varios que ahora contiene un único equipo y adición de servidores cuando es necesario.</span><span class="sxs-lookup"><span data-stu-id="1b358-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="1b358-109">Para obtener información detallada acerca de los grupos de servidores de aplicaciones de confianza, vea [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1b358-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

