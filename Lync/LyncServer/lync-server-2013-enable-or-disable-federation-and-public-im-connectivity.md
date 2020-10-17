---
title: 'Lync Server 2013: habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c94b75aff1b79650adc846d3d761580e9429035d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526797"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a><span data-ttu-id="56980-102">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56980-102">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56980-103">_**Última modificación del tema:** 2013-06-24_</span><span class="sxs-lookup"><span data-stu-id="56980-103">_**Topic Last Modified:** 2013-06-24_</span></span>

<span data-ttu-id="56980-104">Es obligatorio tener compatibilidad para la federación con el fin de que los usuarios que dispongan de una cuenta con un cliente de confianza o con una organización de un socio, incluso dominios y usuarios de proveedores de mensajería instantánea pública que usted admita, puedan colaborar con los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="56980-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="56980-105">La federación también es necesaria para usar un proveedor de servicios hospedados de Exchange para proporcionar correo de voz a usuarios de Telefonía IP empresarial cuyos buzones de correo se ubican en un servicio hospedado de Exchange como Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="56980-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="56980-106">Cuando haya establecido una relación de confianza con estos dominios externos, puede autorizar a los usuarios de esos dominios para que tengan acceso a la implementación y participen en las comunicaciones de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56980-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Lync Server communications.</span></span> <span data-ttu-id="56980-107">Esta relación de confianza se denomina federación y no está relacionada ni depende de una relación de confianza con Active Directory.</span><span class="sxs-lookup"><span data-stu-id="56980-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="56980-p102">Para admitir el acceso de usuarios de dominios federados, es preciso que habilite la federación. Si habilita la federación en su organización, deberá especificar también si se van a implementar las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="56980-p102">To support access by users of federated domains, you must enable federation. If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="56980-110">**Habilitar detección**     de dominio de socio Si habilita esta opción, Lync Server usa registros del sistema de nombres de dominio (DNS) para intentar detectar dominios que no aparecen en la lista de dominios permitidos, evaluar automáticamente el tráfico entrante de socios federados detectados y limitar o bloquear ese tráfico en función del nivel de confianza, la cantidad de tráfico y la configuración del administrador.</span><span class="sxs-lookup"><span data-stu-id="56980-110">**Enable partner domain discovery**   If you enable this option, Lync Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="56980-111">Si no selecciona esta opción, el acceso de usuarios federados se habilitará solamente para los usuarios en los dominios que haya incluido en la lista de dominios admitidos.</span><span class="sxs-lookup"><span data-stu-id="56980-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="56980-112">Independientemente de si selecciona esta opción o no, podrá especificar que se bloqueen o permitan dominios individuales, incluso restringir el acceso de servidores específicos que se ejecuten en el servicio perimetral de acceso del dominio federado.</span><span class="sxs-lookup"><span data-stu-id="56980-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="56980-113">Para obtener información detallada sobre cómo controlar el acceso por parte de los dominios federados, consulte [configurar la compatibilidad con dominios externos permitidos en Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="56980-113">For details about controlling access by federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>

  - <span data-ttu-id="56980-114">**Enviar una declinación de responsabilidades de archivado a socios federados**     Aviso de declinación de responsabilidades se envía a los socios federados que el archivado de la implementación está en su ubicación.</span><span class="sxs-lookup"><span data-stu-id="56980-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="56980-115">Si admite el archivado de las comunicaciones externas con los dominios de socios federados, debe habilitar la notificación de declinación de responsabilidad para avisar a los socios que sus mensajes están siendo archivados.</span><span class="sxs-lookup"><span data-stu-id="56980-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="56980-p105">Si más adelante desea impedir, de forma temporal o permanente, el acceso de usuarios de dominios federados, puede deshabilitar la para su organización. Use el procedimiento que aparece en esta sección para habilitar o deshabilitar el acceso de usuarios federados en su organización, así como para especificar las opciones de federación apropiadas para su organización.</span><span class="sxs-lookup"><span data-stu-id="56980-p105">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization. Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="56980-118">Si se habilita la federación para la organización solo se indica que los servidores que ejecutan el servicio perimetral de acceso admiten el enrutamiento a dominios federados.</span><span class="sxs-lookup"><span data-stu-id="56980-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="56980-119">Los usuarios de dominios federados no pueden participar en la mensajería instantánea o conferencias en su organización hasta que configure asimismo al menos una directiva para admitir el acceso de usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="56980-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="56980-120">Los usuarios de proveedores de servicios de mensajería instantánea pública no podrán participar en la mensajería instantánea ni en conferencias de la organización hasta que configure también al menos una directiva para admitir conectividad de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="56980-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="56980-121">Lync Server no puede usar un servicio hospedado de Exchange para proporcionar servicios de contestador automático, Outlook Voice Access (incluido el correo de voz) o servicios de operador automático para usuarios cuyos buzones de correo se ubican en un servicio hospedado de Exchange hasta que configure una directiva de correo de voz hospedada que proporcione información de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="56980-121">Lync Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="56980-122">Para más información sobre cómo configurar directivas para comunicarse con usuarios de dominios federados en otras organizaciones, consulte <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP Federated Domains for your Organization in Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="56980-122">For details about configuring policies for communication with users of federated domains in other organizations, see <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="56980-123">Por otra parte, si desea admitir la comunicación con usuarios de los proveedores de servicios de mensajería instantánea, es preciso que configure directivas para aportar tal compatibilidad, así como para aportar compatibilidad a los proveedores de servicios individuales que desee.</span><span class="sxs-lookup"><span data-stu-id="56980-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="56980-124">Para obtener más información, consulte <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP Federated Providers for your Organization in Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="56980-124">For details, see <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP federated providers for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="56980-125">Para obtener información detallada sobre cómo crear una directiva de correo de voz hospedado, consulte <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage host Voice Mail policies in Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="56980-125">For details about creating a hosted voice mail policy, see <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="56980-126">Para habilitar o deshabilitar el acceso de usuarios federados en la organización</span><span class="sxs-lookup"><span data-stu-id="56980-126">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="56980-127">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="56980-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="56980-128">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56980-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="56980-129">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="56980-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="56980-130">En el barra de navegación izquierda, haga clic en **Acceso para usuarios externos** y, a continuación, en **Configuración perimetral de acceso**.</span><span class="sxs-lookup"><span data-stu-id="56980-130">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="56980-131">En la página **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, a continuación en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="56980-131">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="56980-132">En **Editar configuración perimetral de acceso**, lleve a cabo uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="56980-132">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="56980-133">Para habilitar el acceso de usuarios federados en la organización, active la casilla **Habilitar comunicaciones con usuarios federados**.</span><span class="sxs-lookup"><span data-stu-id="56980-133">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="56980-134">Para deshabilitar el acceso de usuarios federados en la organización, desactive la casilla **Habilitar comunicaciones con usuarios federados**.</span><span class="sxs-lookup"><span data-stu-id="56980-134">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="56980-135">Si activó la casilla **Habilitar comunicaciones con usuarios federados**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="56980-135">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="56980-136">Si desea admitir la detección automática de dominios de socios, active la casilla **Habilitar detección de dominio de socio**.</span><span class="sxs-lookup"><span data-stu-id="56980-136">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="56980-137">Si la organización admite el archivado de comunicaciones externas, active la casilla **Enviar declinación de responsabilidades de archivado a los socios federados**.</span><span class="sxs-lookup"><span data-stu-id="56980-137">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="56980-138">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="56980-138">Click **Commit**.</span></span>

<span data-ttu-id="56980-139">Para permitir que los usuarios federados colaboren con los usuarios de su implementación de Lync Server 2013, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="56980-139">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="56980-140">Para obtener más información, vea [Configure Policies to control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="56980-140">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="56980-141">Para controlar el acceso a dominios federados específicos, consulte [configurar la compatibilidad con dominios externos permitidos en Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) en la documentación de implementación o de operaciones.</span><span class="sxs-lookup"><span data-stu-id="56980-141">To control access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="56980-142">Habilitar o deshabilitar la Federación y la conectividad de mensajería instantánea pública mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="56980-142">Enabling or Disabling Federation and Public IM Connectivity by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="56980-143">La Federación y la conectividad de mensajería instantánea pública también se pueden administrar con Windows PowerShell y el cmdlet Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="56980-143">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="56980-144">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56980-144">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="56980-145">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="56980-145">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="56980-146">Para habilitar la Federación y la conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="56980-146">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="56980-147">Para habilitar la federación y la conectividad de mensajería instantánea pública, establezca el valor de la propiedad **AllowFederatedUsers** en True ($True):</span><span class="sxs-lookup"><span data-stu-id="56980-147">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="56980-148">Para deshabilitar la Federación y la conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="56980-148">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="56980-149">Para deshabilitar la federación y la conectividad de mensajería instantánea pública, establezca el valor de la propiedad **AllowFederatedUsers** en False ($False):</span><span class="sxs-lookup"><span data-stu-id="56980-149">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

