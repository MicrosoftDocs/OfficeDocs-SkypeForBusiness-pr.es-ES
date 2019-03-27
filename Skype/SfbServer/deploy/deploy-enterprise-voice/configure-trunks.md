---
title: Configuración de troncos en Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Resumen: Obtenga información sobre cómo configurar un tronco entre un servidor de mediación y a los compañeros para Enterprise Voice en Skype para Business Server.'
ms.openlocfilehash: c47d1ff06fe695be939758c8444dac246c555de9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892860"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="4fb35-103">Configuración de troncos en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="4fb35-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="4fb35-104">**Resumen:** Obtenga información sobre cómo configurar un tronco entre un servidor de mediación y a los compañeros para Enterprise Voice en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="4fb35-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="4fb35-105">Como parte de la implementación de Enterprise Voice, puede configurar un tronco entre un servidor de mediación y uno o varios de los siguientes elementos del mismo nivel para proporcionar conectividad de telefónica conmutada (RTC) de la red de clientes de Enterprise Voice y dispositivos en su organización:</span><span class="sxs-lookup"><span data-stu-id="4fb35-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="4fb35-106">Conexión basada en troncos SIP para un proveedor de servicio s de telefonía</span><span class="sxs-lookup"><span data-stu-id="4fb35-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="4fb35-107">Puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="4fb35-107">PSTN gateway</span></span>
    
- <span data-ttu-id="4fb35-108">Central de conmutación (PBX)</span><span class="sxs-lookup"><span data-stu-id="4fb35-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="4fb35-109">Para obtener más información, consulte [Plan para la conectividad de RTC en Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="4fb35-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="4fb35-110">Skype para la funcionalidad de Business Server admite varias asociaciones entre los servidores de mediación y puertas de enlace.</span><span class="sxs-lookup"><span data-stu-id="4fb35-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="4fb35-111">Estas asociaciones se realizan mediante la definición de un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una telefónica conmutada (RTC) de red puerta de enlace, controlador de borde de sesión (SBC) o IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="4fb35-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="4fb35-112">Use el generador de topología para asociar las puertas de enlace con los servidores de mediación (es decir, troncos).</span><span class="sxs-lookup"><span data-stu-id="4fb35-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="4fb35-113">Para asignar o quitar un tronco en Skype para Business Server, primero debe definir un tronco en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="4fb35-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="4fb35-114">Un tronco consta de la asociación siguiente: el servidor de mediación completo (FQDN) del nombre de dominio, el puerto de escucha del servidor de mediación, el FQDN de puerta de enlace y el puerto de escucha de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="4fb35-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="4fb35-115">Para configurar varios troncos, puede crear varias asociaciones entre la misma puerta de enlace y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="4fb35-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="4fb35-116">Esto proporciona resistencia adicional a la infraestructura de telefonía IP empresarial, que es especialmente útil en escenarios de interoperational de central de conmutación (PBX) de exchange.</span><span class="sxs-lookup"><span data-stu-id="4fb35-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="4fb35-117">Cuando se define un tronco, debe estar asociado con una ruta.</span><span class="sxs-lookup"><span data-stu-id="4fb35-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="4fb35-118">Para asociar un tronco a una ruta, defina un nombre sencillo para el tronco en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="4fb35-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="4fb35-119">Este nombre simple se utiliza como el nombre del tronco en el Skype para el Panel de Control de servidor empresarial, donde se pueden asociadas con rutas de troncos.</span><span class="sxs-lookup"><span data-stu-id="4fb35-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="4fb35-120">El nombre del tronco simple se utiliza como el nombre de la puerta de enlace de la Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="4fb35-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="4fb35-121">El administrador debe seleccionar un tronco predeterminado asociado con un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="4fb35-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="4fb35-122">En el generador de topología, haga clic en el servidor de mediación asociado y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4fb35-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="4fb35-123">Especifique la puerta de enlace predeterminada para el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="4fb35-123">Specify the default gateway for the Mediation Server.</span></span> 
  

