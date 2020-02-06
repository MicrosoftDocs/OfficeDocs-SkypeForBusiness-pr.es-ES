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
- NOCSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Defina un nuevo servidor perimetral o un grupo de servidores perimetrales y se le presentará la oportunidad de definir características para el nuevo servidor o grupo. Las opciones que puede elegir son:'
ms.openlocfilehash: 983a8a6e4fdeea34930cc9adf2b2cb29e4c75759
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820992"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="8ed25-104">Agregar opciones de servidor perimetral para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8ed25-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="8ed25-105">Defina un nuevo servidor perimetral o un grupo de servidores perimetrales y se le presentará la oportunidad de definir características para el nuevo servidor o grupo.</span><span class="sxs-lookup"><span data-stu-id="8ed25-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="8ed25-106">Las opciones que puede elegir son:</span><span class="sxs-lookup"><span data-stu-id="8ed25-106">The options that you can choose are:</span></span>

- <span data-ttu-id="8ed25-107">**Use un único FQDN y una dirección IP**: Active la casilla para usar un único IPv4 o IPv6 (si elige usar IPv4 e IPv6, deberá definir una de cada tipo de dirección IP) y la dirección de nombre de dominio completo (FQDN) para las interfaces de borde externo.</span><span class="sxs-lookup"><span data-stu-id="8ed25-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8ed25-108">Si elige esta opción, usará solo una dirección IP, o un IPv4 y un IPv6, pero debe asignar números de Puerto diferentes para cada interfaz perimetral.</span><span class="sxs-lookup"><span data-stu-id="8ed25-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="8ed25-109">**Habilitar Federación (puerto 5061)**: Seleccione esta casilla si se va a federar con otras federaciones, proveedores o federaciones de SIP que usen el protocolo de inicio de sesión (SIP).</span><span class="sxs-lookup"><span data-stu-id="8ed25-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="8ed25-110">**La dirección IP externa de este grupo de límites es traducida por NAT**: Seleccione esta casilla si usa direcciones IP privadas para las interfaces externas de Edge y proporcionará un dispositivo de traducción de direcciones de red (NAT) para colocar el servidor perimetral o el grupo perimetral de forma lógica detrás.</span><span class="sxs-lookup"><span data-stu-id="8ed25-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ed25-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ed25-111">See also</span></span>

[<span data-ttu-id="8ed25-112">Planear el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="8ed25-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="8ed25-113">Implementar el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="8ed25-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
