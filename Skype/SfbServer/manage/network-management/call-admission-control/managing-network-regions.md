---
title: Administrar regiones de red
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Región de red * son los concentradores de red o las redes troncales que se usan en la configuración de control de admisión de llamadas, E9-1-1 y omisión de medios.
ms.openlocfilehash: 8d1d60389fe910e2b5c2b8b1c357520aad30db96
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279532"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="4b958-103">Administrar regiones de red en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4b958-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="4b958-104">Las *regiones de red* son los concentradores de red o las redes troncales que se usan en la configuración de control de admisión de llamadas, E9-1-1 y omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="4b958-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="4b958-105">Use los procedimientos siguientes para ver, crear o modificar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="4b958-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="4b958-106">Por ejemplo, si ya ha creado regiones de red para una característica de voz, no es necesario crear regiones de red nuevas; otras características avanzadas de telefonía empresarial usarán esas mismas regiones de red.</span><span class="sxs-lookup"><span data-stu-id="4b958-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="4b958-107">Sin embargo, es posible que necesite modificar una definición de región de red existente para aplicar una configuración específica de una característica.</span><span class="sxs-lookup"><span data-stu-id="4b958-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="4b958-108">Por ejemplo, si ha creado regiones de red para E9-1-1 (que no requieren un sitio central asociado) y, a continuación, implementa el control de admisión de llamadas, debe modificar las definiciones de región de red para especificar un sitio central.</span><span class="sxs-lookup"><span data-stu-id="4b958-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="4b958-109">Use los procedimientos de este artículo para ver información sobre la región de red o crear, modificar o eliminar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="4b958-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="4b958-110">Ver información de la región de red</span><span class="sxs-lookup"><span data-stu-id="4b958-110">View network region information</span></span> 


<span data-ttu-id="4b958-111">Una región de red interconecta varias partes de una red en varias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="4b958-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="4b958-112">Cada región de la red debe estar asociada con un sitio central.</span><span class="sxs-lookup"><span data-stu-id="4b958-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="4b958-113">El sitio central es el sitio del centro de datos en el que se está ejecutando el servicio de directivas de ancho de banda de control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="4b958-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="4b958-114">Puede usar el panel de control de Skype empresarial Server para ver las regiones de red.</span><span class="sxs-lookup"><span data-stu-id="4b958-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="4b958-115">Las regiones de red incluyen opciones que determinan si se permiten rutas alternativas a través de Internet para conexiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="4b958-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="4b958-116">Use este tema para ver las regiones de red existentes.</span><span class="sxs-lookup"><span data-stu-id="4b958-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="4b958-117">Para ver información sobre una región de red con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4b958-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="4b958-118">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4b958-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4b958-119">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4b958-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4b958-120">En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **región**.</span><span class="sxs-lookup"><span data-stu-id="4b958-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="4b958-121">En la página **región** , haga clic en la región que desea ver.</span><span class="sxs-lookup"><span data-stu-id="4b958-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="4b958-122">Solo puedes ver una región a la vez.</span><span class="sxs-lookup"><span data-stu-id="4b958-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="4b958-123">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="4b958-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4b958-124">Ver información de la región de red mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b958-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="4b958-125">Puede ver la información de la región de red mediante Windows PowerShell y el cmdlet **Get-CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="4b958-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="4b958-126">Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b958-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="4b958-127">Para ver la información de la región de red</span><span class="sxs-lookup"><span data-stu-id="4b958-127">To view network region information</span></span>

  - <span data-ttu-id="4b958-128">Para ver información sobre todas las regiones de la red, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="4b958-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="4b958-129">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b958-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="4b958-130">Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .</span><span class="sxs-lookup"><span data-stu-id="4b958-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="4b958-131">Crear o modificar regiones de red</span><span class="sxs-lookup"><span data-stu-id="4b958-131">Create or modify network regions</span></span> 

<span data-ttu-id="4b958-132">Una región de red interconecta varias partes de una red en varias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="4b958-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="4b958-133">Cada región de la red debe estar asociada con un sitio central.</span><span class="sxs-lookup"><span data-stu-id="4b958-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="4b958-134">El sitio central es el sitio del centro de datos en el que se está ejecutando el servicio de directivas de ancho de banda de control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="4b958-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="4b958-135">Puede usar el panel de control de Skype empresarial Server para configurar las regiones de red.</span><span class="sxs-lookup"><span data-stu-id="4b958-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="4b958-136">Las regiones de red incluyen opciones que determinan si se permiten rutas alternativas a través de Internet para conexiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="4b958-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="4b958-137">Desde el panel de control de Skype empresarial Server, puede crear, modificar o eliminar una región de red.</span><span class="sxs-lookup"><span data-stu-id="4b958-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="4b958-138">Use este tema para crear y modificar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="4b958-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="4b958-139">Para crear una región de red</span><span class="sxs-lookup"><span data-stu-id="4b958-139">To create a network region</span></span>

1.  <span data-ttu-id="4b958-140">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4b958-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4b958-141">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4b958-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4b958-142">En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **región**.</span><span class="sxs-lookup"><span data-stu-id="4b958-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="4b958-143">En la página **región** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4b958-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="4b958-144">En la página **nueva región** , escriba un valor en el campo **nombre** .</span><span class="sxs-lookup"><span data-stu-id="4b958-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="4b958-145">Este valor debe ser único dentro de la implementación de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4b958-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="4b958-146">En la lista desplegable **sitio central** , seleccione el sitio central de esta región de red.</span><span class="sxs-lookup"><span data-stu-id="4b958-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="4b958-147">La casilla de verificación **Habilitar ruta alternativa de audio** está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4b958-147">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="4b958-148">Este campo determina si las llamadas de audio se redirigirán a través de una ruta de acceso alternativa si el ancho de banda adecuado no existe en la ruta de acceso principal.</span><span class="sxs-lookup"><span data-stu-id="4b958-148">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="4b958-149">Desactive esta casilla solo si necesita desactivar la descarga en Internet.</span><span class="sxs-lookup"><span data-stu-id="4b958-149">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="4b958-150">Si cualquiera de las llamadas va a ser de Internet, esta casilla debe estar activada, independientemente de la configuración del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="4b958-150">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="4b958-151">La casilla de verificación **Habilitar ruta alternativa de vídeo** está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4b958-151">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="4b958-152">Este campo determina si las videollamadas se redirigirán a través de una ruta alternativa si el ancho de banda adecuado no existe en la ruta de acceso principal.</span><span class="sxs-lookup"><span data-stu-id="4b958-152">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="4b958-153">Desactive esta casilla solo si necesita desactivar la descarga en Internet.</span><span class="sxs-lookup"><span data-stu-id="4b958-153">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="4b958-154">Si cualquiera de las llamadas va a ser de Internet, esta casilla debe estar activada, independientemente de la configuración del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="4b958-154">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="4b958-155">Faculta Escriba un valor en el campo **Descripción** para proporcionar más información sobre esta región que no puede expresarse solo por el nombre.</span><span class="sxs-lookup"><span data-stu-id="4b958-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="4b958-156">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4b958-156">Click **Commit**.</span></span>

<span data-ttu-id="4b958-157">La tabla de **sitios asociados** no se usa para crear una región de red.</span><span class="sxs-lookup"><span data-stu-id="4b958-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="4b958-158">Al crear o modificar el sitio, se asocia un sitio con una región.</span><span class="sxs-lookup"><span data-stu-id="4b958-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="4b958-159">Para obtener más información, consulte [administrar el control de admisión de llamadas para sitios](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="4b958-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="4b958-160">Para modificar una región de red</span><span class="sxs-lookup"><span data-stu-id="4b958-160">To modify a network region</span></span>

1.  <span data-ttu-id="4b958-161">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4b958-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4b958-162">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4b958-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4b958-163">En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **región**.</span><span class="sxs-lookup"><span data-stu-id="4b958-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="4b958-164">En la página **región** , haga clic en la región que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="4b958-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="4b958-165">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="4b958-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="4b958-166">En la página **Editar región** , puede modificar la configuración para habilitar y deshabilitar rutas de audio y vídeo alternativas, y cambiar la descripción (para obtener información detallada, consulte la sección "para crear una región de red" anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="4b958-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="4b958-167">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4b958-167">Click **Commit**.</span></span>

<span data-ttu-id="4b958-168">No puede modificar los **sitios asociados** en esta página.</span><span class="sxs-lookup"><span data-stu-id="4b958-168">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="4b958-169">La lista de sitios asociados se proporciona como referencia para que usted sepa qué sitios se verán afectados al modificar la configuración de la región.</span><span class="sxs-lookup"><span data-stu-id="4b958-169">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="4b958-170">Eliminar regiones de red existentes</span><span class="sxs-lookup"><span data-stu-id="4b958-170">Delete existing network regions</span></span> 

<span data-ttu-id="4b958-171">Una región de red interconecta varias partes de una red en varias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="4b958-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="4b958-172">Cada región de la red debe estar asociada con un sitio central.</span><span class="sxs-lookup"><span data-stu-id="4b958-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="4b958-173">El sitio central es el sitio del centro de datos en el que se está ejecutando el servicio de directivas de ancho de banda de control de admisión de llamadas (CAC).</span><span class="sxs-lookup"><span data-stu-id="4b958-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="4b958-174">Puede usar el panel de control de Skype empresarial Server para configurar las regiones de red.</span><span class="sxs-lookup"><span data-stu-id="4b958-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="4b958-175">Las regiones de red incluyen opciones que determinan si se permiten rutas alternativas a través de Internet para conexiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="4b958-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="4b958-176">Desde el panel de control de Skype empresarial Server, puede crear, modificar o eliminar una región de red.</span><span class="sxs-lookup"><span data-stu-id="4b958-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="4b958-177">Use este tema para eliminar regiones de red existentes.</span><span class="sxs-lookup"><span data-stu-id="4b958-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="4b958-178">Para eliminar una región de red</span><span class="sxs-lookup"><span data-stu-id="4b958-178">To delete a network region</span></span>

1.  <span data-ttu-id="4b958-179">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4b958-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4b958-180">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4b958-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4b958-181">En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **región**.</span><span class="sxs-lookup"><span data-stu-id="4b958-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="4b958-182">En la página **región** , haga clic en la región que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="4b958-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="4b958-183">Puedes eliminar más de una región a la vez.</span><span class="sxs-lookup"><span data-stu-id="4b958-183">You can delete more than one region at a time.</span></span> <span data-ttu-id="4b958-184">Para ello, presione CTRL y seleccione varias regiones mientras mantiene presionada la tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="4b958-184">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="4b958-185">O bien, para seleccionar todas las regiones, haga clic en **seleccionar todo** en el menú **edición** .</span><span class="sxs-lookup"><span data-stu-id="4b958-185">Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="4b958-186">En el menú **Editar** , haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4b958-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="4b958-187">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4b958-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="4b958-188">No se puede quitar una región de red si está asociada a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="4b958-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="4b958-189">Si intenta quitar una región asociada a un sitio, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="4b958-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="4b958-190">Para ver si una región está asociada a algún sitio, seleccione la región y, a continuación, haga clic en **Mostrar detalles** en el menú **edición** .</span><span class="sxs-lookup"><span data-stu-id="4b958-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="4b958-191">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b958-191">See Also</span></span>

[<span data-ttu-id="4b958-192">Administrar rutas de regiones de red</span><span class="sxs-lookup"><span data-stu-id="4b958-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="4b958-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="4b958-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="4b958-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="4b958-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="4b958-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="4b958-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="4b958-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="4b958-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
