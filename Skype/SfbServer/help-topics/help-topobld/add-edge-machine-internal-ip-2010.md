---
title: Agregar IP interna de equipo perimetral 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeMachineInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b0ac1d-f320-4677-bd0f-b4b0dc84a6a2
description: Use esta página para especificar la dirección IP interna y el nombre de dominio completo interno (FQDN) para el servidor perimetral.
ms.openlocfilehash: b54fae5ce536e1f859c4c05059b18b5e5067af7e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873329"
---
# <a name="add-edge-machine-internal-ip-2010"></a><span data-ttu-id="58532-103">Agregar IP interna de equipo perimetral 2010</span><span class="sxs-lookup"><span data-stu-id="58532-103">Add Edge Machine Internal IP 2010</span></span>

<span data-ttu-id="58532-104">Use esta página para especificar la dirección IP interna y el nombre de dominio completo interno (FQDN) para el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="58532-104">Use this page to specify the internal IP address and the internal fully qualified domain name (FQDN) for the Edge Server.</span></span>

- <span data-ttu-id="58532-105">En **dirección IPv4 interna**, escriba la dirección IP del servidor perimetral que desea agregar al grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="58532-105">In **Internal IPv4 address**, type the IP address of the Edge Server that you want to add to the pool.</span></span>

- <span data-ttu-id="58532-106">En **FQDN interno**, escriba el nombre de dominio completo (FQDN) del servidor perimetral que desea agregar al grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="58532-106">In **Internal FQDN**, type the fully qualified domain name (FQDN) of the Edge Server that you want to add to the pool.</span></span>

<span data-ttu-id="58532-107">El FQDN que especifique debe ser idéntico al nombre del equipo que está configurado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="58532-107">The FQDN that you specify must be identical to the computer name that is configured on the server.</span></span> <span data-ttu-id="58532-108">Un equipo no incorporado a un dominio tiene un nombre corto de forma predeterminada, no un nombre de dominio completo.</span><span class="sxs-lookup"><span data-stu-id="58532-108">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="58532-109">El Generador de topologías usa nombres de dominio completos, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="58532-109">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="58532-110">Por lo tanto, debe configurar un sufijo del sistema de nombres de dominio (DNS) en el nombre del equipo en el que se implemente como un servidor perimetral que no está unido a un dominio.</span><span class="sxs-lookup"><span data-stu-id="58532-110">So, you must configure a Domain Name System (DNS) suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="58532-111">Para obtener información detallada acerca de cómo agregar un sufijo DNS para un nombre de equipo, vea [Configurar DNS para admitir servidores perimetrales](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span><span class="sxs-lookup"><span data-stu-id="58532-111">For details about adding a DNS suffix to a computer name, see [Configure DNS for Edge Support](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx)</span></span>


