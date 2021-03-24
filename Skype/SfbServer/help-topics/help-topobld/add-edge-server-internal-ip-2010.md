---
title: Agregar IP interna de servidor perimetral 2010
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
- ms.lync.tb.AddEdgeServerInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 661dd74e-c42a-4905-a9c6-6efe02acc5f8
description: Utilice esta página para especificar la dirección IP interna y el nombre de dominio completo (FQDN) del servidor perimetral.
ms.openlocfilehash: c8e6c7fb4722d7d6e8b9b01057dc38d64cfe557e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103346"
---
# <a name="add-edge-server-internal-ip-2010"></a><span data-ttu-id="52763-103">Agregar IP interna de servidor perimetral 2010</span><span class="sxs-lookup"><span data-stu-id="52763-103">Add Edge Server Internal IP 2010</span></span>

<span data-ttu-id="52763-104">Utilice esta página para especificar la dirección IP interna y el nombre de dominio completo (FQDN) del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="52763-104">Use this page to specify the internal IP address and internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

<span data-ttu-id="52763-105">El FQDN que especifique debe ser idéntico al nombre del equipo configurado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="52763-105">That FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="52763-106">De forma predeterminada, un equipo no incorporado a un dominio tiene un nombre corto, no un nombre de dominio completo.</span><span class="sxs-lookup"><span data-stu-id="52763-106">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="52763-107">Topology Builder usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="52763-107">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="52763-108">Por lo tanto, debe configurar un sufijo de sistema de nombre de dominio (DNS) en el nombre del equipo a implementarlo como servidor perimetral no unido a un dominio.</span><span class="sxs-lookup"><span data-stu-id="52763-108">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="52763-109">Para obtener más información sobre cómo agregar un sufijo DNS a un nombre de equipo, vea [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support).</span><span class="sxs-lookup"><span data-stu-id="52763-109">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support).</span></span>