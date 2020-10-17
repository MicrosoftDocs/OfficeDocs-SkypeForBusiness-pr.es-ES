---
title: 'Lync Server 2013: mejorado 9-1-1 (E9-1-1) y servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enhanced 9-1-1 (E9-1-1) and Mediation Server
ms:assetid: d231221f-5596-4a87-a463-269f5bcce65f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398903(v=OCS.15)
ms:contentKeyID: 48185448
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1620d9a4d1625335a52c474d608377bd2529425d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526807"
---
# <a name="enhanced-9-1-1-e9-1-1-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="13909-102">Enhanced 9-1-1 (E9-1-1) y servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13909-102">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13909-103">_**Última modificación del tema:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="13909-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="13909-104">El servidor de mediación cuenta con capacidades ampliadas para poder interactuar correctamente con los proveedores de servicios de 9-1-1 mejorado (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="13909-104">The Mediation Server has extended capabilities so that it can correctly interact with Enhanced 9-1-1 (E9-1-1) service providers.</span></span> <span data-ttu-id="13909-105">No se necesita ninguna configuración especial en el servidor de mediación; las extensiones SIP necesarias para la interacción de E9-1-1 se incluyen, de forma predeterminada, en el protocolo SIP del servidor de mediación para sus interacciones con una puerta de enlace RTC (puerta de enlace RTC, IP-PBX o el SBC de un proveedor de servicios de telefonía por Internet, incluidos los proveedores de servicios E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="13909-105">No special configuration is needed on the Mediation Server; the SIP extensions required for E9-1-1 interaction are, by default, included in the Mediation Server’s SIP protocol for its interactions with a gateway peer (PSTN gateway, IP-PBX, or the SBC of an Internet Telephony Service Provider, including E9-1-1 Service Providers)</span></span>

<span data-ttu-id="13909-106">Si el tronco SIP a un proveedor de servicios E9-1-1 se puede terminar en un grupo de servidores de mediación existente o necesitará servidores de mediación independientes, depende de si el SBC E9-1-1 puede interactuar con un grupo de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="13909-106">Whether the SIP trunk to an E9-1-1 Service Provider can be terminated on an existing Mediation Server pool or will require stand-alone Mediation Servers will depend on whether the E9-1-1 SBC can interact with a pool of Mediation Servers.</span></span> <span data-ttu-id="13909-107">Para obtener más información, consulte [M:N trunk en Lync Server 2013](lync-server-2013-m-n-trunk.md).</span><span class="sxs-lookup"><span data-stu-id="13909-107">For details, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

