---
title: 'Lync Server 2013: eliminación de una directiva de ubicación'
description: 'Lync Server 2013: eliminación de una directiva de ubicación.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88935c00a60de377c9812a4d119708fd610338ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575846"
---
# <a name="deleting-a-location-policy-in-lync-server-2013"></a><span data-ttu-id="35fb2-103">Eliminación de una directiva de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35fb2-103">Deleting a location policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35fb2-104">_**Última modificación del tema:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="35fb2-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="35fb2-105">En Lync Server 2013, puede usar la Directiva de ubicación para aplicar la configuración relacionada con la funcionalidad mejorada 9-1-1 (E9-1-1) y la configuración de ubicación de usuarios o contactos.</span><span class="sxs-lookup"><span data-stu-id="35fb2-105">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="35fb2-106">La directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si es así, cuál es el comportamiento de una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="35fb2-106">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="35fb2-107">Por ejemplo, puede usar la Directiva de ubicación para definir el número que constituye una llamada de emergencia (por ejemplo, 911 en Estados Unidos), si se debe notificar automáticamente a la seguridad corporativa y cómo se debe enrutar la llamada.</span><span class="sxs-lookup"><span data-stu-id="35fb2-107">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="35fb2-108">Puede configurar directivas de ubicación desde el grupo de **configuración de red** en el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35fb2-108">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="35fb2-109">En el panel de control de Lync Server, puede ver, crear, modificar o eliminar directivas de ubicación.</span><span class="sxs-lookup"><span data-stu-id="35fb2-109">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="35fb2-110">Utilice los siguientes procedimientos para eliminar una directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="35fb2-110">Use the following procedures delete a location policy.</span></span> <span data-ttu-id="35fb2-111">Para obtener más información sobre cómo crear o modificar directivas de ubicación, consulte [creación o modificación de una directiva de ubicación en Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="35fb2-111">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-delete-a-location-policy"></a><span data-ttu-id="35fb2-112">Para eliminar una directiva de ubicación</span><span class="sxs-lookup"><span data-stu-id="35fb2-112">To delete a location policy</span></span>

1.  <span data-ttu-id="35fb2-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="35fb2-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="35fb2-114">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="35fb2-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="35fb2-115">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="35fb2-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="35fb2-116">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="35fb2-116">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="35fb2-117">En la página  \*\*Directiva de ubicación \*\*, seleccione la directiva de ubicación que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="35fb2-117">On the **Location Policy** page, select the location policy that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="35fb2-p104">Puede eliminar más de una ubicación en la misma operación. Para hacerlo, pulse CTRL y seleccione varias directivas manteniendo pulsada la tecla CTRL. O bien, para seleccionar todas las directivas, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="35fb2-p104">You can delete more than one location policy at a time. To do this, press CTRL and select multiple policies while holding down the CTRL key. Or, to select all policies, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="35fb2-121">En el menú \*\*Editar \*\*, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="35fb2-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="35fb2-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="35fb2-122">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="35fb2-p105">No puede eliminar la directiva de ubicación Global. Si trata de eliminar la directiva Global recibirá un mensaje de advertencia y las propiedades de dicha directiva se restablecerán a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="35fb2-p105">You cannot delete the Global location policy. If you attempt to delete the Global policy you will receive a warning message and that policy will be reset to its default values.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="35fb2-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="35fb2-125">See Also</span></span>


[<span data-ttu-id="35fb2-126">Creación o modificación de una directiva de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35fb2-126">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="35fb2-127">Ver información de directiva de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35fb2-127">Viewing location policy information in Lync Server 2013</span></span>](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

