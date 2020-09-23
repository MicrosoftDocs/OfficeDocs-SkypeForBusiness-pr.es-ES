---
title: Agregar opciones de servidor perimetral para Lync Server 2010
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
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Puede definir un nuevo servidor perimetral o un grupo de servidores perimetrales y se presenta la oportunidad de definir características para el nuevo servidor o grupo de servidores. Las opciones entre las que puede elegir son:'
ms.openlocfilehash: 273b2543fc3eea1373817ab38eab39379ec59132
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216601"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="7c4f7-104">Agregar opciones de servidor perimetral para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7c4f7-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="7c4f7-105">Puede definir un nuevo servidor perimetral o un grupo de servidores perimetrales y se presenta la oportunidad de definir características para el nuevo servidor o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="7c4f7-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="7c4f7-106">Las opciones entre las que puede elegir son:</span><span class="sxs-lookup"><span data-stu-id="7c4f7-106">The options that you can choose are:</span></span>

- <span data-ttu-id="7c4f7-107">**Usar un FQDN único y una dirección IP**: active esta casilla para usar una sola dirección IPv4 o IPv6 (si elige usar ambos IPv4 y IPv6, deberá definir una dirección IP de cada tipo) y un nombre de dominio completo (FQDN) para las interfaces perimetrales externas.</span><span class="sxs-lookup"><span data-stu-id="7c4f7-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7c4f7-108">Si elige esta opción, usará una sola dirección IP, o una IPv4 y una IPv6, pero debe asignar números de puerto diferentes a cada interfaz perimetral.</span><span class="sxs-lookup"><span data-stu-id="7c4f7-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="7c4f7-109">**Habilitar federación (puerto 5061)**: active esta casilla si va a establecer relaciones de federación con otras federaciones SIP, proveedores u ofertas hospedadas que usan el protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="7c4f7-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="7c4f7-110">**La dirección IP externa de este grupo de servidores perimetrales se traduce mediante NAT**: Seleccione esta casilla si usa direcciones IP privadas para las interfaces externas perimetrales y proporcionará un dispositivo de traducción de direcciones de red (NAT) para poner el servidor perimetral o el grupo de servidores perimetrales perimetrales detrás de forma lógica.</span><span class="sxs-lookup"><span data-stu-id="7c4f7-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c4f7-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c4f7-111">See also</span></span>

[<span data-ttu-id="7c4f7-112">Planeación del acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="7c4f7-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="7c4f7-113">Implementación de servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="7c4f7-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
