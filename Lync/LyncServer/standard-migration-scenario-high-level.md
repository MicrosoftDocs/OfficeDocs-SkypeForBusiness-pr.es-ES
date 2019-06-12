---
title: Escenario de migración estándar - Alto nivel
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69349b90c6845d8a3f3d5ed13544da4fe4832eb8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="840bf-102">Escenario de migración estándar - Alto nivel</span><span class="sxs-lookup"><span data-stu-id="840bf-102">Standard migration scenario - high-level</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="840bf-103">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="840bf-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="840bf-104">Use los siguientes elementos como punto de partida al migrar Lync Server 2010, chat grupal u Office Communications Server 2007 R2 chat grupal a Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="840bf-104">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="840bf-105">La ruta de migración estándar de Lync Server 2013 es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="840bf-105">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="840bf-106">Su organización ha implementado previamente Lync Server 2010, chat grupal o chat grupal de Office Communications Server 2007 R2 y desea implementar Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="840bf-106">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="840bf-107">Implemente Lync Server 2013 y, a continuación, implemente grupos de servidores de chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="840bf-107">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="840bf-108">Prepare y planifique la migración de sus salones de chat persistentes y determine el momento adecuado para apagar el sistema para la migración.</span><span class="sxs-lookup"><span data-stu-id="840bf-108">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="840bf-109">Ejecute los cmdlets de Windows PowerShell para la migración (**Export-CsPersistentChatData** e **Import-CsPersistentChatData**) para mover el contenido a un servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="840bf-109">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="840bf-110">Comprobar que la migración se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="840bf-110">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="840bf-111">Dar de baja la implementación heredada.</span><span class="sxs-lookup"><span data-stu-id="840bf-111">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="840bf-112">Configure el servidor de chat persistente para que los clientes heredados puedan conectarse a Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="840bf-112">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="840bf-113">Esto es necesario porque lleva tiempo implementar nuevos clientes y quiere permitir que los usuarios existentes con clientes heredados tengan acceso a sus salones de chat tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="840bf-113">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="840bf-114">Implemente nuevos clientes y siga ayudando a garantizar que los trabajadores con chat grupal heredado (clientes) puedan acceder a sus salones de chat.</span><span class="sxs-lookup"><span data-stu-id="840bf-114">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

