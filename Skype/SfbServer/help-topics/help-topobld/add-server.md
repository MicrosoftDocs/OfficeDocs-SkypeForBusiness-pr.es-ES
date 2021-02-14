---
title: Agregar servidor
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Para agregar un nuevo servidor a un grupo de servidores ya creado que puede ser uno de los siguientes:'
ms.openlocfilehash: e40cf71b0ab52e66a3a28e0362de4f9106ddd831
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818630"
---
# <a name="add-server"></a><span data-ttu-id="25836-103">Agregar servidor</span><span class="sxs-lookup"><span data-stu-id="25836-103">Add Server</span></span>
 
<span data-ttu-id="25836-104">Para agregar un nuevo servidor a un grupo de servidores ya creado que puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="25836-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="25836-105">Servidor front-end de Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="25836-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="25836-106">Servidor director</span><span class="sxs-lookup"><span data-stu-id="25836-106">Director server</span></span>
    
- <span data-ttu-id="25836-107">Servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="25836-107">Mediation Server</span></span>
    
- <span data-ttu-id="25836-108">Servidor de conferencia A/V</span><span class="sxs-lookup"><span data-stu-id="25836-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="25836-109">Servidor de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="25836-109">Trusted Application server</span></span>
    
<span data-ttu-id="25836-p101">Cada uno de los nuevos servidores del grupo de servidores tiene sus propios requisitos. En las secciones siguientes, busque el tipo de servidor que va a agregar al grupo de servidores ya creado y proporcione la información pertinente para cada tipo de servidor. La información solicitada se proporciona para definir el nuevo servidor del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="25836-p101">Each of the new pool servers has different requirements. In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type. You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="25836-113">**Servidor front-end de Enterprise Edition**</span><span class="sxs-lookup"><span data-stu-id="25836-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="25836-114">Nombre de dominio completo del nuevo servidor como se haya especificado en el Sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="25836-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="25836-p102">Seleccione **Usar todas las direcciones IP configuradas**; de este modo, se puede usar cualquier dirección IP que se haya definido en el equipo. Si lo prefiere, seleccione **Limitar el uso del servicio a las direcciones IP seleccionadas** e indique una determinada dirección en el nuevo servidor. La dirección IP que se especifica es la única dirección IP que se encargará de los servicios hospedados.</span><span class="sxs-lookup"><span data-stu-id="25836-p102">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="25836-118">Defina una **dirección IP RTC** cuando un servidor de mediación se coloca en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="25836-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="25836-119">Seleccione **Habilitar IPv6** para habilitar IPv6 para este servidor.</span><span class="sxs-lookup"><span data-stu-id="25836-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="25836-120">**Servidor de director**</span><span class="sxs-lookup"><span data-stu-id="25836-120">**Director server**</span></span>
  
- <span data-ttu-id="25836-121">El nombre de dominio completo del nuevo servidor es el mismo que en DNS.</span><span class="sxs-lookup"><span data-stu-id="25836-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="25836-p103">Seleccione **Usar todas las direcciones IP configuradas**, lo que significa que se puede utilizar cualquier dirección IP definida en el equipo. De forma alternativa, puede seleccionar **Limitar el uso de servicio a las direcciones IP seleccionadas** y escribir una dirección específica en el nuevo servidor. La dirección IP especificada es la única dirección IP que responderá para los servicios hospedados.</span><span class="sxs-lookup"><span data-stu-id="25836-p103">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="25836-125">**Servidor de mediación**</span><span class="sxs-lookup"><span data-stu-id="25836-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="25836-126">El nombre de dominio completo del nuevo servidor es el mismo que en DNS.</span><span class="sxs-lookup"><span data-stu-id="25836-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="25836-p104">Seleccione **Usar todas las direcciones IP configuradas**; de este modo, se puede usar cualquier dirección IP que se haya definido en el equipo. Si lo desea, seleccione **Limitar el uso del servicio a las direcciones IP seleccionadas** y especifique una dirección IP en el nuevo servidor como dirección IP principal; asimismo, indique una dirección IP para la dirección IP de la RTC. Las direcciones IP que se especifican son las únicas direcciones IP que se encargarán de los servicios hospedados.</span><span class="sxs-lookup"><span data-stu-id="25836-p104">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address. The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="25836-p105">En el caso del servidor de mediación, la dirección IP especificada como IP principal y la dirección IP de RTC coinciden por defecto. Las direcciones IP se pueden definir por separado si utiliza interfaces de red dedicada o direcciones IP separadas en la misma interfaz de red. Si tiene dos interfaces de red diferentes, una para la conexión de red local y otra para la conexión de RTC, debe asignar direcciones IP diferentes.</span><span class="sxs-lookup"><span data-stu-id="25836-p105">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default. The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface. If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="25836-133">**Servidor de conferencia audio/vídeo**</span><span class="sxs-lookup"><span data-stu-id="25836-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="25836-134">El nombre de dominio completo del nuevo servidor es el mismo que en DNS.</span><span class="sxs-lookup"><span data-stu-id="25836-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="25836-p106">Seleccione **Usar todas las direcciones IP configuradas**, lo que significa que se puede utilizar cualquier dirección IP definida en el equipo. De forma alternativa, puede seleccionar **Limitar el uso de servicio a las direcciones IP seleccionadas** y escribir una dirección específica en el nuevo servidor. La dirección IP especificada es la única dirección IP que responderá para los servicios hospedados.</span><span class="sxs-lookup"><span data-stu-id="25836-p106">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="25836-138">**Servidor de aplicación de confianza**</span><span class="sxs-lookup"><span data-stu-id="25836-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="25836-139">El FQDN del nuevo servidor tal como se define en el DNS.</span><span class="sxs-lookup"><span data-stu-id="25836-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

