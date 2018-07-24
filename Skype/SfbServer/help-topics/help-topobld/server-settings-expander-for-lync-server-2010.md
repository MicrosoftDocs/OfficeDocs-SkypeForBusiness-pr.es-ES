---
title: Expansor de configuración de servidor para Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Para editar las propiedades de este equipo, realice lo siguiente:'
ms.openlocfilehash: 242f2b25a77de7f81ce8c11828f2fc0fbe1c2d41
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992452"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="10ec5-103">Expansor de configuración de servidor para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="10ec5-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="10ec5-104">Para editar las propiedades de este equipo, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="10ec5-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="10ec5-105">Editar el **nombre de dominio (FQDN) completo** de este equipo.</span><span class="sxs-lookup"><span data-stu-id="10ec5-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="10ec5-106">Esta entrada debe coincidir con el nombre del equipo tal y como se define en el sistema de nombres de dominio (DNS) y en nombres alternativos del sujeto (SAN) o el nombre de sujeto (SN) del certificado asociado con este equipo.</span><span class="sxs-lookup"><span data-stu-id="10ec5-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="10ec5-107">Seleccione una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="10ec5-107">You select one of the following:</span></span>
    
    <span data-ttu-id="10ec5-108">**Utilice todas las direcciones IP configuradas**: seleccione esta opción para usar todas las direcciones IP en el equipo.</span><span class="sxs-lookup"><span data-stu-id="10ec5-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="10ec5-109">Si el equipo tiene varias direcciones IP, debe tener en cuenta que los servicios asociados con este equipo usará todas las direcciones IP para todos los servicios.</span><span class="sxs-lookup"><span data-stu-id="10ec5-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="10ec5-110">Si un servidor escucha o servicio está esperando la comunicación de un puerto y dirección IP específica, el servicio no puede hacer que la mejor selección de qué dirección IP para escuchar en.</span><span class="sxs-lookup"><span data-stu-id="10ec5-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="10ec5-111">**Limitar el uso del servicio a las direcciones IP seleccionadas**: seleccione esta opción si desea definir direcciones IP específicas para la **dirección IP principal** que escuchará este equipo para la comunicación entre otros equipos y grupos de servidores en la implementación.</span><span class="sxs-lookup"><span data-stu-id="10ec5-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="10ec5-112">Definir la **dirección IP de RTC** para la dirección IP específica que el equipo y el servicio se escuchar para las comunicaciones y enviar comunicaciones a la puerta de enlace RTC o IP-PBX definido.</span><span class="sxs-lookup"><span data-stu-id="10ec5-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

