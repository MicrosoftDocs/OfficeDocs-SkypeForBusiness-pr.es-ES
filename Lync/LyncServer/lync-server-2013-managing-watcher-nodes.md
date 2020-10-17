---
title: 'Lync Server 2013: administración de nodos de monitor'
description: 'Lync Server 2013: administración de nodos de monitor.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1795b09bbca73d8157cf796ceeaaeafb9cc2ebc5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556616"
---
# <a name="managing-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="8ce33-103">Administración de nodos de monitor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ce33-103">Managing watcher nodes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ce33-104">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="8ce33-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="8ce33-105">Aparte de modificar las transacciones sintéticas que se ejecutan en un nodo de monitor, los administradores también pueden usar el cmdlet **Set-CsWatcherNodeConfiguration** para llevar a cabo otras tareas importantes, como habilitar y deshabilitar el nodo de monitor o configurarlo para que use direcciones URL internas o externas cuando ejecute sus pruebas.</span><span class="sxs-lookup"><span data-stu-id="8ce33-105">In addition to modifying the synthetic transactions that are executed on a watcher node, administrators can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal URLs or external URLs when running its tests.</span></span>

<span data-ttu-id="8ce33-106">De forma predeterminada, los nodos de monitor están diseñados para ejecutar periódicamente todas sus transacciones sintéticas habilitadas.</span><span class="sxs-lookup"><span data-stu-id="8ce33-106">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="8ce33-107">Sin embargo, a veces es posible que deba suspender esas transacciones.</span><span class="sxs-lookup"><span data-stu-id="8ce33-107">Sometimes, however, you may need to suspend those transactions.</span></span> <span data-ttu-id="8ce33-108">Por ejemplo, si el nodo de monitor se desconecta temporalmente de la red, no hay ninguna razón para ejecutar las transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="8ce33-108">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="8ce33-109">Sin la conectividad de red, se garantizará que se producirá un error en esas transacciones.</span><span class="sxs-lookup"><span data-stu-id="8ce33-109">Without network connectivity, those transactions are guaranteed to fail.</span></span> <span data-ttu-id="8ce33-110">Si desea deshabilitar temporalmente un nodo de monitor, ejecute un comando similar al siguiente desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="8ce33-110">If you want to temporarily disable a watcher node, run a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

<span data-ttu-id="8ce33-p102">Con este comando se deshabilita la ejecución de transacciones sintéticas en el nodo de monitor atl-watcher- 001.litwareinc.com. Para volver a ejecutarlas, establezca la propiedad Enabled en True ($True):</span><span class="sxs-lookup"><span data-stu-id="8ce33-p102">This command will disable the execution of synthetic transactions on the watcher node atl-watcher- 001.litwareinc.com. To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> <span data-ttu-id="8ce33-113">La propiedad Enabled sirve para activar y desactivar nodos de monitor.</span><span class="sxs-lookup"><span data-stu-id="8ce33-113">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="8ce33-114">En caso de que quiera eliminar un nodo de monitor permanentemente, use el cmdlet <STRONG>Remove-CsWatcherNodeConfiguration</STRONG>:</span><span class="sxs-lookup"><span data-stu-id="8ce33-114">If you want to permanently delete a watcher node, use the <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet:</span></span><BR><span data-ttu-id="8ce33-115">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="8ce33-115">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span></span><BR><span data-ttu-id="8ce33-116">Con este comando se elimina toda la configuración de nodo de monitor del equipo en cuestión, lo que evita que se ejecuten transacciones sintéticas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8ce33-116">That command removes all the watcher node configuration settings from the specified computer, which prevents the computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="8ce33-117">Sin embargo, el comando no desinstala los archivos del agente de System Center o los archivos del sistema de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ce33-117">However, the command does not uninstall the System Center agent files or the Lync Server 2013 system files.</span></span>



</div>

<span data-ttu-id="8ce33-p105">Cuando realizan pruebas, los nodos de monitor usan de forma predeterminada las direcciones URL externas de una organización, aunque se pueden configurar para que usen las direcciones URL internas. Esto permite que los administradores comprueben el acceso a la dirección URL de los usuarios de dentro de la red perimetral. Para configurar un nodo de monitor para que use direcciones URL internas en lugar de externas, establezca la propiedad UseInternalWebUrls en True ($True):</span><span class="sxs-lookup"><span data-stu-id="8ce33-p105">By default, watcher nodes use an organization's external URLs when conducting their tests. However, watcher nodes can also be configured to use the organization's internal URLs. This enables administrators to verify URL access for users located inside the perimeter network. To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebUrls property to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

<span data-ttu-id="8ce33-122">Si restablece esta propiedad a su valor predeterminado de False ($False), el monitor usará las direcciones URL externas:</span><span class="sxs-lookup"><span data-stu-id="8ce33-122">If you reset this property to the default value of False ($False), the watcher will then use the external URLs:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

