---
title: Agregar servidor
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Para agregar un nuevo servidor a un grupo de servidores existente, donde el grupo de servidores es uno de los siguientes:'
ms.openlocfilehash: 609fbb28900ac67e0a4e1e2a400f1eebb29b2ff2
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="add-server"></a><span data-ttu-id="d35ac-103">Agregar servidor</span><span class="sxs-lookup"><span data-stu-id="d35ac-103">Add Server</span></span>
 
<span data-ttu-id="d35ac-104">Para agregar un nuevo servidor a un grupo de servidores existente, donde el grupo de servidores es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d35ac-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="d35ac-105">Servidor Front-End Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="d35ac-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="d35ac-106">Servidor de director</span><span class="sxs-lookup"><span data-stu-id="d35ac-106">Director server</span></span>
    
- <span data-ttu-id="d35ac-107">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="d35ac-107">Mediation Server</span></span>
    
- <span data-ttu-id="d35ac-108">Servidor de conferencia de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="d35ac-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="d35ac-109">Servidor de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="d35ac-109">Trusted Application server</span></span>
    
<span data-ttu-id="d35ac-110">Cada uno de los nuevos servidores de grupo de servidores tiene requisitos diferentes.</span><span class="sxs-lookup"><span data-stu-id="d35ac-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="d35ac-111">En las secciones siguientes, busque el tipo de servidor que va a agregar al grupo de servidores existente y facilitar la información solicitada tal y como se define para cada tipo de servidor.</span><span class="sxs-lookup"><span data-stu-id="d35ac-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="d35ac-112">Proporcionar la información solicitada para definir el nuevo servidor de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="d35ac-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="d35ac-113">**Servidor Front-End Enterprise Edition**</span><span class="sxs-lookup"><span data-stu-id="d35ac-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="d35ac-114">Nombre de dominio completo (FQDN) del nuevo servidor tal y como se define en el sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="d35ac-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="d35ac-115">Seleccione **usar todas las direcciones IP**, lo que significa que se puede usar cualquier dirección IP que se haya definido en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d35ac-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="d35ac-116">Como alternativa, puede seleccionar **limitar el uso del servicio a las direcciones IP seleccionadas** y escriba una dirección específica en el nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="d35ac-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="d35ac-117">La dirección IP que ha escrito es la única dirección IP que se va a responder para los servicios hospedados.</span><span class="sxs-lookup"><span data-stu-id="d35ac-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="d35ac-118">Defina una **dirección IP de RTC** cuando un servidor de mediación está combinado en el servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="d35ac-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="d35ac-119">Seleccione **Habilitar IPv6** para habilitar IPv6 para este servidor.</span><span class="sxs-lookup"><span data-stu-id="d35ac-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
 <span data-ttu-id="d35ac-120">**Servidor de director**</span><span class="sxs-lookup"><span data-stu-id="d35ac-120">**Director server**</span></span>
  
- <span data-ttu-id="d35ac-121">El FQDN del nuevo servidor tal como se define en DNS.</span><span class="sxs-lookup"><span data-stu-id="d35ac-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="d35ac-122">Seleccione **usar todas las direcciones IP**, lo que significa que se utilizará cualquier dirección IP que se haya definido en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d35ac-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="d35ac-123">Como alternativa, seleccione **limitar el uso del servicio a las direcciones IP seleccionadas** y escriba una dirección IP específica en el nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="d35ac-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="d35ac-124">La dirección IP que ha escrito es la única dirección IP que se va a responder para los servicios hospedados.</span><span class="sxs-lookup"><span data-stu-id="d35ac-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
 <span data-ttu-id="d35ac-125">**Servidor de mediación**</span><span class="sxs-lookup"><span data-stu-id="d35ac-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="d35ac-126">El FQDN del nuevo servidor tal como se define en DNS.</span><span class="sxs-lookup"><span data-stu-id="d35ac-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="d35ac-127">Seleccione **usar todas las direcciones IP**, lo que significa que se puede usar cualquier dirección IP que se haya definido en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d35ac-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="d35ac-128">Como alternativa, seleccione **limitar el uso del servicio a las direcciones IP seleccionadas** y escriba una dirección IP específica en el nuevo servidor como la dirección IP principal y un entrar una dirección IP para la dirección IP telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="d35ac-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="d35ac-129">Las direcciones IP que ha escrito son la única dirección IP que se va a responder para los servicios designados.</span><span class="sxs-lookup"><span data-stu-id="d35ac-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d35ac-130">Para el servidor de mediación, la dirección IP especificada para la dirección IP principal y la dirección IP de PSTN es el mismo de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d35ac-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="d35ac-131">Las direcciones IP se pueden definir por separado si está usando interfaces de red dedicada o separe las direcciones IP en la misma interfaz de red.</span><span class="sxs-lookup"><span data-stu-id="d35ac-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="d35ac-132">Si dispone de interfaces de red de dos, uno para la conexión de red local y otro para la conexión de RTC, debe asignar direcciones IP diferentes.</span><span class="sxs-lookup"><span data-stu-id="d35ac-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
 <span data-ttu-id="d35ac-133">**Servidor de conferencia de audio y vídeo**</span><span class="sxs-lookup"><span data-stu-id="d35ac-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="d35ac-134">El FQDN del nuevo servidor tal como se define en DNS.</span><span class="sxs-lookup"><span data-stu-id="d35ac-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="d35ac-135">Seleccione **usar todas las direcciones IP**, lo que significa que se puede usar cualquier dirección IP que se haya definido en el equipo.</span><span class="sxs-lookup"><span data-stu-id="d35ac-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="d35ac-136">Como alternativa, puede seleccionar **limitar el uso del servicio a las direcciones IP seleccionadas** y escriba una dirección específica en el nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="d35ac-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="d35ac-137">La dirección IP que ha escrito es la única dirección IP que se va a responder para los servicios hospedados.</span><span class="sxs-lookup"><span data-stu-id="d35ac-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
 <span data-ttu-id="d35ac-138">**Servidor de aplicaciones de confianza**</span><span class="sxs-lookup"><span data-stu-id="d35ac-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="d35ac-139">El FQDN del nuevo servidor tal como se define en DNS.</span><span class="sxs-lookup"><span data-stu-id="d35ac-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

