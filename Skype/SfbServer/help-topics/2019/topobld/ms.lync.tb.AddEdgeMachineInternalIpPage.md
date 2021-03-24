---
title: Agregar dirección IP interna de equipo
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34717d03-5ece-4be3-9d05-25497250dc16
ROBOTS: NOINDEX, NOFOLLOW
description: Utilice esta página para especificar la dirección IP interna y el nombre de dominio completo (FQDN) del servidor perimetral.
ms.openlocfilehash: ff6c965c6256e26ebe905ce25e15c9e18a2cd0d2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095824"
---
# <a name="add-edge-machine-internal-ip"></a><span data-ttu-id="7f16c-103">Agregar dirección IP interna de equipo</span><span class="sxs-lookup"><span data-stu-id="7f16c-103">Add Edge Machine Internal IP</span></span>

<span data-ttu-id="7f16c-104">Utilice esta página para especificar la dirección IP interna y el nombre de dominio completo (FQDN) del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="7f16c-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

<span data-ttu-id="7f16c-105">El FQDN que especifique debe ser idéntico al nombre del equipo configurado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="7f16c-105">The FQDN that you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="7f16c-106">Por defecto, el nombre de equipo de un equipo que no está unido a un dominio es un nombre corto, no un FQDN.</span><span class="sxs-lookup"><span data-stu-id="7f16c-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="7f16c-107">Topology Builder usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="7f16c-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="7f16c-108">Por lo tanto, debe configurar un sufijo de sistema de nombre de dominio (DNS) en el nombre del equipo a implementarlo como servidor perimetral no unido a un dominio.</span><span class="sxs-lookup"><span data-stu-id="7f16c-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="7f16c-109">Para más información sobre cómo añadir un sufijo de DNS a un nombre de equipo, consulte [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)</span><span class="sxs-lookup"><span data-stu-id="7f16c-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support)</span></span>