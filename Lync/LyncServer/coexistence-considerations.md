---
title: Consideraciones sobre la coexistencia
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7052042afbc3927e1047a9c2fbb30a71168f317
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a><span data-ttu-id="37a60-102">Consideraciones sobre la coexistencia</span><span class="sxs-lookup"><span data-stu-id="37a60-102">Coexistence considerations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37a60-103">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="37a60-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="37a60-104">Después de la migración, solo existirá un grupo de servidores de chat persistente y Lync Server 2013 y podrá retirar su implementación heredada.</span><span class="sxs-lookup"><span data-stu-id="37a60-104">After migration, only a Lync Server 2013, Persistent Chat Server pool will exist, and you can decommission your legacy deployment.</span></span>

<span data-ttu-id="37a60-105">Antes de que se complete la migración y antes de que haya retirado la implementación actual del servidor de chat de grupo, puede tener alguna de las siguientes implementaciones:</span><span class="sxs-lookup"><span data-stu-id="37a60-105">Before migration completes and before you have decommissioned your current Group Chat Server deployment completely, you may have any of the following deployments:</span></span>

  - <span data-ttu-id="37a60-106">Lync Server 2013, grupo de servidores de chat persistente, que debe estar alojado en un grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37a60-106">Lync Server 2013, Persistent Chat Server pool, which must be homed on a Lync Server 2013 pool.</span></span>

  - <span data-ttu-id="37a60-107">Lync Server 2010, grupo de chats en grupo, que debe estar alojado en un grupo de servidores de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="37a60-107">Lync Server 2010, Group Chat pool, which must be homed on a Lync Server 2010 pool.</span></span>

  - <span data-ttu-id="37a60-108">Grupo de servidores de chat en grupo de Office Communications Server 2007 R2, que debe estar alojado en un grupo de servidores de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="37a60-108">Office Communications Server 2007 R2 Group Chat pool, which must be homed on an Office Communications Server 2007 R2 pool.</span></span>

<span data-ttu-id="37a60-109">These deployments can exist side by side.</span><span class="sxs-lookup"><span data-stu-id="37a60-109">These deployments can exist side by side.</span></span> <span data-ttu-id="37a60-110">However the categories, rooms, and add-ins in one deployment do not interact with those in the accompanying deployment.</span><span class="sxs-lookup"><span data-stu-id="37a60-110">However the categories, rooms, and add-ins in one deployment do not interact with those in the accompanying deployment.</span></span>

<span data-ttu-id="37a60-111">Mediante la configuración manual, un cliente heredado (cliente de chat en grupo) puede conectarse a un grupo de servidores a la vez para Office Communications Server 2007 R2, Lync Server 2010, chat en grupo o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37a60-111">Using manual configuration, a legacy client (Group Chat client) can connect to one pool at a time for Office Communications Server 2007 R2, Lync Server 2010, Group Chat, or Lync Server 2013.</span></span>

<span data-ttu-id="37a60-112">Lync 2013 (cliente) solo puede interactuar con el grupo de servidores de chat persistente de Lync Server 2013 y no con grupos de servidores de chat de grupo heredados.</span><span class="sxs-lookup"><span data-stu-id="37a60-112">The Lync 2013 (client) can interact only with the Lync Server 2013, Persistent Chat Server pool, not with legacy Group Chat Server pools.</span></span> <span data-ttu-id="37a60-113">Para usar chat persistente en un equipo con Lync 2013 (cliente), el usuario debe estar alojado en Lync 2013 y habilitado por la Directiva.</span><span class="sxs-lookup"><span data-stu-id="37a60-113">To use Persistent Chat in a Lync 2013 (client), the user must be homed on Lync 2013 and enabled by policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

