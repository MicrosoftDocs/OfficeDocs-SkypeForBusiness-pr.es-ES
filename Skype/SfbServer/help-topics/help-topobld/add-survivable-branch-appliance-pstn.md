---
title: Agregar RTC de aplicación de sucursal con funciones de supervivencia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Para definir la puerta de enlace de telefónica conmutada (RTC) para una aplicación de sucursal con funciones de supervivencia en un sitio de sucursal, especifique lo siguiente:'
ms.openlocfilehash: df05edb2ee682336cf46fd2fa8a6b7a7b4736696
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888818"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="92a95-103">Agregar RTC de aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="92a95-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="92a95-104">Para definir la puerta de enlace de telefónica conmutada (RTC) para una aplicación de sucursal con funciones de supervivencia en un sitio de sucursal, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="92a95-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="92a95-105">Un nombre de dominio completo (FQDN) o la dirección IP para el mismo nivel de puerta de enlace que la aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia está asociado con para el enrutamiento de entrada y salida llamadas RTC.</span><span class="sxs-lookup"><span data-stu-id="92a95-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="92a95-106">Si está definiendo una aplicación de sucursal con funciones de supervivencia, esta es la puerta de enlace al que se conectará el servidor de mediación dentro de la aplicación de sucursal con funciones de supervivencia para la conectividad de RTC.</span><span class="sxs-lookup"><span data-stu-id="92a95-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="92a95-p101">El puerto de escucha que debe usarse para los mensajes del Protocolo de inicio de sesión (SIP). De forma predeterminada, los puertos son 5066 para el protocolo de control de transmisión (TCP) y 5067 para seguridad de la capa de transporte (TLS) en una puerta de enlace, central de conmutación (PBX) o controlador del borde de sesión (SBC). En una aplicación de sucursal con funciones de supervivencia de una sucursal, los puertos predeterminados son 5081 para TCP y 5082 para Seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="92a95-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="92a95-110">Por motivos de seguridad, se recomienda encarecidamente usar TLS.</span><span class="sxs-lookup"><span data-stu-id="92a95-110">For security reasons, we strongly recommend that you use TLS.</span></span> <span data-ttu-id="92a95-111">Si está definiendo una aplicación de sucursal con funciones de supervivencia, consulte la documentación del proveedor de aplicación de sucursal con funciones de supervivencia para comprobar que la aplicación de sucursal con funciones de supervivencia admite el protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="92a95-111">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="92a95-112">Por motivos de seguridad, se recomienda encarecidamente implementar una puerta de enlace que pueda usar TLS.</span><span class="sxs-lookup"><span data-stu-id="92a95-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="92a95-113">Si desea agregar una puerta de enlace de RTC, puede configurarla posteriormente; sin embargo, no estará plenamente operativa hasta que se haya definido y configurado la puerta de enlace de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="92a95-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

