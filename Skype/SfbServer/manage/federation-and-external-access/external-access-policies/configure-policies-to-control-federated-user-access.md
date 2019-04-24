---
title: Configurar directivas para controlar el acceso de usuarios federados
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Al configurar directivas para admitir comunicaciones con los socios federados, las directivas se aplican a los usuarios de dominios federados. '
ms.openlocfilehash: df5702fb217d238a26a8a9975e7e4a0792787399
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199901"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="127a7-103">Configurar directivas para controlar el acceso de usuarios federados en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="127a7-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="127a7-104">Al configurar directivas para admitir comunicaciones con los socios federados, las directivas se aplican a los usuarios de dominios federados.</span><span class="sxs-lookup"><span data-stu-id="127a7-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="127a7-105">Puede configurar uno o más directivas de acceso de usuarios externos para controlar si los usuarios de dominios federados puedan colaborar con su Skype para los usuarios de Business Server.</span><span class="sxs-lookup"><span data-stu-id="127a7-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="127a7-106">Para controlar el acceso de usuarios federados, puede configurar las directivas a nivel global, sitio y el nivel de usuario.</span><span class="sxs-lookup"><span data-stu-id="127a7-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="127a7-107">Skype para la configuración de directiva de Business Server que se aplican en un nivel de directiva puede invalidar la configuración que se aplica en el nivel de directiva de otra.</span><span class="sxs-lookup"><span data-stu-id="127a7-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="127a7-108">Skype para la prioridad de la directiva de Business Server es: directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva Global (menos influencia).</span><span class="sxs-lookup"><span data-stu-id="127a7-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="127a7-109">Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="127a7-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="127a7-110">Puede configurar directivas para controlar el acceso de usuarios federados, incluso si no ha habilitado la federación para su organización.</span><span class="sxs-lookup"><span data-stu-id="127a7-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="127a7-111">Sin embargo, las directivas que configurar entren en vigor sólo cuando tenga federación habilitada para su organización.</span><span class="sxs-lookup"><span data-stu-id="127a7-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="127a7-112">Para obtener información detallada acerca de cómo habilitar la federación, vea [Habilitar o deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="127a7-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="127a7-113">Además, si se especifica una directiva de usuario para controlar el acceso de usuarios federados, la directiva se aplica sólo a los usuarios que están habilitados para Skype para Business Server y configurados para utilizar la directiva.</span><span class="sxs-lookup"><span data-stu-id="127a7-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="127a7-114">Para configurar una directiva para admitir el acceso de usuarios de dominios federados</span><span class="sxs-lookup"><span data-stu-id="127a7-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="127a7-115">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="127a7-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="127a7-116">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="127a7-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="127a7-117">En la barra de navegación izquierda, haga clic en **Acceso de usuarios externos**y, a continuación, haga clic en **Directiva de acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="127a7-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="127a7-118">En la página **Directiva de acceso externo** , realice una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="127a7-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="127a7-119">Para configurar la directiva global para admitir el acceso de usuarios federados, haga clic en la directiva global, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="127a7-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="127a7-120">Para crear una nueva directiva de sitio, haga clic en **nuevo**y, a continuación, haga clic en **Directiva de sitio**.</span><span class="sxs-lookup"><span data-stu-id="127a7-120">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="127a7-121">En **Seleccionar un sitio**, haga clic en el sitio apropiado de la lista y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="127a7-121">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="127a7-122">Para crear una nueva directiva de usuario, haga clic en **nuevo**y, a continuación, haga clic en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="127a7-122">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="127a7-123">En la **Nueva directiva de acceso externo**, cree un nombre único en el campo **nombre** que indica qué usuario cubiertos por la directiva (por ejemplo, **EnableFederatedUsers** para una directiva de usuario que permite a comunicaciones para los usuarios de dominio federado).</span><span class="sxs-lookup"><span data-stu-id="127a7-123">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="127a7-124">Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="127a7-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="127a7-125">(Opcional) Si desea agregar o editar una descripción, especifique la información de la directiva en **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="127a7-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="127a7-126">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="127a7-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="127a7-127">Para habilitar el acceso de usuarios federados para la directiva, active la casilla de verificación **Habilitar las comunicaciones con los usuarios federados** .</span><span class="sxs-lookup"><span data-stu-id="127a7-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="127a7-128">Para deshabilitar el acceso de usuarios federados para la directiva, desactive la casilla de verificación **Habilitar las comunicaciones con los usuarios federados** .</span><span class="sxs-lookup"><span data-stu-id="127a7-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="127a7-129">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="127a7-129">Click **Commit**.</span></span>

<span data-ttu-id="127a7-130">Para habilitar el acceso de usuarios federados, también debe habilitar la compatibilidad para la federación en la organización.</span><span class="sxs-lookup"><span data-stu-id="127a7-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="127a7-131">Para obtener información detallada, vea [Habilitar o deshabilitar la federación y la conectividad de mensajería instantánea pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="127a7-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="127a7-132">Si se trata de una directiva de usuario, también debe aplicar la directiva a los usuarios que desea que puedan colaborar con los usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="127a7-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="127a7-133">Para obtener información detallada, vea [asignar una directiva de acceso de usuarios externos](assign-an-external-user-access-policy.md).</span><span class="sxs-lookup"><span data-stu-id="127a7-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="127a7-134">Para configurar una directiva existente con Windows PowerShell para admitir el acceso de usuarios de dominios federados</span><span class="sxs-lookup"><span data-stu-id="127a7-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="127a7-135">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="127a7-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="127a7-136">Iniciar el Skype para Shell de administración de negocios Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="127a7-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="127a7-137">Escriba lo siguiente en el Skype para Shell de administración de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="127a7-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="127a7-138">El parámetro "EnablePublicCloudAudioVideoAccess" no tiene una selección correspondiente en el Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="127a7-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="127a7-139">Para crear una nueva directiva de uso de Windows PowerShell para admitir el acceso de usuarios de dominios federados</span><span class="sxs-lookup"><span data-stu-id="127a7-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="127a7-140">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="127a7-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="127a7-141">Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Microsoft Skype para Business Server**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="127a7-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="127a7-142">Escriba lo siguiente en el Skype para Shell de administración de servidor empresarial:</span><span class="sxs-lookup"><span data-stu-id="127a7-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="127a7-143">Un ejemplo de creación de una nueva directiva de sitio:</span><span class="sxs-lookup"><span data-stu-id="127a7-143">An example of creating a new site policy:</span></span>
    
    ```
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="127a7-144">Para eliminar o restablecer una directiva de uso de Windows PowerShell para admitir el acceso de usuarios de dominios federados</span><span class="sxs-lookup"><span data-stu-id="127a7-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="127a7-145">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="127a7-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="127a7-146">Escriba lo siguiente en el Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="127a7-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="127a7-147">Un ejemplo de restablecimiento de la directiva global (la directiva global sólo puede tener su configuración se ha quitado.</span><span class="sxs-lookup"><span data-stu-id="127a7-147">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="127a7-148">La directiva no se puede eliminar):</span><span class="sxs-lookup"><span data-stu-id="127a7-148">The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="127a7-149">Para quitar una directiva de sitio, escriba:</span><span class="sxs-lookup"><span data-stu-id="127a7-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="127a7-150">Elimina la directiva de sitio Redmond.</span><span class="sxs-lookup"><span data-stu-id="127a7-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="127a7-151">Para eliminar una directiva de usuario denominada UserEAPPolicy, escriba:</span><span class="sxs-lookup"><span data-stu-id="127a7-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="127a7-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="127a7-152">See Also</span></span>


[<span data-ttu-id="127a7-153">Habilitar o deshabilitar la federación y conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="127a7-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="127a7-154">Asignar una directiva de acceso de usuario externo</span><span class="sxs-lookup"><span data-stu-id="127a7-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="127a7-155">Administrar dominios federados SIP para la organización</span><span class="sxs-lookup"><span data-stu-id="127a7-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="127a7-156">Administrar proveedores federados SIP para la organización</span><span class="sxs-lookup"><span data-stu-id="127a7-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="127a7-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="127a7-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="127a7-158">Nueva CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="127a7-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="127a7-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="127a7-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="127a7-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="127a7-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="127a7-161">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="127a7-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

