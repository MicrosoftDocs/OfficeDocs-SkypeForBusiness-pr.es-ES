---
title: Configurar troncos en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Resumen: obtenga información sobre cómo configurar un tronco entre un servidor de mediación y los sistemas del mismo nivel Telefonía IP empresarial en Skype Empresarial Server.'
ms.openlocfilehash: f2e9f3a5e9fa9d89ef9db63aa82b6a3ce3a86c6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824960"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="75de0-103">Configurar troncos en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="75de0-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="75de0-104">**Resumen:** Learn how to configure a trunk between a Mediation Server and peers for Telefonía IP empresarial in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="75de0-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="75de0-105">Como parte de la implementación de Telefonía IP empresarial, puede configurar un tronco entre un servidor de mediación y uno o varios de los siguientes sistemas del mismo nivel para proporcionar conectividad de red telefónica conmutada (RTC) para los clientes y dispositivos de Telefonía IP empresarial de su organización:</span><span class="sxs-lookup"><span data-stu-id="75de0-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="75de0-106">Conexión basada en troncos SIP para un proveedor de servicio s de telefonía</span><span class="sxs-lookup"><span data-stu-id="75de0-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="75de0-107">Puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="75de0-107">PSTN gateway</span></span>
    
- <span data-ttu-id="75de0-108">Central de conmutación (PBX)</span><span class="sxs-lookup"><span data-stu-id="75de0-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="75de0-109">Para obtener más información, consulte [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="75de0-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="75de0-110">La funcionalidad de Skype Empresarial Server admite varias asociaciones entre puertas de enlace y servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="75de0-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="75de0-111">Estas asociaciones se realizan definiendo un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una puerta de enlace de red telefónica conmutada (RTC), un controlador de borde de sesión (SBC) o una IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="75de0-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="75de0-112">Use el Generador de topologías para asociar puertas de enlace con servidores de mediación (es decir, troncos).</span><span class="sxs-lookup"><span data-stu-id="75de0-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="75de0-113">Para asignar o quitar un tronco en Skype Empresarial Server, primero debe definir un tronco en topology Builder.</span><span class="sxs-lookup"><span data-stu-id="75de0-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="75de0-114">Un tronco consta de la siguiente asociación: nombre de dominio completo (FQDN) del servidor de mediación, puerto de escucha del servidor de mediación, FQDN de puerta de enlace y puerto de escucha de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="75de0-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="75de0-115">Para configurar varios troncos, puede crear varias asociaciones entre la misma puerta de enlace y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="75de0-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="75de0-116">Esto proporciona resistencia adicional a la infraestructura Telefonía IP empresarial, que es especialmente útil en escenarios interoperacionales de central de conmutación (PBX).</span><span class="sxs-lookup"><span data-stu-id="75de0-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="75de0-117">Cuando se define un tronco, debe estar asociado con una ruta.</span><span class="sxs-lookup"><span data-stu-id="75de0-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="75de0-118">Para asociar un tronco a una ruta, debe definir un nombre simple para el tronco en topology Builder.</span><span class="sxs-lookup"><span data-stu-id="75de0-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="75de0-119">Este nombre simple se usa como nombre de tronco en el Panel de control de Skype Empresarial Server, donde los troncos se pueden asociar con rutas.</span><span class="sxs-lookup"><span data-stu-id="75de0-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="75de0-120">El nombre de tronco simple se usa como el nombre de puerta de enlace del Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="75de0-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="75de0-121">El administrador debe seleccionar un tronco predeterminado asociado a un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="75de0-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="75de0-122">En el Generador de topologías, haga clic con el botón secundario en el servidor de mediación asociado y, a continuación, haga clic en **Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="75de0-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="75de0-123">Especifique la puerta de enlace predeterminada para el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="75de0-123">Specify the default gateway for the Mediation Server.</span></span> 
  

