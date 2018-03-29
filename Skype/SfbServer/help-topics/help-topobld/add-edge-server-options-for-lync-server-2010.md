---
title: Agregar las opciones de servidor de borde de Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Definir un nuevo servidor perimetral o un grupo de servidores de borde y se presentan con la oportunidad de definir funciones para el nuevo servidor o grupo de servidores. Las opciones que puede elegir son:'
ms.openlocfilehash: c031480dd3553aa4fc1ca2f2a8ddd03f67d9bc02
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="a57fb-104">Agregar las opciones de servidor de borde de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a57fb-104">Add Edge Server Options for Lync Server 2010</span></span>
 
<span data-ttu-id="a57fb-105">Definir un nuevo servidor perimetral o un grupo de servidores de borde y se presentan con la oportunidad de definir funciones para el nuevo servidor o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="a57fb-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="a57fb-106">Las opciones que puede elegir son:</span><span class="sxs-lookup"><span data-stu-id="a57fb-106">The options that you can choose are:</span></span>
  
- <span data-ttu-id="a57fb-107">**Utilizar una única dirección IP y FQDN**: Active la casilla de verificación utilizar un solo IPv4 o IPv6 (Si opta por utilizar IPv4 e IPv6, debe definir uno de cada tipo de dirección IP) dirección y nombre de dominio completo (FQDN) para el externo interfaces del borde.</span><span class="sxs-lookup"><span data-stu-id="a57fb-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="a57fb-108">Si elige esta opción, se utiliza una única dirección IP, o uno de IPv4 y una IPv6, pero debe asignar a números de puerto diferentes para cada interfaz de bordes.</span><span class="sxs-lookup"><span data-stu-id="a57fb-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span> 
  
- <span data-ttu-id="a57fb-109">**Habilitar la federación (puerto 5061)**: seleccione esta casilla de verificación si va a federar con otras federaciones, proveedores u ofertas de host que utilicen el protocolo de inicio de sesión (SIP) de SIP.</span><span class="sxs-lookup"><span data-stu-id="a57fb-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>
    
- <span data-ttu-id="a57fb-110">**NAT traduce la dirección IP externa de este grupo de borde**: seleccione esta casilla de verificación si utiliza direcciones IP privadas para las interfaces externas del borde y proporcionará un dispositivo de traducción (NAT) de direcciones de red para colocar el servidor perimetral o bordes de piscina lógicamente subyacente.</span><span class="sxs-lookup"><span data-stu-id="a57fb-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a57fb-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a57fb-111">See also</span></span>

#### 

[<span data-ttu-id="a57fb-112">Planificación para el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="a57fb-112">Planning for External User Access</span></span>](http://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)
  
[<span data-ttu-id="a57fb-113">Implementar el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="a57fb-113">Deploying External User Access</span></span>](http://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)

