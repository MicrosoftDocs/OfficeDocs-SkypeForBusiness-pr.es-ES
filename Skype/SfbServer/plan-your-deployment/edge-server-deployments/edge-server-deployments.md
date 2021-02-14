---
title: Planeación de implementaciones de servidores perimetrales en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Resumen: planee su entorno perimetral de Skype Empresarial Server. Este tema le presenta los conceptos de Edge y le permite organizarse con nuestros temas más exhaustivos.'
ms.openlocfilehash: 277e344448f5229d15addf965695f19ec2884649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813810"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="32f4a-104">Planeación de implementaciones de servidores perimetrales en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="32f4a-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="32f4a-105">**Resumen:** Planee su entorno perimetral de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="32f4a-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="32f4a-106">Este tema le presenta los conceptos de Edge y le permite organizarse con nuestros temas más exhaustivos.</span><span class="sxs-lookup"><span data-stu-id="32f4a-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="32f4a-107">Cuando tiene un entorno de Skype Empresarial Server que funciona bien internamente, es posible que el siguiente paso sea introducir un servidor perimetral o un grupo de servidores perimetrales en el entorno.</span><span class="sxs-lookup"><span data-stu-id="32f4a-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="32f4a-108">Este rol sería fundamental si quiere que los servicios proporcionados por Skype Empresarial Server sean usados por personas que están fuera de la red interna.</span><span class="sxs-lookup"><span data-stu-id="32f4a-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="32f4a-109">Estos pueden incluir posiblemente:</span><span class="sxs-lookup"><span data-stu-id="32f4a-109">These can potentially include:</span></span>
  
- <span data-ttu-id="32f4a-110">Usuarios remotos: empleados que están fuera del sitio, ya sea temporalmente o de forma continua.</span><span class="sxs-lookup"><span data-stu-id="32f4a-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="32f4a-111">Usuarios federados: los empleados de las organizaciones asociadas.</span><span class="sxs-lookup"><span data-stu-id="32f4a-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="32f4a-112">Usuarios móviles.</span><span class="sxs-lookup"><span data-stu-id="32f4a-112">Mobile Users.</span></span>
    
- <span data-ttu-id="32f4a-113">Posibles clientes, partners e incluso usuarios anónimos a los que quiera invitar a reuniones y presentaciones.</span><span class="sxs-lookup"><span data-stu-id="32f4a-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="32f4a-114">El acceso de usuarios externos, que es lo que proporcionan los servidores perimetrales, permite que todo esto suceda.</span><span class="sxs-lookup"><span data-stu-id="32f4a-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="32f4a-115">Los usuarios internos podrán disfrutar de los siguientes servicios hospedados en la implementación de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="32f4a-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="32f4a-116">Mensajería instantánea y presencia para la comunicación: los usuarios externos autorizados pueden unirse a conversaciones y conferencias de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="32f4a-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="32f4a-117">Pueden obtener información de presencia para otros usuarios (que también obtienen su información de presencia).</span><span class="sxs-lookup"><span data-stu-id="32f4a-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="32f4a-118">No podrá realizar conferencias entre varias entidades si usa un proveedor de mensajería instantánea pública, que es estrictamente comunicación punto a punto.</span><span class="sxs-lookup"><span data-stu-id="32f4a-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="32f4a-119">Pero se admiten los protocolos SIP y XMPP.</span><span class="sxs-lookup"><span data-stu-id="32f4a-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="32f4a-120">Conferencia de audio y vídeo (A/V): los usuarios externos autorizados pueden participar en las conferencias de audio y vídeo de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="32f4a-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="32f4a-121">Conferencia web: los usuarios externos autorizados pueden participar en las conferencias de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="32f4a-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="32f4a-122">También puede habilitar la participación de usuarios remotos, usuarios federados y usuarios anónimos si lo desea.</span><span class="sxs-lookup"><span data-stu-id="32f4a-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="32f4a-123">Los usuarios de mensajería instantánea pública no pueden participar en conferencias.</span><span class="sxs-lookup"><span data-stu-id="32f4a-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="32f4a-124">También hay opciones para permitir que estos usuarios participen en el uso compartido de aplicaciones y escritorios, e incluso actuar como organizadores o presentadores de reuniones.</span><span class="sxs-lookup"><span data-stu-id="32f4a-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="32f4a-125">Se admite el acceso a dispositivos móviles, como Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="32f4a-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="32f4a-126">Puede invitar a usuarios externos a esas reuniones a las que desea que asistan, incluso a los usuarios anónimos, si desea concederles permisos.</span><span class="sxs-lookup"><span data-stu-id="32f4a-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="32f4a-127">Si esto parece algo que necesita su organización, la planeación de un entorno perimetral le será de gran ayuda para implementarlo.</span><span class="sxs-lookup"><span data-stu-id="32f4a-127">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it.</span></span> <span data-ttu-id="32f4a-128">Para obtener más información, tenemos los temas que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="32f4a-128">For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="32f4a-129">Las puertas de enlace XMPP y los servidores proxy están disponibles en Skype Empresarial Server 2015, pero ya no se admiten en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="32f4a-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="32f4a-130">Consulte [Migración de la federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="32f4a-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="32f4a-131">Temas de planeación:</span><span class="sxs-lookup"><span data-stu-id="32f4a-131">Planning topics:</span></span>

<span data-ttu-id="32f4a-132">Los artículos de planeación son:</span><span class="sxs-lookup"><span data-stu-id="32f4a-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="32f4a-133">Requisitos del sistema del servidor perimetral en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="32f4a-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="32f4a-134">Requisitos del entorno del servidor perimetral en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="32f4a-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="32f4a-135">Escenarios de servidor perimetral en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="32f4a-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

