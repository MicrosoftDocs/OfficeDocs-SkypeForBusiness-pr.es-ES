---
title: Agregar opciones IP de servidor perimetral
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: 'Skype empresarial Server le permite configurar direcciones IPv4 e IPv6 para cada interfaz para el servidor perimetral y el grupo Edge. Para ello, haga lo siguiente:'
ms.openlocfilehash: 5b63847f3044411dcb8e04e29eea21492597993d
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798207"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="2eb74-104">Agregar opciones IP de servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="2eb74-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="2eb74-105">Skype empresarial Server le permite configurar direcciones IPv4 e IPv6 para cada interfaz para el servidor perimetral y el grupo Edge.</span><span class="sxs-lookup"><span data-stu-id="2eb74-105">Skype for Business Server allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="2eb74-106">Para ello, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2eb74-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="2eb74-107">**Habilitar IPv4 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv4 al servidor perimetral o a la interfaz interna de grupo perimetral.</span><span class="sxs-lookup"><span data-stu-id="2eb74-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="2eb74-108">**Habilitar IPv6 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz interna de la agrupación perimetral.</span><span class="sxs-lookup"><span data-stu-id="2eb74-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="2eb74-109">**Habilitar IPv4 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv4 al servidor perimetral o a la interfaz externa del grupo perimetral.</span><span class="sxs-lookup"><span data-stu-id="2eb74-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="2eb74-110">**Habilitar IPv6 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz externa del grupo perimetral.</span><span class="sxs-lookup"><span data-stu-id="2eb74-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="2eb74-111">También puede configurar el servidor perimetral o el grupo Edge para usar una dirección de traducción de direcciones de red para las direcciones IP externas.</span><span class="sxs-lookup"><span data-stu-id="2eb74-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="2eb74-112">Para ello, active la casilla **la dirección IP externa de este grupo de límites la traduce nat**.</span><span class="sxs-lookup"><span data-stu-id="2eb74-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="2eb74-113">Compatibilidad con NAT.</span><span class="sxs-lookup"><span data-stu-id="2eb74-113">NAT support.</span></span> <span data-ttu-id="2eb74-114">La traducción de direcciones de red (NAT) no es compatible cuando se usa el equilibrio de carga de hardware, por lo tanto, no seleccione la opción NAT si está implementando un grupo de servidores perimetrales con el equilibrio de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="2eb74-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

