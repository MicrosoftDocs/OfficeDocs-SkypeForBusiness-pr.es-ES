---
title: 'Escenario de migración estándar: alto nivel'
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62a557d8b5a0f2a3e1e0f248b01795e75c02b3a1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529807"
---
# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="77044-102">Escenario de migración estándar: alto nivel</span><span class="sxs-lookup"><span data-stu-id="77044-102">Standard migration scenario - high-level</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77044-103">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="77044-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="77044-104">Use los siguientes elementos como punto de partida al migrar Lync Server 2010, Group chat u Office Communications Server 2007 R2 Group chat a Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="77044-104">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="77044-105">La ruta de migración estándar de Lync Server 2013 es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="77044-105">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="77044-106">Su organización ha implementado anteriormente Lync Server 2010, Group chat o un chat en grupo de Office Communications Server 2007 R2 y desea implementar Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="77044-106">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="77044-107">Implemente Lync Server 2013 y, a continuación, implemente grupos de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="77044-107">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="77044-108">Prepare y planifique la migración de sus salones de chat persistente y determine el momento adecuado para apagar el sistema para la migración.</span><span class="sxs-lookup"><span data-stu-id="77044-108">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="77044-109">Ejecute los cmdlets de Windows PowerShell para la migración (**Export-CsPersistentChatData** y **Import-CsPersistentChatData**) para mover el contenido al servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="77044-109">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="77044-110">Compruebe que la migración se haya efectuado correctamente.</span><span class="sxs-lookup"><span data-stu-id="77044-110">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="77044-111">Dé de baja la implementación heredada.</span><span class="sxs-lookup"><span data-stu-id="77044-111">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="77044-112">Configure el servidor de chat persistente para que los clientes heredados puedan conectarse a Lync Server 2013, el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="77044-112">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="77044-113">Esto es necesario porque se tarda tiempo en implementar nuevos clientes y probablemente quiera habilitar los usuarios existentes con clientes heredados para que obtengan acceso a sus salones de chat lo más pronto posible.</span><span class="sxs-lookup"><span data-stu-id="77044-113">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="77044-114">Implemente nuevos clientes, a la vez que sigue contribuyendo a garantizar que los trabajadores con chat de grupo heredado (clientes) puedan acceder a sus salones de chat.</span><span class="sxs-lookup"><span data-stu-id="77044-114">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

