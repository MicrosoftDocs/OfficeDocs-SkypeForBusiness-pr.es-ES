---
title: Compatibilidad con varios troncos en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La funcionalidad de Skype Empresarial Server admite varias asociaciones entre puertas de enlace y servidores de mediación. Estas asociaciones se realizan definiendo un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una puerta de enlace de red telefónica conmutada (RTC), un controlador de borde de sesión (SBC) o una IP-PBX. Use el Generador de topologías para asociar puertas de enlace con servidores de mediación (es decir, troncos).
ms.openlocfilehash: 0f4c8d2ee16c900ef666c12230964a9abb8f5a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826230"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="fed64-105">Compatibilidad con varios troncos en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="fed64-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="fed64-106">La funcionalidad de Skype Empresarial Server admite varias asociaciones entre puertas de enlace y servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="fed64-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="fed64-107">Estas asociaciones se realizan definiendo un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una puerta de enlace de red telefónica conmutada (RTC), un controlador de borde de sesión (SBC) o una IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="fed64-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="fed64-108">Use el Generador de topologías para asociar puertas de enlace con servidores de mediación (es decir, troncos).</span><span class="sxs-lookup"><span data-stu-id="fed64-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="fed64-109">Para asignar o quitar un tronco en Skype Empresarial Server, primero debe definir un tronco en topology Builder.</span><span class="sxs-lookup"><span data-stu-id="fed64-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="fed64-110">Un tronco consta de la siguiente asociación: nombre de dominio completo (FQDN) del servidor de mediación, puerto de escucha del servidor de mediación, FQDN de puerta de enlace y puerto de escucha de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="fed64-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="fed64-111">Para configurar varios troncos, puede crear varias asociaciones entre la misma puerta de enlace y el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="fed64-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="fed64-112">Esto proporciona resistencia adicional a la infraestructura Telefonía IP empresarial, que es especialmente útil en escenarios interoperacionales de central de conmutación (PBX).</span><span class="sxs-lookup"><span data-stu-id="fed64-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="fed64-113">Cuando se define un tronco, debe estar asociado con una ruta.</span><span class="sxs-lookup"><span data-stu-id="fed64-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="fed64-114">Para asociar un tronco a una ruta, debe definir un nombre simple para el tronco en topology Builder.</span><span class="sxs-lookup"><span data-stu-id="fed64-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="fed64-115">Este nombre simple se usa como nombre de tronco en el Panel de control de Skype Empresarial Server, donde los troncos se pueden asociar con rutas.</span><span class="sxs-lookup"><span data-stu-id="fed64-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="fed64-116">El nombre de tronco simple se usa como el nombre de puerta de enlace del Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="fed64-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="fed64-117">El administrador debe seleccionar un tronco predeterminado asociado a un servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="fed64-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="fed64-118">En el Generador de topologías, haga clic con el botón secundario en el servidor de mediación asociado y, a continuación, haga clic en **Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="fed64-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="fed64-119">Especifique la puerta de enlace predeterminada para el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="fed64-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="fed64-120">El siguiente diagrama ilustra los múltiples troncos que se definen para cada servidor de mediación y puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="fed64-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![Asignaciones de varios troncos](../../media/multiple-trunk-assignments.jpg)
