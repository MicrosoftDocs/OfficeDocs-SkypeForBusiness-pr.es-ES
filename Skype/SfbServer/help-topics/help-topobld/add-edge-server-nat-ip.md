---
title: Agregar IP de NAT de servidor perimetral
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: La dirección IP pública es la dirección IP que se usa en la traducción de direcciones de red (NAT). La dirección IP debe ser públicamente enrutable. Esto es necesario porque ha seleccionado la dirección IP externa de este borde se traduce el grupo de servidores mediante la opción de NAT en la página Seleccionar características de este asistente.
ms.openlocfilehash: be14b49a0d5ccac83dbee483d45aef91f1182621
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003120"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="afa87-105">Agregar IP de NAT de servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="afa87-105">Add Edge Server NAT IP</span></span>
 
<span data-ttu-id="afa87-106">La dirección IP pública es la dirección IP que se usa en la traducción de direcciones de red (NAT).</span><span class="sxs-lookup"><span data-stu-id="afa87-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="afa87-107">La dirección IP debe ser públicamente enrutable.</span><span class="sxs-lookup"><span data-stu-id="afa87-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="afa87-108">Esto es necesario porque seleccionó la opción de **la dirección IP externa de este grupo de servidores perimetrales se traduce mediante NAT** en la página **Seleccionar características** de este asistente.</span><span class="sxs-lookup"><span data-stu-id="afa87-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>
  
> [!NOTE]
> <span data-ttu-id="afa87-109">Traducción de direcciones de red (NAT) permite a los clientes o servidores en una red privada (por ejemplo, la 192.168.0.0 intervalo) para comunicarse con sistemas en redes remotas a través de las redes públicas de Internet.</span><span class="sxs-lookup"><span data-stu-id="afa87-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="afa87-110">NAT funciona con una sola dirección IP pública en una interfaz externa y asociar las direcciones IP internas a la dirección IP pública uno.</span><span class="sxs-lookup"><span data-stu-id="afa87-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="afa87-111">NAT asigna una dirección interna a la dirección IP pública externa.</span><span class="sxs-lookup"><span data-stu-id="afa87-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="afa87-112">El sistema remoto ve sólo la dirección pública del origen.</span><span class="sxs-lookup"><span data-stu-id="afa87-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="afa87-113">El sistema remoto responde a la fuente y el origen hace referencia a la asignación NAT para determinar qué dirección IP interna de que la respuesta se debe devolver al.</span><span class="sxs-lookup"><span data-stu-id="afa87-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span> 
  
<span data-ttu-id="afa87-114">La compatibilidad para el acceso de usuarios externos se puede agregar al implementar la topología inicial o más adelante.</span><span class="sxs-lookup"><span data-stu-id="afa87-114">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="afa87-115">Para obtener información detallada sobre la adición de servidores perimetrales a una topología existente, consulte [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) en la documentación de implementación del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="afa87-115">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>
  

