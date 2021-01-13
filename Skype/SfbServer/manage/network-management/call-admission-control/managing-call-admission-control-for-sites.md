---
title: Administración del control de admisión de llamadas para sitios
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Los sitios de red se encuentran oficinas o ubicaciones dentro de cada región de la red de control de admisión de llamadas (CAC), E9-1-1 y las implementaciones de desvío de medios.
ms.openlocfilehash: dbe02c78c40cab48a79d7c63d3c6239b4ae59458
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816460"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="54212-103">Administrar el control de admisión de llamadas para sitios en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="54212-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="54212-104">Los sitios de red se encuentran oficinas o ubicaciones dentro de cada región de la red de control de admisión de llamadas (CAC), E9-1-1 y las implementaciones de desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="54212-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="54212-105">Use los procedimientos descritos en este artículo para configurar el control de admisión de llamadas para sitios de red.</span><span class="sxs-lookup"><span data-stu-id="54212-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="54212-106">Configurar vínculos de sitio de red</span><span class="sxs-lookup"><span data-stu-id="54212-106">Configure network site links</span></span>

<span data-ttu-id="54212-107">Dentro de una configuración de control de admisión de llamadas (CAC), puede crear directivas entre sitios de red que definan limitaciones de ancho de banda entre sitios que están vinculados directamente.</span><span class="sxs-lookup"><span data-stu-id="54212-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="54212-108">Cuando los sitios de red comparten un vínculo directo, es posible definir limitaciones de ancho de banda para las conexiones de audio y vídeo entre ambos sitos.</span><span class="sxs-lookup"><span data-stu-id="54212-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="54212-109">No puede usar el Panel de control de Skype Empresarial Server para configurar directivas de sitio de red, esto solo se puede hacer con cmdlets del Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="54212-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="54212-110">Puede crear, modificar y quitar un vínculo de sitio de red (también conocido como directiva entre sitios de red) del Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="54212-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="54212-111">Para crear un vínculo de sitio de red</span><span class="sxs-lookup"><span data-stu-id="54212-111">To create a network site link</span></span>

1.  <span data-ttu-id="54212-112">Inicie sesión en el equipo donde está instalado el Shell de administración de Skype Empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios.</span><span class="sxs-lookup"><span data-stu-id="54212-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="54212-113">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en Skype Empresarial **Server** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="54212-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="54212-114">Desde el símbolo del sistema, escriba el comando siguiente, usando los valores aplicables a su configuración:</span><span class="sxs-lookup"><span data-stu-id="54212-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="54212-115">En este ejemplo se crea un nuevo vínculo de sitio de red denominado Reno Portland que establece las limitaciones de ancho de banda entre los sitios de red \_ de Reno y Portland.</span><span class="sxs-lookup"><span data-stu-id="54212-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="54212-116">El perfil de la directiva de sitios de red y de ancho de banda debe existir antes de ejecutar este comando.</span><span class="sxs-lookup"><span data-stu-id="54212-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="54212-117">Para obtener descripciones detalladas de los parámetros, [consulte New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="54212-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="54212-118">Para recuperar una lista de perfiles de directivas de ancho de banda que puedan aplicarse al vínculo de sitio de red, ejecute el cmdlet **Get-CsNetworkBandwidthPolicyProfile**.</span><span class="sxs-lookup"><span data-stu-id="54212-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="54212-119">Para obtener más información, [consulte Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="54212-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="54212-120">Para modificar un vínculo de sitio de red</span><span class="sxs-lookup"><span data-stu-id="54212-120">To modify a network site link</span></span>

1.  <span data-ttu-id="54212-121">Inicie sesión en el equipo donde está instalado el Shell de administración de Skype Empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios.</span><span class="sxs-lookup"><span data-stu-id="54212-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="54212-122">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en Skype Empresarial **Server** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="54212-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="54212-123">Use el cmdlet **Set-CsNetworkInterSitePolicy** para modificar las propiedades de un vínculo de sitio de red.</span><span class="sxs-lookup"><span data-stu-id="54212-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="54212-124">Puede modificar uno de los sitios conectados (o ambos), y también puede modificar el perfil de directiva de banda de ancha asociado al vínculo.</span><span class="sxs-lookup"><span data-stu-id="54212-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="54212-125">Este es un ejemplo de modificación del perfil de directiva de ancho de banda de un vínculo de sitio denominado Reno \_ Portland:</span><span class="sxs-lookup"><span data-stu-id="54212-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="54212-126">Para obtener descripciones detalladas de los parámetros, [vea Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="54212-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="54212-127">Para eliminar un vínculo de sitio de red</span><span class="sxs-lookup"><span data-stu-id="54212-127">To delete a network site link</span></span>

1.  <span data-ttu-id="54212-128">Inicie sesión en el equipo donde está instalado el Shell de administración de Skype Empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios.</span><span class="sxs-lookup"><span data-stu-id="54212-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="54212-129">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en Skype Empresarial **Server** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="54212-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="54212-130">Use el cmdlet **Remove-CsNetworkInterSitePolicy** para quitar un vínculo de sitio de red.</span><span class="sxs-lookup"><span data-stu-id="54212-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="54212-131">En el siguiente ejemplo se elimina el vínculo de sitio de red Reno \_ Portland:</span><span class="sxs-lookup"><span data-stu-id="54212-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="54212-132">Para obtener descripciones detalladas de los parámetros, [consulte Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="54212-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="54212-133">Ver información del sitio de red</span><span class="sxs-lookup"><span data-stu-id="54212-133">View network site information</span></span>

<span data-ttu-id="54212-134">Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de una implementación de Enhanced 9-1-1 o control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="54212-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="54212-135">Puede ver la información del sitio de red en el Panel de control de Skype Empresarial Server o en el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="54212-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="54212-136">Para ver la información del sitio de red en el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="54212-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="54212-137">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="54212-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="54212-138">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="54212-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="54212-139">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en **Sitio.**</span><span class="sxs-lookup"><span data-stu-id="54212-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="54212-140">En la página **Sitio**, haga clic en el sitio que desea ver.</span><span class="sxs-lookup"><span data-stu-id="54212-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="54212-141">Solo puede ver información para un sitio cada vez.</span><span class="sxs-lookup"><span data-stu-id="54212-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="54212-142">En el menú  **Editar**, haga clic en  **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="54212-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="54212-143">Visualización de la información del sitio de red mediante Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="54212-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="54212-144">Puede ver la información del sitio de red mediante Windows PowerShell y el cmdlet Get-CsNetworkSite web.</span><span class="sxs-lookup"><span data-stu-id="54212-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="54212-145">Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54212-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="54212-146">Para ver la información de sitio de red</span><span class="sxs-lookup"><span data-stu-id="54212-146">To view network site information</span></span>

  - <span data-ttu-id="54212-147">Para ver información sobre todos los sitios de red, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="54212-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="54212-148">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="54212-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="54212-149">Para obtener más información, vea el tema de la Ayuda para el cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="54212-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="54212-150">Crear o modificar sitios de red</span><span class="sxs-lookup"><span data-stu-id="54212-150">Create or modify network sites</span></span> 

<span data-ttu-id="54212-151">Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de una implementación de Enhanced 9-1-1 o control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="54212-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="54212-152">Puede usar el Panel de control de Skype Empresarial Server para configurar sitios y asociarlos a regiones.</span><span class="sxs-lookup"><span data-stu-id="54212-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="54212-153">Por ejemplo, una región de red para Norteamérica se podría asociar con sitios de red como Chicago, Redmond y Vancouver.</span><span class="sxs-lookup"><span data-stu-id="54212-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="54212-154">Debe crearse un sitio de red CAC para cada sitio de una organización, incluso aunque no tenga limitaciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="54212-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="54212-155">Desde el Panel de control de Skype Empresarial Server puede crear, modificar y eliminar sitios de red.</span><span class="sxs-lookup"><span data-stu-id="54212-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="54212-156">Utilice los procedimientos siguientes para crear o modificar un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="54212-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="54212-157">Para crear un sitio de red</span><span class="sxs-lookup"><span data-stu-id="54212-157">To create a network site</span></span>

1.  <span data-ttu-id="54212-158">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="54212-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="54212-159">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="54212-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="54212-160">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en **Sitio.**</span><span class="sxs-lookup"><span data-stu-id="54212-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="54212-161">En la página **Sitio**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="54212-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="54212-162">En **Sitio nuevo**, escriba un nombre para este sitio en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="54212-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="54212-163">Los nombres de sitio deben ser únicos en la implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="54212-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="54212-164">En la lista desplegable **Región**, seleccione una región de red para asociarla con este sitio.</span><span class="sxs-lookup"><span data-stu-id="54212-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="54212-165">(Opcional) Si desea definir limitaciones de ancho de banda en las llamadas de audio o vídeo para este sitio, seleccione el perfil de directiva de ancho de banda con la configuración adecuada en la lista desplegable **Directiva de ancho de banda**.</span><span class="sxs-lookup"><span data-stu-id="54212-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="54212-166">Puede ver los detalles de los perfiles de directiva de ancho  de banda disponibles o crear un nuevo perfil de directiva de ancho de banda en la página Perfil de directiva del grupo **Configuración de** red.</span><span class="sxs-lookup"><span data-stu-id="54212-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="54212-167">Para obtener más información, consulte [Administración de perfiles de directiva de ancho de banda de red.](managing-network-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="54212-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="54212-168">(Opcional) Si desea proporcionar parámetros de ubicación para este sitio, seleccione una directiva de ubicación de la lista desplegable **Directiva de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="54212-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="54212-169">La directiva de ubicación asigna al sitio un Enhanced 9-1-1 (E9-1-1) específico y parámetros de ubicación de cliente.</span><span class="sxs-lookup"><span data-stu-id="54212-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="54212-170">Puede ver la información detallada de las directivas de ubicación disponibles o crear una nueva desde la página **Directiva de ubicación** del grupo **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="54212-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="54212-171">(Opcional) Escriba un valor en el campo **Descripción** para proporcionar más información acerca de este sitio más allá de lo que se pueda deducir de su nombre.</span><span class="sxs-lookup"><span data-stu-id="54212-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="54212-172">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="54212-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="54212-173">No use la tabla **Subredes asociadas** al crear un sitio de red nuevo.</span><span class="sxs-lookup"><span data-stu-id="54212-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="54212-174">Al crear o modificar la subred, asocie una subred con un sitio.</span><span class="sxs-lookup"><span data-stu-id="54212-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="54212-175">Para obtener más información, consulte [Administración de subredes de red.](managing-network-subnets.md)</span><span class="sxs-lookup"><span data-stu-id="54212-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="54212-176">Para modificar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="54212-176">To modify a network site</span></span>

1.  <span data-ttu-id="54212-177">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="54212-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="54212-178">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="54212-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="54212-179">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en **Sitio.**</span><span class="sxs-lookup"><span data-stu-id="54212-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="54212-180">En la página **Sitio**, haga clic en el sitio que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="54212-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="54212-181">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="54212-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="54212-182">En la página **Editar sitio**, puede modificar la descripción, la región, el perfil de directiva de ancho de banda y la directiva de ubicación asociados con el sitio.</span><span class="sxs-lookup"><span data-stu-id="54212-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="54212-183">Para obtener más información, [consulte Para crear un sitio de red anterior.](#to-create-a-network-site)</span><span class="sxs-lookup"><span data-stu-id="54212-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="54212-184">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="54212-184">Click **Commit**.</span></span>

<span data-ttu-id="54212-p114">No es posible modificar la tabla **Subredes asociadas** de esta página. La lista de subredes asociadas solo es de referencia, por lo que debe conocer qué subredes se verán afectadas cuando modifique la configuración del sitio.</span><span class="sxs-lookup"><span data-stu-id="54212-p114">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="54212-187">Eliminar un sitio de red existente</span><span class="sxs-lookup"><span data-stu-id="54212-187">Delete an existing network site</span></span>

<span data-ttu-id="54212-188">Los sitios de red son las oficinas o ubicaciones configuradas dentro de cada región de una implementación de Enhanced 9-1-1 o control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="54212-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="54212-189">Puede usar el Panel de control de Skype Empresarial Server para configurar sitios y asociarlos a regiones.</span><span class="sxs-lookup"><span data-stu-id="54212-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="54212-190">Por ejemplo, una región de red para Norteamérica se podría asociar con sitios de red como Chicago, Redmond y Vancouver.</span><span class="sxs-lookup"><span data-stu-id="54212-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="54212-191">Debe crearse un sitio de red CAC para cada sitio de una organización, incluso aunque no tenga limitaciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="54212-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="54212-192">Desde el Panel de control de Skype Empresarial Server puede crear, modificar y eliminar sitios de red.</span><span class="sxs-lookup"><span data-stu-id="54212-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="54212-193">Utilice el procedimiento siguiente para eliminar un sitio de red existente.</span><span class="sxs-lookup"><span data-stu-id="54212-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="54212-194">Para obtener más información acerca de la creación o modificación de sitios de red, consulte Administración del control de [admisión de llamadas para sitios.](managing-call-admission-control-for-sites.md)</span><span class="sxs-lookup"><span data-stu-id="54212-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="54212-195">Para eliminar un sitio de red</span><span class="sxs-lookup"><span data-stu-id="54212-195">To delete a network site</span></span>

1.  <span data-ttu-id="54212-196">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="54212-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="54212-197">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="54212-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="54212-198">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en **Sitio.**</span><span class="sxs-lookup"><span data-stu-id="54212-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="54212-199">En la página **Sitio**, haga clic en el sitio que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="54212-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="54212-p116">Puede eliminar más de un sitio en la misma operación. Para hacerlo, pulse CTRL y seleccione varios sitios manteniendo pulsada la tecla CTRL. O bien, para seleccionar todos los sitios, haga clic en **Seleccionar todo** en el menú **Editar**.</span><span class="sxs-lookup"><span data-stu-id="54212-p116">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="54212-203">En el menú **Editar**, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="54212-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="54212-204">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="54212-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="54212-p117">No se puede eliminar un sitio de red si está asociado con la subred de una red. Si intenta quitar un sitio asociado a una subred, recibirá un mensaje de error. Para ver si un sitio está asociado con alguna subred, haga clic en el sitio y, a continuación, haga clic en **Mostrar detalles** en el menú **Editar**.</span><span class="sxs-lookup"><span data-stu-id="54212-p117">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="54212-208">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54212-208">See Also</span></span>


[<span data-ttu-id="54212-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="54212-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="54212-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="54212-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="54212-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="54212-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="54212-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="54212-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="54212-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="54212-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="54212-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="54212-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="54212-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="54212-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="54212-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="54212-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="54212-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="54212-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
