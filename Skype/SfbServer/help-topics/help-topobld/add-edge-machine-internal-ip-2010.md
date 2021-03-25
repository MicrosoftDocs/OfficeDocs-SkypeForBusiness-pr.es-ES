---
title: Agregar IP interna de equipo perimetral 2010
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
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Use esta página para especificar la dirección IP interna y el nombre de dominio completo interno del servidor perimetral.
ms.openlocfilehash: 51ab7e117892efbbbd7fd16a27b3f06b599297b9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120961"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="a4cf3-103">Agregar IP interna de equipo perimetral 2010</span><span class="sxs-lookup"><span data-stu-id="a4cf3-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="a4cf3-104">Use esta página para especificar la dirección IP interna y el nombre de dominio completo interno del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="a4cf3-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="a4cf3-105">En **Dirección IPv4 interna,** escriba la dirección IP del servidor perimetral que desea agregar al grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="a4cf3-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="a4cf3-106">En **FQDN interno,** escriba el nombre de dominio completo (FQDN) del servidor perimetral que desea agregar al grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="a4cf3-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="a4cf3-107">El nombre que especifique debe ser idéntico al nombre del equipo configurado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="a4cf3-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="a4cf3-108">De manera predeterminada, el nombre de un equipo que no está unido a un dominio es un nombre corto, en lugar de un nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="a4cf3-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="a4cf3-109">Topology Builder usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="a4cf3-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a4cf3-110">Por lo tanto, debe configurar un sufijo de sistema de nombre de dominio (DNS) en el nombre del equipo a implementarlo como servidor perimetral no unido a un dominio.</span><span class="sxs-lookup"><span data-stu-id="a4cf3-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="a4cf3-111">Para más información sobre cómo añadir un sufijo de DNS a un nombre de equipo, consulte [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)</span><span class="sxs-lookup"><span data-stu-id="a4cf3-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)</span></span>