---
title: 'Escenario de migración estándar: alto nivel'
description: 'Escenario de migración estándar: alto nivel.'
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
ms.openlocfilehash: a931b76e528b7e6468f6b7e7b9a718724d27501f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573166"
---
# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="0ce5e-103">Escenario de migración estándar: alto nivel</span><span class="sxs-lookup"><span data-stu-id="0ce5e-103">Standard migration scenario - high-level</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ce5e-104">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="0ce5e-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="0ce5e-105">Use los siguientes elementos como punto de partida al migrar Lync Server 2010, Group chat u Office Communications Server 2007 R2 Group chat a Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0ce5e-105">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="0ce5e-106">La ruta de migración estándar de Lync Server 2013 es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ce5e-106">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="0ce5e-107">Su organización ha implementado anteriormente Lync Server 2010, Group chat o un chat en grupo de Office Communications Server 2007 R2 y desea implementar Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0ce5e-107">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="0ce5e-108">Implemente Lync Server 2013 y, a continuación, implemente grupos de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0ce5e-108">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="0ce5e-109">Prepare y planifique la migración de sus salones de chat persistente y determine el momento adecuado para apagar el sistema para la migración.</span><span class="sxs-lookup"><span data-stu-id="0ce5e-109">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="0ce5e-110">Ejecute los cmdlets de Windows PowerShell para la migración (**Export-CsPersistentChatData** y **Import-CsPersistentChatData**) para mover el contenido al servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0ce5e-110">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="0ce5e-111">Compruebe que la migración se haya efectuado correctamente.</span><span class="sxs-lookup"><span data-stu-id="0ce5e-111">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="0ce5e-112">Dé de baja la implementación heredada.</span><span class="sxs-lookup"><span data-stu-id="0ce5e-112">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="0ce5e-113">Configure el servidor de chat persistente para que los clientes heredados puedan conectarse a Lync Server 2013, el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0ce5e-113">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="0ce5e-114">Esto es necesario porque se tarda tiempo en implementar nuevos clientes y probablemente quiera habilitar los usuarios existentes con clientes heredados para que obtengan acceso a sus salones de chat lo más pronto posible.</span><span class="sxs-lookup"><span data-stu-id="0ce5e-114">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="0ce5e-115">Implemente nuevos clientes, a la vez que sigue contribuyendo a garantizar que los trabajadores con chat de grupo heredado (clientes) puedan acceder a sus salones de chat.</span><span class="sxs-lookup"><span data-stu-id="0ce5e-115">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

