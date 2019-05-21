---
title: Configurar troncos en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Resumen: Aprenda a configurar un tronco entre un servidor de mediación y los homólogos de telefonía IP empresarial en Skype empresarial Server.'
ms.openlocfilehash: 5e5fc044e5217ef4661e716ba02ba286c7a631f8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289100"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="7452e-103">Configurar troncos en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="7452e-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="7452e-104">**Resumen:** Obtenga información sobre cómo configurar un tronco entre un servidor de mediación y los interlocutores de telefonía IP empresarial en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7452e-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="7452e-105">Como parte de la implementación de telefonía IP empresarial, puede configurar un tronco entre un servidor de mediación y uno o más de los siguientes elementos para proporcionar conectividad de red telefónica conmutada (RTC) pública para los clientes y dispositivos de voz de su organización:</span><span class="sxs-lookup"><span data-stu-id="7452e-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="7452e-106">Conexión basada en troncos SIP para un proveedor de servicio s de telefonía</span><span class="sxs-lookup"><span data-stu-id="7452e-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="7452e-107">Puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="7452e-107">PSTN gateway</span></span>
    
- <span data-ttu-id="7452e-108">Central de conmutación (PBX)</span><span class="sxs-lookup"><span data-stu-id="7452e-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="7452e-109">Para obtener más información, consulte [planear la conectividad RTC en Skype empresarial Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="7452e-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="7452e-110">La funcionalidad de Skype empresarial Server admite varias asociaciones entre puertas de enlace y servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="7452e-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="7452e-111">Estas asociaciones se realizan mediante la definición de un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una puerta de enlace de red de telefonía pública conmutada (RTC), controlador de borde de sesión (SBC) o IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="7452e-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="7452e-112">Use el generador de topología para asociar puertas de enlace con servidores de mediación (es decir, troncos).</span><span class="sxs-lookup"><span data-stu-id="7452e-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="7452e-113">Para asignar o quitar un tronco en Skype empresarial Server, primero debe definir un tronco en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="7452e-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="7452e-114">Un tronco consiste en la siguiente Asociación: nombre de dominio completo (FQDN) de Media Server, el puerto de escucha del servidor de mediación, el FQDN de la puerta de enlace y el puerto de escucha de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="7452e-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="7452e-115">Para configurar varios troncos, puede crear varias asociaciones entre la misma puerta de enlace y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="7452e-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="7452e-116">Esto proporciona resistencia adicional a la infraestructura de telefonía IP empresarial, que es especialmente útil en escenarios de interoperabilidad de la intercambiación privada (PBX).</span><span class="sxs-lookup"><span data-stu-id="7452e-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="7452e-117">Cuando se define un tronco, debe estar asociado con una ruta.</span><span class="sxs-lookup"><span data-stu-id="7452e-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="7452e-118">Para asociar un tronco a una ruta, defina un nombre simple para el tronco en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="7452e-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="7452e-119">Este nombre simple se usa como el nombre del tronco en el panel de control de Skype empresarial Server, donde se pueden asociar los troncos con las rutas.</span><span class="sxs-lookup"><span data-stu-id="7452e-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="7452e-120">El nombre de tronco simple se usa como el nombre de la puerta de enlace desde el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7452e-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="7452e-121">El administrador debe seleccionar un tronco predeterminado asociado a un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="7452e-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="7452e-122">En el generador de topología, haga clic con el botón secundario en el servidor de mediación asociado y luego haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7452e-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="7452e-123">Especificar la puerta de enlace predeterminada para el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="7452e-123">Specify the default gateway for the Mediation Server.</span></span> 
  

