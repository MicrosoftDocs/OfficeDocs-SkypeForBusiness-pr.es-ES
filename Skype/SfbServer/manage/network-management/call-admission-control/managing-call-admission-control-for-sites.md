---
title: Administración de control de admisión de llamadas para sitios
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sitios de red son las oficinas o ubicaciones dentro de cada región de red de llamadas (CAC) el control de admisión, E9-1-1 y las implementaciones de desvío de medios.
ms.openlocfilehash: ecf23a8a052afbd21b02f8ff5507c248d42b7118
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223174"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="3194e-103">Administración de control de admisión de llamadas para sitios de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="3194e-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="3194e-104">Sitios de red son las oficinas o ubicaciones dentro de cada región de red de llamadas (CAC) el control de admisión, E9-1-1 y las implementaciones de desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="3194e-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="3194e-105">Use los procedimientos de este artículo para configurar el control de admisión de llamadas para sitios de red.</span><span class="sxs-lookup"><span data-stu-id="3194e-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="3194e-106">Configuración de vínculos de sitio de red</span><span class="sxs-lookup"><span data-stu-id="3194e-106">Configure network site links</span></span>

<span data-ttu-id="3194e-107">Dentro de una configuración de (CAC) del control de admisión de llamadas, puede crear directivas entre sitios que definen las limitaciones de ancho de banda entre sitios que están vinculados directamente de red.</span><span class="sxs-lookup"><span data-stu-id="3194e-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="3194e-108">Cuando los sitios de red compartirán un vínculo directo, se pueden definir las limitaciones de ancho de banda para las conexiones de audio y vídeos entre los dos sitios.</span><span class="sxs-lookup"><span data-stu-id="3194e-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="3194e-109">No se puede usar el Skype para el Panel de Control de servidor empresarial para configurar las directivas de sitio de red, esto puede realizarse sólo mediante el uso de cmdlets desde el Skype de consola de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="3194e-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="3194e-110">Puede crear, modificar y quitar un vínculo de sitio de red (también conocido como una directiva entre sitios de red) de la Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="3194e-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="3194e-111">Para crear un vínculo de sitio de red</span><span class="sxs-lookup"><span data-stu-id="3194e-111">To create a network site link</span></span>

1.  <span data-ttu-id="3194e-112">Inicie sesión en el equipo donde está instalado Skype para Shell de administración de servidor empresarial como un miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios.</span><span class="sxs-lookup"><span data-stu-id="3194e-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="3194e-113">Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="3194e-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="3194e-114">En el símbolo del sistema, escriba el siguiente comando, sustituyendo los valores que son válidos para su configuración:</span><span class="sxs-lookup"><span data-stu-id="3194e-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="3194e-115">En este ejemplo se crea un nuevo vínculo de sitio de red denominado Reno\_Portland que establece las limitaciones de ancho de banda entre los sitios de red Reno y Portland.</span><span class="sxs-lookup"><span data-stu-id="3194e-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="3194e-116">Los sitios de red y el perfil de directiva de ancho de banda ya deben existir antes de ejecutar este comando.</span><span class="sxs-lookup"><span data-stu-id="3194e-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="3194e-117">Para obtener descripciones de parámetros detalladas, vea [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="3194e-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="3194e-118">Para recuperar una lista de perfiles de directivas de ancho de banda que se puede aplicar el vínculo de sitio de red, llamar al cmdlet **Get-CsNetworkBandwidthPolicyProfile** .</span><span class="sxs-lookup"><span data-stu-id="3194e-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="3194e-119">Para obtener información detallada, vea [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="3194e-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="3194e-120">Para modificar un vínculo de sitio de red</span><span class="sxs-lookup"><span data-stu-id="3194e-120">To modify a network site link</span></span>

1.  <span data-ttu-id="3194e-121">Inicie sesión en el equipo donde está instalado Skype para Shell de administración de servidor empresarial como un miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios.</span><span class="sxs-lookup"><span data-stu-id="3194e-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="3194e-122">Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="3194e-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="3194e-123">Use el cmdlet **Set-CsNetworkInterSitePolicy** para modificar las propiedades de un vínculo de sitio de red determinado.</span><span class="sxs-lookup"><span data-stu-id="3194e-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="3194e-124">Puede modificar una (o ambas) o los sitios conectados y se puede modificar el perfil de directiva de ancho de banda asociado con el vínculo.</span><span class="sxs-lookup"><span data-stu-id="3194e-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="3194e-125">Este es un ejemplo de cómo modificar el perfil de directiva de ancho de banda de un vínculo de sitio denominado Reno\_Portland:</span><span class="sxs-lookup"><span data-stu-id="3194e-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="3194e-126">Para obtener descripciones de parámetros detalladas, consulte [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="3194e-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="3194e-127">Para eliminar un vínculo de sitio de red</span><span class="sxs-lookup"><span data-stu-id="3194e-127">To delete a network site link</span></span>

1.  <span data-ttu-id="3194e-128">Inicie sesión en el equipo donde está instalado Skype para Shell de administración de servidor empresarial como un miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios.</span><span class="sxs-lookup"><span data-stu-id="3194e-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="3194e-129">Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="3194e-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="3194e-130">Use el cmdlet **Remove-CsNetworkInterSitePolicy** para quitar un vínculo de sitio de red.</span><span class="sxs-lookup"><span data-stu-id="3194e-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="3194e-131">En el ejemplo siguiente se elimina el Reno\_vínculo de sitio de red de Portland:</span><span class="sxs-lookup"><span data-stu-id="3194e-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="3194e-132">Para obtener descripciones de parámetros detalladas, consulte [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="3194e-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="3194e-133">Ver información de sitios de red</span><span class="sxs-lookup"><span data-stu-id="3194e-133">View network site information</span></span>

<span data-ttu-id="3194e-134">Sitios de red son las oficinas o las ubicaciones configuradas dentro de cada región de un control de admisión de llamadas (CAC) o la implementación de Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="3194e-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="3194e-135">Puede ver información de sitio de red en puede ser la Skype para el Panel de Control de servidor empresarial o el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="3194e-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="3194e-136">Para ver la información de sitio de red en Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="3194e-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="3194e-137">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3194e-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3194e-138">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="3194e-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3194e-139">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **sitio**.</span><span class="sxs-lookup"><span data-stu-id="3194e-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="3194e-140">En la página del **sitio** , haga clic en el sitio que desea ver.</span><span class="sxs-lookup"><span data-stu-id="3194e-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="3194e-141">Sólo se puede ver información para un sitio a la vez.</span><span class="sxs-lookup"><span data-stu-id="3194e-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="3194e-142">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="3194e-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3194e-143">Visualización de información de sitio de red mediante el uso de cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3194e-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="3194e-144">Puede ver información de sitio de red mediante el uso de Windows PowerShell y el cmdlet Get-CsNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="3194e-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="3194e-145">Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3194e-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="3194e-146">Para ver la información de sitio de red</span><span class="sxs-lookup"><span data-stu-id="3194e-146">To view network site information</span></span>

  - <span data-ttu-id="3194e-147">Para ver información acerca de todos los sitios de red, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="3194e-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="3194e-148">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="3194e-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="3194e-149">Para obtener más información, vea el tema de ayuda para el cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .</span><span class="sxs-lookup"><span data-stu-id="3194e-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="3194e-150">Crear o modificar sitios de red</span><span class="sxs-lookup"><span data-stu-id="3194e-150">Create or modify network sites</span></span> 

<span data-ttu-id="3194e-151">Sitios de red son las oficinas o las ubicaciones configuradas dentro de cada región de un control de admisión de llamadas (CAC) o la implementación de Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="3194e-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="3194e-152">Puede usar el Skype para el Panel de Control de servidor empresarial para configurar sitios y asociarlos a regiones.</span><span class="sxs-lookup"><span data-stu-id="3194e-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="3194e-153">Por ejemplo, una región de red para Norteamérica podría ser asociada a los sitios de redes como Chicago, Redmond y Vancouver.</span><span class="sxs-lookup"><span data-stu-id="3194e-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="3194e-154">Debe crearse un sitio de red CAC para cada sitio dentro de una organización, incluso si ese sitio tiene no hay limitaciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="3194e-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="3194e-155">Desde el Skype para el Panel de Control de servidor empresarial puede crear, modificar y eliminar sitios de red.</span><span class="sxs-lookup"><span data-stu-id="3194e-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="3194e-156">Use los procedimientos siguientes para crear o modificar un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="3194e-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="3194e-157">Para crear un sitio de red</span><span class="sxs-lookup"><span data-stu-id="3194e-157">To create a network site</span></span>

1.  <span data-ttu-id="3194e-158">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3194e-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3194e-159">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="3194e-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3194e-160">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **sitio**.</span><span class="sxs-lookup"><span data-stu-id="3194e-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="3194e-161">En la página del **sitio** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3194e-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="3194e-162">En el **Nuevo sitio**, escriba un nombre para este sitio en el campo **nombre** .</span><span class="sxs-lookup"><span data-stu-id="3194e-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="3194e-163">Los nombres de sitios deben ser únicos dentro de la Skype para la implementación de Business Server.</span><span class="sxs-lookup"><span data-stu-id="3194e-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="3194e-164">En la lista desplegable **región** , seleccione una región de red para asociar con este sitio.</span><span class="sxs-lookup"><span data-stu-id="3194e-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="3194e-165">(Opcional) Si desea poner limitaciones de ancho de banda en llamadas de audio o vídeos a este sitio, seleccione el perfil de directiva de ancho de banda con la configuración correspondiente de la lista desplegable **Directiva de ancho de banda** .</span><span class="sxs-lookup"><span data-stu-id="3194e-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="3194e-166">Puede ver los detalles de los perfiles de directiva de ancho de banda disponible, o crear un nuevo perfil de directiva de ancho de banda, en la página **Perfiles de directiva de** grupo de la **Configuración de red** .</span><span class="sxs-lookup"><span data-stu-id="3194e-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="3194e-167">Para obtener información detallada, vea [perfiles de directivas de ancho de banda de red de administración](managing-network-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3194e-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="3194e-168">(Opcional) Si desea proporcionar parámetros de ubicación para este sitio, seleccione una directiva de ubicación de la lista desplegable **Directiva de ubicación** .</span><span class="sxs-lookup"><span data-stu-id="3194e-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="3194e-169">La directiva de ubicación asigna específico Enhanced 9-1-1 (E9-1-1) y el cliente de configuración de ubicación al sitio.</span><span class="sxs-lookup"><span data-stu-id="3194e-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="3194e-170">Puede ver los detalles de las directivas de ubicación disponibles, o crear una nueva directiva de ubicación, desde la página **Directiva de ubicación** del grupo de **Configuración de red** .</span><span class="sxs-lookup"><span data-stu-id="3194e-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="3194e-171">(Opcional) Escriba un valor en el campo **Descripción** para proporcionar más información acerca de este sitio que se pueda deducir de su nombre.</span><span class="sxs-lookup"><span data-stu-id="3194e-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="3194e-172">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3194e-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="3194e-173">No use la tabla de **Subredes asociadas** al crear un nuevo sitio de red.</span><span class="sxs-lookup"><span data-stu-id="3194e-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="3194e-174">Asociar una subred a un sitio al crear o modificar la subred.</span><span class="sxs-lookup"><span data-stu-id="3194e-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="3194e-175">Para obtener información detallada, vea [Managing subredes de la red](managing-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="3194e-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="3194e-176">Para modificar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="3194e-176">To modify a network site</span></span>

1.  <span data-ttu-id="3194e-177">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3194e-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3194e-178">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="3194e-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3194e-179">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **sitio**.</span><span class="sxs-lookup"><span data-stu-id="3194e-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="3194e-180">En la página del **sitio** , haga clic en el sitio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="3194e-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="3194e-181">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="3194e-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="3194e-182">En la página **Modificar sitio** , puede modificar la descripción, región, perfil de directiva de ancho de banda y directiva de ubicación asociada con el sitio.</span><span class="sxs-lookup"><span data-stu-id="3194e-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="3194e-183">Para obtener más información, vea [para crear un sitio de red](#to-create-a-network-site) anterior.</span><span class="sxs-lookup"><span data-stu-id="3194e-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="3194e-184">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3194e-184">Click **Commit**.</span></span>

<span data-ttu-id="3194e-185">No se puede modificar la tabla de **Subredes asociadas** en esta página.</span><span class="sxs-lookup"><span data-stu-id="3194e-185">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="3194e-186">La lista de subredes asociadas se proporciona como referencia para que tener en cuenta qué subredes se verán afectadas cuando se modifica la configuración del sitio.</span><span class="sxs-lookup"><span data-stu-id="3194e-186">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="3194e-187">Eliminación de un sitio de red existente</span><span class="sxs-lookup"><span data-stu-id="3194e-187">Delete an existing network site</span></span>

<span data-ttu-id="3194e-188">Sitios de red son las oficinas o las ubicaciones configuradas dentro de cada región de un control de admisión de llamadas (CAC) o la implementación de Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="3194e-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="3194e-189">Puede usar el Skype para el Panel de Control de servidor empresarial para configurar sitios y asociarlos a regiones.</span><span class="sxs-lookup"><span data-stu-id="3194e-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="3194e-190">Por ejemplo, una región de red para Norteamérica podría ser asociada a los sitios de redes como Chicago, Redmond y Vancouver.</span><span class="sxs-lookup"><span data-stu-id="3194e-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="3194e-191">Debe crearse un sitio de red CAC para cada sitio dentro de una organización, incluso si ese sitio tiene no hay limitaciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="3194e-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="3194e-192">Desde el Skype para el Panel de Control de servidor empresarial puede crear, modificar y eliminar sitios de red.</span><span class="sxs-lookup"><span data-stu-id="3194e-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="3194e-193">Use el procedimiento siguiente para eliminar un sitio de red existente.</span><span class="sxs-lookup"><span data-stu-id="3194e-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="3194e-194">Para obtener información detallada acerca de la creación o modificación de sitios de red, consulte [Managing control de admisión de llamadas para los sitios](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="3194e-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="3194e-195">Para eliminar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="3194e-195">To delete a network site</span></span>

1.  <span data-ttu-id="3194e-196">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3194e-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3194e-197">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="3194e-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3194e-198">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **sitio**.</span><span class="sxs-lookup"><span data-stu-id="3194e-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="3194e-199">En la página del **sitio** , haga clic en el sitio que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="3194e-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="3194e-200">Puede eliminar más de un sitio a la vez.</span><span class="sxs-lookup"><span data-stu-id="3194e-200">You can delete more than one site at a time.</span></span> <span data-ttu-id="3194e-201">Para ello, presione la tecla CTRL y seleccione varios sitios mientras mantiene presionada la tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="3194e-201">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="3194e-202">O bien, para seleccionar todos los sitios, haga clic en **Seleccionar todo** en el menú **Edición** .</span><span class="sxs-lookup"><span data-stu-id="3194e-202">Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="3194e-203">En el menú **Edición** , haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="3194e-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="3194e-204">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3194e-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="3194e-205">No se puede quitar un sitio de red si está asociada con una subred de red.</span><span class="sxs-lookup"><span data-stu-id="3194e-205">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="3194e-206">Si se intenta eliminar un sitio asociado con una subred recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="3194e-206">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="3194e-207">Para ver si un sitio está asociado a las subredes, haga clic en el sitio y, a continuación, haga clic en **Mostrar detalles** en el menú **Edición** .</span><span class="sxs-lookup"><span data-stu-id="3194e-207">To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="3194e-208">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3194e-208">See Also</span></span>


[<span data-ttu-id="3194e-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="3194e-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="3194e-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="3194e-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="3194e-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="3194e-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="3194e-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="3194e-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="3194e-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="3194e-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="3194e-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="3194e-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="3194e-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="3194e-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="3194e-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="3194e-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="3194e-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="3194e-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  