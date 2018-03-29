---
title: Ampliador de configuración de servidor de Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Para editar las propiedades de este equipo, siga este procedimiento:'
ms.openlocfilehash: 0e5e595382bb92621c1551158edecf736ff0aa6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="287b0-103">Ampliador de configuración de servidor de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="287b0-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="287b0-104">Para editar las propiedades de este equipo, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="287b0-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="287b0-105">Editar el **nombre de dominio (completo FQDN) completo** para este equipo.</span><span class="sxs-lookup"><span data-stu-id="287b0-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="287b0-106">Esta entrada debe coincidir con el nombre del equipo tal como se define en el sistema de nombres de dominio (DNS) y en nombres alternativos de asunto (SAN) o nombre (SN) del sujeto del certificado asociado con este equipo.</span><span class="sxs-lookup"><span data-stu-id="287b0-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="287b0-107">Seleccione uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="287b0-107">You select one of the following:</span></span>
    
    <span data-ttu-id="287b0-108">**Utilice todas las direcciones IP**: seleccione esta opción para utilizar todas las direcciones IP en el equipo.</span><span class="sxs-lookup"><span data-stu-id="287b0-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="287b0-109">Si el equipo tiene varias direcciones IP, debe tener en cuenta que los servicios asociados a este equipo utilizará todas las direcciones IP para todos los servicios.</span><span class="sxs-lookup"><span data-stu-id="287b0-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="287b0-110">Si un servidor escucha o servicio está esperando la comunicación de un puerto y una dirección IP específica, el servicio no tiene la mejor selección de la dirección IP para escuchar.</span><span class="sxs-lookup"><span data-stu-id="287b0-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="287b0-111">**Uso del servicio de límite a las direcciones IP seleccionadas**: seleccione esta opción si desea definir direcciones IP específicas para la **dirección IP principal** en el que escucha en este equipo para la comunicación de otros equipos y grupos en la implementación.</span><span class="sxs-lookup"><span data-stu-id="287b0-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="287b0-112">Definir la **dirección IP de RTC** para la dirección IP específica que el equipo y el servicio escuchará comunicaciones y enviar comunicaciones a la puerta de enlace PSTN o PBX-IP definido.</span><span class="sxs-lookup"><span data-stu-id="287b0-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

