---
title: Agregar IP de NAT de servidor perimetral
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: La dirección IP pública es la dirección IP que utiliza traducción de direcciones de red (NAT). La dirección IP debe ser enrutable públicamente. Esto es necesario porque ha seleccionado la dirección IP externa de este borde pool se traduce por opción de NAT en la página Seleccionar características de este asistente.
ms.openlocfilehash: 4bfbcb7d8859dc928c78c8e32b21604ef473317b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="8b104-105">Agregar IP de NAT de servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8b104-105">Add Edge Server NAT IP</span></span>
 
<span data-ttu-id="8b104-106">La dirección IP pública es la dirección IP que utiliza traducción de direcciones de red (NAT).</span><span class="sxs-lookup"><span data-stu-id="8b104-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="8b104-107">La dirección IP debe ser enrutable públicamente.</span><span class="sxs-lookup"><span data-stu-id="8b104-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="8b104-108">Esto es necesario porque se seleccionó la opción **NAT traduce la dirección IP externa de este grupo de borde** en la página **Seleccionar características** de este asistente.</span><span class="sxs-lookup"><span data-stu-id="8b104-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8b104-109">Traducción de direcciones de red (NAT) permite a los clientes o servidores en una red privada (por ejemplo, el 192.168.0.0 intervalo) para comunicarse con sistemas en redes remotas a través de las redes públicas de Internet.</span><span class="sxs-lookup"><span data-stu-id="8b104-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="8b104-110">NAT funciona mediante una única dirección IP pública en una interfaz externa y asociar las direcciones IP internas con las direcciones IP públicas.</span><span class="sxs-lookup"><span data-stu-id="8b104-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="8b104-111">NAT asigna una dirección interna a la dirección IP pública externa.</span><span class="sxs-lookup"><span data-stu-id="8b104-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="8b104-112">El sistema remoto ve sólo la dirección pública de la fuente.</span><span class="sxs-lookup"><span data-stu-id="8b104-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="8b104-113">El sistema remoto responde a la fuente y el origen se refiere a la asignación NAT para determinar qué dirección IP interna a que debe devolverse la respuesta.</span><span class="sxs-lookup"><span data-stu-id="8b104-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span> 
  
<span data-ttu-id="8b104-114">La compatibilidad para el acceso de usuarios externos se puede agregar al implementar la topología inicial o más adelante.</span><span class="sxs-lookup"><span data-stu-id="8b104-114">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="8b104-115">Para obtener más información sobre cómo agregar servidores de borde a una topología existente, vea [Definir su topología de borde](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) en la documentación de implementación de servidor de borde.</span><span class="sxs-lookup"><span data-stu-id="8b104-115">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>
  

