---
title: 'Lync Server 2013: administración de nodos de monitor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7edddd1a1bb67dc4bf3df5b7809aa76b2397e56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="b1a20-102">Administración de nodos de monitor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1a20-102">Managing watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1a20-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="b1a20-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="b1a20-104">Además de modificar las transacciones sintéticas que se ejecutan en un nodo de monitor, los administradores también pueden usar el cmdlet **set-CsWatcherNodeConfiguration** para llevar a cabo otras dos tareas importantes: habilitar y deshabilitar el nodo de monitor, y configurar el nodo de monitor para que use direcciones URL internas o direcciones URL externas al ejecutar sus pruebas.</span><span class="sxs-lookup"><span data-stu-id="b1a20-104">In addition to modifying the synthetic transactions that are executed on a watcher node, administrators can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal URLs or external URLs when running its tests.</span></span>

<span data-ttu-id="b1a20-105">De forma predeterminada, los nodos de monitor están diseñadas para ejecutar periódicamente todas sus transacciones sintéticas habilitadas.</span><span class="sxs-lookup"><span data-stu-id="b1a20-105">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="b1a20-106">Sin embargo, a veces es posible que debas suspender dichas transacciones.</span><span class="sxs-lookup"><span data-stu-id="b1a20-106">Sometimes, however, you may need to suspend those transactions.</span></span> <span data-ttu-id="b1a20-107">Por ejemplo, si el nodo de monitor está desconectado temporalmente de la red y, a continuación, no hay ningún motivo para ejecutar las transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="b1a20-107">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="b1a20-108">Sin la conectividad de red, se garantizará el error de esas transacciones.</span><span class="sxs-lookup"><span data-stu-id="b1a20-108">Without network connectivity, those transactions are guaranteed to fail.</span></span> <span data-ttu-id="b1a20-109">Si desea deshabilitar temporalmente un nodo de monitor, ejecute un comando similar a este desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="b1a20-109">If you want to temporarily disable a watcher node, run a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

<span data-ttu-id="b1a20-110">Este comando deshabilitará la ejecución de transacciones sintéticas en el nodo de monitor ATL-Watcher-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b1a20-110">This command will disable the execution of synthetic transactions on the watcher node atl-watcher- 001.litwareinc.com.</span></span> <span data-ttu-id="b1a20-111">Para volver a ejecutarlas, establezca la propiedad Enabled en True ($True):</span><span class="sxs-lookup"><span data-stu-id="b1a20-111">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> <span data-ttu-id="b1a20-p103">La propiedad Enabled sirve para activar y desactivar nodos de monitor. En caso de que quiera eliminar un nodo de monitor permanentemente, use el cmdlet <STRONG>Remove-CsWatcherNodeConfiguration</STRONG>:</span><span class="sxs-lookup"><span data-stu-id="b1a20-p103">The Enabled property can be used to turn watcher nodes on or off. If you want to permanently delete a watcher node, use the <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet:</span></span><BR><span data-ttu-id="b1a20-114">Remove-CsWatcherNodeConfiguration: Identity "atl-watcher-001.litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="b1a20-114">Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"</span></span><BR><span data-ttu-id="b1a20-115">Ese comando quita todos los parámetros de configuración de nodo de monitor del equipo especificado, lo que impide que el equipo ejecute automáticamente transacciones sintéticas.</span><span class="sxs-lookup"><span data-stu-id="b1a20-115">That command removes all the watcher node configuration settings from the specified computer, which prevents the computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="b1a20-116">Sin embargo, el comando no desinstala los archivos del agente de System Center ni los archivos de sistema de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1a20-116">However, the command does not uninstall the System Center agent files or the Lync Server 2013 system files.</span></span>



</div>

<span data-ttu-id="b1a20-117">De forma predeterminada, los nodos de monitor usan las direcciones URL externas de una organización al realizar sus pruebas.</span><span class="sxs-lookup"><span data-stu-id="b1a20-117">By default, watcher nodes use an organization's external URLs when conducting their tests.</span></span> <span data-ttu-id="b1a20-118">Sin embargo, los nodos de monitor también se pueden configurar para usar las direcciones URL internas de la organización.</span><span class="sxs-lookup"><span data-stu-id="b1a20-118">However, watcher nodes can also be configured to use the organization's internal URLs.</span></span> <span data-ttu-id="b1a20-119">Esto permite a los administradores comprobar el acceso a la dirección URL para los usuarios que se encuentran dentro de la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="b1a20-119">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="b1a20-120">Para configurar un nodo de monitor para que use direcciones URL internas en lugar de direcciones URL externas, establece la propiedad UseInternalWebUrls en true ($True):</span><span class="sxs-lookup"><span data-stu-id="b1a20-120">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebUrls property to True ($True):</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

<span data-ttu-id="b1a20-121">Si restablece esta propiedad en el valor predeterminado de falso ($False), el observador usará las direcciones URL externas:</span><span class="sxs-lookup"><span data-stu-id="b1a20-121">If you reset this property to the default value of False ($False), the watcher will then use the external URLs:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

