---
title: 'Lync Server 2013: visualización de información de directivas de ubicación'
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
ms.openlocfilehash: 0b5c4b512acc3541b933f583ad69e3f730dc14f9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523517"
---
# <a name="viewing-location-policy-information-in-lync-server-2013"></a><span data-ttu-id="bd991-102">Ver información de directiva de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd991-102">Viewing location policy information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd991-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bd991-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bd991-104">En Lync Server 2013, puede usar la Directiva de ubicación para aplicar la configuración relacionada con la funcionalidad mejorada 9-1-1 (E9-1-1) y la configuración de ubicación de usuarios o contactos.</span><span class="sxs-lookup"><span data-stu-id="bd991-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="bd991-105">La directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si es así, cuál es el comportamiento de una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="bd991-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="bd991-106">Por ejemplo, puede usar la Directiva de ubicación para definir el número que constituye una llamada de emergencia (por ejemplo, 911 en Estados Unidos), si se debe notificar automáticamente a la seguridad corporativa y cómo se debe enrutar la llamada.</span><span class="sxs-lookup"><span data-stu-id="bd991-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="bd991-107">Puede configurar directivas de ubicación desde el grupo de **configuración de red** en el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd991-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="bd991-108">En el panel de control de Lync Server, puede ver, crear, modificar o eliminar directivas de ubicación.</span><span class="sxs-lookup"><span data-stu-id="bd991-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="bd991-109">Use el siguiente procedimiento para ver información acerca de las directivas de ubicación.</span><span class="sxs-lookup"><span data-stu-id="bd991-109">Use the following procedure to view information about location policies.</span></span> <span data-ttu-id="bd991-110">Para obtener más información sobre cómo crear o modificar directivas de ubicación, consulte [creación o modificación de una directiva de ubicación en Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="bd991-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-view-information-about-a-location-policy"></a><span data-ttu-id="bd991-111">Para ver información acerca de una directiva de ubicación</span><span class="sxs-lookup"><span data-stu-id="bd991-111">To view information about a location policy</span></span>

1.  <span data-ttu-id="bd991-112">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="bd991-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bd991-113">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bd991-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bd991-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bd991-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bd991-115">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="bd991-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="bd991-116">En la página **Directiva de ubicación**, seleccione la directiva de ubicación que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="bd991-116">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="bd991-117">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="bd991-117">On the **Edit** menu, click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd991-118">Solo puede ver información sobre una directiva de ubicación a la vez.</span><span class="sxs-lookup"><span data-stu-id="bd991-118">You can only view information about one location policy at a time.</span></span>

    
    </div>

<span data-ttu-id="bd991-119">Una sola directiva, denominada global, existe de forma predeterminada y no se puede eliminar ni cambiar de nombre.</span><span class="sxs-lookup"><span data-stu-id="bd991-119">A single policy, called Global, exists by default and cannot be deleted or renamed.</span></span> <span data-ttu-id="bd991-120">Sin embargo, puede modificar la directiva global.</span><span class="sxs-lookup"><span data-stu-id="bd991-120">However, you can modify the Global policy.</span></span> <span data-ttu-id="bd991-121">Esta Directiva se aplicará a todos los usuarios y contactos, a menos que cree directivas de sitio o directivas por usuario.</span><span class="sxs-lookup"><span data-stu-id="bd991-121">This policy will apply to all users and contacts, unless you create site policies or per-user policies.</span></span> <span data-ttu-id="bd991-122">Las directivas por usuario deben aplicarse a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="bd991-122">Per-user policies must be applied to specific users.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bd991-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd991-123">See Also</span></span>


[<span data-ttu-id="bd991-124">Creación o modificación de una directiva de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd991-124">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="bd991-125">Crear directivas de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd991-125">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)  
[<span data-ttu-id="bd991-126">Crear o modificar un sitio de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd991-126">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)  


[<span data-ttu-id="bd991-127">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="bd991-127">New-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[<span data-ttu-id="bd991-128">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="bd991-128">Set-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[<span data-ttu-id="bd991-129">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="bd991-129">Remove-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[<span data-ttu-id="bd991-130">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="bd991-130">Get-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

