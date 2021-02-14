---
title: Expansor de configuración de servidor para Lync Server 2010
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
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Para editar las propiedades de este equipo, realice lo siguiente:'
ms.openlocfilehash: 8b05fa82bcfeb10caa201ce303ddbbd8e8378b7e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806660"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="8665e-103">Expansor de configuración de servidor para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8665e-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="8665e-104">Para editar las propiedades de este equipo, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8665e-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="8665e-p101">Edite el **Nombre de dominio completo (FQDN)** de este equipo. Este nombre debe coincidir con el nombre del equipo definido en el sistema de nombres de dominio (DNS) y en nombres alternativos de sujeto (SAN) o nombres de sujeto (SN) del certificado asociado con el equipo.</span><span class="sxs-lookup"><span data-stu-id="8665e-p101">Edit the **Fully qualified domain name (FQDN)** for this computer. This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="8665e-107">Seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="8665e-107">You select one of the following:</span></span>
    
    <span data-ttu-id="8665e-108">**Usar todas las direcciones IP configuradas**: seleccione esta opción para usar todas las direcciones IP configuradas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="8665e-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8665e-p102">Si el equipo tiene varias direcciones IP, debe ser consciente de que los servicios asociados con el equipo utilizarán todas las direcciones IP para todos los servicios. Si un servidor o servicio de escucha está a la espera de comunicación con una dirección IP o puerto específico, es posible que el servicio no elija la mejor dirección IP desde la que realizar la escucha.</span><span class="sxs-lookup"><span data-stu-id="8665e-p102">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services. If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="8665e-p103">**Limitar el uso del servicio a las direcciones IP seleccionadas**: seleccione esta opción si desea definir direcciones IP específicas para la **Dirección IP principal** a la que escuchará este equipo para comunicaciones desde otros equipos y grupos servidores en la implementación. Defina la **Dirección IP de RTC** para la dirección IP específica a la que escucharán el equipo y el servicio para comunicarse y enviar comunicaciones a la puerta de enlace RTC definida o IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="8665e-p103">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment. Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

