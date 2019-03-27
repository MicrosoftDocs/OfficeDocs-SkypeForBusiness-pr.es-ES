---
title: Administración de regiones de red
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Región de red * son los concentradores de red o redes troncales utilizados en la configuración de desvío de medios, E9-1-1 y control de admisión llamada.
ms.openlocfilehash: ea574fe981af679e4d841d786daf04460d1fb7c3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877632"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="0696f-103">Administrar regiones de red en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0696f-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="0696f-104">*Regiones de red* son los concentradores de red o redes troncales utilizados en la configuración de desvío de medios, E9-1-1 y control de admisión llamada.</span><span class="sxs-lookup"><span data-stu-id="0696f-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="0696f-105">Use los siguientes procedimientos para ver, crear o modificar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="0696f-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="0696f-106">Por ejemplo, si ya ha creado las regiones de red para una característica de voz, no es necesario crear nuevas regiones de red; otras características avanzadas de Enterprise Voice utilizará esas mismos regiones de red.</span><span class="sxs-lookup"><span data-stu-id="0696f-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="0696f-107">Sin embargo, es posible que necesite modificar una definición de región de red existente para aplicar una configuración específica de una característica.</span><span class="sxs-lookup"><span data-stu-id="0696f-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="0696f-108">Por ejemplo, si ha creado regiones de red para E9-1-1 (que no requieren un sitio central asociado) y, a continuación, implementa el control de admisión de llamadas, debe modificar las definiciones de región de red para especificar un sitio central.</span><span class="sxs-lookup"><span data-stu-id="0696f-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="0696f-109">Use los procedimientos de este artículo para ver la información de la región de red o crear, modificar o eliminar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="0696f-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="0696f-110">Ver información de región de red</span><span class="sxs-lookup"><span data-stu-id="0696f-110">View network region information</span></span> 


<span data-ttu-id="0696f-111">Una región de red interconexiones distintas partes de una red a través de varias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="0696f-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="0696f-112">Cada región de red debe estar asociado a un sitio central.</span><span class="sxs-lookup"><span data-stu-id="0696f-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="0696f-113">El sitio central es el sitio del centro de datos en el que se ejecuta el servicio de directiva de ancho de banda de llamada admisión control (CAC).</span><span class="sxs-lookup"><span data-stu-id="0696f-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="0696f-114">Puede usar Skype para el Panel de Control de servidor empresarial para ver las regiones de red.</span><span class="sxs-lookup"><span data-stu-id="0696f-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="0696f-115">Regiones de red incluyen opciones de configuración que determinan si se permiten las rutas de acceso alternativas a través de Internet para las conexiones de audio y vídeos.</span><span class="sxs-lookup"><span data-stu-id="0696f-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="0696f-116">Use este tema para ver las regiones de red existente.</span><span class="sxs-lookup"><span data-stu-id="0696f-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="0696f-117">Para ver información acerca de una región de red con Skype de Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="0696f-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="0696f-118">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0696f-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0696f-119">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="0696f-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0696f-120">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **región**.</span><span class="sxs-lookup"><span data-stu-id="0696f-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="0696f-121">En la página **región** , haga clic en la región que desea ver.</span><span class="sxs-lookup"><span data-stu-id="0696f-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="0696f-122">Sólo se puede ver una región a la vez.</span><span class="sxs-lookup"><span data-stu-id="0696f-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="0696f-123">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="0696f-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0696f-124">Visualización de información de región de red mediante el uso de cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0696f-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="0696f-125">Puede ver información de la región de red mediante el uso de Windows PowerShell y el cmdlet **Get-CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="0696f-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="0696f-126">Se puede ejecutar este cmdlet, ya sea desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0696f-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="0696f-127">Para ver la información de la región de red</span><span class="sxs-lookup"><span data-stu-id="0696f-127">To view network region information</span></span>

  - <span data-ttu-id="0696f-128">Para ver información acerca de todas las regiones de red, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="0696f-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="0696f-129">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="0696f-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="0696f-130">Para obtener más información, vea el tema de ayuda para el cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .</span><span class="sxs-lookup"><span data-stu-id="0696f-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="0696f-131">Creación o modificación de regiones de red</span><span class="sxs-lookup"><span data-stu-id="0696f-131">Create or modify network regions</span></span> 

<span data-ttu-id="0696f-132">Una región de red interconexiones distintas partes de una red a través de varias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="0696f-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="0696f-133">Cada región de red debe estar asociado a un sitio central.</span><span class="sxs-lookup"><span data-stu-id="0696f-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="0696f-134">El sitio central es el sitio del centro de datos en el que se ejecuta el servicio de directiva de ancho de banda de llamada admisión control (CAC).</span><span class="sxs-lookup"><span data-stu-id="0696f-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="0696f-135">Puede usar el Skype para el Panel de Control de servidor empresarial para configurar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="0696f-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="0696f-136">Regiones de red incluyen opciones de configuración que determinan si se permiten las rutas de acceso alternativas a través de Internet para las conexiones de audio y vídeos.</span><span class="sxs-lookup"><span data-stu-id="0696f-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="0696f-137">De Skype para el Panel de Control de servidor empresarial, puede crear, modificar o eliminar una región de red.</span><span class="sxs-lookup"><span data-stu-id="0696f-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="0696f-138">Use este tema para crear y modificar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="0696f-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="0696f-139">Para crear una región de red</span><span class="sxs-lookup"><span data-stu-id="0696f-139">To create a network region</span></span>

1.  <span data-ttu-id="0696f-140">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0696f-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0696f-141">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="0696f-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0696f-142">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **región**.</span><span class="sxs-lookup"><span data-stu-id="0696f-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="0696f-143">En la página **región** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0696f-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="0696f-144">En la página **Región nueva** , escriba un valor en el campo **nombre** .</span><span class="sxs-lookup"><span data-stu-id="0696f-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="0696f-145">Este valor debe ser único dentro de su Skype para la implementación de Business Server.</span><span class="sxs-lookup"><span data-stu-id="0696f-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="0696f-146">En la lista desplegable **sitio Central** , seleccione el sitio central para esta región de red.</span><span class="sxs-lookup"><span data-stu-id="0696f-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="0696f-147">La casilla de verificación **Habilitar la ruta de acceso alternativa audio** está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0696f-147">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="0696f-148">Este campo determina si se van a enrutar las llamadas de audio a través de una ruta de acceso alternativa si no existe ancho de banda adecuado en la ruta de acceso principal.</span><span class="sxs-lookup"><span data-stu-id="0696f-148">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="0696f-149">Desactive esta casilla de verificación sólo si necesita desactivar la descarga de Internet.</span><span class="sxs-lookup"><span data-stu-id="0696f-149">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="0696f-150">Si alguna de las llamadas va a ser llamadas por Internet, esta casilla de verificación debe ser activado, independientemente de la configuración de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="0696f-150">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="0696f-151">La casilla de verificación **Habilitar la ruta de acceso alternativa vídeo** está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0696f-151">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="0696f-152">Este campo determina si se van a enrutar las llamadas de vídeo a través de una ruta de acceso alternativa si no existe ancho de banda adecuado en la ruta de acceso principal.</span><span class="sxs-lookup"><span data-stu-id="0696f-152">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="0696f-153">Desactive esta casilla de verificación sólo si necesita desactivar la descarga de Internet.</span><span class="sxs-lookup"><span data-stu-id="0696f-153">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="0696f-154">Si alguna de las llamadas va a ser llamadas por Internet, esta casilla de verificación debe ser activado, independientemente de la configuración de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="0696f-154">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="0696f-155">(Opcional) Escriba un valor en el campo **Descripción** para proporcionar más información acerca de esta región que se pueda deducir de su nombre.</span><span class="sxs-lookup"><span data-stu-id="0696f-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="0696f-156">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0696f-156">Click **Commit**.</span></span>

<span data-ttu-id="0696f-157">La tabla de **sitios asociados** no se usa para la creación de una región de red.</span><span class="sxs-lookup"><span data-stu-id="0696f-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="0696f-158">Asociar un sitio con una región al crear o modificar el sitio.</span><span class="sxs-lookup"><span data-stu-id="0696f-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="0696f-159">Para obtener información detallada, vea [Managing control de admisión de llamadas para los sitios](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="0696f-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="0696f-160">Para modificar una región de red</span><span class="sxs-lookup"><span data-stu-id="0696f-160">To modify a network region</span></span>

1.  <span data-ttu-id="0696f-161">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0696f-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0696f-162">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="0696f-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0696f-163">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **región**.</span><span class="sxs-lookup"><span data-stu-id="0696f-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="0696f-164">En la página **región** , haga clic en la región que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="0696f-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="0696f-165">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="0696f-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="0696f-166">En la página **Editar región** , puede modificar la configuración para habilitar y deshabilitar audio y vídeo alternan de rutas de acceso y cambiar la descripción (para obtener información detallada, vea la sección "para crear una región de red" anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="0696f-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="0696f-167">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0696f-167">Click **Commit**.</span></span>

<span data-ttu-id="0696f-168">No se puede modificar los **sitios asociados** en esta página.</span><span class="sxs-lookup"><span data-stu-id="0696f-168">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="0696f-169">La lista de sitios asociados se proporciona para referencia para que conozcan de los sitios que se verán afectados cuando se modifica la configuración de la región.</span><span class="sxs-lookup"><span data-stu-id="0696f-169">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="0696f-170">Eliminación de regiones de red existentes</span><span class="sxs-lookup"><span data-stu-id="0696f-170">Delete existing network regions</span></span> 

<span data-ttu-id="0696f-171">Una región de red interconexiones distintas partes de una red a través de varias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="0696f-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="0696f-172">Cada región de red debe estar asociado a un sitio central.</span><span class="sxs-lookup"><span data-stu-id="0696f-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="0696f-173">El sitio central es el sitio del centro de datos en el que se ejecuta el servicio de directiva de ancho de banda de llamada admisión control (CAC).</span><span class="sxs-lookup"><span data-stu-id="0696f-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="0696f-174">Puede usar el Skype para el Panel de Control de servidor empresarial para configurar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="0696f-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="0696f-175">Regiones de red incluyen opciones de configuración que determinan si se permiten las rutas de acceso alternativas a través de Internet para las conexiones de audio y vídeos.</span><span class="sxs-lookup"><span data-stu-id="0696f-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="0696f-176">De Skype para el Panel de Control de servidor empresarial, puede crear, modificar o eliminar una región de red.</span><span class="sxs-lookup"><span data-stu-id="0696f-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="0696f-177">Use este tema para eliminar las regiones de red existente.</span><span class="sxs-lookup"><span data-stu-id="0696f-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="0696f-178">Para eliminar una región de red</span><span class="sxs-lookup"><span data-stu-id="0696f-178">To delete a network region</span></span>

1.  <span data-ttu-id="0696f-179">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0696f-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0696f-180">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="0696f-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="0696f-181">En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **región**.</span><span class="sxs-lookup"><span data-stu-id="0696f-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="0696f-182">En la página **región** , haga clic en la región que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="0696f-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="0696f-183">Puede eliminar más de una región a la vez.</span><span class="sxs-lookup"><span data-stu-id="0696f-183">You can delete more than one region at a time.</span></span> <span data-ttu-id="0696f-184">Para ello, presione la tecla CTRL y seleccione varias regiones mientras mantiene presionada la tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="0696f-184">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="0696f-185">O bien, para seleccionar todas las regiones, haga clic en **Seleccionar todo** en el menú **Edición** .</span><span class="sxs-lookup"><span data-stu-id="0696f-185">Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="0696f-186">En el menú **Edición** , haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="0696f-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="0696f-187">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0696f-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="0696f-188">No se puede quitar una región de red si está asociada con un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="0696f-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="0696f-189">Si intenta quitar una región asociada con un sitio, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="0696f-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="0696f-190">Para ver si una región está asociada con todos los sitios, seleccione la región y, a continuación, haga clic en **Mostrar detalles** en el menú **Edición** .</span><span class="sxs-lookup"><span data-stu-id="0696f-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="0696f-191">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0696f-191">See Also</span></span>

[<span data-ttu-id="0696f-192">Administración de rutas de región de red</span><span class="sxs-lookup"><span data-stu-id="0696f-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="0696f-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="0696f-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="0696f-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="0696f-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="0696f-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="0696f-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="0696f-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="0696f-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
