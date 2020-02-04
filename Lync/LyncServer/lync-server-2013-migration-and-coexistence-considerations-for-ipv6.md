---
title: 'Lync Server 2013: Consideraciones sobre coexistencia y migración para IPv6'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5785b270aa3070c2b1592112ab4d5ae582e52bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="e3ae2-102">Consideraciones sobre coexistencia y migración para IPv6 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3ae2-102">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3ae2-103">_**Última modificación del tema:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="e3ae2-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="e3ae2-104">La versión 6 de IP (IPv6) no es compatible con Lync Server 2010 o con Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="e3ae2-104">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="e3ae2-105">Para fines piloto, puede probar Lync Server 2010 y Lync Server 2013, coexistencia de pila doble.</span><span class="sxs-lookup"><span data-stu-id="e3ae2-105">For piloting purposes, you can test Lync Server 2010 and Lync Server 2013 dual-stack coexistence.</span></span> <span data-ttu-id="e3ae2-106">Le recomendamos que todos los grupos de un sitio central determinado se actualicen a Lync Server 2013 antes de habilitar IPv6 (red de pila doble) para cualquiera de los grupos.</span><span class="sxs-lookup"><span data-stu-id="e3ae2-106">We recommend that all pools for a given central site are upgraded to Lync Server 2013 before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="e3ae2-107">Si necesita configurar un grupo solo para IPv6, recomendamos configurar un grupo de servidores solo IPv6 en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="e3ae2-107">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>

<span data-ttu-id="e3ae2-108">Se admiten los siguientes escenarios durante la migración y coexistencia:</span><span class="sxs-lookup"><span data-stu-id="e3ae2-108">The following scenarios are supported during migration and coexistence:</span></span>

  - <span data-ttu-id="e3ae2-109">Lync Server 2013, Lync Server 2010 y los grupos de Office Communications Server 2007 R2 en modo IPv4, coexistencia con Lync Server 2013 en modo Dual Stack.</span><span class="sxs-lookup"><span data-stu-id="e3ae2-109">Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2 pools in IPv4 mode, coexisting with Lync Server 2013 in dual-stack mode.</span></span>

  - <span data-ttu-id="e3ae2-110">Grupo de servidores de Lync Server 2013 en modo de solo IPv6, si el grupo de solo IPv6 está en silos.</span><span class="sxs-lookup"><span data-stu-id="e3ae2-110">Lync Server 2013 pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

