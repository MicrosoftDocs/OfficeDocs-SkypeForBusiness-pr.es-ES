---
title: Expansor de configuración de servidor para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Para editar las propiedades de este equipo, haga lo siguiente:'
ms.openlocfilehash: da1029b6298d85aab8a80af1c52b152e040fbd80
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684413"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="14932-103">Expansor de configuración de servidor para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="14932-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="14932-104">Para editar las propiedades de este equipo, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="14932-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="14932-105">Edite el **nombre de dominio completo (FQDN)** de este equipo.</span><span class="sxs-lookup"><span data-stu-id="14932-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="14932-106">Esta entrada debe coincidir con el nombre del equipo tal como está definido en el sistema de nombres de dominio (DNS) y en los nombres alternativos de asunto (SAN) o el nombre de sujeto (SN) del certificado asociado con este equipo.</span><span class="sxs-lookup"><span data-stu-id="14932-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="14932-107">Seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="14932-107">You select one of the following:</span></span>
    
    <span data-ttu-id="14932-108">**Usar todas las direcciones IP configuradas**: Seleccione esta para usar todas las direcciones IP configuradas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="14932-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="14932-109">Si el equipo tiene varias direcciones IP, debe tener en cuenta que los servicios asociados con este equipo usarán todas las direcciones IP para todos los servicios.</span><span class="sxs-lookup"><span data-stu-id="14932-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="14932-110">Si un servidor o servicio de escucha espera la comunicación de una dirección IP y un puerto específicos, es posible que el servicio no haga la mejor selección de la dirección IP en la que escuchar.</span><span class="sxs-lookup"><span data-stu-id="14932-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="14932-111">**Limitar el uso del servicio a las direcciones IP seleccionadas**: Seleccione esta opción si desea definir direcciones IP específicas para la **dirección IP principal** en la que este equipo escuchará la comunicación de otros equipos y grupos en la implementación.</span><span class="sxs-lookup"><span data-stu-id="14932-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="14932-112">Defina la **dirección IP de RTC** para la dirección IP específica en la que el equipo y el servicio escucharán las comunicaciones y enviarán las comunicaciones a la puerta de enlace o IP-PBX definida.</span><span class="sxs-lookup"><span data-stu-id="14932-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

