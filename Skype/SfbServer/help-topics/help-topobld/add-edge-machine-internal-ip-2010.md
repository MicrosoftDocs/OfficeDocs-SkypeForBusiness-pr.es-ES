---
title: Agregar IP interna de equipo perimetral 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Use esta página para especificar la dirección IP interna y el nombre de dominio completo interno (FQDN) para el servidor perimetral.
ms.openlocfilehash: 53b4a3d7d7347a151cc34195236f50d492206825
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304719"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="64a41-103">Agregar IP interna de equipo perimetral 2010</span><span class="sxs-lookup"><span data-stu-id="64a41-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="64a41-104">Use esta página para especificar la dirección IP interna y el nombre de dominio completo interno (FQDN) para el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="64a41-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="64a41-105">En **dirección IPv4 interna**, escriba la dirección IP del servidor perimetral que desea agregar al grupo.</span><span class="sxs-lookup"><span data-stu-id="64a41-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="64a41-106">En nombre de dominio **interno**, escriba el nombre de dominio completo (FQDN) del servidor perimetral que desea agregar al grupo.</span><span class="sxs-lookup"><span data-stu-id="64a41-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="64a41-107">El FQDN que especifique debe ser idéntico al nombre del equipo que está configurado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="64a41-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="64a41-108">Un equipo no incorporado a un dominio tiene un nombre corto de forma predeterminada, no un nombre de dominio completo.</span><span class="sxs-lookup"><span data-stu-id="64a41-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="64a41-109">El Generador de topologías usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="64a41-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="64a41-110">Por lo tanto, debe configurar un sufijo de sistema de nombre de dominio (DNS) en el nombre del equipo que se va a implementar como un servidor perimetral que no está unido a un dominio.</span><span class="sxs-lookup"><span data-stu-id="64a41-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="64a41-111">Para más información sobre cómo agregar un sufijo DNS al nombre de un equipo, consulte [configurar DNS para la compatibilidad con Edge](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="64a41-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


