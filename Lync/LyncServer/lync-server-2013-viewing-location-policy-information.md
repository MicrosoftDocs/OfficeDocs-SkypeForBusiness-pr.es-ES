---
title: 'Lync Server 2013: visualización de la información de directiva de ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72e932449cc0e5b69fad46056dfda898d463c531
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-location-policy-information-in-lync-server-2013"></a><span data-ttu-id="ab021-102">Ver información de la Directiva de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab021-102">Viewing location policy information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab021-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ab021-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ab021-104">En Lync Server 2013, puede usar la Directiva de ubicación para aplicar la configuración relacionada con la funcionalidad mejorada de 9-1-1 (E9-1-1) y la configuración de ubicación de los usuarios o los contactos.</span><span class="sxs-lookup"><span data-stu-id="ab021-104">In Lync Server 2013, you can use the location policy to apply settings that relate to Enhanced 9-1-1 (E9-1-1) functionality and to location settings for users or contacts.</span></span> <span data-ttu-id="ab021-105">La Directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si es así, cuál es el comportamiento de una llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="ab021-105">The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call.</span></span> <span data-ttu-id="ab021-106">Por ejemplo, puede usar la política de ubicación para definir qué número constituye una llamada de emergencia (por ejemplo, 911 en los Estados Unidos), si se debe notificar automáticamente la seguridad corporativa y cómo debe dirigirse la llamada.</span><span class="sxs-lookup"><span data-stu-id="ab021-106">For example, you can use the location policy to define what number constitutes an emergency call (for example, 911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="ab021-107">Puede configurar directivas de ubicación desde el grupo **configuración de red** en el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab021-107">You can configure location policies from the **Network Configuration** group in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="ab021-108">En el panel de control de Lync Server puede ver, crear, modificar o eliminar directivas de ubicación.</span><span class="sxs-lookup"><span data-stu-id="ab021-108">From Lync Server Control Panel you can view, create, modify, or delete location policies.</span></span> <span data-ttu-id="ab021-109">Use el procedimiento siguiente para ver información sobre las directivas de ubicación.</span><span class="sxs-lookup"><span data-stu-id="ab021-109">Use the following procedure to view information about location policies.</span></span> <span data-ttu-id="ab021-110">Para obtener más información sobre cómo crear o modificar directivas de ubicación, vea [crear o modificar una directiva de ubicación en Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="ab021-110">For details on creating or modifying location policies, see [Creating or modifying a location policy in Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).</span></span>

<div>

## <a name="to-view-information-about-a-location-policy"></a><span data-ttu-id="ab021-111">Para ver información sobre una directiva de ubicación</span><span class="sxs-lookup"><span data-stu-id="ab021-111">To view information about a location policy</span></span>

1.  <span data-ttu-id="ab021-112">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ab021-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ab021-113">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ab021-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ab021-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ab021-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ab021-115">En la barra de navegación izquierda, haga clic en **configuración de red** y luego en **Directiva de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="ab021-115">In the left navigation bar, click **Network Configuration** and then click **Location Policy**.</span></span>

4.  <span data-ttu-id="ab021-116">En la página **Directiva de ubicación** , seleccione la Directiva de ubicación que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="ab021-116">On the **Location Policy** page, select the location policy that you want to modify.</span></span>

5.  <span data-ttu-id="ab021-117">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="ab021-117">On the **Edit** menu, click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ab021-118">Solo puede ver información sobre una política de ubicación a la vez.</span><span class="sxs-lookup"><span data-stu-id="ab021-118">You can only view information about one location policy at a time.</span></span>

    
    </div>

<span data-ttu-id="ab021-119">De forma predeterminada, existe una única directiva, denominada global, que no se puede eliminar ni cambiar de nombre.</span><span class="sxs-lookup"><span data-stu-id="ab021-119">A single policy, called Global, exists by default and cannot be deleted or renamed.</span></span> <span data-ttu-id="ab021-120">Sin embargo, puede modificar la directiva global.</span><span class="sxs-lookup"><span data-stu-id="ab021-120">However, you can modify the Global policy.</span></span> <span data-ttu-id="ab021-121">Esta Directiva se aplicará a todos los usuarios y contactos, a menos que cree directivas de sitio o directivas por usuario.</span><span class="sxs-lookup"><span data-stu-id="ab021-121">This policy will apply to all users and contacts, unless you create site policies or per-user policies.</span></span> <span data-ttu-id="ab021-122">Las directivas por usuario deben aplicarse a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="ab021-122">Per-user policies must be applied to specific users.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ab021-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab021-123">See Also</span></span>


[<span data-ttu-id="ab021-124">Crear o modificar una directiva de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab021-124">Creating or modifying a location policy in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[<span data-ttu-id="ab021-125">Crear directivas de ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab021-125">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)  
[<span data-ttu-id="ab021-126">Crear o modificar un sitio de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab021-126">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)  


[<span data-ttu-id="ab021-127">Nuevo: CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="ab021-127">New-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[<span data-ttu-id="ab021-128">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="ab021-128">Set-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[<span data-ttu-id="ab021-129">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="ab021-129">Remove-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[<span data-ttu-id="ab021-130">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="ab021-130">Get-CsLocationPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

