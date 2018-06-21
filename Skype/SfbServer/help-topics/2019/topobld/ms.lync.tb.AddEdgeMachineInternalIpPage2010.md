---
title: Agregar IP interna del equipo perimetral 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Use esta página para especificar la dirección IP interna y el nombre de dominio completo interno (FQDN) para el servidor perimetral.
ms.openlocfilehash: d25819b45fea7ba46501e931beeb8d5032b43c1f
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/20/2018
ms.locfileid: "19975388"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="87b6e-103">Agregar IP interna del equipo perimetral 2010</span><span class="sxs-lookup"><span data-stu-id="87b6e-103">Add Edge Machine Internal IP 2010</span></span>
 
<span data-ttu-id="87b6e-104">Use esta página para especificar la dirección IP interna y el nombre de dominio completo interno (FQDN) para el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="87b6e-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>
  
- <span data-ttu-id="87b6e-105">En **dirección IPv4 interna**, escriba la dirección IP del servidor perimetral que desea agregar al grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="87b6e-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>
    
- <span data-ttu-id="87b6e-106">En **FQDN interno**, escriba el nombre de dominio completo (FQDN) del servidor perimetral que desea agregar al grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="87b6e-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>
    
<span data-ttu-id="87b6e-107">El FQDN que especifique debe ser idéntico al nombre del equipo que está configurado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="87b6e-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="87b6e-108">Un equipo no incorporado a un dominio tiene un nombre corto de forma predeterminada, no un nombre de dominio completo.</span><span class="sxs-lookup"><span data-stu-id="87b6e-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="87b6e-109">El Generador de topologías usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="87b6e-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="87b6e-110">Por lo tanto, debe configurar un sufijo del sistema de nombres de dominio (DNS) en el nombre del equipo en el que se implemente como un servidor perimetral que no está unido a un dominio.</span><span class="sxs-lookup"><span data-stu-id="87b6e-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="87b6e-111">Para obtener información detallada acerca de cómo agregar un sufijo DNS para un nombre de equipo, vea [Configurar DNS para admitir servidores perimetrales](http://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="87b6e-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](http://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>
  

