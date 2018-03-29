---
title: Agregar RTC de aplicación de sucursal con funciones de supervivencia
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
description: 'Para definir la puerta de enlace de telefónica pública conmutada (PSTN) de red de un dispositivo de la rama que sobreviven en un sitio de sucursal, especifique lo siguiente:'
ms.openlocfilehash: cefdc46eb2f5b7573e5e5bd9acb93cb5ab384622
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="47f6b-103">Agregar RTC de aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="47f6b-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="47f6b-104">Para definir la puerta de enlace de telefónica pública conmutada (PSTN) de red de un dispositivo de la rama que sobreviven en un sitio de sucursal, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="47f6b-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="47f6b-105">Un nombre de dominio completo (FQDN) o dirección IP para el interlocutor de puerta de enlace que el dispositivo de sucursal que sobreviven o el servidor de sucursal que sobreviven está asociado para el enrutamiento entrante y saliente se llama PSTN.</span><span class="sxs-lookup"><span data-stu-id="47f6b-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="47f6b-106">Si va a definir un dispositivo de la rama que sobreviven, ésta es la puerta de enlace al que se conectará el servidor de mediación ubicado dentro del dispositivo de la rama que sobreviven para conectividad PSTN.</span><span class="sxs-lookup"><span data-stu-id="47f6b-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="47f6b-p101">El puerto de escucha que debe usarse para los mensajes del Protocolo de inicio de sesión (SIP). De forma predeterminada, los puertos son 5066 para el protocolo de control de transmisión (TCP) y 5067 para seguridad de la capa de transporte (TLS) en una puerta de enlace, central de conmutación (PBX) o controlador del borde de sesión (SBC). En una aplicación de sucursal con funciones de supervivencia de una sucursal, los puertos predeterminados son 5081 para TCP y 5082 para Seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="47f6b-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="47f6b-110">Por motivos de seguridad, se recomienda encarecidamente usar TLS.</span><span class="sxs-lookup"><span data-stu-id="47f6b-110">For security reasons, we strongly recommend that you use TLS.</span></span> <span data-ttu-id="47f6b-111">Si va a definir un dispositivo de la rama que sobreviven, consulte la documentación del proveedor de dispositivo de sucursal que sobreviven para comprobar que el dispositivo de la rama que sobreviven admite el protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="47f6b-111">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="47f6b-112">Por motivos de seguridad, se recomienda encarecidamente implementar una puerta de enlace que pueda usar TLS.</span><span class="sxs-lookup"><span data-stu-id="47f6b-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="47f6b-113">Si desea agregar una puerta de enlace de RTC, puede configurarla posteriormente; sin embargo, no estará plenamente operativa hasta que se haya definido y configurado la puerta de enlace de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="47f6b-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

