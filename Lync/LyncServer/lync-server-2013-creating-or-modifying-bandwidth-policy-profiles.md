---
title: 'Lync Server 2013: creación o modificación de perfiles de directiva de ancho de banda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee744459f284355b0bd4aa13f7ac6a1cfba908e2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516777"
---
# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="8b06b-102">Creación o modificación de perfiles de directiva de ancho de banda en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b06b-102">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b06b-103">_**Última modificación del tema:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="8b06b-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="8b06b-104">Como parte del control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir las limitaciones de ancho de banda para ciertas modalidades.</span><span class="sxs-lookup"><span data-stu-id="8b06b-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="8b06b-105">En Microsoft Lync Server 2013, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="8b06b-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="8b06b-106">Puede establecer limitaciones generales de ancho de banda y sesión.</span><span class="sxs-lookup"><span data-stu-id="8b06b-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="8b06b-107">Puede usar el panel de control de Lync Server para crear, modificar o eliminar un perfil de contenedor para estas directivas.</span><span class="sxs-lookup"><span data-stu-id="8b06b-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="8b06b-108">Cada perfil de directiva de ancho de banda se puede asociar a uno o más sitios de red.</span><span class="sxs-lookup"><span data-stu-id="8b06b-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="8b06b-109">Use los siguientes procedimientos para crear o modificar un perfil de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="8b06b-109">Use the following procedures to create or modify a bandwidth policy profile.</span></span> <span data-ttu-id="8b06b-110">Para eliminar un perfil de directiva de ancho de banda, consulte [eliminar perfiles de directiva de ancho de banda de red en Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="8b06b-110">To delete a bandwidth policy profile, see [Deleting network bandwidth policy profiles in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span></span>

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="8b06b-111">Para crear un nuevo perfil de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="8b06b-111">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="8b06b-112">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8b06b-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8b06b-113">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8b06b-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8b06b-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8b06b-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8b06b-115">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ancho de banda**.</span><span class="sxs-lookup"><span data-stu-id="8b06b-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="8b06b-116">En la página **Directiva de ancho de banda**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="8b06b-116">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="8b06b-p103">En **Nuevo perfil de directiva de ancho de banda**, escriba un nombre en el campo **Nombre**. Este nombre debe ser diferente al resto de perfiles de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="8b06b-p103">In **New Bandwidth Policy Profile**, type a name in the **Name** field. This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="8b06b-p104">En el campo **Límite de audio**, escriba un valor numérico. Este valor es la cantidad máxima de ancho de banda que se puede asignar a todas las conexiones de audio, expresado en kbps.</span><span class="sxs-lookup"><span data-stu-id="8b06b-p104">In the **Audio limit** field, type a numeric value. This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="8b06b-p105">Especifique un valor numérico en el campo **Límite de sesión de audio**. Este valor es la cantidad máxima de ancho de banda que se puede asignar a una conexión de audio individual, expresado en kbps. El valor debe ser mayor o igual que 40.</span><span class="sxs-lookup"><span data-stu-id="8b06b-p105">Enter a numeric value in the **Audio session limit** field. This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps. This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="8b06b-p106">Especifique un valor numérico en el campo **Límite de vídeo**. Este valor es la cantidad máxima de ancho de banda que se puede asignar a todas las conexiones de vídeo, expresado en kbps.</span><span class="sxs-lookup"><span data-stu-id="8b06b-p106">Enter a numeric value in the **Video limit** field. This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="8b06b-p107">Especifique un valor numérico en el campo **Límite de sesión de vídeo**. Este valor es la cantidad máxima de ancho de banda que se puede asignar a una conexión de vídeo individual, expresado en kbps. El valor debe ser mayor o igual que 100.</span><span class="sxs-lookup"><span data-stu-id="8b06b-p107">Enter a numeric value in the **Video session limit** field. This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps. This value must be 100 or higher.</span></span>

10. <span data-ttu-id="8b06b-129">(Opcional) Escriba un valor en el campo **Descripción** para proporcionar información sobre este perfil de directiva de ancho de banda más allá de lo que se pueda deducir de su nombre.</span><span class="sxs-lookup"><span data-stu-id="8b06b-129">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="8b06b-130">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8b06b-130">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8b06b-131">Crear un nuevo perfil de directiva de ancho de banda no supone la aplicación automática de las restricciones de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="8b06b-131">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="8b06b-132">Primero debe asociar el perfil de directiva a un sitio.</span><span class="sxs-lookup"><span data-stu-id="8b06b-132">You must first associate the policy profile with a site.</span></span> <span data-ttu-id="8b06b-133">Para más información sobre cómo asociar un perfil de directiva a un sitio, vea <A href="lync-server-2013-creating-or-modifying-network-sites.md">crear o modificar sitios de red en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8b06b-133">For details about how to associate a policy profile with a site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="8b06b-134">Para modificar un perfil de directiva de ancho de banda</span><span class="sxs-lookup"><span data-stu-id="8b06b-134">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="8b06b-135">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="8b06b-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8b06b-136">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8b06b-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8b06b-137">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8b06b-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8b06b-138">En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ancho de banda**.</span><span class="sxs-lookup"><span data-stu-id="8b06b-138">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="8b06b-139">En la página **Directiva de ancho de banda**, haga clic en el perfil de directiva de ancho de banda que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="8b06b-139">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="8b06b-140">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="8b06b-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="8b06b-141">En la página **Editar perfil de directiva de ancho de banda**, modifique los campos según sea necesario (para obtener más información, consulte la sección "Para crear un nuevo perfil de directiva de ancho de banda" expuesta anteriormente en este tema).</span><span class="sxs-lookup"><span data-stu-id="8b06b-141">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see the "To create a bandwidth policy profile" section earlier in this topic).</span></span>

7.  <span data-ttu-id="8b06b-142">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8b06b-142">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8b06b-143">Cuando modifique el perfil de directiva de ancho de banda, se actualizarán inmediatamente las limitaciones de ancho de banda de todos los sitios de red asociados a este perfil de directiva de ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="8b06b-143">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8b06b-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8b06b-144">See Also</span></span>


[<span data-ttu-id="8b06b-145">Eliminación de perfiles de directiva de ancho de banda de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b06b-145">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="8b06b-146">Configurar el control de admisión de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b06b-146">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="8b06b-147">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="8b06b-147">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="8b06b-148">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="8b06b-148">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="8b06b-149">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="8b06b-149">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

