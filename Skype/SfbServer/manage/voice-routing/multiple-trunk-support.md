---
title: Compatibilidad con varios troncales en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La funcionalidad de Skype empresarial Server admite varias asociaciones entre puertas de enlace y servidores de mediación. Estas asociaciones se realizan mediante la definición de un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una puerta de enlace de red de telefonía pública conmutada (RTC), controlador de borde de sesión (SBC) o IP-PBX. Use el generador de topología para asociar puertas de enlace con servidores de mediación (es decir, troncos).
ms.openlocfilehash: 6f950f089d23687f0215bd9db1f253eb57c17c75
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816950"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="bdbd5-105">Compatibilidad con varios troncales en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="bdbd5-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="bdbd5-106">La funcionalidad de Skype empresarial Server admite varias asociaciones entre puertas de enlace y servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="bdbd5-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="bdbd5-107">Estas asociaciones se realizan mediante la definición de un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una puerta de enlace de red de telefonía pública conmutada (RTC), controlador de borde de sesión (SBC) o IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="bdbd5-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="bdbd5-108">Use el generador de topología para asociar puertas de enlace con servidores de mediación (es decir, troncos).</span><span class="sxs-lookup"><span data-stu-id="bdbd5-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="bdbd5-109">Para asignar o quitar un tronco en Skype empresarial Server, primero debe definir un tronco en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="bdbd5-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="bdbd5-110">Un tronco consiste en la siguiente Asociación: nombre de dominio completo (FQDN) de Media Server, el puerto de escucha del servidor de mediación, el FQDN de la puerta de enlace y el puerto de escucha de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="bdbd5-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="bdbd5-111">Para configurar varios troncos, puede crear varias asociaciones entre la misma puerta de enlace y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="bdbd5-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="bdbd5-112">Esto proporciona resistencia adicional a la infraestructura de telefonía IP empresarial, que es especialmente útil en escenarios de interoperabilidad de la intercambiación privada (PBX).</span><span class="sxs-lookup"><span data-stu-id="bdbd5-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="bdbd5-113">Cuando se define un tronco, debe estar asociado con una ruta.</span><span class="sxs-lookup"><span data-stu-id="bdbd5-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="bdbd5-114">Para asociar un tronco a una ruta, defina un nombre simple para el tronco en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="bdbd5-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="bdbd5-115">Este nombre simple se usa como el nombre del tronco en el panel de control de Skype empresarial Server, donde se pueden asociar los troncos con las rutas.</span><span class="sxs-lookup"><span data-stu-id="bdbd5-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="bdbd5-116">El nombre de tronco simple se usa como el nombre de la puerta de enlace desde el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bdbd5-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="bdbd5-117">El administrador debe seleccionar un tronco predeterminado asociado a un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="bdbd5-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="bdbd5-118">En el generador de topología, haga clic con el botón secundario en el servidor de mediación asociado y luego haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bdbd5-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="bdbd5-119">Especificar la puerta de enlace predeterminada para el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="bdbd5-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="bdbd5-120">En el siguiente diagrama se muestran los diversos troncos que se definen para cada servidor de mediación y puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="bdbd5-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![Varias asignaciones de tronco](../../media/multiple-trunk-assignments.jpg)
