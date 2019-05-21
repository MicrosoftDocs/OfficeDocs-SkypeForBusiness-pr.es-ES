---
title: Plan para implementaciones de servidores perimetrales en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Resumen: Planee su entorno de Skype empresarial Server Edge. En este tema te presentamos los conceptos básicos y te permite organizarte con nuestros temas más detallados.'
ms.openlocfilehash: 536ab82ec6845c55a0ee067ad8c1a4f5d9b9e153
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277163"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="50940-104">Plan para implementaciones de servidores perimetrales en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="50940-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="50940-105">**Resumen:** Planear el entorno de Skype empresarial Server Edge.</span><span class="sxs-lookup"><span data-stu-id="50940-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="50940-106">En este tema te presentamos los conceptos básicos y te permite organizarte con nuestros temas más detallados.</span><span class="sxs-lookup"><span data-stu-id="50940-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="50940-107">Cuando tiene un entorno de Skype empresarial Server que funciona bien internamente, el siguiente paso para usted puede ser introducir un servidor perimetral o un grupo de servidores perimetrales en el entorno.</span><span class="sxs-lookup"><span data-stu-id="50940-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="50940-108">Este rol sería vital si desea que los servicios proporcionados por Skype empresarial Server los usen personas que estén fuera de su red interna.</span><span class="sxs-lookup"><span data-stu-id="50940-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="50940-109">Estos pueden incluir potencialmente:</span><span class="sxs-lookup"><span data-stu-id="50940-109">These can potentially include:</span></span>
  
- <span data-ttu-id="50940-110">Usuarios remotos: empleados que están fuera del sitio, ya sea de forma temporal o continua.</span><span class="sxs-lookup"><span data-stu-id="50940-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="50940-111">Usuarios federados: los empleados de su compañero.</span><span class="sxs-lookup"><span data-stu-id="50940-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="50940-112">Usuarios móviles.</span><span class="sxs-lookup"><span data-stu-id="50940-112">Mobile Users.</span></span>
    
- <span data-ttu-id="50940-113">Clientes potenciales, asociados e incluso usuarios anónimos que desea invitar a reuniones y presentaciones.</span><span class="sxs-lookup"><span data-stu-id="50940-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="50940-114">Acceso externo de usuario, que es lo que proporcionan los servidores perimetrales, permita que esto suceda.</span><span class="sxs-lookup"><span data-stu-id="50940-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="50940-115">Los usuarios internos podrán disfrutar de los siguientes servicios que se hospedan en la implementación de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="50940-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="50940-116">Mensajería instantánea y presencia para la comunicación: los usuarios externos autorizados pueden participar en conversaciones y conferencias de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="50940-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="50940-117">Pueden obtener información de presencia de otros usuarios (que también obtienen su información de presencia).</span><span class="sxs-lookup"><span data-stu-id="50940-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="50940-118">No podrá realizar conferencias de varias partes si está usando un proveedor de mensajería instantánea pública, que es estrictamente una comunicación par a par.</span><span class="sxs-lookup"><span data-stu-id="50940-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="50940-119">Pero se admiten los protocolos SIP y XMPP.</span><span class="sxs-lookup"><span data-stu-id="50940-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="50940-120">Conferencias de audio y vídeo (A/V): los usuarios externos autorizados pueden participar en sus conferencias de audio y vídeo de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="50940-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="50940-121">Conferencias web: los usuarios externos autorizados pueden participar en sus conferencias de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="50940-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="50940-122">También puede habilitar la participación para usuarios remotos, usuarios federados y usuarios anónimos si lo desea.</span><span class="sxs-lookup"><span data-stu-id="50940-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="50940-123">Los usuarios de la mensajería instantánea pública no pueden participar en conferencias.</span><span class="sxs-lookup"><span data-stu-id="50940-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="50940-124">También hay opciones para permitir que estos usuarios participen en el uso compartido de aplicaciones y escritorio, e incluso actuar como organizadores o moderadores de reuniones.</span><span class="sxs-lookup"><span data-stu-id="50940-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="50940-125">El acceso a dispositivos móviles es compatible, como la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="50940-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="50940-126">Puede invitar a usuarios externos a esas reuniones que quiere que asistan, incluso a los usuarios anónimos, si desea concederles permisos.</span><span class="sxs-lookup"><span data-stu-id="50940-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="50940-p108">Si esto le parece algo que necesita su organización, entonces planificar un entorno perimetral va a ser de gran ayuda al implementarlo. Para más información, hay los temas enumerados a continuación.</span><span class="sxs-lookup"><span data-stu-id="50940-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="50940-129">Las puertas de enlace y los servidores proxy XMPP están disponibles en Skype empresarial Server 2015, pero ya no son compatibles con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="50940-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="50940-130">Para obtener más información, consulte migrar la [Federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="50940-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="50940-131">Temas de planeamiento:</span><span class="sxs-lookup"><span data-stu-id="50940-131">Planning topics:</span></span>

<span data-ttu-id="50940-132">Los artículos de planeamiento son:</span><span class="sxs-lookup"><span data-stu-id="50940-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="50940-133">Requisitos del sistema del servidor perimetral en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="50940-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="50940-134">Requisitos del entorno del servidor perimetral en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="50940-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="50940-135">Escenarios del servidor perimetral en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="50940-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

