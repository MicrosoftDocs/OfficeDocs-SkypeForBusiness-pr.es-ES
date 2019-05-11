---
title: Plan para las implementaciones de servidor perimetral de Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Resumen: Planear su Skype para el entorno empresarial servidor perimetral. En este tema se presenta a los conceptos de borde y le permite organizarse con nuestros temas más detallados.'
ms.openlocfilehash: 4c4348d0d3aa56aa82b8ea8930176d9d135a64f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885078"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="29283-104">Plan para las implementaciones de servidor perimetral de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="29283-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="29283-105">**Resumen:** Plan para su Skype para el entorno empresarial servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="29283-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="29283-106">En este tema se presenta a los conceptos de borde y le permite organizarse con nuestros temas más detallados.</span><span class="sxs-lookup"><span data-stu-id="29283-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="29283-107">Cuando haya un Skype para el entorno de servidor empresarial que funciona bien internamente, podría ser el siguiente paso para presentan un servidor perimetral o un grupo de servidores perimetrales para el entorno.</span><span class="sxs-lookup"><span data-stu-id="29283-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="29283-108">Esta función sería vital si desea que los servicios proporcionados por Skype para Business Server se pueden utilizar aquellas personas que están fuera de la red interna.</span><span class="sxs-lookup"><span data-stu-id="29283-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="29283-109">Estos pueden incluir potencialmente:</span><span class="sxs-lookup"><span data-stu-id="29283-109">These can potentially include:</span></span>
  
- <span data-ttu-id="29283-110">Usuarios remotos: empleados que están fuera del sitio, ya sea de forma temporal o continua.</span><span class="sxs-lookup"><span data-stu-id="29283-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="29283-111">Los usuarios federados: Los empleados las organizaciones del socio.</span><span class="sxs-lookup"><span data-stu-id="29283-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="29283-112">Usuarios móviles.</span><span class="sxs-lookup"><span data-stu-id="29283-112">Mobile Users.</span></span>
    
- <span data-ttu-id="29283-113">Clientes potenciales, asociados e incluso usuarios anónimos que desea invitar a reuniones y presentaciones.</span><span class="sxs-lookup"><span data-stu-id="29283-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="29283-114">Acceso de usuarios externos, que es lo que proporcionan los servidores perimetrales, permitir que todos los que esto ocurra.</span><span class="sxs-lookup"><span data-stu-id="29283-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="29283-115">Los usuarios internos podrán disfrutar de los siguientes servicios hospedados por su Skype para la implementación de Business Server:</span><span class="sxs-lookup"><span data-stu-id="29283-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="29283-116">Mensajería instantánea y presencia para la comunicación: los usuarios externos autorizados pueden participar en conversaciones y conferencias de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="29283-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="29283-117">Pueden obtener información de presencia de otros usuarios (que también obtienen su información de presencia).</span><span class="sxs-lookup"><span data-stu-id="29283-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="29283-118">No podrá realizar conferencias con varios participantes si está usando un proveedor de mensajería instantánea público, que es la comunicación de manera estricta de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="29283-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="29283-119">Pero se admiten los protocolos SIP y XMPP.</span><span class="sxs-lookup"><span data-stu-id="29283-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="29283-120">Audio y vídeo (A / V) conferencia: los usuarios externos autorizados pueden participar en su Skype para las conferencias de audio y vídeos de Business Server.</span><span class="sxs-lookup"><span data-stu-id="29283-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="29283-121">Conferencias Web: los usuarios externos autorizados pueden participar en su Skype para conferencias de empresa.</span><span class="sxs-lookup"><span data-stu-id="29283-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="29283-122">También puede habilitar la participación de los usuarios remotos, usuarios federados y usuarios anónimos si así lo desea.</span><span class="sxs-lookup"><span data-stu-id="29283-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="29283-123">Los usuarios de mensajería instantánea pública no pueden participar en conferencias.</span><span class="sxs-lookup"><span data-stu-id="29283-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="29283-124">También hay opciones para permitir que estos usuarios participen en el uso compartido de aplicaciones y escritorio, e incluso actuar como organizadores o moderadores de reuniones.</span><span class="sxs-lookup"><span data-stu-id="29283-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="29283-125">Se admite el acceso a dispositivos móviles, como Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="29283-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="29283-126">Puede invitar a usuarios externos a esas reuniones que quiere que asistan, incluso a los usuarios anónimos, si desea concederles permisos.</span><span class="sxs-lookup"><span data-stu-id="29283-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="29283-p108">Si esto le parece algo que necesita su organización, entonces planificar un entorno perimetral va a ser de gran ayuda al implementarlo. Para más información, hay los temas enumerados a continuación.</span><span class="sxs-lookup"><span data-stu-id="29283-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="29283-129">Las puertas de enlace XMPP y los servidores proxy están disponibles en Skype para Business Server 2015, pero ya no se admiten en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="29283-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="29283-130">Para obtener más información, vea [la federación XMPP migrar](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="29283-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="29283-131">Temas de planeamiento:</span><span class="sxs-lookup"><span data-stu-id="29283-131">Planning topics:</span></span>

<span data-ttu-id="29283-132">Los artículos de planeamiento son:</span><span class="sxs-lookup"><span data-stu-id="29283-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="29283-133">Requisitos del sistema del servidor perimetral en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="29283-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="29283-134">Requisitos del entorno del servidor perimetral en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="29283-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="29283-135">Escenarios del servidor perimetral en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="29283-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

