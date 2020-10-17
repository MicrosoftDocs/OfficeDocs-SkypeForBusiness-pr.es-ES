---
title: 'Lync Server 2013: crear o modificar sitios de red'
description: 'Lync Server 2013: crear o modificar sitios de red.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 700f089cfe190a8f46b5eefc05e656e7c62a59a9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544016"
---
# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a><span data-ttu-id="d297d-103">Crear o modificar sitios de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d297d-103">Creating or modifying network sites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d297d-104">_**Última modificación del tema:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="d297d-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="d297d-105">Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de una implementación de Enhanced 9-1-1 o control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="d297d-105">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="d297d-106">Puede usar el panel de control de Microsoft Lync Server 2013 para configurar sitios y asociarlos con regiones.</span><span class="sxs-lookup"><span data-stu-id="d297d-106">You can use the Microsoft Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="d297d-107">Por ejemplo, una región de red para Norteamérica se podría asociar con sitios de red como Chicago, Redmond y Vancouver.</span><span class="sxs-lookup"><span data-stu-id="d297d-107">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="d297d-108">Debe crearse un sitio de red CAC para cada sitio de una organización, incluso aunque no tenga limitaciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="d297d-108">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="d297d-109">En el panel de control de Lync Server, puede crear, modificar y eliminar sitios de red.</span><span class="sxs-lookup"><span data-stu-id="d297d-109">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="d297d-110">Utilice los procedimientos siguientes para crear o modificar un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="d297d-110">Use the following procedures to create or modify a network site.</span></span> <span data-ttu-id="d297d-111">Para obtener más información sobre cómo eliminar un sitio de red existente, consulte [eliminar un sitio de red existente en Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="d297d-111">For details on deleting an existing network site, see [Deleting an existing network site in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span></span>

<div>

## <a name="to-create-a-network-site"></a><span data-ttu-id="d297d-112">Para crear un sitio de red</span><span class="sxs-lookup"><span data-stu-id="d297d-112">To create a network site</span></span>

1.  <span data-ttu-id="d297d-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="d297d-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d297d-114">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d297d-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d297d-115">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d297d-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d297d-116">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Sitio**.</span><span class="sxs-lookup"><span data-stu-id="d297d-116">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="d297d-117">En la página **Sitio**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d297d-117">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="d297d-118">En **Sitio nuevo**, escriba un nombre para este sitio en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="d297d-118">In **New Site**, type a name for this site in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d297d-119">Los nombres de sitio deben ser únicos dentro de la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d297d-119">Site names must be unique within the Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="d297d-120">En la lista desplegable **Región**, seleccione una región de red para asociarla con este sitio.</span><span class="sxs-lookup"><span data-stu-id="d297d-120">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="d297d-121">(Opcional) Si desea definir limitaciones de ancho de banda en las llamadas de audio o vídeo para este sitio, seleccione el perfil de directiva de ancho de banda con la configuración adecuada en la lista desplegable **Directiva de ancho de banda**.</span><span class="sxs-lookup"><span data-stu-id="d297d-121">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d297d-122">Puede ver la información detallada de los perfiles de directivas de ancho de banda disponibles o crear uno nuevo en la página <STRONG>Perfil de directiva</STRONG> del grupo <STRONG>Configuración de red</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d297d-122">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the <STRONG>Policy Profile</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="d297d-123">Para obtener más información, consulte <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">creación o modificación de perfiles de directiva de ancho de banda en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d297d-123">For details, see <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creating or modifying bandwidth policy profiles in Lync Server 2013</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="d297d-124">(Opcional) Si desea proporcionar parámetros de ubicación para este sitio, seleccione una directiva de ubicación de la lista desplegable **Directiva de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="d297d-124">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d297d-125">La directiva de ubicación asigna al sitio un Enhanced 9-1-1 (E9-1-1) específico y parámetros de ubicación de cliente.</span><span class="sxs-lookup"><span data-stu-id="d297d-125">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="d297d-126">Puede ver la información detallada de las directivas de ubicación disponibles o crear una nueva desde la página <STRONG>Directiva de ubicación</STRONG> del grupo <STRONG>Configuración de red</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d297d-126">You can view the details of the available location policies, or create a new location policy, from the <STRONG>Location Policy</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="d297d-127">Para obtener más información, consulte <A href="lync-server-2013-viewing-location-policy-information.md">ver información de directivas de ubicación en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d297d-127">For details, see <A href="lync-server-2013-viewing-location-policy-information.md">Viewing location policy information in Lync Server 2013</A>.</span></span>

    
    </div>

9.  <span data-ttu-id="d297d-128">(Opcional) Escriba un valor en el campo **Descripción** para proporcionar más información acerca de este sitio más allá de lo que se pueda deducir de su nombre.</span><span class="sxs-lookup"><span data-stu-id="d297d-128">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="d297d-129">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d297d-129">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d297d-130">No use la tabla <STRONG>Subredes asociadas</STRONG> al crear un sitio de red nuevo.</span><span class="sxs-lookup"><span data-stu-id="d297d-130">You do not use the <STRONG>Associated Subnets</STRONG> table when you create a new network site.</span></span> <span data-ttu-id="d297d-131">Al crear o modificar la subred, asocie una subred con un sitio.</span><span class="sxs-lookup"><span data-stu-id="d297d-131">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="d297d-132">Para obtener más información, consulte <A href="lync-server-2013-create-or-modify-network-subnets.md">crear o modificar subredes de red en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d297d-132">For details, see <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnets in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="d297d-133">Para modificar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="d297d-133">To modify a network site</span></span>

1.  <span data-ttu-id="d297d-134">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="d297d-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d297d-135">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d297d-135">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d297d-136">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d297d-136">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d297d-137">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Sitio**.</span><span class="sxs-lookup"><span data-stu-id="d297d-137">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="d297d-138">En la página **Sitio**, haga clic en el sitio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="d297d-138">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="d297d-139">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d297d-139">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="d297d-p107">En la página **Editar sitio**, puede modificar la descripción, la región, el perfil de directiva de ancho de banda y la directiva de ubicación asociados con el sitio. Para obtener más información, consulte la sección "Para crear un sitio de red" que aparece anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="d297d-p107">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site. For details, see "To create a network site" section earlier in this topic.</span></span>

7.  <span data-ttu-id="d297d-142">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d297d-142">Click **Commit**.</span></span>

<span data-ttu-id="d297d-p108">No es posible modificar la tabla **Subredes asociadas** de esta página. La lista de subredes asociadas solo es de referencia, por lo que debe conocer qué subredes se verán afectadas cuando modifique la configuración del sitio.</span><span class="sxs-lookup"><span data-stu-id="d297d-p108">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="d297d-145">Para eliminar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="d297d-145">To delete a network site</span></span>

1.  <span data-ttu-id="d297d-146">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="d297d-146">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d297d-147">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d297d-147">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d297d-148">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d297d-148">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d297d-149">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Sitio**.</span><span class="sxs-lookup"><span data-stu-id="d297d-149">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="d297d-150">En la página **Sitio**, haga clic en el sitio que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="d297d-150">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d297d-p110">Puede eliminar más de un sitio en la misma operación. Para hacerlo, pulse CTRL y seleccione varios sitios manteniendo pulsada la tecla CTRL. O bien, para seleccionar todos los sitios, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d297d-p110">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="d297d-154">En el menú **Editar**, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d297d-154">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="d297d-155">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d297d-155">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d297d-p111">No se puede eliminar un sitio de red si está asociado con la subred de una red. Si intenta quitar un sitio asociado a una subred, recibirá un mensaje de error. Para ver si un sitio está asociado con alguna subred, haga clic en el sitio y, a continuación, haga clic en <STRONG>Mostrar detalles</STRONG> en el menú <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d297d-p111">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d297d-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d297d-159">See Also</span></span>


[<span data-ttu-id="d297d-160">Eliminación de un sitio de red existente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d297d-160">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  


[<span data-ttu-id="d297d-161">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="d297d-161">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[<span data-ttu-id="d297d-162">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="d297d-162">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[<span data-ttu-id="d297d-163">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="d297d-163">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[<span data-ttu-id="d297d-164">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="d297d-164">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

