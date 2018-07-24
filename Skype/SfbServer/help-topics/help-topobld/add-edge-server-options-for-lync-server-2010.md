---
title: Agregar opciones de servidor perimetral de Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Definir un nuevo servidor perimetral o grupo de servidores perimetrales y se presentan con la oportunidad para definir las características para el nuevo servidor o grupo de servidores. Las opciones que puede elegir son:'
ms.openlocfilehash: 7cd5af525e87f23bc07245f5fed139bc2c9c7356
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967624"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="6ef16-104">Agregar opciones de servidor perimetral de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6ef16-104">Add Edge Server Options for Lync Server 2010</span></span>
 
<span data-ttu-id="6ef16-105">Definir un nuevo servidor perimetral o grupo de servidores perimetrales y se presentan con la oportunidad para definir las características para el nuevo servidor o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="6ef16-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="6ef16-106">Las opciones que puede elegir son:</span><span class="sxs-lookup"><span data-stu-id="6ef16-106">The options that you can choose are:</span></span>
  
- <span data-ttu-id="6ef16-107">**Usar una única dirección IP y FQDN**: Active la casilla de verificación para usar un solo IPv4 o IPv6 (Si opta por utilizar IPv4 como IPv6, y, a continuación, debe definir uno de cada tipo de dirección IP) dirección y nombre de dominio completo (FQDN) para la externa perimetral interfaces.</span><span class="sxs-lookup"><span data-stu-id="6ef16-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="6ef16-108">Si elige esta opción, va a usar una única dirección IP, o una IPv4 y uno IPv6, pero debe asignar a números de puerto diferentes para cada interfaz perimetral.</span><span class="sxs-lookup"><span data-stu-id="6ef16-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span> 
  
- <span data-ttu-id="6ef16-109">**Habilitar la federación (puerto 5061)**: seleccione esta casilla de verificación si va a federar con otras federaciones SIP, proveedores u ofertas hospedadas que usan el protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="6ef16-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>
    
- <span data-ttu-id="6ef16-110">**La dirección IP externa de este grupo de servidores perimetrales se traduce mediante NAT**: seleccione esta casilla de verificación si se usa direcciones IP privadas para las interfaces externas perimetrales y proporcionará un dispositivo de traducción (NAT) de direcciones de red para colocar el servidor perimetral o grupo de servidores perimetrales lógicamente subyacente.</span><span class="sxs-lookup"><span data-stu-id="6ef16-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6ef16-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ef16-111">See also</span></span>

[<span data-ttu-id="6ef16-112">Planear el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="6ef16-112">Planning for External User Access</span></span>](http://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)
  
[<span data-ttu-id="6ef16-113">Implementación de acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="6ef16-113">Deploying External User Access</span></span>](http://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)