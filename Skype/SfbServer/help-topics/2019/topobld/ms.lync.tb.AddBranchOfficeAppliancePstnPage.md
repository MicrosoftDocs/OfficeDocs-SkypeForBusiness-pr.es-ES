---
title: Agregar RTC de aplicación de sucursal con funciones de supervivencia
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para definir la puerta de enlace de la red telefónica conmutada (RTC) de una aplicación de sucursal con funciones de supervivencia en una sucursal, especifique los elementos siguientes:'
ms.openlocfilehash: 30b5922e3d18b4dfe57bef23ddb0f00a25df7f9f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811950"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="85f0c-103">Agregar RTC de aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="85f0c-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="85f0c-104">Para definir la puerta de enlace de la red telefónica conmutada (RTC) de una aplicación de sucursal con funciones de supervivencia en una sucursal, especifique los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="85f0c-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="85f0c-105">Un nombre de dominio completo o una dirección IP para la puerta de enlace del mismo nivel con el que esté asociado la aplicación o el servidor de sucursal con funciones de supervivencia para llamadas de red telefónica conmutada (RTC) de enrutamiento de entrada y de salida.</span><span class="sxs-lookup"><span data-stu-id="85f0c-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="85f0c-106">Si está definiendo una aplicación de sucursal con funciones de supervivencia, esta es la puerta de enlace a la que se conectará el servidor de mediación de dicha aplicación para conectividad de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="85f0c-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="85f0c-p101">El puerto de escucha que debe usarse para los mensajes del Protocolo de inicio de sesión (SIP). De forma predeterminada, los puertos son 5066 para el protocolo de control de transmisión (TCP) y 5067 para seguridad de la capa de transporte (TLS) en una puerta de enlace, central de conmutación (PBX) o controlador del borde de sesión (SBC). En una aplicación de sucursal con funciones de supervivencia de una sucursal, los puertos predeterminados son 5081 para TCP y 5082 para Seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="85f0c-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="85f0c-p102">Por motivos de seguridad, se recomienda usar Seguridad de la capa de transporte (TLS). Si está definiendo una aplicación de sucursal con funciones de supervivencia, consulte la documentación del proveedor para verificar que dicha aplicación admita el protocolo de Seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="85f0c-p102">For security reasons, we strongly recommend that you use TLS. If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="85f0c-112">Por motivos de seguridad, se recomienda encarecidamente implementar una puerta de enlace que pueda usar TLS.</span><span class="sxs-lookup"><span data-stu-id="85f0c-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="85f0c-113">Si desea agregar una puerta de enlace de RTC, puede configurarla posteriormente; sin embargo, no estará plenamente operativa hasta que se haya definido y configurado la puerta de enlace de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="85f0c-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

