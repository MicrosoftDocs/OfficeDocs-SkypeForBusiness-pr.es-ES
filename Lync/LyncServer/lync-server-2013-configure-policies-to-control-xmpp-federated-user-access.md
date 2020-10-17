---
title: 'Lync Server 2013: configurar directivas para controlar el acceso de usuarios federados de XMPP'
description: 'Lync Server 2013: configurar directivas para controlar el acceso de usuarios federados de XMPP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdb2b7a3da6c00aa7725ecbb69856756f229ed97
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542786"
---
# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="05891-103">Configurar directivas para controlar el acceso de usuarios federados de XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05891-103">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05891-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="05891-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="05891-105">Esta documentación es preliminar y está sujeta a cambios.</span><span class="sxs-lookup"><span data-stu-id="05891-105">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="05891-106">Los temas en blanco se incluyen para referencia futura.</span><span class="sxs-lookup"><span data-stu-id="05891-106">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="05891-107">Cuando configura las directivas para admitir socios federados del Protocolo extensible de mensajería y presencia (XMPP), las directivas se aplican a los usuarios de dominios federados de XMPP, pero no a usuarios de proveedores de servicios de mensajería instantánea (IM) del Protocolo de inicio de sesión (SIP) (por ejemplo, Windows Live) o dominios federados de SIP.</span><span class="sxs-lookup"><span data-stu-id="05891-107">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="05891-108">Configure un **Socio federado de XMPP** para cada dominio federado de XMPP al que desee que sus usuarios puedan agregar contactos y con el que puedan comunicarse.</span><span class="sxs-lookup"><span data-stu-id="05891-108">You configure an **XMPP Federated Partner** for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="05891-109">Las directivas de socios federados de XMPP están solamente disponibles en un único ámbito; pese a que no están definidas como una directiva global, actúan como una directiva global.</span><span class="sxs-lookup"><span data-stu-id="05891-109">XMPP federated partners policies are only available in a single scope, though it is not defined as a global policy, acts as a global policy.</span></span> <span data-ttu-id="05891-110">Para definir una directiva de usuario o sitio global para los socios federados de XMPP, configure el ámbito de directiva en primer lugar creando y configurando la Directiva de acceso externo para el ámbito que necesita.</span><span class="sxs-lookup"><span data-stu-id="05891-110">To define a global, site or user policy for XMPP Federation Partners, you configure the policy scope by first creating and configuring the External Access Policy for the scope you require.</span></span> <span data-ttu-id="05891-111">Para obtener más información sobre los tipos de directivas que puede configurar para el acceso externo y la Federación, consulte [Managing Federation and external Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="05891-111">For details about the types of policies that you can configure for external access and federation, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="05891-112">Todas las directivas de <STRONG>Acceso externo y federación</STRONG> se aplican a través del aprovisionamiento en banda.</span><span class="sxs-lookup"><span data-stu-id="05891-112">All <STRONG>Federation and External Access</STRONG> policies are applied through in-band provisioning.</span></span> <span data-ttu-id="05891-113">Las directivas que se aplican al usuario, que pertenecen a un sitio o que tienen un ámbito global se comunican al cliente durante el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="05891-113">The policies that apply to the user, belong to a site, or are global in scope are communicated to the client during login.</span></span> <span data-ttu-id="05891-114">Puede configurar directivas para controlar el acceso de socios federados de XMPP, incluso aunque no haya habilitado una federación de XMPP para su organización.</span><span class="sxs-lookup"><span data-stu-id="05891-114">You can configure policies to control XMPP federated partner access, even if you have not enabled XMPP federation for your organization.</span></span> <span data-ttu-id="05891-115">Sin embargo, las directivas que configura entran en vigencia solo cuando tiene una federación de socios de XMPP implementada, habilitada o configurada para su organización.</span><span class="sxs-lookup"><span data-stu-id="05891-115">However, the policies that you configure take effect only when you have XMPP partner federation deployed, enabled and configured for your organization.</span></span> <span data-ttu-id="05891-116">Para obtener información detallada sobre la implementación y la configuración de la Federación del asociado XMPP, consulte <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP Federation, XMPP Federation and Public Instant Messaging in Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="05891-116">For details about deploying and configuring XMPP partner federation, see <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="05891-117">Además, si especifica una directiva de usuario en la Directiva de acceso externo para controlar los socios federados XMPP, la Directiva solo se aplicará a los usuarios que estén habilitados para Lync Server 2013 y que estén configurados para usar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="05891-117">Additionally, if you specify a user policy in External Access Policy to control XMPP federated partners, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a><span data-ttu-id="05891-118">Editar una directiva global para socios federados de XMPP</span><span class="sxs-lookup"><span data-stu-id="05891-118">To edit a global policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="05891-119">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="05891-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="05891-120">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05891-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="05891-121">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="05891-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="05891-122">En el barra de navegación izquierda, haga clic en  \*\*Acceso para usuarios externos \*\* y, a continuación, en  \*\*Directiva de acceso externo \*\*.</span><span class="sxs-lookup"><span data-stu-id="05891-122">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="05891-123">En la página **Directiva de acceso externo**, realice lo siguiente para la directiva global:</span><span class="sxs-lookup"><span data-stu-id="05891-123">On the **External Access Policy** page, do the following for the global policy:</span></span>

5.  <span data-ttu-id="05891-124">Haga clic en la directiva global, haga clic en **Editar** y, a continuación, en Mostrar detalles.</span><span class="sxs-lookup"><span data-stu-id="05891-124">Click the global policy, click **Edit**, and then click Show details.</span></span>

6.  <span data-ttu-id="05891-125">Proporcione una descripción para la directiva global (opcional).</span><span class="sxs-lookup"><span data-stu-id="05891-125">Provide a description for the Global policy (optional).</span></span>

7.  <span data-ttu-id="05891-126">Seleccione **Habilitar las comunicaciones con usuarios asociados**.</span><span class="sxs-lookup"><span data-stu-id="05891-126">Select **Enable communications with federated users**.</span></span>

8.  <span data-ttu-id="05891-127">Seleccione **Habilitar las comunicaciones con usuarios asociados de XMPP**.</span><span class="sxs-lookup"><span data-stu-id="05891-127">Select **Enable communications with XMPP federated users**.</span></span>

9.  <span data-ttu-id="05891-128">Haga clic en **Confirmar** para guardar los cambios realizados en la directiva global.</span><span class="sxs-lookup"><span data-stu-id="05891-128">Click **Commit** to save your changes to the Global policy.</span></span>

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a><span data-ttu-id="05891-129">Crear una directiva de usuario o de sitio para socios federados de XMPP</span><span class="sxs-lookup"><span data-stu-id="05891-129">To create a site or user policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="05891-p105">Haga clic en **Nuevo** y en **Directiva de sitio** o **Directiva de usuario**. En **Seleccionar un sitio**, haga clic en el sitio apropiado de la lista y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="05891-p105">Click **New**, and then click **Site policy** or **User policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>

2.  <span data-ttu-id="05891-132">Proporcione una descripción para la directiva de sitio (opcional).</span><span class="sxs-lookup"><span data-stu-id="05891-132">Provide a description for the Site policy (optional).</span></span>

3.  <span data-ttu-id="05891-133">En la directiva de usuario o de sitio, seleccione **Habilitar las comunicaciones con usuarios asociados**.</span><span class="sxs-lookup"><span data-stu-id="05891-133">In the site or user policy, select **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="05891-134">Seleccione **Habilitar las comunicaciones con usuarios asociados de XMPP**.</span><span class="sxs-lookup"><span data-stu-id="05891-134">Select **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="05891-135">Haga clic en **Confirmar** para guardar los cambios realizados en la directiva de usuario o de sitio.</span><span class="sxs-lookup"><span data-stu-id="05891-135">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a><span data-ttu-id="05891-136">Editar una directiva existente para socios federados de XMPP</span><span class="sxs-lookup"><span data-stu-id="05891-136">To edit an existing policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="05891-137">Para cambiar una directiva existente, seleccione la directiva correspondiente que aparece en la lista, haga clic en **Editar** y, a continuación en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="05891-137">To change an existing policy, select the appropriate policy in the list, click **Edit**, and then click **Show details**.</span></span>

2.  <span data-ttu-id="05891-138">Modificar o actualizar la descripción de la directiva (opcional).</span><span class="sxs-lookup"><span data-stu-id="05891-138">Change or update the description for the policy (optional).</span></span>

3.  <span data-ttu-id="05891-139">Seleccione o anule la selección de **Habilitar las comunicaciones con usuarios asociados**.</span><span class="sxs-lookup"><span data-stu-id="05891-139">Select or unselect **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="05891-140">Seleccione o anule la selección de **Habilitar las comunicaciones con usuarios asociados de XMPP**.</span><span class="sxs-lookup"><span data-stu-id="05891-140">Select or unselect **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="05891-141">Haga clic en **Confirmar** para guardar los cambios realizados en la directiva.</span><span class="sxs-lookup"><span data-stu-id="05891-141">Click **Commit** to save your changes to the policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="05891-142">Para editar una directiva existente para socios federados de XMPP mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05891-142">To edit an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="05891-143">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="05891-143">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="05891-144">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="05891-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="05891-145">Escriba lo siguiente en el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="05891-145">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="05891-146">Un comando de ejemplo que establecerá la directiva global para el acceso de usuarios federados en verdadero (habilitado) y el acceso de dominio XMPP a verdadero (habilitado):</span><span class="sxs-lookup"><span data-stu-id="05891-146">An example command that will set the global policy for Federated user access to True (enabled) and XMPP domain access to True (enabled):</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a><span data-ttu-id="05891-147">Para crear una directiva de usuario o de sitio para socios federados de XMPP mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05891-147">To create a site or user policy for XMPP federated partners using Windows PowerShell</span></span>

1.  <span data-ttu-id="05891-148">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="05891-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="05891-149">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="05891-149">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="05891-150">Escriba lo siguiente en el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="05891-150">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="05891-151">Un comando de ejemplo que establecerá una directiva de sitio para el sitio Redmond para Acceso de usuarios asociados como habilitada y para Acceso de dominios de XMPP como habilitada:</span><span class="sxs-lookup"><span data-stu-id="05891-151">An example command that will set a site policy for the Redmond site for Federated user access to enabled and XMPP domain access to enabled:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="05891-152">Para eliminar una directiva existente para socios federados de XMPP mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="05891-152">To delete an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="05891-153">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="05891-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="05891-154">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="05891-154">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="05891-155">Escriba lo siguiente en el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="05891-155">Type the following in the Lync Server Management Shell:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    <span data-ttu-id="05891-156">Un comando de ejemplo que eliminará una directiva de usuario:</span><span class="sxs-lookup"><span data-stu-id="05891-156">An example command that will delete a user policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  <span data-ttu-id="05891-157">Un comando de ejemplo que restablecerá la directiva global a los valores predeterminados:</span><span class="sxs-lookup"><span data-stu-id="05891-157">An example command that will reset the global policy to defaults:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="05891-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="05891-158">See Also</span></span>


[<span data-ttu-id="05891-159">Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05891-159">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[<span data-ttu-id="05891-160">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05891-160">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[<span data-ttu-id="05891-161">Administrar socios federados XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05891-161">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[<span data-ttu-id="05891-162">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="05891-162">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="05891-163">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="05891-163">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="05891-164">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="05891-164">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="05891-165">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="05891-165">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="05891-166">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="05891-166">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

