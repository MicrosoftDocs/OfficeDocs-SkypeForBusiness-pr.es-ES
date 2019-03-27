---
title: Agregar opciones IP de servidor perimetral
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: 'Skype para Business Server le permite configurar las direcciones IPv4 e IPv6 para cada interfaz para el servidor perimetral y el grupo de servidores perimetrales. Para ello, realice lo siguiente:'
ms.openlocfilehash: 727a946c6e9992b9391e7bf77238fdb61910c830
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898588"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="361fd-104">Agregar opciones IP de servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="361fd-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="361fd-105">Skype para Business Server le permite configurar las direcciones IPv4 e IPv6 para cada interfaz para el servidor perimetral y el grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="361fd-105">Skype for Business Server allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="361fd-106">Para ello, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="361fd-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="361fd-107">**Habilitar IPv4 en interfaz interna**: Active la casilla de verificación si desea aplicar una dirección IPv4 para el servidor perimetral o la interfaz interna del grupo de servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="361fd-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="361fd-108">**Habilitar IPv6 en la interfaz interna**: Active la casilla de verificación si desea aplicar una dirección IPv6 para el servidor perimetral o la interfaz interna del grupo de servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="361fd-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="361fd-109">**Habilitar IPv4 en interfaz externa**: Active la casilla de verificación si desea aplicar una dirección IPv4 para el servidor perimetral o la interfaz externa de grupo de servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="361fd-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="361fd-110">**Habilitar IPv6 en la interfaz externa**: Active la casilla de verificación si desea aplicar una dirección IPv6 para el servidor perimetral o la interfaz externa de grupo de servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="361fd-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="361fd-111">También puede configurar el servidor perimetral o grupo de servidores perimetrales para usar una dirección de traducción de direcciones de red para las direcciones IP externas.</span><span class="sxs-lookup"><span data-stu-id="361fd-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="361fd-112">Para ello, mediante la selección de la casilla de verificación **NAT traduce la dirección IP externa de este grupo de servidores perimetrales**.</span><span class="sxs-lookup"><span data-stu-id="361fd-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="361fd-113">Compatibilidad con NAT.</span><span class="sxs-lookup"><span data-stu-id="361fd-113">NAT support.</span></span> <span data-ttu-id="361fd-114">Traducción de direcciones de red (NAT) no se admite cuando se usa hardware equilibrio de carga, por lo que no seleccione la opción de NAT si va a implementar un grupo de servidores perimetrales con equilibrio de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="361fd-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

