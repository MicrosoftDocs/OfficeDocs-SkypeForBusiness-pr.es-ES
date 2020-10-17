---
title: 'Lync Server 2013: eliminar un intervalo de números de atención de llamadas de grupo'
description: 'Lync Server 2013: eliminar un intervalo de números de recepción de llamadas de grupo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Group Call Pickup number range
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945629(v=OCS.15)
ms:contentKeyID: 51541475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b40d423b64d29300741c55433864128897c3ac8f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566556"
---
# <a name="delete-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="eeebe-103">Eliminar un intervalo de números de atención de llamadas grupales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eeebe-103">Delete a Group Call Pickup number range in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eeebe-104">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="eeebe-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="eeebe-105">Use el siguiente procedimiento para eliminar un intervalo de números de atención de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="eeebe-105">Use the following procedure to delete a Group Call Pickup number range.</span></span>

<div>

## <a name="to-delete-a-call-pickup-group-number-range"></a><span data-ttu-id="eeebe-106">Para eliminar un intervalo de números del grupo de atención de llamadas</span><span class="sxs-lookup"><span data-stu-id="eeebe-106">To delete a call pickup group number range</span></span>

1.  <span data-ttu-id="eeebe-107">Inicie sesión en el equipo donde esté instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="eeebe-107">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="eeebe-108">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="eeebe-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="eeebe-109">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="eeebe-109">At the command line, type:</span></span>
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    <span data-ttu-id="eeebe-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="eeebe-110">For example:</span></span>
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eeebe-111">Para obtener más información sobre más opciones, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span><span class="sxs-lookup"><span data-stu-id="eeebe-111">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eeebe-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eeebe-112">See Also</span></span>


[<span data-ttu-id="eeebe-113">Crear o modificar un intervalo de órbitas de estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eeebe-113">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[<span data-ttu-id="eeebe-114">Remove-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="eeebe-114">Remove-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[<span data-ttu-id="eeebe-115">Get-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="eeebe-115">Get-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

