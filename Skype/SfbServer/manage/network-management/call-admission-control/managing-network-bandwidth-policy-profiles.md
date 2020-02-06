---
title: Administrar perfiles de directiva de ancho de banda de red
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
description: Use los procedimientos de este artículo para ver, crear, modificar o eliminar perfiles de directiva de ancho de banda de red.
ms.openlocfilehash: a9203c0935673e0dfd12d052876f06583c7c92c8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817509"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="03e00-103">Administrar perfiles de directivas de ancho de banda de red en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="03e00-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="03e00-104">Use los procedimientos de este artículo para ver, crear, modificar o eliminar perfiles de directiva de ancho de banda de red.</span><span class="sxs-lookup"><span data-stu-id="03e00-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="03e00-105">Ver la información de Perfil de la Directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="03e00-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="03e00-106">Como parte de control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir limitaciones de ancho de banda para determinadas modalidades.</span><span class="sxs-lookup"><span data-stu-id="03e00-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="03e00-107">En Skype empresarial Server, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="03e00-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="03e00-108">Puede establecer limitaciones generales de ancho de banda y limitaciones de sesión.</span><span class="sxs-lookup"><span data-stu-id="03e00-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="03e00-109">Puede usar el panel de control de Skype empresarial Server para crear, modificar o eliminar un perfil de contenedor para estas directivas.</span><span class="sxs-lookup"><span data-stu-id="03e00-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="03e00-110">Cada perfil de directiva de ancho de banda se puede asociar a uno o varios sitios de red.</span><span class="sxs-lookup"><span data-stu-id="03e00-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="03e00-111">Use los procedimientos siguientes para ver un perfil de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="03e00-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="03e00-112">Para ver un perfil de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="03e00-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="03e00-113">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="03e00-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="03e00-114">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="03e00-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="03e00-115">En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en Directiva de **ancho de banda**.</span><span class="sxs-lookup"><span data-stu-id="03e00-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="03e00-116">En la página **Directiva de ancho de banda** , haga clic en el perfil de directiva de ancho de banda que desea ver.</span><span class="sxs-lookup"><span data-stu-id="03e00-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="03e00-117">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="03e00-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="03e00-118">Ver la información de Perfil de la Directiva de ancho de banda mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="03e00-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="03e00-119">Los perfiles de ancho de banda de red se pueden ver con Windows PowerShell y el cmdlet Get-CsNetworkBandwidthPolicyProfile.</span><span class="sxs-lookup"><span data-stu-id="03e00-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="03e00-120">Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03e00-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="03e00-121">Para ver la información de Perfil de la Directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="03e00-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="03e00-122">Para ver información sobre todos los perfiles de la Directiva de ancho de banda de la red, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="03e00-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="03e00-123">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="03e00-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="03e00-124">Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .</span><span class="sxs-lookup"><span data-stu-id="03e00-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="03e00-125">Crear o modificar perfiles de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="03e00-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="03e00-126">Como parte de control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir limitaciones de ancho de banda para determinadas modalidades.</span><span class="sxs-lookup"><span data-stu-id="03e00-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="03e00-127">En Skype empresarial Server, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="03e00-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="03e00-128">Puede establecer limitaciones generales de ancho de banda y limitaciones de sesión.</span><span class="sxs-lookup"><span data-stu-id="03e00-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="03e00-129">Puede usar el panel de control de Skype empresarial Server para crear, modificar o eliminar un perfil de contenedor para estas directivas.</span><span class="sxs-lookup"><span data-stu-id="03e00-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="03e00-130">Cada perfil de directiva de ancho de banda se puede asociar a uno o varios sitios de red.</span><span class="sxs-lookup"><span data-stu-id="03e00-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="03e00-131">Use los procedimientos siguientes para crear o modificar un perfil de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="03e00-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="03e00-132">Para crear un nuevo perfil de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="03e00-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="03e00-133">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="03e00-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="03e00-134">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="03e00-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="03e00-135">En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en Directiva de **ancho de banda**.</span><span class="sxs-lookup"><span data-stu-id="03e00-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="03e00-136">En la página **Directiva de ancho de banda** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="03e00-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="03e00-137">En **nuevo perfil de directiva de ancho de banda**, escriba un nombre en el campo **nombre** .</span><span class="sxs-lookup"><span data-stu-id="03e00-137">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="03e00-138">Este nombre debe ser único entre todos los perfiles de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="03e00-138">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="03e00-139">En el campo **límite de audio** , escriba un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="03e00-139">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="03e00-140">Este valor es la cantidad máxima de ancho de banda que se asignará a todas las conexiones de audio, expresadas en kbps.</span><span class="sxs-lookup"><span data-stu-id="03e00-140">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="03e00-141">Escriba un valor numérico en el campo límite de la **sesión de audio** .</span><span class="sxs-lookup"><span data-stu-id="03e00-141">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="03e00-142">Este valor es la cantidad máxima de ancho de banda que se asignará a una conexión de audio individual, expresada en kbps.</span><span class="sxs-lookup"><span data-stu-id="03e00-142">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="03e00-143">Este valor debe ser 40 o superior.</span><span class="sxs-lookup"><span data-stu-id="03e00-143">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="03e00-144">Escriba un valor numérico en el campo **límite de video** .</span><span class="sxs-lookup"><span data-stu-id="03e00-144">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="03e00-145">Este valor es la cantidad máxima de ancho de banda que se asignará a todas las conexiones de vídeo, expresadas en kbps.</span><span class="sxs-lookup"><span data-stu-id="03e00-145">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="03e00-146">Escriba un valor numérico en el campo límite de la **sesión de vídeo** .</span><span class="sxs-lookup"><span data-stu-id="03e00-146">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="03e00-147">Este valor es la cantidad máxima de ancho de banda que se asignará a una conexión de video individual, expresada en kbps.</span><span class="sxs-lookup"><span data-stu-id="03e00-147">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="03e00-148">Este valor debe ser 100 o superior.</span><span class="sxs-lookup"><span data-stu-id="03e00-148">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="03e00-149">Faculta Escriba un valor en el campo **Descripción** para proporcionar más información sobre este perfil de directiva de ancho de banda que no se puede expresar solo con el nombre.</span><span class="sxs-lookup"><span data-stu-id="03e00-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="03e00-150">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="03e00-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="03e00-151">La creación de un nuevo perfil de directiva de ancho de banda no aplica automáticamente restricciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="03e00-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="03e00-152">Primero debe asociar el perfil de directiva con un sitio.</span><span class="sxs-lookup"><span data-stu-id="03e00-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="03e00-153">Para modificar un perfil de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="03e00-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="03e00-154">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="03e00-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="03e00-155">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="03e00-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="03e00-156">En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en Directiva de **ancho de banda**.</span><span class="sxs-lookup"><span data-stu-id="03e00-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="03e00-157">En la página **Directiva de ancho de banda** , haga clic en el perfil de directiva de ancho de banda que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="03e00-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="03e00-158">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="03e00-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="03e00-159">En la página **Editar perfil** de la Directiva de ancho de banda, modifique los campos según sea necesario (para obtener información detallada, consulte [para crear un nuevo perfil de directiva de ancho de banda](#to-create-a-new-bandwidth-policy-profile)).</span><span class="sxs-lookup"><span data-stu-id="03e00-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="03e00-160">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="03e00-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="03e00-161">Al modificar el perfil de directiva de ancho de banda, se actualizarán inmediatamente las limitaciones de ancho de banda de todos los sitios de red asociados a este perfil de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="03e00-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="03e00-162">Eliminar perfiles de directiva de ancho de banda de red</span><span class="sxs-lookup"><span data-stu-id="03e00-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="03e00-163">Como parte de control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir limitaciones de ancho de banda para determinadas modalidades.</span><span class="sxs-lookup"><span data-stu-id="03e00-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="03e00-164">En Skype empresarial Server, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="03e00-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="03e00-165">Puede establecer limitaciones generales de ancho de banda y limitaciones de sesión.</span><span class="sxs-lookup"><span data-stu-id="03e00-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="03e00-166">Puede usar el panel de control de Skype empresarial Server para crear, modificar o eliminar un perfil de contenedor para estas directivas.</span><span class="sxs-lookup"><span data-stu-id="03e00-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="03e00-167">Use los procedimientos siguientes para eliminar los perfiles de la Directiva de ancho de banda de red.</span><span class="sxs-lookup"><span data-stu-id="03e00-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="03e00-168">Para eliminar un perfil de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="03e00-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="03e00-169">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="03e00-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="03e00-170">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="03e00-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="03e00-171">En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en Directiva de **ancho de banda**.</span><span class="sxs-lookup"><span data-stu-id="03e00-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="03e00-172">En la página **Directiva de ancho de banda** , haga clic en el perfil de directiva de ancho de banda que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="03e00-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="03e00-173">Puede eliminar más de un perfil a la vez.</span><span class="sxs-lookup"><span data-stu-id="03e00-173">You can delete more than one profile at a time.</span></span> <span data-ttu-id="03e00-174">Para ello, presione CTRL y seleccione varios perfiles manteniendo presionada la tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="03e00-174">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="03e00-175">O bien, para seleccionar todos los perfiles, haga clic en **seleccionar todo** en el menú **edición** .</span><span class="sxs-lookup"><span data-stu-id="03e00-175">Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="03e00-176">En el menú **Editar** , haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="03e00-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="03e00-177">No se puede eliminar un perfil de directiva de ancho de banda asociado a un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="03e00-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="03e00-178">Primero debe quitar la asociación con el sitio de red para poder eliminar el perfil.</span><span class="sxs-lookup"><span data-stu-id="03e00-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="03e00-179">Vea también</span><span class="sxs-lookup"><span data-stu-id="03e00-179">See Also</span></span>

[<span data-ttu-id="03e00-180">Administrar el control de admisión de llamadas para sitios</span><span class="sxs-lookup"><span data-stu-id="03e00-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="03e00-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="03e00-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="03e00-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="03e00-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="03e00-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="03e00-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="03e00-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="03e00-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

