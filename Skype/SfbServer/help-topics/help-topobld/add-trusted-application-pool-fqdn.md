---
title: Agregar FQDN de grupo de servidores de aplicaciones de confianza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 'Para definir un nombre de dominio completo (FQDN) de un grupo de aplicaciones de confianza, especifique lo siguiente:'
ms.openlocfilehash: bb473aaab771038c0556234d865edcb19eca23f8
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697965"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="d64ea-103">Agregar FQDN de grupo de servidores de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="d64ea-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="d64ea-104">Para definir un nombre de dominio completo (FQDN) de un grupo de aplicaciones de confianza, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d64ea-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="d64ea-105">Un FQDN del servidor o grupo de servidores que hospedarán las aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="d64ea-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="d64ea-106">Seleccione **varios grupos de equipos** si va a implementar un grupo de servidores para las aplicaciones de confianza desde el equilibrio de carga y alta disponibilidad, o bien seleccione un **solo grupo de equipos** si no necesita equilibrio de carga o alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="d64ea-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d64ea-107">Un servidor de aplicaciones de confianza único no se puede convertir en un grupo de servidores más adelante.</span><span class="sxs-lookup"><span data-stu-id="d64ea-107">A single Trusted Applications Server cannot be converted to a pool of servers later.</span></span> <span data-ttu-id="d64ea-108">Si cree que puede necesitar un grupo en el futuro, puede implementar un grupo de varios servidores que contenga un solo equipo y agregar servidores cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d64ea-108">If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="d64ea-109">Para obtener más información sobre los grupos de aplicaciones de confianza, vea [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d64ea-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

