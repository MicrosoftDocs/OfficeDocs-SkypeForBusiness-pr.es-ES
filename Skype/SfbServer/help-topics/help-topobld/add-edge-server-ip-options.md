---
title: Agregar opciones IP de servidor perimetral
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 permite configurar direcciones IPv4 e IPv6 para cada interfaz del servidor perimetral y el grupo de servidores perimetrales. Para ello, siga este procedimiento:'
ms.openlocfilehash: 2c68fcfcb2e99759536224889a818639b61d5fcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219795"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="29500-104">Agregar opciones IP de servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="29500-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="29500-105">Microsoft Lync Server 2013 permite configurar direcciones IPv4 e IPv6 para cada interfaz del servidor perimetral y el grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="29500-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="29500-106">Para ello, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="29500-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="29500-107">**Habilitar IPv4 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv4 a la interfaz interna del servidor perimetral o del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="29500-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="29500-108">**Habilitar IPv6 en la interfaz interna**: Active la casilla si desea aplicar una dirección IPv6 a la interfaz interna del servidor perimetral o del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="29500-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="29500-109">**Habilitar IPv4 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv4 a la interfaz externa del servidor perimetral o del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="29500-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="29500-110">**Habilitar IPv6 en la interfaz externa**: Active la casilla si desea aplicar una dirección IPv6 al servidor perimetral o a la interfaz externa del grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="29500-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="29500-111">También puede configurar el servidor perimetral o el grupo de servidores perimetrales para que usen una dirección de traducción de direcciones de red para las direcciones IP externas.</span><span class="sxs-lookup"><span data-stu-id="29500-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="29500-112">Para hacerlo, active la casilla **La dirección IP externa del grupo de servidores perimetral se traduce mediante NAT**.</span><span class="sxs-lookup"><span data-stu-id="29500-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="29500-113">Compatibilidad con NAT.</span><span class="sxs-lookup"><span data-stu-id="29500-113">NAT support.</span></span> <span data-ttu-id="29500-114">La traducción de direcciones de red (NAT) no es compatible cuando se usa el equilibrio de carga de hardware, por lo que no seleccione la opción NAT si va a implementar un grupo de servidores perimetrales con el equilibrio de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="29500-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

