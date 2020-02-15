---
title: 'Lync Server 2013: crear o modificar sitios de red'
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
ms.openlocfilehash: 1e7c3db5b37cba514a0c07e11a907628dcc7823f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a><span data-ttu-id="4812f-102">Crear o modificar sitios de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4812f-102">Creating or modifying network sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4812f-103">_**Última modificación del tema:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="4812f-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="4812f-104">Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de una implementación de Enhanced 9-1-1 o control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="4812f-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="4812f-105">Puede usar el panel de control de Microsoft Lync Server 2013 para configurar sitios y asociarlos con regiones.</span><span class="sxs-lookup"><span data-stu-id="4812f-105">You can use the Microsoft Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="4812f-106">Por ejemplo, una región de red para Norteamérica se podría asociar con sitios de red como Chicago, Redmond y Vancouver.</span><span class="sxs-lookup"><span data-stu-id="4812f-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="4812f-107">Debe crearse un sitio de red CAC para cada sitio de una organización, incluso aunque no tenga limitaciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="4812f-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="4812f-108">En el panel de control de Lync Server, puede crear, modificar y eliminar sitios de red.</span><span class="sxs-lookup"><span data-stu-id="4812f-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="4812f-109">Utilice los procedimientos siguientes para crear o modificar un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="4812f-109">Use the following procedures to create or modify a network site.</span></span> <span data-ttu-id="4812f-110">Para obtener más información sobre cómo eliminar un sitio de red existente, consulte [eliminar un sitio de red existente en Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="4812f-110">For details on deleting an existing network site, see [Deleting an existing network site in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span></span>

<div>

## <a name="to-create-a-network-site"></a><span data-ttu-id="4812f-111">Para crear un sitio de red</span><span class="sxs-lookup"><span data-stu-id="4812f-111">To create a network site</span></span>

1.  <span data-ttu-id="4812f-112">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4812f-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4812f-113">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4812f-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4812f-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4812f-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4812f-115">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Sitio**.</span><span class="sxs-lookup"><span data-stu-id="4812f-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="4812f-116">En la página **Sitio**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4812f-116">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="4812f-117">En **Sitio nuevo**, escriba un nombre para este sitio en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="4812f-117">In **New Site**, type a name for this site in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4812f-118">Los nombres de sitio deben ser únicos dentro de la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4812f-118">Site names must be unique within the Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="4812f-119">En la lista desplegable **Región**, seleccione una región de red para asociarla con este sitio.</span><span class="sxs-lookup"><span data-stu-id="4812f-119">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="4812f-120">(Opcional) Si desea definir limitaciones de ancho de banda en las llamadas de audio o vídeo para este sitio, seleccione el perfil de directiva de ancho de banda con la configuración adecuada en la lista desplegable **Directiva de ancho de banda**.</span><span class="sxs-lookup"><span data-stu-id="4812f-120">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4812f-121">Puede ver la información detallada de los perfiles de directivas de ancho de banda disponibles o crear uno nuevo en la página <STRONG>Perfil de directiva</STRONG> del grupo <STRONG>Configuración de red</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4812f-121">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the <STRONG>Policy Profile</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="4812f-122">Para obtener más información, consulte <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">creación o modificación de perfiles de directiva de ancho de banda en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4812f-122">For details, see <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creating or modifying bandwidth policy profiles in Lync Server 2013</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="4812f-123">(Opcional) Si desea proporcionar parámetros de ubicación para este sitio, seleccione una directiva de ubicación de la lista desplegable **Directiva de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="4812f-123">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4812f-124">La directiva de ubicación asigna al sitio un Enhanced 9-1-1 (E9-1-1) específico y parámetros de ubicación de cliente.</span><span class="sxs-lookup"><span data-stu-id="4812f-124">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="4812f-125">Puede ver la información detallada de las directivas de ubicación disponibles o crear una nueva desde la página <STRONG>Directiva de ubicación</STRONG> del grupo <STRONG>Configuración de red</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4812f-125">You can view the details of the available location policies, or create a new location policy, from the <STRONG>Location Policy</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="4812f-126">Para obtener más información, consulte <A href="lync-server-2013-viewing-location-policy-information.md">ver información de directivas de ubicación en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4812f-126">For details, see <A href="lync-server-2013-viewing-location-policy-information.md">Viewing location policy information in Lync Server 2013</A>.</span></span>

    
    </div>

9.  <span data-ttu-id="4812f-127">(Opcional) Escriba un valor en el campo **Descripción** para proporcionar más información acerca de este sitio más allá de lo que se pueda deducir de su nombre.</span><span class="sxs-lookup"><span data-stu-id="4812f-127">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="4812f-128">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4812f-128">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4812f-129">No use la tabla <STRONG>Subredes asociadas</STRONG> al crear un sitio de red nuevo.</span><span class="sxs-lookup"><span data-stu-id="4812f-129">You do not use the <STRONG>Associated Subnets</STRONG> table when you create a new network site.</span></span> <span data-ttu-id="4812f-130">Al crear o modificar la subred, asocie una subred con un sitio.</span><span class="sxs-lookup"><span data-stu-id="4812f-130">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="4812f-131">Para obtener más información, consulte <A href="lync-server-2013-create-or-modify-network-subnets.md">crear o modificar subredes de red en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4812f-131">For details, see <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnets in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="4812f-132">Para modificar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="4812f-132">To modify a network site</span></span>

1.  <span data-ttu-id="4812f-133">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4812f-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4812f-134">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4812f-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4812f-135">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4812f-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4812f-136">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Sitio**.</span><span class="sxs-lookup"><span data-stu-id="4812f-136">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="4812f-137">En la página **Sitio**, haga clic en el sitio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="4812f-137">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="4812f-138">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="4812f-138">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="4812f-p107">En la página **Editar sitio**, puede modificar la descripción, la región, el perfil de directiva de ancho de banda y la directiva de ubicación asociados con el sitio. Para obtener más información, consulte la sección "Para crear un sitio de red" que aparece anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="4812f-p107">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site. For details, see "To create a network site" section earlier in this topic.</span></span>

7.  <span data-ttu-id="4812f-141">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4812f-141">Click **Commit**.</span></span>

<span data-ttu-id="4812f-p108">No es posible modificar la tabla **Subredes asociadas** de esta página. La lista de subredes asociadas solo es de referencia, por lo que debe conocer qué subredes se verán afectadas cuando modifique la configuración del sitio.</span><span class="sxs-lookup"><span data-stu-id="4812f-p108">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="4812f-144">Para eliminar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="4812f-144">To delete a network site</span></span>

1.  <span data-ttu-id="4812f-145">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4812f-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4812f-146">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4812f-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4812f-147">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4812f-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4812f-148">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Sitio**.</span><span class="sxs-lookup"><span data-stu-id="4812f-148">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="4812f-149">En la página **Sitio**, haga clic en el sitio que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="4812f-149">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4812f-p110">Puede eliminar más de un sitio en la misma operación. Para hacerlo, pulse CTRL y seleccione varios sitios manteniendo pulsada la tecla CTRL. O bien, para seleccionar todos los sitios, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4812f-p110">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="4812f-153">En el menú **Editar**, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4812f-153">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="4812f-154">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4812f-154">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4812f-p111">No se puede eliminar un sitio de red si está asociado con la subred de una red. Si intenta quitar un sitio asociado a una subred, recibirá un mensaje de error. Para ver si un sitio está asociado con alguna subred, haga clic en el sitio y, a continuación, haga clic en <STRONG>Mostrar detalles</STRONG> en el menú <STRONG>Editar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4812f-p111">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4812f-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="4812f-158">See Also</span></span>


[<span data-ttu-id="4812f-159">Eliminación de un sitio de red existente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4812f-159">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  


[<span data-ttu-id="4812f-160">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="4812f-160">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[<span data-ttu-id="4812f-161">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="4812f-161">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[<span data-ttu-id="4812f-162">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="4812f-162">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[<span data-ttu-id="4812f-163">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="4812f-163">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

