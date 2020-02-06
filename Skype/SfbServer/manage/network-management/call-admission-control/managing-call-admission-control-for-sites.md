---
title: Administrar el control de admisión de llamadas para sitios
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Los sitios de red son las oficinas o ubicaciones dentro de cada región de la red de control de admisión de llamadas (CAC), E9-1-1 y las implementaciones por omisión de medios.
ms.openlocfilehash: ec2a3dda70bdd4b952169ca663ca271b76f98481
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817519"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="1d4f8-103">Administrar el control de admisión de llamadas para sitios en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1d4f8-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="1d4f8-104">Los sitios de red son las oficinas o ubicaciones dentro de cada región de la red de control de admisión de llamadas (CAC), E9-1-1 y las implementaciones por omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="1d4f8-105">Use los procedimientos de este artículo para configurar el control de admisión de llamadas para los sitios de red.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="1d4f8-106">Configurar vínculos de sitio de red</span><span class="sxs-lookup"><span data-stu-id="1d4f8-106">Configure network site links</span></span>

<span data-ttu-id="1d4f8-107">Dentro de una configuración de control de admisión de llamadas (CAC), puede crear directivas entre sitios de red que definan limitaciones de ancho de banda entre sitios directamente vinculados.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="1d4f8-108">Cuando los sitios de red comparten un vínculo directo, se pueden definir limitaciones de ancho de banda para conexiones de audio y vídeo entre esos dos sitios.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="1d4f8-109">No puede usar el panel de control de Skype empresarial Server para configurar directivas de sitio de red, esto solo se puede realizar mediante cmdlets desde el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="1d4f8-110">Puede crear, modificar y quitar un vínculo de sitio de red (también conocido como una directiva entre sitios de red) desde el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="1d4f8-111">Para crear un vínculo de sitio de red</span><span class="sxs-lookup"><span data-stu-id="1d4f8-111">To create a network site link</span></span>

1.  <span data-ttu-id="1d4f8-112">Inicie sesión en el equipo donde está instalado el shell de administración de Skype empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="1d4f8-113">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial Server**y, por último, en **consola de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="1d4f8-114">En el símbolo del sistema, escriba el siguiente comando y cambie los valores que sean válidos para su configuración:</span><span class="sxs-lookup"><span data-stu-id="1d4f8-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="1d4f8-115">Este ejemplo crea un nuevo vínculo de sitio de red\_denominado Reno Portland que establece limitaciones de ancho de banda entre los sitios de red de Reno y Portland.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="1d4f8-116">Los sitios de red y el perfil de directiva de ancho de banda ya deben existir antes de ejecutar este comando.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="1d4f8-117">Para obtener descripciones detalladas de parámetros, consulte [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="1d4f8-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="1d4f8-118">Para recuperar una lista de perfiles de directiva de ancho de banda que se pueden aplicar al vínculo de sitio de red, llame al cmdlet **Get-CsNetworkBandwidthPolicyProfile** .</span><span class="sxs-lookup"><span data-stu-id="1d4f8-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="1d4f8-119">Para obtener más información, vea [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="1d4f8-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="1d4f8-120">Para modificar un vínculo de sitio de red</span><span class="sxs-lookup"><span data-stu-id="1d4f8-120">To modify a network site link</span></span>

1.  <span data-ttu-id="1d4f8-121">Inicie sesión en el equipo donde está instalado el shell de administración de Skype empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="1d4f8-122">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial Server**y, por último, en **consola de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="1d4f8-123">Use el cmdlet **set-CsNetworkInterSitePolicy** para modificar las propiedades de un vínculo de sitio de red determinado.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="1d4f8-124">Puede modificar uno (o ambos) o los sitios conectados, y puede modificar el perfil de directiva de ancho de banda asociado con el vínculo.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="1d4f8-125">Este es un ejemplo de cómo modificar el perfil de directiva de ancho de banda de un\_vínculo a sitios denominado Reno Portland:</span><span class="sxs-lookup"><span data-stu-id="1d4f8-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="1d4f8-126">Para obtener descripciones detalladas de parámetros, consulte [set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="1d4f8-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="1d4f8-127">Para eliminar un vínculo de sitio de red</span><span class="sxs-lookup"><span data-stu-id="1d4f8-127">To delete a network site link</span></span>

1.  <span data-ttu-id="1d4f8-128">Inicie sesión en el equipo donde está instalado el shell de administración de Skype empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="1d4f8-129">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial Server**y, por último, en **consola de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="1d4f8-130">Use el cmdlet **Remove-CsNetworkInterSitePolicy** para quitar un vínculo de sitio de red.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="1d4f8-131">En el siguiente ejemplo se elimina el\_vínculo de sitio de la red Reno Portland:</span><span class="sxs-lookup"><span data-stu-id="1d4f8-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="1d4f8-132">Para obtener descripciones detalladas de parámetros, consulte [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="1d4f8-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="1d4f8-133">Ver información del sitio de red</span><span class="sxs-lookup"><span data-stu-id="1d4f8-133">View network site information</span></span>

<span data-ttu-id="1d4f8-134">Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de control de admisión de llamadas (CAC) o implementación mejorada de 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="1d4f8-135">Puede ver la información del sitio de red en el panel de control de Skype empresarial Server o en el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="1d4f8-136">Para ver la información del sitio de red en el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="1d4f8-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1d4f8-137">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1d4f8-138">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1d4f8-139">En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **sitio**.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="1d4f8-140">En la página del **sitio** , haga clic en el sitio que desea ver.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="1d4f8-141">Solo puede ver la información de un sitio a la vez.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="1d4f8-142">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1d4f8-143">Ver información del sitio de red con cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d4f8-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="1d4f8-144">Puede ver la información del sitio de red con Windows PowerShell y el cmdlet Get-CsNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="1d4f8-145">Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="1d4f8-146">Para ver la información del sitio de red</span><span class="sxs-lookup"><span data-stu-id="1d4f8-146">To view network site information</span></span>

  - <span data-ttu-id="1d4f8-147">Para ver información sobre todos los sitios de red, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="1d4f8-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="1d4f8-148">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d4f8-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="1d4f8-149">Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .</span><span class="sxs-lookup"><span data-stu-id="1d4f8-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="1d4f8-150">Crear o modificar sitios de red</span><span class="sxs-lookup"><span data-stu-id="1d4f8-150">Create or modify network sites</span></span> 

<span data-ttu-id="1d4f8-151">Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de control de admisión de llamadas (CAC) o implementación mejorada de 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="1d4f8-152">Puede usar el panel de control de Skype empresarial Server para configurar sitios y asociarlos con regiones.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="1d4f8-153">Por ejemplo, una región de red para Norteamérica puede estar asociada a sitios de redes como Chicago, Redmond y Vancouver.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="1d4f8-154">Es necesario crear un sitio de red CAC para cada sitio dentro de una organización, incluso si ese sitio no tiene limitaciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="1d4f8-155">Desde el panel de control de Skype empresarial Server puede crear, modificar y eliminar sitios de red.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="1d4f8-156">Use los procedimientos siguientes para crear o modificar un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="1d4f8-157">Para crear un sitio de red</span><span class="sxs-lookup"><span data-stu-id="1d4f8-157">To create a network site</span></span>

1.  <span data-ttu-id="1d4f8-158">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1d4f8-159">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1d4f8-160">En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **sitio**.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="1d4f8-161">En la página **sitio** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="1d4f8-162">En **nuevo sitio**, escriba un nombre para este sitio en el campo **nombre** .</span><span class="sxs-lookup"><span data-stu-id="1d4f8-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="1d4f8-163">Los nombres de los sitios deben ser únicos dentro de la implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="1d4f8-164">En la lista desplegable **región** , seleccione la región de red que se va a asociar con este sitio.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="1d4f8-165">Faculta Si desea colocar limitaciones de ancho de banda en las llamadas de audio o vídeo a este sitio, seleccione el perfil de directiva de ancho de banda con la configuración adecuada de la lista desplegable **Directiva de ancho de banda** .</span><span class="sxs-lookup"><span data-stu-id="1d4f8-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="1d4f8-166">Puede ver los detalles de los perfiles de directiva de ancho de banda disponibles o crear un nuevo perfil de directiva de ancho de banda en la página de **Profil de directivas** del grupo **configuración de red** .</span><span class="sxs-lookup"><span data-stu-id="1d4f8-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="1d4f8-167">Para obtener más información, consulte [administrar perfiles de directiva de ancho de banda de red](managing-network-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1d4f8-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="1d4f8-168">Faculta Si desea proporcionar la configuración de ubicación para este sitio, seleccione una directiva de ubicación en la lista desplegable **Directiva de ubicación** .</span><span class="sxs-lookup"><span data-stu-id="1d4f8-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="1d4f8-169">La Directiva de ubicación asigna una configuración de ubicación de cliente, 9-1-1 (E9-1-1) específica y mejorada al sitio.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="1d4f8-170">Puede ver los detalles de las directivas de ubicación disponibles o crear una nueva Directiva de ubicación desde la página de **directivas** de ubicación del grupo **configuración de red** .</span><span class="sxs-lookup"><span data-stu-id="1d4f8-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="1d4f8-171">Faculta Escriba un valor en el campo **Descripción** para proporcionar más información sobre este sitio que no puede expresarse solo por el nombre.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="1d4f8-172">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="1d4f8-173">No use la tabla de **subredes asociada** cuando cree un nuevo sitio de red.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="1d4f8-174">Al crear o modificar la subred, se asocia una subred con un sitio.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="1d4f8-175">Para obtener más información, consulte [Administración de subredes de red](managing-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="1d4f8-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="1d4f8-176">Para modificar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="1d4f8-176">To modify a network site</span></span>

1.  <span data-ttu-id="1d4f8-177">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1d4f8-178">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1d4f8-179">En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **sitio**.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="1d4f8-180">En la página del **sitio** , haga clic en el sitio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="1d4f8-181">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="1d4f8-182">En la página **Editar sitio** , puede modificar la descripción, la región, el perfil de la Directiva de ancho de banda y la Directiva de ubicación asociada al sitio.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="1d4f8-183">Para obtener más información, consulte [para crear un sitio de red](#to-create-a-network-site) arriba.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="1d4f8-184">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-184">Click **Commit**.</span></span>

<span data-ttu-id="1d4f8-185">No puede modificar la tabla de **subredes asociada** en esta página.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-185">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="1d4f8-186">La lista de subredes asociadas se proporciona para que sea consciente de las subredes que se verán afectadas al modificar la configuración del sitio.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-186">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="1d4f8-187">Eliminar un sitio de red existente</span><span class="sxs-lookup"><span data-stu-id="1d4f8-187">Delete an existing network site</span></span>

<span data-ttu-id="1d4f8-188">Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de control de admisión de llamadas (CAC) o implementación mejorada de 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="1d4f8-189">Puede usar el panel de control de Skype empresarial Server para configurar sitios y asociarlos con regiones.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="1d4f8-190">Por ejemplo, una región de red para Norteamérica puede estar asociada a sitios de redes como Chicago, Redmond y Vancouver.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="1d4f8-191">Es necesario crear un sitio de red CAC para cada sitio dentro de una organización, incluso si ese sitio no tiene limitaciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="1d4f8-192">Desde el panel de control de Skype empresarial Server puede crear, modificar y eliminar sitios de red.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="1d4f8-193">Use el siguiente procedimiento para eliminar un sitio de red existente.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="1d4f8-194">Para obtener detalles sobre cómo crear o modificar sitios de red, consulte [administrar el control de admisión de llamadas para sitios](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="1d4f8-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="1d4f8-195">Para eliminar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="1d4f8-195">To delete a network site</span></span>

1.  <span data-ttu-id="1d4f8-196">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1d4f8-197">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1d4f8-198">En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **sitio**.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="1d4f8-199">En la página del **sitio** , haga clic en el sitio que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="1d4f8-200">Puede eliminar más de un sitio a la vez.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-200">You can delete more than one site at a time.</span></span> <span data-ttu-id="1d4f8-201">Para ello, presione CTRL y seleccione varios sitios mientras mantiene presionada la tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-201">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="1d4f8-202">O bien, para seleccionar todos los sitios, haga clic en **seleccionar todo** en el menú **edición** .</span><span class="sxs-lookup"><span data-stu-id="1d4f8-202">Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="1d4f8-203">En el menú **Editar** , haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="1d4f8-204">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="1d4f8-205">No puede quitar un sitio de red si está asociado con una subred de red.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-205">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="1d4f8-206">Si intenta quitar un sitio asociado a una subred, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="1d4f8-206">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="1d4f8-207">Para ver si un sitio está asociado con cualquier subred, haga clic en el sitio y, a continuación, haga clic en **Mostrar detalles** en el menú **edición** .</span><span class="sxs-lookup"><span data-stu-id="1d4f8-207">To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="1d4f8-208">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d4f8-208">See Also</span></span>


[<span data-ttu-id="1d4f8-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="1d4f8-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="1d4f8-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="1d4f8-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="1d4f8-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="1d4f8-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="1d4f8-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="1d4f8-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="1d4f8-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="1d4f8-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="1d4f8-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="1d4f8-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="1d4f8-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="1d4f8-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="1d4f8-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="1d4f8-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="1d4f8-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="1d4f8-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
