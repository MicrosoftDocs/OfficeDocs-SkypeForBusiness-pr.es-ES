---
title: 'Lync Server 2013: asignar números de llamada de llamadas de grupo a los usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b437b9da1abaa62d34a177c0188396c30bf7a3e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a><span data-ttu-id="2f635-102">Asignar números de llamada de llamada de grupo a los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f635-102">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f635-103">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="2f635-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="2f635-104">Después de agregar los números del grupo de recogida de llamadas de grupo a la tabla de órbitas de estacionamiento de llamadas, puede asignar los grupos a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2f635-104">After you add Group Call Pickup group numbers to the call park orbit table, you can assign the groups to users.</span></span> <span data-ttu-id="2f635-105">Use la herramienta de kit de recursos de activación de característica de extensión secundaria (SEFAUtil) para asignar grupos de recogida de llamadas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2f635-105">Use the secondary extension feature activation (SEFAUtil ) resource kit tool to assign call pickup groups to users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f635-106">En una implementación híbrida, no asigne un grupo de recogida de llamadas de grupo a los usuarios hospedados en línea.</span><span class="sxs-lookup"><span data-stu-id="2f635-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="2f635-107">Los usuarios hospedados en línea no pueden participar en la recogida de llamadas de grupo.</span><span class="sxs-lookup"><span data-stu-id="2f635-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="2f635-108">Es decir, otros usuarios no pueden contestar a sus llamadas y no pueden responder llamadas a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="2f635-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a><span data-ttu-id="2f635-109">Para asignar un grupo de recogida de llamadas grupales a un usuario</span><span class="sxs-lookup"><span data-stu-id="2f635-109">To assign a Group Call Pickup group to a user</span></span>

1.  <span data-ttu-id="2f635-110">Inicie sesión en el equipo donde instaló la herramienta SEFAUtil con derechos de administrador.</span><span class="sxs-lookup"><span data-stu-id="2f635-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="2f635-111">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="2f635-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="2f635-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2f635-112">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2f635-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f635-113">See Also</span></span>


[<span data-ttu-id="2f635-114">Habilitar la atención de llamadas grupales para los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f635-114">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
[<span data-ttu-id="2f635-115">Deshabilitar la atención de llamadas grupales para los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f635-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

