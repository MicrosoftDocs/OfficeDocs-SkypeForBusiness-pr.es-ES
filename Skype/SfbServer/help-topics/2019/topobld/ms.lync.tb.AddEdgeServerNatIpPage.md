---
title: Agregar IP de NAT del servidor perimetral
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: La dirección IP pública es la dirección IP que usa la traducción de direcciones de red (NAT). La dirección IP debe ser públicamente enrutable. Esto es necesario porque la opción NAT ha traducido la dirección IP externa de este grupo de límites de la página seleccionar características de este asistente.
ms.openlocfilehash: f06d9b61d5ffad29d24e143cf3afbbc4501a67d4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689419"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="9964c-105">Agregar IP de NAT del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="9964c-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="9964c-106">La dirección IP pública es la dirección IP que usa la traducción de direcciones de red (NAT).</span><span class="sxs-lookup"><span data-stu-id="9964c-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="9964c-107">La dirección IP debe ser públicamente enrutable.</span><span class="sxs-lookup"><span data-stu-id="9964c-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="9964c-108">Esto es necesario porque la opción **NAT ha traducido la dirección IP externa de este grupo de límites** de la página **seleccionar características** de este asistente.</span><span class="sxs-lookup"><span data-stu-id="9964c-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="9964c-109">La traducción de direcciones de red (NAT) permite que los clientes o servidores de una red privada (por ejemplo, el intervalo 192.168.0.0) se comuniquen con sistemas de redes remotas a través de redes públicas de Internet.</span><span class="sxs-lookup"><span data-stu-id="9964c-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="9964c-110">NAT funciona con una única dirección IP pública en una interfaz externa y asocia las direcciones IP internas a la dirección IP pública.</span><span class="sxs-lookup"><span data-stu-id="9964c-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="9964c-111">La asignación NAT asigna una dirección interna a la dirección IP pública externa.</span><span class="sxs-lookup"><span data-stu-id="9964c-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="9964c-112">El sistema remoto solo ve la dirección pública del origen.</span><span class="sxs-lookup"><span data-stu-id="9964c-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="9964c-113">El sistema remoto responde al origen y el origen hace referencia al mapa NAT para determinar la dirección IP interna a la que se debe devolver la respuesta.</span><span class="sxs-lookup"><span data-stu-id="9964c-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="9964c-p104">La compatibilidad para el acceso de usuarios externos se puede agregar al implementar la topología inicial o más adelante. Para más detalles sobre cómo agregar servidores perimetrales a una topología existente, mire [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) en la documentación de implementación de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="9964c-p104">You can add support for external user access when you deploy your initial topology or afterward. For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


