---
title: 'Lync Server 2013: deshabilitar la recogida de llamadas grupales para usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76b7e0d17b91accdab0f1590d9fc505dec42f430
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="47e6b-102">Deshabilitar la recogida de llamadas grupales para los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47e6b-102">Disable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47e6b-103">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="47e6b-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="47e6b-104">Use el siguiente procedimiento para deshabilitar la recogida de llamadas grupales para un usuario.</span><span class="sxs-lookup"><span data-stu-id="47e6b-104">Use the following procedure to disable Group Call Pickup for a user.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="47e6b-105">Al deshabilitar la recogida de llamadas grupales para un usuario, el número del grupo de recogida de llamadas que se asignó al usuario no se conserva.</span><span class="sxs-lookup"><span data-stu-id="47e6b-105">When you disable Group Call Pickup for a user, the call pickup group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="47e6b-106">Si posteriormente deseas volver a habilitar la recogida de llamadas grupales para ese usuario, debes asignar el número del grupo de recogida de llamadas de nuevo con el parámetro/enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="47e6b-106">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the call pickup group number again with the /enablegrouppickup parameter.</span></span>



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a><span data-ttu-id="47e6b-107">Para deshabilitar la recogida de llamadas grupales para un usuario</span><span class="sxs-lookup"><span data-stu-id="47e6b-107">To disable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="47e6b-108">Inicie sesión como administrador en el equipo en el que haya instalado la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="47e6b-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="47e6b-109">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="47e6b-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    <span data-ttu-id="47e6b-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="47e6b-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="47e6b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="47e6b-111">See Also</span></span>


[<span data-ttu-id="47e6b-112">Asignar números de recogida de llamadas grupales a los usuarios de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47e6b-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="47e6b-113">Habilitar la recogida de llamadas grupales para los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47e6b-113">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

