---
title: Planificar las implementaciones del servidor perimetral en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Resumen: Planear su Skype para el entorno de servidor perimetral de Business Server 2015. Este tema presenta los conceptos de borde y le permite organizarse con nuestros temas más detallados.'
ms.openlocfilehash: 828bdc52a6c4fe55294768d69c441b9c996fa9a0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server-2015"></a><span data-ttu-id="dc904-104">Planificar las implementaciones del servidor perimetral en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="dc904-104">Plan for Edge Server deployments in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dc904-p102">**Resumen:** planifique el entorno de servidor perimetral de Skype Empresarial Server 2015. Este tema presenta los conceptos del servidor perimetral y le permite organizarse con los temas que lo tratan más en profundidad.</span><span class="sxs-lookup"><span data-stu-id="dc904-p102">**Summary:** Plan for your Skype for Business Server 2015 Server Edge environment. This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="dc904-107">Cuando tenga un Skype para entorno de 2015 de servidor empresarial que funciona bien internamente, podría ser el siguiente paso para introducir un servidor perimetral o un grupo de servidores de borde en el entorno.</span><span class="sxs-lookup"><span data-stu-id="dc904-107">When you have a Skype for Business Server 2015 environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="dc904-108">Esta función sería vital si desea que los servicios proporcionados por Skype para Business Server 2015 ser utilizada por personas que se encuentran fuera de la red interna.</span><span class="sxs-lookup"><span data-stu-id="dc904-108">This role would be vital if you want the services provided by Skype for Business Server 2015 to be used by people who are outside your internal network.</span></span> <span data-ttu-id="dc904-109">Estos pueden incluir potencialmente:</span><span class="sxs-lookup"><span data-stu-id="dc904-109">These can potentially include:</span></span>
  
- <span data-ttu-id="dc904-110">Usuarios remotos: empleados que están fuera del sitio, ya sea de forma temporal o continua.</span><span class="sxs-lookup"><span data-stu-id="dc904-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="dc904-111">Usuarios federados: Los empleados de las organizaciones del socio.</span><span class="sxs-lookup"><span data-stu-id="dc904-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="dc904-112">Usuarios móviles.</span><span class="sxs-lookup"><span data-stu-id="dc904-112">Mobile Users.</span></span>
    
- <span data-ttu-id="dc904-113">Clientes potenciales, asociados e incluso usuarios anónimos que desea invitar a reuniones y presentaciones.</span><span class="sxs-lookup"><span data-stu-id="dc904-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="dc904-114">Acceso de usuario externo, que es lo que proporcionan los servidores perimetrales, permitir que esto suceda.</span><span class="sxs-lookup"><span data-stu-id="dc904-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="dc904-115">Los usuarios internos podrán disfrutar de los siguientes servicios alojados por su Skype para la implementación de Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="dc904-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server 2015 deployment:</span></span>
  
- <span data-ttu-id="dc904-116">Mensajería instantánea y presencia para la comunicación: los usuarios externos autorizados pueden participar en conversaciones y conferencias de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="dc904-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="dc904-117">Pueden obtener información de presencia de otros usuarios (que también obtienen su información de presencia).</span><span class="sxs-lookup"><span data-stu-id="dc904-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="dc904-118">No podrá realizar conferencias con varios participantes, si utiliza un proveedor de mensajería instantánea pública, que es la comunicación estrictamente peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="dc904-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="dc904-119">Pero se admiten los protocolos SIP y XMPP.</span><span class="sxs-lookup"><span data-stu-id="dc904-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="dc904-120">Audio y vídeo (A / V) conferencia: los usuarios externos autorizados pueden participar en su Skype para conferencias de audio y vídeo de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="dc904-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server 2015 audio and video conferences.</span></span>
    
- <span data-ttu-id="dc904-121">Conferencias Web: los usuarios externos autorizados pueden participar en su Skype para conferencias de empresa.</span><span class="sxs-lookup"><span data-stu-id="dc904-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="dc904-122">También puede habilitar la participación de los usuarios remotos, usuarios federados y usuarios anónimos si lo desea.</span><span class="sxs-lookup"><span data-stu-id="dc904-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="dc904-123">Los usuarios de mensajería instantánea pública no pueden participar en conferencias.</span><span class="sxs-lookup"><span data-stu-id="dc904-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="dc904-124">También hay opciones para permitir que estos usuarios participen en el uso compartido de aplicaciones y escritorio, e incluso actuar como organizadores o moderadores de reuniones.</span><span class="sxs-lookup"><span data-stu-id="dc904-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="dc904-125">Se admite el acceso a dispositivos móviles, como es la Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="dc904-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="dc904-126">Puede invitar a usuarios externos a esas reuniones que quiere que asistan, incluso a los usuarios anónimos, si desea concederles permisos.</span><span class="sxs-lookup"><span data-stu-id="dc904-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="dc904-p108">Si esto le parece algo que necesita su organización, entonces planificar un entorno perimetral va a ser de gran ayuda al implementarlo. Para más información, hay los temas enumerados a continuación.</span><span class="sxs-lookup"><span data-stu-id="dc904-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>
  
## <a name="planning-topics"></a><span data-ttu-id="dc904-129">Temas de planeamiento:</span><span class="sxs-lookup"><span data-stu-id="dc904-129">Planning topics:</span></span>

<span data-ttu-id="dc904-130">Los artículos de planeamiento son:</span><span class="sxs-lookup"><span data-stu-id="dc904-130">The planning articles are:</span></span>
  
- [<span data-ttu-id="dc904-131">Requisitos del sistema servidor de borde en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dc904-131">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="dc904-132">Edge Server requisitos medioambientales en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dc904-132">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="dc904-133">Escenarios de servidor de borde en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dc904-133">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

