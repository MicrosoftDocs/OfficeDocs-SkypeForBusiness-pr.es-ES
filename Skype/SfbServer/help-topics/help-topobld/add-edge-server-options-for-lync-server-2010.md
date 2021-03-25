---
title: Agregar opciones de servidor perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Defina un nuevo servidor perimetral o grupo de servidores perimetrales y se le ofrece la oportunidad de definir características para el nuevo servidor o grupo de servidores. Las opciones entre las que puede elegir son:'
ms.openlocfilehash: dfc8238bbbe4899f9819118a11fc11ba47fe21f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119809"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="7a60b-104">Agregar opciones de servidor perimetral para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7a60b-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="7a60b-105">Defina un nuevo servidor perimetral o grupo de servidores perimetrales y se le ofrece la oportunidad de definir características para el nuevo servidor o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="7a60b-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="7a60b-106">Las opciones entre las que puede elegir son:</span><span class="sxs-lookup"><span data-stu-id="7a60b-106">The options that you can choose are:</span></span>

- <span data-ttu-id="7a60b-107">**Usar un FQDN único y una dirección IP**: active esta casilla para usar una sola dirección IPv4 o IPv6 (si elige usar ambos IPv4 y IPv6, deberá definir una dirección IP de cada tipo) y un nombre de dominio completo (FQDN) para las interfaces perimetrales externas.</span><span class="sxs-lookup"><span data-stu-id="7a60b-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7a60b-108">Si elige esta opción, usará una sola dirección IP, o una IPv4 y una IPv6, pero debe asignar números de puerto diferentes a cada interfaz perimetral.</span><span class="sxs-lookup"><span data-stu-id="7a60b-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="7a60b-109">**Habilitar federación (puerto 5061)**: active esta casilla si va a establecer relaciones de federación con otras federaciones SIP, proveedores u ofertas hospedadas que usan el protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="7a60b-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="7a60b-110">NAT traduce la dirección IP externa de este grupo de servidores perimetrales: active esta casilla si usa direcciones **IP** privadas para las interfaces externas perimetrales y proporcionará un dispositivo de traducción de direcciones de red (NAT) para colocar el servidor perimetral o el grupo perimetral lógicamente detrás.</span><span class="sxs-lookup"><span data-stu-id="7a60b-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a60b-111">Ver también</span><span class="sxs-lookup"><span data-stu-id="7a60b-111">See also</span></span>

[<span data-ttu-id="7a60b-112">Planeación del acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="7a60b-112">Planning for External User Access</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access)

[<span data-ttu-id="7a60b-113">Implementación de servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="7a60b-113">Deploying External User Access</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-external-user-access)