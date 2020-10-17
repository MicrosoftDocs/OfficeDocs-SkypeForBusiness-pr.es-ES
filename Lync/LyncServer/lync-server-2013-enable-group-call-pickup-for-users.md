---
title: 'Lync Server 2013: habilitar la atención de llamadas grupales para los usuarios'
description: 'Lync Server 2013: habilitar la atención de llamadas grupales para los usuarios.'
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
ms.openlocfilehash: 27951e9000fd17aac90339cf2a507757ae96a397
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559626"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="1aa52-103">Habilitar la atención de llamadas grupales para los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aa52-103">Enable Group Call Pickup for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1aa52-104">_**Última modificación del tema:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="1aa52-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="1aa52-105">Use la herramienta del kit de recursos de SEFAUtil para habilitar la atención de llamadas grupales para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="1aa52-105">Use the SEFAUtil resource kit tool to enable Group Call Pickup for users.</span></span> <span data-ttu-id="1aa52-106">Los usuarios deben tener asignado un número de grupo con el tipo GroupPickup en la tabla de órbitas de estacionamiento de llamadas para tener habilitada la recepción de llamadas de grupo.</span><span class="sxs-lookup"><span data-stu-id="1aa52-106">Users must be assigned a group number with type GroupPickup in the call park orbit table to have Group Call Pickup enabled.</span></span> <span data-ttu-id="1aa52-107">Puede asignar un número de grupo de atención de llamadas y habilitar la recogida de llamadas de grupo al mismo tiempo mediante el parámetro/enablegrouppickup al ejecutar SEFAUtil.exe.</span><span class="sxs-lookup"><span data-stu-id="1aa52-107">You assign a call pickup group number and enable Group Call Pickup at the same time by using the /enablegrouppickup parameter when you run SEFAUtil.exe.</span></span>

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="1aa52-108">Para habilitar la recepción de llamadas de grupo para un usuario</span><span class="sxs-lookup"><span data-stu-id="1aa52-108">To enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="1aa52-109">Inicie sesión en el equipo donde instaló la herramienta SEFAUtil con derechos de administrador.</span><span class="sxs-lookup"><span data-stu-id="1aa52-109">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="1aa52-110">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="1aa52-110">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="1aa52-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1aa52-111">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1aa52-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1aa52-112">See Also</span></span>


[<span data-ttu-id="1aa52-113">Asignar números de llamada de llamada de grupo a los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aa52-113">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="1aa52-114">Deshabilitar la atención de llamadas grupales para los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aa52-114">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

