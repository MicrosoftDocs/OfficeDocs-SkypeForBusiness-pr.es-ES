---
title: Administración de perfiles de directiva de ancho de banda de red
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
description: Use los procedimientos de este artículo para ver, crear, modificar o eliminar perfiles de directiva de ancho de banda de red.
ms.openlocfilehash: 47a4d268c24cd8d57c8aeda4deacc6b03e795c2c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096676"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="4b89b-103">Administrar perfiles de directivas de ancho de banda de red en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4b89b-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="4b89b-104">Use los procedimientos de este artículo para ver, crear, modificar o eliminar perfiles de directiva de ancho de banda de red.</span><span class="sxs-lookup"><span data-stu-id="4b89b-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="4b89b-105">Ver información de perfil de directiva de ancho de banda de red</span><span class="sxs-lookup"><span data-stu-id="4b89b-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="4b89b-106">Como parte del control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir las limitaciones de ancho de banda para ciertas modalidades.</span><span class="sxs-lookup"><span data-stu-id="4b89b-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="4b89b-107">En Skype Empresarial Server, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="4b89b-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="4b89b-108">Puede establecer limitaciones generales de ancho de banda y sesión.</span><span class="sxs-lookup"><span data-stu-id="4b89b-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="4b89b-109">Puede usar el Panel de control de Skype Empresarial Server para crear, modificar o eliminar un perfil de contenedor para estas directivas.</span><span class="sxs-lookup"><span data-stu-id="4b89b-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="4b89b-110">Cada perfil de directiva de ancho de banda se puede asociar a uno o más sitios de red.</span><span class="sxs-lookup"><span data-stu-id="4b89b-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="4b89b-111">Utilice los siguientes procedimientos para ver un perfil de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="4b89b-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="4b89b-112">Para ver un perfil de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="4b89b-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="4b89b-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4b89b-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4b89b-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4b89b-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4b89b-115">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ancho de banda**.</span><span class="sxs-lookup"><span data-stu-id="4b89b-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="4b89b-116">En la página **Directiva de ancho de** banda, haga clic en el perfil de directiva de ancho de banda que desea ver.</span><span class="sxs-lookup"><span data-stu-id="4b89b-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="4b89b-117">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="4b89b-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4b89b-118">Visualización de información de perfil de directiva de ancho de banda de red mediante Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="4b89b-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="4b89b-119">Los perfiles de ancho de banda de red se pueden ver mediante Windows PowerShell y el cmdlet Get-CsNetworkBandwidthPolicyProfile de red.</span><span class="sxs-lookup"><span data-stu-id="4b89b-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="4b89b-120">Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b89b-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="4b89b-121">Para ver la información del perfil de directiva de ancho de banda de red</span><span class="sxs-lookup"><span data-stu-id="4b89b-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="4b89b-122">Para ver información sobre todos los perfiles de directiva de ancho de banda de red, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="4b89b-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="4b89b-123">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b89b-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="4b89b-124">Si desea más información, consulte el tema de ayuda relativo al cmdlet [Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="4b89b-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="4b89b-125">Crear o modificar perfiles de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="4b89b-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="4b89b-126">Como parte del control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir las limitaciones de ancho de banda para ciertas modalidades.</span><span class="sxs-lookup"><span data-stu-id="4b89b-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="4b89b-127">En Skype Empresarial Server, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="4b89b-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="4b89b-128">Puede establecer limitaciones generales de ancho de banda y sesión.</span><span class="sxs-lookup"><span data-stu-id="4b89b-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="4b89b-129">Puede usar el Panel de control de Skype Empresarial Server para crear, modificar o eliminar un perfil de contenedor para estas directivas.</span><span class="sxs-lookup"><span data-stu-id="4b89b-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="4b89b-130">Cada perfil de directiva de ancho de banda se puede asociar a uno o más sitios de red.</span><span class="sxs-lookup"><span data-stu-id="4b89b-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="4b89b-131">Use los siguientes procedimientos para crear o modificar un perfil de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="4b89b-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="4b89b-132">Para crear un nuevo perfil de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="4b89b-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="4b89b-133">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4b89b-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4b89b-134">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4b89b-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4b89b-135">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Directiva de ancho **de banda.**</span><span class="sxs-lookup"><span data-stu-id="4b89b-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="4b89b-136">En la página **Directiva de ancho de banda**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4b89b-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="4b89b-p104">En **Nuevo perfil de directiva de ancho de banda**, escriba un nombre en el campo **Nombre**. Este nombre debe ser diferente al resto de perfiles de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="4b89b-p104">In **New Bandwidth Policy Profile**, type a name in the **Name** field. This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="4b89b-p105">En el campo **Límite de audio**, escriba un valor numérico. Este valor es la cantidad máxima de ancho de banda que se puede asignar a todas las conexiones de audio, expresado en kbps.</span><span class="sxs-lookup"><span data-stu-id="4b89b-p105">In the **Audio limit** field, type a numeric value. This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="4b89b-p106">Especifique un valor numérico en el campo **Límite de sesión de audio**. Este valor es la cantidad máxima de ancho de banda que se puede asignar a una conexión de audio individual, expresado en kbps. El valor debe ser mayor o igual que 40.</span><span class="sxs-lookup"><span data-stu-id="4b89b-p106">Enter a numeric value in the **Audio session limit** field. This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps. This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="4b89b-p107">Especifique un valor numérico en el campo **Límite de vídeo**. Este valor es la cantidad máxima de ancho de banda que se puede asignar a todas las conexiones de vídeo, expresado en kbps.</span><span class="sxs-lookup"><span data-stu-id="4b89b-p107">Enter a numeric value in the **Video limit** field. This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="4b89b-p108">Especifique un valor numérico en el campo **Límite de sesión de vídeo**. Este valor es la cantidad máxima de ancho de banda que se puede asignar a una conexión de vídeo individual, expresado en kbps. El valor debe ser mayor o igual que 100.</span><span class="sxs-lookup"><span data-stu-id="4b89b-p108">Enter a numeric value in the **Video session limit** field. This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps. This value must be 100 or higher.</span></span>

10. <span data-ttu-id="4b89b-149">(Opcional) Escriba un valor en el campo **Descripción** para proporcionar información sobre este perfil de directiva de ancho de banda más allá de lo que se pueda deducir de su nombre.</span><span class="sxs-lookup"><span data-stu-id="4b89b-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="4b89b-150">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4b89b-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="4b89b-151">Crear un nuevo perfil de directiva de ancho de banda no supone la aplicación automática de las restricciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="4b89b-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="4b89b-152">Primero debe asociar el perfil de directiva a un sitio.</span><span class="sxs-lookup"><span data-stu-id="4b89b-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="4b89b-153">Para modificar un perfil de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="4b89b-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="4b89b-154">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4b89b-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4b89b-155">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4b89b-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4b89b-156">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Directiva de ancho **de banda.**</span><span class="sxs-lookup"><span data-stu-id="4b89b-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="4b89b-157">En la página **Directiva de ancho de banda**, haga clic en el perfil de directiva de ancho de banda que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="4b89b-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="4b89b-158">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="4b89b-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="4b89b-159">En la **página Editar perfil de** directiva de ancho de banda, modifique los campos según sea necesario (para obtener más información, vea Para crear un nuevo perfil de directiva de ancho de [banda).](#to-create-a-new-bandwidth-policy-profile)</span><span class="sxs-lookup"><span data-stu-id="4b89b-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="4b89b-160">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4b89b-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="4b89b-161">Cuando modifique el perfil de directiva de ancho de banda, se actualizarán inmediatamente las limitaciones de ancho de banda de todos los sitios de red asociados a este perfil de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="4b89b-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="4b89b-162">Eliminar perfiles de directiva de ancho de banda de red</span><span class="sxs-lookup"><span data-stu-id="4b89b-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="4b89b-163">Como parte del control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir las limitaciones de ancho de banda para ciertas modalidades.</span><span class="sxs-lookup"><span data-stu-id="4b89b-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="4b89b-164">En Skype Empresarial Server, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="4b89b-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="4b89b-165">Puede establecer limitaciones generales de ancho de banda y sesión.</span><span class="sxs-lookup"><span data-stu-id="4b89b-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="4b89b-166">Puede usar el Panel de control de Skype Empresarial Server para crear, modificar o eliminar un perfil de contenedor para estas directivas.</span><span class="sxs-lookup"><span data-stu-id="4b89b-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="4b89b-167">Use los siguientes procedimientos para eliminar perfiles de directiva de ancho de banda de red.</span><span class="sxs-lookup"><span data-stu-id="4b89b-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="4b89b-168">Para eliminar un perfil de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="4b89b-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="4b89b-169">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="4b89b-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4b89b-170">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4b89b-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4b89b-171">En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic en Directiva de ancho **de banda.**</span><span class="sxs-lookup"><span data-stu-id="4b89b-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="4b89b-172">En la página **Directiva de ancho de banda**, haga clic en el perfil de directiva de ancho de banda que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="4b89b-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="4b89b-p111">Puede eliminar más de un perfil en la misma operación. Para hacerlo, pulse CTRL y seleccione varios perfiles manteniendo pulsada la tecla CTRL. O bien, para seleccionar todos los perfiles, haga clic en **Seleccionar todo** en el menú **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4b89b-p111">You can delete more than one profile at a time. To do this, press CTRL and select multiple profiles while holding down the CTRL key. Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="4b89b-176">En el menú **Editar**, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="4b89b-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="4b89b-177">No puede eliminar un perfil de directiva de ancho de banda que esté asociado a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="4b89b-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="4b89b-178">Primero debe eliminar la asociación establecida con el sitio de red para poder eliminar el perfil.</span><span class="sxs-lookup"><span data-stu-id="4b89b-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="4b89b-179">Consulta también</span><span class="sxs-lookup"><span data-stu-id="4b89b-179">See Also</span></span>

[<span data-ttu-id="4b89b-180">Administración del control de admisión de llamadas para sitios</span><span class="sxs-lookup"><span data-stu-id="4b89b-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="4b89b-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="4b89b-181">New-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="4b89b-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="4b89b-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="4b89b-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="4b89b-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="4b89b-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="4b89b-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
