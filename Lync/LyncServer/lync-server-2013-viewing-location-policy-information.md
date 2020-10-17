---
title: 'Lync Server 2013: visualización de información de directivas de ubicación'
description: 'Lync Server 2013: visualización de información de directivas de ubicación.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fecc5de5fb71014a1641038e9e09afba0e90cdb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565426"
---
# <a name="viewing-location-policy-information-in-lync-server-2013"></a><span data-ttu-id="d47e6-103">Ver información de directiva de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d47e6-103">Viewing location policy information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d47e6-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d47e6-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d47e6-105">En Lync Server 2013, puede usar la Directiva de ubicación para aplicar la configuración relacionada con la funcionalidad mejorada 9-1-1 (E9-1-1) y la configuración de ubicación de usuarios o contactos.</span><span class="sxs-lookup"><span data-stu-id="d47e6-105">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="d47e6-106">La directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si es así, cuál es el comportamiento de una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="d47e6-106">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="d47e6-107">Por ejemplo, puede usar la Directiva de ubicación para definir el número que constituye una llamada de emergencia (por ejemplo, 911 en Estados Unidos), si se debe notificar automáticamente a la seguridad corporativa y cómo se debe enrutar la llamada.</span><span class="sxs-lookup"><span data-stu-id="d47e6-107">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="d47e6-108">Puede configurar directivas de ubicación desde el grupo de **configuración de red** en el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d47e6-108">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="d47e6-109">En el panel de control de Lync Server, puede ver, crear, modificar o eliminar directivas de ubicación.</span><span class="sxs-lookup"><span data-stu-id="d47e6-109">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="d47e6-110">Use el siguiente procedimiento para ver información acerca de las directivas de ubicación.</span><span class="sxs-lookup"><span data-stu-id="d47e6-110">Use the following procedure to view information about location policies.</span></span> <span data-ttu-id="d47e6-111">Para obtener más información sobre cómo crear o modificar directivas de ubicación, consulte [creación o modificación de una directiva de ubicación en Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="d47e6-111">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-view-information-about-a-location-policy"></a><span data-ttu-id="d47e6-112">Para ver información acerca de una directiva de ubicación</span><span class="sxs-lookup"><span data-stu-id="d47e6-112">To view information about a location policy</span></span>

1.  <span data-ttu-id="d47e6-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="d47e6-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d47e6-114">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d47e6-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d47e6-115">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d47e6-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d47e6-116">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="d47e6-116">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="d47e6-117">En la página **Directiva de ubicación**, seleccione la directiva de ubicación que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="d47e6-117">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="d47e6-118">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d47e6-118">On the **Edit** menu, click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d47e6-119">Solo puede ver información sobre una directiva de ubicación a la vez.</span><span class="sxs-lookup"><span data-stu-id="d47e6-119">You can only view information about one location policy at a time.</span></span>

    
    </div>

<span data-ttu-id="d47e6-120">Una sola directiva, denominada global, existe de forma predeterminada y no se puede eliminar ni cambiar de nombre.</span><span class="sxs-lookup"><span data-stu-id="d47e6-120">A single policy, called Global, exists by default and cannot be deleted or renamed.</span></span> <span data-ttu-id="d47e6-121">Sin embargo, puede modificar la directiva global.</span><span class="sxs-lookup"><span data-stu-id="d47e6-121">However, you can modify the Global policy.</span></span> <span data-ttu-id="d47e6-122">Esta Directiva se aplicará a todos los usuarios y contactos, a menos que cree directivas de sitio o directivas por usuario.</span><span class="sxs-lookup"><span data-stu-id="d47e6-122">This policy will apply to all users and contacts, unless you create site policies or per-user policies.</span></span> <span data-ttu-id="d47e6-123">Las directivas por usuario deben aplicarse a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="d47e6-123">Per-user policies must be applied to specific users.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d47e6-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d47e6-124">See Also</span></span>


[<span data-ttu-id="d47e6-125">Creación o modificación de una directiva de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d47e6-125">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="d47e6-126">Crear directivas de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d47e6-126">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)  
[<span data-ttu-id="d47e6-127">Crear o modificar un sitio de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d47e6-127">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)  


[<span data-ttu-id="d47e6-128">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="d47e6-128">New-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[<span data-ttu-id="d47e6-129">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="d47e6-129">Set-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[<span data-ttu-id="d47e6-130">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="d47e6-130">Remove-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[<span data-ttu-id="d47e6-131">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="d47e6-131">Get-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

