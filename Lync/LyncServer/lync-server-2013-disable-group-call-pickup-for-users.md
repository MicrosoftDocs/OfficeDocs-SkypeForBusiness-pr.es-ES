---
title: 'Lync Server 2013: deshabilitar la atención de llamadas grupales para los usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 777ca1494738707014c2e121b56e8d01e87f4a3b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="8dc51-102">Deshabilitar la atención de llamadas grupales para los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dc51-102">Disable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dc51-103">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="8dc51-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="8dc51-104">Use el siguiente procedimiento para deshabilitar la atención de llamadas grupales para un usuario.</span><span class="sxs-lookup"><span data-stu-id="8dc51-104">Use the following procedure to disable Group Call Pickup for a user.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8dc51-105">Cuando se deshabilita la recepción de llamadas de grupo para un usuario, no se conserva el número del grupo de atención de llamadas que se asignó al usuario.</span><span class="sxs-lookup"><span data-stu-id="8dc51-105">When you disable Group Call Pickup for a user, the call pickup group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="8dc51-106">Si, posteriormente, desea volver a habilitar la atención de llamadas grupales para ese usuario, debe asignar el número de grupo de recogida de llamadas de nuevo con el parámetro/enablegrouppickup.</span><span class="sxs-lookup"><span data-stu-id="8dc51-106">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the call pickup group number again with the /enablegrouppickup parameter.</span></span>



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a><span data-ttu-id="8dc51-107">Para deshabilitar la recepción de llamadas de grupo para un usuario</span><span class="sxs-lookup"><span data-stu-id="8dc51-107">To disable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="8dc51-108">Inicie sesión en el equipo donde instaló la herramienta SEFAUtil con derechos de administrador.</span><span class="sxs-lookup"><span data-stu-id="8dc51-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="8dc51-109">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="8dc51-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    <span data-ttu-id="8dc51-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8dc51-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8dc51-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="8dc51-111">See Also</span></span>


[<span data-ttu-id="8dc51-112">Asignar números de llamada de llamada de grupo a los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dc51-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="8dc51-113">Habilitar la atención de llamadas grupales para los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dc51-113">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

