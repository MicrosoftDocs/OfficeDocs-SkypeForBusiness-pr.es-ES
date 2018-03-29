---
title: Configurar troncos en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Resumen: Conozca cómo configurar un enlace entre un servidor de mediación y compañeros para Telefonía IP empresarial en Skype para Business Server 2015.'
ms.openlocfilehash: a2630d3e37e6ab15a0e88593549e9365ac69a3e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-trunks-in-skype-for-business-server-2015"></a><span data-ttu-id="619ee-103">Configurar troncos en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="619ee-103">Configure trunks in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="619ee-104">**Resumen:** Obtenga información sobre cómo configurar un enlace entre un servidor de mediación y compañeros para Telefonía IP empresarial en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="619ee-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="619ee-105">Como parte de la implementación de Telefonía IP empresarial, puede configurar un enlace entre un servidor de mediación y uno o más de los siguientes pares para proporcionar conectividad de telefónica pública conmutada (PSTN) de red para clientes de Telefonía IP empresarial y dispositivos de su organización:</span><span class="sxs-lookup"><span data-stu-id="619ee-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="619ee-106">Conexión basada en troncos SIP para un proveedor de servicio s de telefonía</span><span class="sxs-lookup"><span data-stu-id="619ee-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="619ee-107">Puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="619ee-107">PSTN gateway</span></span>
    
- <span data-ttu-id="619ee-108">Central de conmutación (PBX)</span><span class="sxs-lookup"><span data-stu-id="619ee-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="619ee-109">Para obtener más detalles, consulte [Plan de conectividad PSTN en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="619ee-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="619ee-110">Skype para la funcionalidad de Business Server admite varias asociaciones entre los servidores de mediación y puertas de enlace.</span><span class="sxs-lookup"><span data-stu-id="619ee-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="619ee-111">Estas asociaciones se realizan mediante la definición de un tronco, que es una asociación lógica entre un grupo de servidores de mediación y telefónica pública conmutada (PSTN) de red puerta de enlace, controlador de borde de sesión (SBC) o IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="619ee-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="619ee-112">Utilice el generador de topología para asociar las puertas de enlace con los servidores de mediación (es decir, troncos).</span><span class="sxs-lookup"><span data-stu-id="619ee-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="619ee-113">Para asignar o quitar un tronco en Skype para Business Server, primero debe definir un tronco en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="619ee-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="619ee-114">Un tronco consiste en la asociación siguiente: servidor de mediación completo nombre de dominio (completo FQDN), el puerto de escucha del servidor de mediación, el FQDN de la puerta de enlace y el puerto de escucha de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="619ee-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="619ee-115">Para configurar varios troncos, puede crear varias asociaciones entre la misma puerta de enlace y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="619ee-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="619ee-116">Esto proporciona resistencia adicional a la infraestructura de Telefonía IP empresarial, que es especialmente útil en escenarios interoperables de private branch exchange (PBX).</span><span class="sxs-lookup"><span data-stu-id="619ee-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="619ee-117">Cuando se define un tronco, debe estar asociado con una ruta.</span><span class="sxs-lookup"><span data-stu-id="619ee-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="619ee-118">Para asociar un tronco a una ruta, define un nombre sencillo para el tronco en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="619ee-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="619ee-119">Este nombre simple se utiliza como el nombre de tronco en el Skype Business Server Panel de Control, donde los troncos pueden asociarse con rutas.</span><span class="sxs-lookup"><span data-stu-id="619ee-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="619ee-120">El nombre simple del tronco se utiliza como el nombre de puerta de enlace desde el Skype para el Shell de administración de servidor de empresa.</span><span class="sxs-lookup"><span data-stu-id="619ee-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="619ee-121">El administrador debe seleccionar un tronco predeterminado asociado con un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="619ee-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="619ee-122">En el generador de topología (ratón) en el servidor de mediación asociado y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="619ee-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="619ee-123">Especifique la puerta de enlace predeterminada para el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="619ee-123">Specify the default gateway for the Mediation Server.</span></span> 
  

