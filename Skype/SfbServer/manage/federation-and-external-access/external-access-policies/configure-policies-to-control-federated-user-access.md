---
title: Configuración de directivas para controlar el acceso de usuarios federados
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Al configurar directivas para admitir comunicaciones con socios federados, las directivas se aplican a los usuarios de dominios federados. '
ms.openlocfilehash: 447aad751ce6fc91bf2d6b80c8a14e92f9d4da82
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037410"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="3836b-103">Configuración de directivas para controlar el acceso de usuarios federados en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="3836b-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="3836b-104">Al configurar directivas para admitir comunicaciones con socios federados, las directivas se aplican a los usuarios de dominios federados.</span><span class="sxs-lookup"><span data-stu-id="3836b-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="3836b-105">Puede configurar una o más directivas de acceso de usuarios externos para controlar si los usuarios de dominios federados pueden colaborar con los usuarios de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3836b-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="3836b-106">Puede configurar directivas de nivel global, de sitio y de usuario para controlar el acceso de usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="3836b-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="3836b-107">La configuración de directivas de Skype empresarial Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica en otro nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="3836b-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="3836b-108">La prioridad de la Directiva de Skype empresarial Server es: la Directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva global (menor influencia).</span><span class="sxs-lookup"><span data-stu-id="3836b-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="3836b-109">Esto significa que cuanto más cerca esté la configuración de la Directiva, el objeto al que afecta la Directiva, más influencia tendrá en el objeto.</span><span class="sxs-lookup"><span data-stu-id="3836b-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="3836b-110">Puede configurar directivas para controlar el acceso de usuarios federados, incluso aunque no haya habilitado una federación para la organización.</span><span class="sxs-lookup"><span data-stu-id="3836b-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="3836b-111">Sin embargo, las directivas que configure únicamente surtirán efecto cuando haya habilitado la federación en la organización.</span><span class="sxs-lookup"><span data-stu-id="3836b-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="3836b-112">Para obtener información detallada acerca de la habilitación de la Federación, consulte [habilitar o deshabilitar el acceso de usuarios remotos](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="3836b-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="3836b-113">Además, si especifica una directiva de usuario para controlar el acceso de usuarios federados, la Directiva solo se aplica a los usuarios que están habilitados para Skype empresarial Server y que están configurados para usar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="3836b-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="3836b-114">Para configurar una directiva para permitir el acceso de usuarios de dominios federados</span><span class="sxs-lookup"><span data-stu-id="3836b-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="3836b-115">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3836b-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3836b-116">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3836b-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="3836b-117">En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Directiva de acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="3836b-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="3836b-118">En la página **Directiva de acceso externo**, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="3836b-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="3836b-119">Para configurar la directiva global para permitir el acceso de usuarios federados, haga clic en la directiva global, en **Editar** y en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="3836b-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="3836b-p103">Para crear una directiva de sitio nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de sitio**. En **Seleccionar un sitio**, haga clic en el sitio apropiado de la lista y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3836b-p103">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="3836b-p104">Para crear una directiva de usuario nueva, haga clic en **Nuevo** y, a continuación, en **Directiva de usuario**. En **Nueva directiva de acceso externo**, cree un nombre único en el campo **Nombre** que indique lo que cubre la directiva de usuario (por ejemplo, **PermitirUsuariosFederados** para una directiva de usuario que permita comunicaciones para usuarios de dominios federados).</span><span class="sxs-lookup"><span data-stu-id="3836b-p104">To create a new user policy, click **New**, and then click **User policy**. In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="3836b-124">Para cambiar una directiva existente, haga clic en la directiva correspondiente que aparece en la tabla, en **Editar** y, a continuación en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="3836b-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3836b-125">(Opcional) Si quiere agregar o editar una descripción, especifique la información para la directiva en **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="3836b-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="3836b-126">Siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="3836b-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="3836b-127">Para habilitar el acceso de usuarios federados para la directiva, active la casilla **Habilitar comunicaciones con usuarios federados**.</span><span class="sxs-lookup"><span data-stu-id="3836b-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="3836b-128">Para deshabilitar el acceso de usuarios federados para la directiva, desactive la casilla **Habilitar comunicaciones con usuarios federados**.</span><span class="sxs-lookup"><span data-stu-id="3836b-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="3836b-129">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3836b-129">Click **Commit**.</span></span>

<span data-ttu-id="3836b-130">Para habilitar el acceso de usuarios federados, también debe admitir una federación en la organización.</span><span class="sxs-lookup"><span data-stu-id="3836b-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="3836b-131">Para obtener más información, consulte [habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="3836b-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="3836b-132">Si se trata de una directiva de usuario, también tiene que aplicar la directiva a los usuarios que desee que puedan colaborar con usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="3836b-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="3836b-133">Para obtener más información, consulte [asignar una directiva de acceso de usuario externo](assign-an-external-user-access-policy.md).</span><span class="sxs-lookup"><span data-stu-id="3836b-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="3836b-134">Para configurar una directiva existente mediante Windows PowerShell para permitir el acceso de usuarios de dominios federados</span><span class="sxs-lookup"><span data-stu-id="3836b-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="3836b-135">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3836b-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3836b-136">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, en **todos los programas**, en **Skype empresarial Server**y, a continuación, en **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="3836b-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="3836b-137">Escriba lo siguiente en el shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="3836b-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="3836b-138">El parámetro "EnablePublicCloudAudioVideoAccess" no tiene una selección correspondiente en el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="3836b-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="3836b-139">Para crear una nueva Directiva mediante Windows PowerShell para permitir el acceso de usuarios de dominios federados</span><span class="sxs-lookup"><span data-stu-id="3836b-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="3836b-140">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3836b-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3836b-141">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, **todos los programas**, **Microsoft Skype empresarial Server**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="3836b-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="3836b-142">Escriba lo siguiente en el shell de administración de Skype empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="3836b-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="3836b-143">Un ejemplo de creación de una nueva directiva de sitio:</span><span class="sxs-lookup"><span data-stu-id="3836b-143">An example of creating a new site policy:</span></span>
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="3836b-144">Para eliminar o restablecer una Directiva mediante Windows PowerShell para permitir el acceso de usuarios de dominios federados</span><span class="sxs-lookup"><span data-stu-id="3836b-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="3836b-145">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3836b-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3836b-146">Escriba lo siguiente en el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="3836b-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="3836b-p107">Un ejemplo de restablecimiento de la directiva global (la directiva global solo puede tener su parámetro eliminado. La directiva no se puede eliminar):</span><span class="sxs-lookup"><span data-stu-id="3836b-p107">An example of resetting the global policy (The global policy can only have its setting removed. The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="3836b-149">Para quitar una directiva de sitio, escriba:</span><span class="sxs-lookup"><span data-stu-id="3836b-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="3836b-150">Elimina la directiva de sitio Redmond.</span><span class="sxs-lookup"><span data-stu-id="3836b-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="3836b-151">Para eliminar una directiva de usuario denominada UserEAPPolicy, escriba:</span><span class="sxs-lookup"><span data-stu-id="3836b-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="3836b-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="3836b-152">See Also</span></span>


[<span data-ttu-id="3836b-153">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="3836b-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="3836b-154">Asignar una directiva de acceso de usuario externo</span><span class="sxs-lookup"><span data-stu-id="3836b-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="3836b-155">Administrar dominios federados SIP para la organización</span><span class="sxs-lookup"><span data-stu-id="3836b-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="3836b-156">Administrar proveedores federados SIP para la organización</span><span class="sxs-lookup"><span data-stu-id="3836b-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="3836b-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="3836b-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="3836b-158">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="3836b-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="3836b-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="3836b-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="3836b-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="3836b-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="3836b-161">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="3836b-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

