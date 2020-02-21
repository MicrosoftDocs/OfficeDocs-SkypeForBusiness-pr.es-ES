---
title: 'Lync Server 2013: administración de nodos de monitor'
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
ms.openlocfilehash: f01d1375890d632052ee9b6110cf64111a6bdd20
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="1af60-102">Administración de nodos de monitor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1af60-102">Managing watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1af60-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="1af60-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="1af60-104">Aparte de modificar las transacciones sintéticas que se ejecutan en un nodo de monitor, los administradores también pueden usar el cmdlet **Set-CsWatcherNodeConfiguration** para llevar a cabo otras tareas importantes, como habilitar y deshabilitar el nodo de monitor o configurarlo para que use direcciones URL internas o externas cuando ejecute sus pruebas.</span><span class="sxs-lookup"><span data-stu-id="1af60-104">In addition to modifying the synthetic transactions that are executed on a watcher node, administrators can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal URLs or external URLs when running its tests.</span></span>

<span data-ttu-id="1af60-105">De forma predeterminada, los nodos de monitor están diseñados para ejecutar periódicamente todas sus transacciones sintéticas habilitadas.</span><span class="sxs-lookup"><span data-stu-id="1af60-105">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="1af60-106">Sin embargo, a veces es posible que deba suspender esas transacciones.</span><span class="sxs-lookup"><span data-stu-id="1af60-106">Sometimes, however, you may need to suspend those transactions.</span></span> <span data-ttu-id="1af60-107">Por ejemplo, si el nodo de monitor se desconecta temporalmente de la red, no hay ninguna razón para ejecutar las transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="1af60-107">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="1af60-108">Sin la conectividad de red, se garantizará que se producirá un error en esas transacciones.</span><span class="sxs-lookup"><span data-stu-id="1af60-108">Without network connectivity, those transactions are guaranteed to fail.</span></span> <span data-ttu-id="1af60-109">Si desea deshabilitar temporalmente un nodo de monitor, ejecute un comando similar al siguiente desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="1af60-109">If you want to temporarily disable a watcher node, run a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

<span data-ttu-id="1af60-p102">Con este comando se deshabilita la ejecución de transacciones sintéticas en el nodo de monitor atl-watcher- 001.litwareinc.com. Para volver a ejecutarlas, establezca la propiedad Enabled en True ($True):</span><span class="sxs-lookup"><span data-stu-id="1af60-p102">This command will disable the execution of synthetic transactions on the watcher node atl-watcher- 001.litwareinc.com. To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> <span data-ttu-id="1af60-112">La propiedad Enabled sirve para activar y desactivar nodos de monitor.</span><span class="sxs-lookup"><span data-stu-id="1af60-112">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="1af60-113">En caso de que quiera eliminar un nodo de monitor permanentemente, use el cmdlet <STRONG>Remove-CsWatcherNodeConfiguration</STRONG>:</span><span class="sxs-lookup"><span data-stu-id="1af60-113">If you want to permanently delete a watcher node, use the <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet:</span></span><BR><span data-ttu-id="1af60-114">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="1af60-114">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span></span><BR><span data-ttu-id="1af60-115">Con este comando se elimina toda la configuración de nodo de monitor del equipo en cuestión, lo que evita que se ejecuten transacciones sintéticas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1af60-115">That command removes all the watcher node configuration settings from the specified computer, which prevents the computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="1af60-116">Sin embargo, el comando no desinstala los archivos del agente de System Center o los archivos del sistema de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1af60-116">However, the command does not uninstall the System Center agent files or the Lync Server 2013 system files.</span></span>



</div>

<span data-ttu-id="1af60-p105">Cuando realizan pruebas, los nodos de monitor usan de forma predeterminada las direcciones URL externas de una organización, aunque se pueden configurar para que usen las direcciones URL internas. Esto permite que los administradores comprueben el acceso a la dirección URL de los usuarios de dentro de la red perimetral. Para configurar un nodo de monitor para que use direcciones URL internas en lugar de externas, establezca la propiedad UseInternalWebUrls en True ($True):</span><span class="sxs-lookup"><span data-stu-id="1af60-p105">By default, watcher nodes use an organization's external URLs when conducting their tests. However, watcher nodes can also be configured to use the organization's internal URLs. This enables administrators to verify URL access for users located inside the perimeter network. To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebUrls property to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

<span data-ttu-id="1af60-121">Si restablece esta propiedad a su valor predeterminado de False ($False), el monitor usará las direcciones URL externas:</span><span class="sxs-lookup"><span data-stu-id="1af60-121">If you reset this property to the default value of False ($False), the watcher will then use the external URLs:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

