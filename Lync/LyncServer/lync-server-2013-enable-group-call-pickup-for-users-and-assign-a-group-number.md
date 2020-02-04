---
title: 'Lync Server 2013: habilitar la recogida de llamadas grupales para los usuarios y asignar un número de grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5ad9bbc6f5505e5778872a568bdbc80b3f7bf91
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a><span data-ttu-id="f8e43-102">Habilitar la recogida de llamadas grupales para los usuarios en Lync Server 2013 y asignar un número de grupo</span><span class="sxs-lookup"><span data-stu-id="f8e43-102">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8e43-103">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="f8e43-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="f8e43-104">Después de agregar los números del grupo de recogida de llamadas a la tabla de llamadas en órbita, asigne los números de grupo a los usuarios y habilite la recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="f8e43-104">After you add call pickup group numbers to the call park orbit table, you assign the group numbers to users and enable Group Call Pickup for them.</span></span> <span data-ttu-id="f8e43-105">Use la herramienta del kit de recursos de activación de características de extensión secundaria (SEFAUtil) para asignar números de grupo y habilitar la recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="f8e43-105">Use the secondary extension feature activation (SEFAUtil) resource kit tool to assign group numbers and enable Group Call Pickup.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8e43-106">En una implementación híbrida, no asigne un grupo de recogida de llamadas grupal a los usuarios alojados en línea.</span><span class="sxs-lookup"><span data-stu-id="f8e43-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="f8e43-107">Los usuarios alojados en Internet no pueden participar en la recogida de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="f8e43-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="f8e43-108">Es decir, otros usuarios no pueden contestar las llamadas y no pueden responder llamadas a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="f8e43-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="f8e43-109">Para asignar un número de grupo y habilitar la recogida de llamadas grupales para un usuario</span><span class="sxs-lookup"><span data-stu-id="f8e43-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="f8e43-110">Inicie sesión como administrador en el equipo en el que haya instalado la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="f8e43-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="f8e43-111">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f8e43-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="f8e43-112">Por ejemplo, para asignar el número de grupo 199 a un usuario:</span><span class="sxs-lookup"><span data-stu-id="f8e43-112">For example, to assign group number 199 to a user:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f8e43-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8e43-113">See Also</span></span>


[<span data-ttu-id="f8e43-114">Deshabilitar la recogida de llamadas grupales para los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8e43-114">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

