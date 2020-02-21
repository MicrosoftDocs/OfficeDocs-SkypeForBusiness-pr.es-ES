---
title: Lync Server 2013 compatibilidad con resistencia de sitios metropolitana de Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7f1c637c49784dd5acb81c26d8ab36400730278
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a><span data-ttu-id="1a787-102">Lync Server 2010 resistencia del sitio metropolitana</span><span class="sxs-lookup"><span data-stu-id="1a787-102">Lync Server 2010 metropolitan site resiliency</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a787-103">_**Última modificación del tema:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="1a787-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="1a787-104">La solución de resistencia de sitios metropolitana compatible con Lync Server 2010 no es compatible con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a787-104">The metropolitan site resiliency solution supported for Lync Server 2010 is not supported for Lync Server 2013.</span></span> <span data-ttu-id="1a787-105">Esta solución incluye la expansión de un grupo de servidores front-end a través de dos centros de datos en la misma área metropolitana.</span><span class="sxs-lookup"><span data-stu-id="1a787-105">This solution involved spanning a single Front End pool across two data centers in the same metropolitan area.</span></span>

<span data-ttu-id="1a787-106">La solución de resistencia de sitios metropolitana se ha diseñado para recuperarse de la pérdida de un centro de seguridad completo.</span><span class="sxs-lookup"><span data-stu-id="1a787-106">The metropolitan site resiliency solution was designed to recover from the loss of a full datacenter.</span></span> <span data-ttu-id="1a787-107">Cuando expande el grupo de servidores en dos centros de recursos, normalmente pone la mitad de los servidores front-end en un centro de recursos y la otra mitad en el segundo centro de recursos.</span><span class="sxs-lookup"><span data-stu-id="1a787-107">When you span your pool across two datacenters, you typically put half of your front ends in one datacenter and the other half in the second datacenter.</span></span> <span data-ttu-id="1a787-108">Si pierde un centro de información completo, perderá la mitad de los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="1a787-108">If you lose an entire datacenter, you have lost half of your Front End Servers.</span></span> <span data-ttu-id="1a787-109">Esto puede causar problemas con el nuevo modelo de sistemas distribuidos para grupos de servidores front-end en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a787-109">This can cause issues with the new distributed system model for Front End Pools in Lync Server 2013.</span></span> <span data-ttu-id="1a787-110">Para obtener más información, vea [topologías y componentes para los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="1a787-110">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

