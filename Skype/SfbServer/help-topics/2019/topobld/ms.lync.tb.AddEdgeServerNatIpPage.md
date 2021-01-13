---
title: Agregar IP de NAT del servidor perimetral
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: La dirección IP pública es la dirección IP que utiliza la traducción de direcciones de red (NAT). La dirección IP debe ser enrutable públicamente. Esto es necesario porque ha seleccionado la opción La dirección IP externa de este grupo de servidores perimetrales se traduce mediante NAT en la página Seleccionar características de este asistente.
ms.openlocfilehash: 1e722a997346daadedf1f017a66f85d6a7355e18
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800970"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="8f3fe-105">Agregar IP de NAT del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="8f3fe-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="8f3fe-p102">La dirección IP pública es la dirección IP que utiliza la traducción de direcciones de red (NAT). La dirección IP debe ser enrutable públicamente. Esto es necesario porque ha seleccionado la opción **La dirección IP externa de este grupo de servidores perimetrales se traduce mediante NAT** en la página **Seleccionar características** de este asistente.</span><span class="sxs-lookup"><span data-stu-id="8f3fe-p102">The public IP address is the IP address that is used by network address translation (NAT). The IP address must be publicly routable. This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="8f3fe-p103">La traducción de direcciones de red (NAT) permite a los clientes o servidores de una red pública (por ejemplo, el intervalo 192.168.0.0) comunicarse con sistemas de redes remotas a través de redes públicas de Internet. La NAT funciona mediante el uso de una única dirección IP pública en una interfaz externa y la asociación de direcciones IP internas con esa dirección IP pública. La asignación de NAT asigna una dirección interna a la dirección IP pública externa. El sistema remoto solamente ve la dirección pública de origen. El sistema remoto responde al origen y éste consulta la asignación de NAT para determinar a qué dirección IP interna se debería mandar la respuesta.</span><span class="sxs-lookup"><span data-stu-id="8f3fe-p103">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks. NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address. NAT mapping maps an internal address to the external public IP address. The remote system sees only the public address of the source. The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="8f3fe-114">Puede permitir que los usuarios externos tengan acceso al implementar la topología inicial o después.</span><span class="sxs-lookup"><span data-stu-id="8f3fe-114">You can add support for external user access when you deploy your initial topology or afterward.</span></span> <span data-ttu-id="8f3fe-115">Para obtener más información sobre cómo agregar servidores perimetrales a una topología ya creada, consulte [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) en la documentación sobre implementación de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="8f3fe-115">For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


