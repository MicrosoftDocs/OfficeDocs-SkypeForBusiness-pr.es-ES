---
title: Plan para las implementaciones de servidor perimetral de Skype para Business Server
ms.author: heidip
author: microsoftheidi
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
ms.openlocfilehash: f558a4a9623e54a38e134716afe9b95021f237dc
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886125"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="bdf6b-104">Plan para las implementaciones de servidor perimetral de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="bdf6b-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="bdf6b-105">**Resumen:** Plan para su Skype para el entorno empresarial servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="bdf6b-106">En este tema se presenta a los conceptos de borde y le permite organizarse con nuestros temas más detallados.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="bdf6b-107">Cuando haya un Skype para el entorno de servidor empresarial que funciona bien internamente, podría ser el siguiente paso para presentan un servidor perimetral o un grupo de servidores perimetrales para el entorno.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="bdf6b-108">Esta función sería vital si desea que los servicios proporcionados por Skype para Business Server se pueden utilizar aquellas personas que están fuera de la red interna.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="bdf6b-109">Estos pueden incluir potencialmente:</span><span class="sxs-lookup"><span data-stu-id="bdf6b-109">These can potentially include:</span></span>
  
- <span data-ttu-id="bdf6b-110">Usuarios remotos: empleados que están fuera del sitio, ya sea de forma temporal o continua.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="bdf6b-111">Los usuarios federados: Los empleados las organizaciones del socio.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="bdf6b-112">Usuarios móviles.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-112">Mobile Users.</span></span>
    
- <span data-ttu-id="bdf6b-113">Clientes potenciales, asociados e incluso usuarios anónimos que desea invitar a reuniones y presentaciones.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="bdf6b-114">Acceso de usuarios externos, que es lo que proporcionan los servidores perimetrales, permitir que todos los que esto ocurra.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="bdf6b-115">Los usuarios internos podrán disfrutar de los siguientes servicios hospedados por su Skype para la implementación de Business Server:</span><span class="sxs-lookup"><span data-stu-id="bdf6b-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="bdf6b-116">Mensajería instantánea y presencia para la comunicación: los usuarios externos autorizados pueden participar en conversaciones y conferencias de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="bdf6b-117">Pueden obtener información de presencia de otros usuarios (que también obtienen su información de presencia).</span><span class="sxs-lookup"><span data-stu-id="bdf6b-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="bdf6b-118">No podrá realizar conferencias con varios participantes si está usando un proveedor de mensajería instantánea público, que es la comunicación de manera estricta de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="bdf6b-119">Pero se admiten los protocolos SIP y XMPP.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="bdf6b-120">Audio y vídeo (A / V) conferencia: los usuarios externos autorizados pueden participar en su Skype para las conferencias de audio y vídeos de Business Server.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="bdf6b-121">Conferencias Web: los usuarios externos autorizados pueden participar en su Skype para conferencias de empresa.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="bdf6b-122">También puede habilitar la participación de los usuarios remotos, usuarios federados y usuarios anónimos si así lo desea.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="bdf6b-123">Los usuarios de mensajería instantánea pública no pueden participar en conferencias.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="bdf6b-124">También hay opciones para permitir que estos usuarios participen en el uso compartido de aplicaciones y escritorio, e incluso actuar como organizadores o moderadores de reuniones.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="bdf6b-125">Se admite el acceso a dispositivos móviles, como Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="bdf6b-126">Puede invitar a usuarios externos a esas reuniones que quiere que asistan, incluso a los usuarios anónimos, si desea concederles permisos.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="bdf6b-p108">Si esto le parece algo que necesita su organización, entonces planificar un entorno perimetral va a ser de gran ayuda al implementarlo. Para más información, hay los temas enumerados a continuación.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="bdf6b-129">Las puertas de enlace XMPP y los servidores proxy están disponibles en Skype para Business Server 2015, pero ya no se admiten en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bdf6b-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="bdf6b-130">Para obtener más información, vea [la federación XMPP migrar](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="bdf6b-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="bdf6b-131">Temas de planeamiento:</span><span class="sxs-lookup"><span data-stu-id="bdf6b-131">Planning topics:</span></span>

<span data-ttu-id="bdf6b-132">Los artículos de planeamiento son:</span><span class="sxs-lookup"><span data-stu-id="bdf6b-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="bdf6b-133">Requisitos del sistema del servidor perimetral en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="bdf6b-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="bdf6b-134">Requisitos del entorno del servidor perimetral en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="bdf6b-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="bdf6b-135">Escenarios del servidor perimetral en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="bdf6b-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

