---
title: 'Lync Server 2013: habilitar la recogida de llamadas grupales para los usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fc2f513960371d0115b63260d35180f319bd923
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="2cd71-102">Habilitar la recogida de llamadas grupales para los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cd71-102">Enable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cd71-103">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="2cd71-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="2cd71-104">Use la herramienta del kit de recursos de SEFAUtil para habilitar la recogida de llamadas grupales para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2cd71-104">Use the SEFAUtil resource kit tool to enable Group Call Pickup for users.</span></span> <span data-ttu-id="2cd71-105">Los usuarios deben tener asignado un número de grupo con el tipo GroupPickup en la tabla llamada de la órbita de la llamada para tener habilitada la recopilación de llamadas de grupo.</span><span class="sxs-lookup"><span data-stu-id="2cd71-105">Users must be assigned a group number with type GroupPickup in the call park orbit table to have Group Call Pickup enabled.</span></span> <span data-ttu-id="2cd71-106">Para asignar un número de grupo de recogida de llamadas y habilitar la recogida de llamadas grupales al mismo tiempo, use el parámetro/enablegrouppickup cuando ejecute SEFAUtil. exe.</span><span class="sxs-lookup"><span data-stu-id="2cd71-106">You assign a call pickup group number and enable Group Call Pickup at the same time by using the /enablegrouppickup parameter when you run SEFAUtil.exe.</span></span>

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="2cd71-107">Para habilitar la recogida de llamadas grupales para un usuario</span><span class="sxs-lookup"><span data-stu-id="2cd71-107">To enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="2cd71-108">Inicie sesión como administrador en el equipo en el que haya instalado la herramienta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="2cd71-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="2cd71-109">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="2cd71-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="2cd71-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2cd71-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2cd71-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="2cd71-111">See Also</span></span>


[<span data-ttu-id="2cd71-112">Asignar números de recogida de llamadas grupales a los usuarios de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cd71-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="2cd71-113">Deshabilitar la recogida de llamadas grupales para los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cd71-113">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

