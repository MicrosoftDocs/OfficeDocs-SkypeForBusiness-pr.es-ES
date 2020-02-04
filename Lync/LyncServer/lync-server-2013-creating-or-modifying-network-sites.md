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
ms.openlocfilehash: 4c77c343bff92e25ffc1678bc06e7a0ef05d3f96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a><span data-ttu-id="1625d-102">Crear o modificar sitios de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1625d-102">Creating or modifying network sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1625d-103">_**Última modificación del tema:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="1625d-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="1625d-104">Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de control de admisión de llamadas (CAC) o implementación mejorada de 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="1625d-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="1625d-105">Puede usar el panel de control de Microsoft Lync Server 2013 para configurar sitios y asociarlos con regiones.</span><span class="sxs-lookup"><span data-stu-id="1625d-105">You can use the Microsoft Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="1625d-106">Por ejemplo, una región de red para Norteamérica puede estar asociada a sitios de redes como Chicago, Redmond y Vancouver.</span><span class="sxs-lookup"><span data-stu-id="1625d-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="1625d-107">Es necesario crear un sitio de red CAC para cada sitio dentro de una organización, incluso si ese sitio no tiene limitaciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="1625d-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="1625d-108">En el panel de control de Lync Server puede crear, modificar y eliminar sitios de red.</span><span class="sxs-lookup"><span data-stu-id="1625d-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="1625d-109">Use los procedimientos siguientes para crear o modificar un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="1625d-109">Use the following procedures to create or modify a network site.</span></span> <span data-ttu-id="1625d-110">Para obtener más información sobre cómo eliminar un sitio de red existente, consulte [eliminar un sitio de red existente en Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="1625d-110">For details on deleting an existing network site, see [Deleting an existing network site in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span></span>

<div>

## <a name="to-create-a-network-site"></a><span data-ttu-id="1625d-111">Para crear un sitio de red</span><span class="sxs-lookup"><span data-stu-id="1625d-111">To create a network site</span></span>

1.  <span data-ttu-id="1625d-112">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="1625d-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1625d-113">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1625d-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1625d-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1625d-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1625d-115">En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **sitio**.</span><span class="sxs-lookup"><span data-stu-id="1625d-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="1625d-116">En la página **sitio** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="1625d-116">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="1625d-117">En **nuevo sitio**, escriba un nombre para este sitio en el campo **nombre** .</span><span class="sxs-lookup"><span data-stu-id="1625d-117">In **New Site**, type a name for this site in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1625d-118">Los nombres de los sitios deben ser únicos en la implementación de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1625d-118">Site names must be unique within the Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="1625d-119">En la lista desplegable **región** , seleccione la región de red que se va a asociar con este sitio.</span><span class="sxs-lookup"><span data-stu-id="1625d-119">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="1625d-120">Faculta Si desea colocar limitaciones de ancho de banda en las llamadas de audio o vídeo a este sitio, seleccione el perfil de directiva de ancho de banda con la configuración adecuada de la lista desplegable **Directiva de ancho de banda** .</span><span class="sxs-lookup"><span data-stu-id="1625d-120">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1625d-121">Puede ver los detalles de los perfiles de directiva de ancho de banda disponibles o crear un nuevo perfil de directiva de ancho de banda en la página <STRONG>Perfil de directiva</STRONG> del grupo <STRONG>configuración de red</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="1625d-121">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the <STRONG>Policy Profile</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="1625d-122">Para obtener más información, vea <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">crear o modificar perfiles de directiva de ancho de banda en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1625d-122">For details, see <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creating or modifying bandwidth policy profiles in Lync Server 2013</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="1625d-123">Faculta Si desea proporcionar la configuración de ubicación para este sitio, seleccione una directiva de ubicación en la lista desplegable **Directiva de ubicación** .</span><span class="sxs-lookup"><span data-stu-id="1625d-123">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1625d-124">La Directiva de ubicación asigna una configuración de ubicación de cliente, 9-1-1 (E9-1-1) específica y mejorada al sitio.</span><span class="sxs-lookup"><span data-stu-id="1625d-124">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="1625d-125">Puede ver los detalles de las directivas de ubicación disponibles o crear una nueva Directiva de ubicación desde la página de <STRONG>directivas</STRONG> de ubicación del grupo <STRONG>configuración de red</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="1625d-125">You can view the details of the available location policies, or create a new location policy, from the <STRONG>Location Policy</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="1625d-126">Para obtener más información, consulte <A href="lync-server-2013-viewing-location-policy-information.md">ver información de directivas de ubicación en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1625d-126">For details, see <A href="lync-server-2013-viewing-location-policy-information.md">Viewing location policy information in Lync Server 2013</A>.</span></span>

    
    </div>

9.  <span data-ttu-id="1625d-127">Faculta Escriba un valor en el campo **Descripción** para proporcionar más información sobre este sitio que no puede expresarse solo por el nombre.</span><span class="sxs-lookup"><span data-stu-id="1625d-127">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="1625d-128">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1625d-128">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1625d-129">No use la tabla de <STRONG>subredes asociada</STRONG> cuando cree un nuevo sitio de red.</span><span class="sxs-lookup"><span data-stu-id="1625d-129">You do not use the <STRONG>Associated Subnets</STRONG> table when you create a new network site.</span></span> <span data-ttu-id="1625d-130">Al crear o modificar la subred, se asocia una subred con un sitio.</span><span class="sxs-lookup"><span data-stu-id="1625d-130">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="1625d-131">Para obtener más información, consulte <A href="lync-server-2013-create-or-modify-network-subnets.md">crear o modificar subredes de red en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1625d-131">For details, see <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnets in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="1625d-132">Para modificar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="1625d-132">To modify a network site</span></span>

1.  <span data-ttu-id="1625d-133">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="1625d-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1625d-134">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1625d-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1625d-135">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1625d-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1625d-136">En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **sitio**.</span><span class="sxs-lookup"><span data-stu-id="1625d-136">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="1625d-137">En la página del **sitio** , haga clic en el sitio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="1625d-137">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="1625d-138">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="1625d-138">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="1625d-139">En la página **Editar sitio** , puede modificar la descripción, la región, el perfil de la Directiva de ancho de banda y la Directiva de ubicación asociada al sitio.</span><span class="sxs-lookup"><span data-stu-id="1625d-139">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="1625d-140">Para obtener más información, vea la sección "para crear un sitio de red" anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="1625d-140">For details, see "To create a network site" section earlier in this topic.</span></span>

7.  <span data-ttu-id="1625d-141">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1625d-141">Click **Commit**.</span></span>

<span data-ttu-id="1625d-142">No puede modificar la tabla de **subredes asociada** en esta página.</span><span class="sxs-lookup"><span data-stu-id="1625d-142">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="1625d-143">La lista de subredes asociadas se proporciona para que sea consciente de las subredes que se verán afectadas al modificar la configuración del sitio.</span><span class="sxs-lookup"><span data-stu-id="1625d-143">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="1625d-144">Para eliminar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="1625d-144">To delete a network site</span></span>

1.  <span data-ttu-id="1625d-145">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="1625d-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1625d-146">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1625d-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1625d-147">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1625d-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1625d-148">En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **sitio**.</span><span class="sxs-lookup"><span data-stu-id="1625d-148">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="1625d-149">En la página del **sitio** , haga clic en el sitio que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="1625d-149">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1625d-150">Puede eliminar más de un sitio a la vez.</span><span class="sxs-lookup"><span data-stu-id="1625d-150">You can delete more than one site at a time.</span></span> <span data-ttu-id="1625d-151">Para ello, presione CTRL y seleccione varios sitios mientras mantiene presionada la tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="1625d-151">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="1625d-152">O bien, para seleccionar todos los sitios, haga clic en <STRONG>seleccionar todo</STRONG> en el menú <STRONG>edición</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="1625d-152">Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="1625d-153">En el menú **Editar** , haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="1625d-153">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="1625d-154">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1625d-154">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1625d-155">No puede quitar un sitio de red si está asociado con una subred de red.</span><span class="sxs-lookup"><span data-stu-id="1625d-155">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="1625d-156">Si intenta quitar un sitio asociado a una subred, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="1625d-156">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="1625d-157">Para ver si un sitio está asociado con cualquier subred, haga clic en el sitio y, a continuación, haga clic en <STRONG>Mostrar detalles</STRONG> en el menú <STRONG>edición</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="1625d-157">To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1625d-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="1625d-158">See Also</span></span>


[<span data-ttu-id="1625d-159">Eliminar un sitio de red existente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1625d-159">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  


[<span data-ttu-id="1625d-160">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="1625d-160">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[<span data-ttu-id="1625d-161">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="1625d-161">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[<span data-ttu-id="1625d-162">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="1625d-162">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[<span data-ttu-id="1625d-163">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="1625d-163">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

