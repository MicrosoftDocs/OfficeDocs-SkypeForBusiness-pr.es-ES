---
title: Agregar servidor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Para agregar un nuevo servidor a un grupo de servidores existente, donde el grupo es uno de los siguientes:'
ms.openlocfilehash: c19aad7f55c6ebc22ee64c715700d8cc7116bccb
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698045"
---
# <a name="add-server"></a><span data-ttu-id="dffdf-103">Agregar servidor</span><span class="sxs-lookup"><span data-stu-id="dffdf-103">Add Server</span></span>
 
<span data-ttu-id="dffdf-104">Para agregar un nuevo servidor a un grupo de servidores existente, donde el grupo es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="dffdf-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="dffdf-105">Servidor front-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="dffdf-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="dffdf-106">Servidor Director</span><span class="sxs-lookup"><span data-stu-id="dffdf-106">Director server</span></span>
    
- <span data-ttu-id="dffdf-107">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="dffdf-107">Mediation Server</span></span>
    
- <span data-ttu-id="dffdf-108">Servidor de conferencias de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="dffdf-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="dffdf-109">Servidor de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="dffdf-109">Trusted Application server</span></span>
    
<span data-ttu-id="dffdf-110">Cada uno de los nuevos servidores de grupo tiene requisitos diferentes.</span><span class="sxs-lookup"><span data-stu-id="dffdf-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="dffdf-111">En las secciones siguientes, busque el tipo de servidor que está agregando al grupo existente y proporcione la información solicitada, ya que se define para cada tipo de servidor.</span><span class="sxs-lookup"><span data-stu-id="dffdf-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="dffdf-112">Proporcione la información solicitada para definir el nuevo servidor de grupo.</span><span class="sxs-lookup"><span data-stu-id="dffdf-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="dffdf-113">**Servidor front-end Enterprise Edition**</span><span class="sxs-lookup"><span data-stu-id="dffdf-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="dffdf-114">Nombre de dominio completo (FQDN) del nuevo servidor como se define en el sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="dffdf-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="dffdf-115">Seleccione **usar todas las direcciones IP configuradas**, lo que significa que se puede usar cualquier dirección IP definida en el equipo.</span><span class="sxs-lookup"><span data-stu-id="dffdf-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="dffdf-116">También puede seleccionar **limitar el uso del servicio a las direcciones IP seleccionadas** e introducir una dirección específica en el nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="dffdf-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="dffdf-117">La dirección IP introducida es la única dirección IP que responderá a los servicios hospedados.</span><span class="sxs-lookup"><span data-stu-id="dffdf-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="dffdf-118">Defina una **dirección IP de RTC** cuando se colocará un servidor de mediación en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="dffdf-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="dffdf-119">Seleccione **Habilitar IPv6** para habilitar IPv6 en este servidor.</span><span class="sxs-lookup"><span data-stu-id="dffdf-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="dffdf-120">**Servidor Director**</span><span class="sxs-lookup"><span data-stu-id="dffdf-120">**Director server**</span></span>
  
- <span data-ttu-id="dffdf-121">El FQDN del nuevo servidor como se define en DNS.</span><span class="sxs-lookup"><span data-stu-id="dffdf-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="dffdf-122">Seleccione **usar todas las direcciones IP configuradas**, lo que significa que se usará cualquier dirección IP definida en el equipo.</span><span class="sxs-lookup"><span data-stu-id="dffdf-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="dffdf-123">También puede seleccionar limitar el **uso del servicio a las direcciones IP seleccionadas** e introducir una dirección IP específica en el nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="dffdf-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="dffdf-124">La dirección IP introducida es la única dirección IP que responderá a los servicios hospedados.</span><span class="sxs-lookup"><span data-stu-id="dffdf-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="dffdf-125">**Servidor de mediación**</span><span class="sxs-lookup"><span data-stu-id="dffdf-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="dffdf-126">El FQDN del nuevo servidor como se define en DNS.</span><span class="sxs-lookup"><span data-stu-id="dffdf-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="dffdf-127">Seleccione **usar todas las direcciones IP configuradas**, lo que significa que se puede usar cualquier dirección IP definida en el equipo.</span><span class="sxs-lookup"><span data-stu-id="dffdf-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="dffdf-128">También puede seleccionar limitar el **uso del servicio a las direcciones IP seleccionadas** e introducir una dirección IP específica en el nuevo servidor como dirección IP principal y una dirección IP para la dirección IP de la red de telefonía pública conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="dffdf-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="dffdf-129">Las direcciones IP especificadas son la única dirección IP que responderá a los servicios designados.</span><span class="sxs-lookup"><span data-stu-id="dffdf-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dffdf-130">Para el servidor de mediación, la dirección IP especificada para la dirección IP principal y la dirección IP de RTC es la misma de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dffdf-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="dffdf-131">Las direcciones IP se pueden definir por separado si está usando interfaces de red dedicadas o direcciones IP independientes en la misma interfaz de red.</span><span class="sxs-lookup"><span data-stu-id="dffdf-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="dffdf-132">Si tiene dos interfaces de red, una para la conexión de red local y otra para la conexión RTC, debe asignar direcciones IP diferentes.</span><span class="sxs-lookup"><span data-stu-id="dffdf-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="dffdf-133">**Servidor de conferencias de audio y vídeo**</span><span class="sxs-lookup"><span data-stu-id="dffdf-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="dffdf-134">El FQDN del nuevo servidor como se define en DNS.</span><span class="sxs-lookup"><span data-stu-id="dffdf-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="dffdf-135">Seleccione **usar todas las direcciones IP configuradas**, lo que significa que se puede usar cualquier dirección IP definida en el equipo.</span><span class="sxs-lookup"><span data-stu-id="dffdf-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="dffdf-136">También puede seleccionar **limitar el uso del servicio a las direcciones IP seleccionadas** e introducir una dirección específica en el nuevo servidor.</span><span class="sxs-lookup"><span data-stu-id="dffdf-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="dffdf-137">La dirección IP introducida es la única dirección IP que responderá a los servicios hospedados.</span><span class="sxs-lookup"><span data-stu-id="dffdf-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="dffdf-138">**Servidor de aplicaciones de confianza**</span><span class="sxs-lookup"><span data-stu-id="dffdf-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="dffdf-139">El FQDN del nuevo servidor como se define en DNS.</span><span class="sxs-lookup"><span data-stu-id="dffdf-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

