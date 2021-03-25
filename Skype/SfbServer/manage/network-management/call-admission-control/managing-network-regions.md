---
title: Administración de regiones de red
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
description: La región de red* son los concentradores de red o redes troncales usados en la configuración del control de admisión de llamadas, E9-1-1 y desvío de medios.
ms.openlocfilehash: 2020eea2cf8bf85c915ebf88de6f86cb3a0ee9ca
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122454"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="ab9ba-103">Administrar regiones de red en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ab9ba-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="ab9ba-104">Las *regiones de red* son los concentradores de red o redes troncales que se usan en la configuración del control de admisión de llamadas, de E9-1-1 y del desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="ab9ba-105">Siga los siguientes procedimientos para ver, crear o modificar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="ab9ba-106">Por ejemplo, si ya ha creado regiones de red para una característica de voz, no es necesario que cree nuevas regiones de red; otras características avanzadas de Enterprise Voice usarán las mismas regiones de red.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="ab9ba-107">Sin embargo, es posible que necesite modificar una definición de región de red existente para aplicar una configuración específica de una característica.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="ab9ba-108">Por ejemplo, si ha creado regiones de red para E9-1-1 (que no requieren un sitio central asociado) y, a continuación, implementa el control de admisión de llamadas, debe modificar las definiciones de región de red para especificar un sitio central.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="ab9ba-109">Use los procedimientos de este artículo para ver información de región de red o crear, modificar o eliminar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="ab9ba-110">Ver información de región de red</span><span class="sxs-lookup"><span data-stu-id="ab9ba-110">View network region information</span></span> 


<span data-ttu-id="ab9ba-111">Una región de red interconecta varias partes de una red a través de varias zonas geográficas.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="ab9ba-112">Cada región de red debe asociarse con un sitio central.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="ab9ba-113">El sitio central es el sitio del centro de datos donde se está ejecutando el servicio de directiva de ancho de banda de CAC (servicio de control de admisión de llamadas).</span><span class="sxs-lookup"><span data-stu-id="ab9ba-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="ab9ba-114">Puede usar el Panel de control de Skype Empresarial Server para ver las regiones de red.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="ab9ba-115">Las regiones de red incluyen valores de configuración que determinan si se permiten las rutas alterativas a través de Internet para las conexiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="ab9ba-116">Use este tema para ver las regiones de red existentes.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="ab9ba-117">Para ver información sobre una región de red con el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ab9ba-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="ab9ba-118">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ab9ba-119">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ab9ba-120">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Región**.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="ab9ba-121">En la **página Región,** haga clic en la región que desea ver.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="ab9ba-122">Solo puede ver una región a la vez.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="ab9ba-123">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ab9ba-124">Visualización de información de región de red mediante el uso Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="ab9ba-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="ab9ba-125">Puede ver la información de región de red mediante Windows PowerShell y el cmdlet **Get-CsNetworkRegion.**</span><span class="sxs-lookup"><span data-stu-id="ab9ba-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="ab9ba-126">Puede ejecutar este cmdlet desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="ab9ba-127">Para ver información de región de red</span><span class="sxs-lookup"><span data-stu-id="ab9ba-127">To view network region information</span></span>

  - <span data-ttu-id="ab9ba-128">Para ver información sobre todas las regiones de red, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="ab9ba-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="ab9ba-129">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="ab9ba-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="ab9ba-130">Para obtener más información, vea el tema de ayuda del cmdlet [Get-CsNetworkRegion.](/powershell/module/skype/Get-CsNetworkRegionLink)</span><span class="sxs-lookup"><span data-stu-id="ab9ba-130">For more information, see the help topic for the [Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="ab9ba-131">Crear o modificar regiones de red</span><span class="sxs-lookup"><span data-stu-id="ab9ba-131">Create or modify network regions</span></span> 

<span data-ttu-id="ab9ba-132">Una región de red interconecta varias partes de una red a través de varias zonas geográficas.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="ab9ba-133">Cada región de red debe asociarse con un sitio central.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="ab9ba-134">El sitio central es el sitio del centro de datos donde se está ejecutando el servicio de directiva de ancho de banda de CAC (servicio de control de admisión de llamadas).</span><span class="sxs-lookup"><span data-stu-id="ab9ba-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="ab9ba-135">Puede usar el Panel de control de Skype Empresarial Server para configurar las regiones de red.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="ab9ba-136">Las regiones de red incluyen valores de configuración que determinan si se permiten las rutas alterativas a través de Internet para las conexiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="ab9ba-137">Desde el Panel de control de Skype Empresarial Server, puede crear, modificar o eliminar una región de red.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="ab9ba-138">Siga este tema para crear y modificar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="ab9ba-139">Para crear una región de red</span><span class="sxs-lookup"><span data-stu-id="ab9ba-139">To create a network region</span></span>

1.  <span data-ttu-id="ab9ba-140">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ab9ba-141">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ab9ba-142">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Región**.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="ab9ba-143">En la página **Región**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="ab9ba-144">En la página **Región nueva**, escriba un valor en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="ab9ba-145">Este valor debe ser único dentro de la implementación de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="ab9ba-146">En la lista desplegable **Sitio central**, seleccione el sitio central para esta región de red.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="ab9ba-p106">La casilla  **Habilitar ruta alternativa de audio** está activada de forma predeterminada. Este campo determina si las llamadas de audio se enrutarán a través de una ruta de acceso alternativa cuando no exista un ancho de banda adecuado en la ruta de acceso principal. Desactívela solamente si necesita cancelar la descarga de Internet. Si alguna de las llamadas que realice se hará por Internet, esta casilla debe estar marcada, independientemente del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-p106">The **Enable audio alternate path** check box is checked by default. This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="ab9ba-p107">La casilla  **Habilitar ruta alternativa de vídeo** está activada de forma predeterminada. Este campo determina si las llamadas de vídeo se enrutarán a través de una ruta de acceso alternativa cuando no exista un ancho de banda adecuado en la ruta de acceso principal. Desactívela solamente si necesita cancelar la descarga de Internet. Si alguna de las llamadas que realice se hará por Internet, esta casilla debe estar marcada, independientemente del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-p107">The **Enable video alternate path** check box is checked by default. This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="ab9ba-155">(Opcional) Escriba un valor en el campo **Descripción** para proporcionar información sobre esta región aparte de lo que se pueda deducir de su nombre.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="ab9ba-156">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-156">Click **Commit**.</span></span>

<span data-ttu-id="ab9ba-157">La tabla **Sitios asociados** no se usa para crear una región de red.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="ab9ba-158">Un sitio se asocia a una región cuando se crea o modifica el sitio.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="ab9ba-159">Para obtener más información, vea [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="ab9ba-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="ab9ba-160">Para modificar una región de red</span><span class="sxs-lookup"><span data-stu-id="ab9ba-160">To modify a network region</span></span>

1.  <span data-ttu-id="ab9ba-161">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ab9ba-162">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ab9ba-163">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Región**.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="ab9ba-164">En la página **Región**, haga clic en el vínculo regional que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="ab9ba-165">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="ab9ba-166">En la página **Editar región**, puede modificar la configuración para habilitar y deshabilitar las rutas alternativas de audio y vídeo y modificar la descripción (para obtener información detallada, consulte la sección "Para crear una sección de red" de más arriba en este tema).</span><span class="sxs-lookup"><span data-stu-id="ab9ba-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="ab9ba-167">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-167">Click **Commit**.</span></span>

<span data-ttu-id="ab9ba-p109">En esta página, no se pueden modificar los **Sitios asociados**. La lista de sitios asociados se proporciona a modo de referencia, de forma que pueda saber los sitios que se verán afectados cuando modifique la configuración de la región.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-p109">You cannot modify the **Associated sites** on this page. The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="ab9ba-170">Eliminar regiones de red existentes</span><span class="sxs-lookup"><span data-stu-id="ab9ba-170">Delete existing network regions</span></span> 

<span data-ttu-id="ab9ba-171">Una región de red interconecta varias partes de una red a través de varias zonas geográficas.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="ab9ba-172">Cada región de red debe asociarse con un sitio central.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="ab9ba-173">El sitio central es el sitio del centro de datos donde se está ejecutando el servicio de directiva de ancho de banda de CAC (servicio de control de admisión de llamadas).</span><span class="sxs-lookup"><span data-stu-id="ab9ba-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="ab9ba-174">Puede usar el Panel de control de Skype Empresarial Server para configurar las regiones de red.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="ab9ba-175">Las regiones de red incluyen valores de configuración que determinan si se permiten las rutas alterativas a través de Internet para las conexiones de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="ab9ba-176">Desde el Panel de control de Skype Empresarial Server, puede crear, modificar o eliminar una región de red.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="ab9ba-177">Use este tema para eliminar las regiones de red existentes.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="ab9ba-178">Para eliminar una región de red:</span><span class="sxs-lookup"><span data-stu-id="ab9ba-178">To delete a network region</span></span>

1.  <span data-ttu-id="ab9ba-179">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ab9ba-180">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ab9ba-181">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Región**.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="ab9ba-182">En la página **Región**, haga clic en la región que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="ab9ba-p111">Si lo desea, puede eliminar varias regiones en la misma operación. Para ello, presione Ctrl y seleccione varias regiones mientras mantiene presionada esta tecla. O bien, para seleccionar todas las regiones, haga clic en **Seleccionar todo** en el menú **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-p111">You can delete more than one region at a time. To do this, press CTRL and select multiple regions while holding down the CTRL key. Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="ab9ba-186">En el menú **Editar**, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="ab9ba-187">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="ab9ba-188">No se puede quitar una región si está asociada a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="ab9ba-189">Si intenta quitar una región asociada a un sitio, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="ab9ba-190">Para ver si una región está asociada a algún sitio, seleccione la región y haga clic en **Mostrar detalles** en el menú **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ab9ba-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="ab9ba-191">Consulta también</span><span class="sxs-lookup"><span data-stu-id="ab9ba-191">See Also</span></span>

[<span data-ttu-id="ab9ba-192">Administración de rutas de región de red</span><span class="sxs-lookup"><span data-stu-id="ab9ba-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="ab9ba-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ab9ba-193">New-CsNetworkRegion</span></span>](/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="ab9ba-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ab9ba-194">Set-CsNetworkRegion</span></span>](/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="ab9ba-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ab9ba-195">Remove-CsNetworkRegion</span></span>](/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="ab9ba-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ab9ba-196">Get-CsNetworkRegion</span></span>](/powershell/module/skype/Get-CsNetworkRegionLink)