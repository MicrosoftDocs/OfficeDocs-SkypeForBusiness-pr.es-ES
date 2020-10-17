---
title: 'Lync Server 2013: Planeación y configuración de IPv6'
description: 'Lync Server 2013: Planeación y configuración de IPv6.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for and configuring IPv6
ms:assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204624(v=OCS.15)
ms:contentKeyID: 48183236
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c63268bd92fc9d3b683cfa05ab49f01ea56d6ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554366"
---
# <a name="planning-for-and-configuring-ipv6-in-lync-server-2013"></a><span data-ttu-id="81925-103">Planeación y configuración de IPv6 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81925-103">Planning for and configuring IPv6 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81925-104">_**Última modificación del tema:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="81925-104">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="81925-105">Lync Server 2013 incluye compatibilidad con direcciones IP versión 6 (IPv6), junto con soporte técnico continuado de direcciones IP versión 4 (IPv4).</span><span class="sxs-lookup"><span data-stu-id="81925-105">Lync Server 2013 includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> <span data-ttu-id="81925-106">Las direcciones IPv4 son direcciones de 32 bits que permiten a los equipos comunicarse a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="81925-106">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="81925-107">Debido al creciente número de dispositivos en todo el mundo, las direcciones IPv4 disponibles se han agotado. Debido a esto, muchos dispositivos nuevos se mueven a usar direcciones IPv6.</span><span class="sxs-lookup"><span data-stu-id="81925-107">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="81925-108">Las direcciones IPv6 realizan la misma función que las direcciones IPv4 (con algunas funciones adicionales), pero en lugar de usar solo 32 bits, usan 128 bits.</span><span class="sxs-lookup"><span data-stu-id="81925-108">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="81925-109">Esto no solo proporciona un nuevo conjunto de direcciones, sino también un número mucho más elevado de ellas.</span><span class="sxs-lookup"><span data-stu-id="81925-109">This provides not only a new set of addresses, but also a much larger number of them.</span></span> <span data-ttu-id="81925-110">Las direcciones IPv4 típicas son similares a esta: 192.0.2.235, mientras que las direcciones IPv6 son de este tipo: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span><span class="sxs-lookup"><span data-stu-id="81925-110">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="81925-111">El cambio en el formato y la funcionalidad de los dispositivos que usan direcciones IPv6 requiere varias consideraciones de implementación y configuración en la instalación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81925-111">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Lync Server 2013 installation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="81925-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="81925-112">In This Section</span></span>

  - [<span data-ttu-id="81925-113">Información general sobre los tipos de direcciones IP para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81925-113">Overview of IP address types for Lync Server 2013</span></span>](lync-server-2013-overview-of-ip-address-types.md)

  - [<span data-ttu-id="81925-114">Requisitos técnicos para IPv6 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81925-114">Technical requirements for IPv6 in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-ipv6.md)

  - [<span data-ttu-id="81925-115">Consideraciones sobre la coexistencia y la migración para IPv6 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81925-115">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>](lync-server-2013-migration-and-coexistence-considerations-for-ipv6.md)

  - [<span data-ttu-id="81925-116">Configurar tipos de direcciones IP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81925-116">Configure IP address types in Lync Server 2013</span></span>](lync-server-2013-configure-ip-address-types.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

