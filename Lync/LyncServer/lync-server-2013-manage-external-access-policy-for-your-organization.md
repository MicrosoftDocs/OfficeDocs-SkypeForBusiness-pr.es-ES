---
title: 'Lync Server 2013: administrar la Directiva de acceso externo para la organización'
description: 'Lync Server 2013: administre la Directiva de acceso externo para su organización.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f0bb0e6764f67403065187c62debef13c77fcc3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558416"
---
# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="9c2ca-103">Administrar la Directiva de acceso externo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c2ca-103">Manage external access policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c2ca-104">_**Última modificación del tema:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="9c2ca-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="9c2ca-105">Después de implementar uno o varios servidores Edge, debe habilitar los tipos de acceso externo que se permitirán en la organización.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-105">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="9c2ca-p101">De forma predeterminada, no hay ninguna directiva configurada para admitir el acceso de usuarios externos, incluido el acceso de usuarios remotos, el acceso de usuarios federados, incluso si ya ha habilitado la compatibilidad con el acceso de usuarios externos para su organización. Para controlar el uso del acceso de usuarios externos, debe configurar una o más directivas, especificando el tipo de acceso de usuarios externos que es compatible con cada directiva. Para la creación y configuración están disponibles los siguientes ámbitos de directivas. De forma predeterminada, se crea la directiva global, pero no se puede eliminar.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="9c2ca-110">**Directiva global**   La directiva global se crea cuando se implementan los servidores Edge.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-110">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="9c2ca-111">De forma predeterminada, no hay habilitadas opciones de acceso de usuarios externos en la directiva global.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-111">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="9c2ca-112">Para admitir el acceso de usuarios externos en el nivel global, debe configurar la directiva global para que admita uno o más tipos de opciones de acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-112">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="9c2ca-113">La directiva global se aplica a todos los usuarios de su organización, pero las directivas de sitio y usuario invalidan la directiva global.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-113">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="9c2ca-114">Eliminar la directiva global no hará que desaparezca.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-114">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="9c2ca-115">En lugar de eso, se restablece la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-115">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="9c2ca-116">**Directiva de sitio**   Puede crear y configurar una o más directivas de sitio para limitar el acceso de usuarios externos a determinados sitios.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-116">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="9c2ca-117">La configuración de la directiva de sitio invalida la directiva global, pero solo en el caso del sitio específico que determina la directiva.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-117">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="9c2ca-118">Por ejemplo, si activa el acceso de usuarios remotos en la directiva global, puede especificar una directiva de sitio que deshabilite el acceso de usuarios remotos para un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-118">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="9c2ca-119">De forma predeterminada, una directiva de sitio se aplica a todos los usuarios de dicho sitio, aunque puede asignar una directiva de usuario a un usuario determinado para invalidar dicho parámetro de la directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-119">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="9c2ca-120">**Directiva de usuario**   Puede crear y configurar una o más directivas de usuario para limitar el acceso de usuarios remotos a determinados usuarios.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-120">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="9c2ca-121">La configuración de la directiva de usuario invalida la directiva global y la directiva de sitio, pero solo para los usuarios concretos a los que se ha asignado la directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-121">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="9c2ca-122">Por ejemplo, si deshabilita el acceso de usuarios remotos en la directiva global y a la directiva de sitio, puede especificar una directiva de usuario para deshabilitar el acceso de usuarios remotos y, a continuación, asignar dicha directiva de usuario a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-122">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="9c2ca-123">Si crea una directiva de sitio, debe aplicarla a uno o más usuarios antes de que se haga efectiva.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-123">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9c2ca-124">La configuración de la Directiva de Lync Server que se aplica en un nivel de Directiva puede invalidar la configuración que se aplica en otro nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-124">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="9c2ca-125">La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva global (menor influencia).</span><span class="sxs-lookup"><span data-stu-id="9c2ca-125">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="9c2ca-126">Esto significa que cuanto más se aproxime la configuración de la directiva al objeto al que afecta la directiva, más influencia tendrá en el objeto.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-126">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="9c2ca-127">Entre estas opciones se incluyen los siguientes tipos de acceso externo:</span><span class="sxs-lookup"><span data-stu-id="9c2ca-127">These options include the following types of external access:</span></span>

  - <span data-ttu-id="9c2ca-128">**Habilitar comunicaciones con usuarios federados**   habilite esta opción si quiere admitir el acceso de usuarios a los dominios de asociados federados.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-128">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="9c2ca-129">Esta opción configura la posibilidad de que los usuarios se comuniquen con otros dominios federados SIP, así como con proveedores hospedados como Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-129">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft 365.</span></span> <span data-ttu-id="9c2ca-130">La selección de esta opción le permite seleccionar la opción de permitir la comunicación con dominios XMPP federados.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-130">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="9c2ca-p107">Como opción, puede activar **Habilitar comunicaciones con socios XMPP federados** si primero activa **Habilitar comunicaciones con usuarios federados**. La federación XMPP es una federación con las organizaciones que usan el protocolo de mensajería extensible y presencia (XMPP).</span><span class="sxs-lookup"><span data-stu-id="9c2ca-p107">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**. XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9c2ca-133">Si habilita la Federación de XMPP, también debe seleccionar implementar la <STRONG>Federación XMPP</STRONG> en la sección configuración de grupos de servidores perimetrales del generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-133">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="9c2ca-134">La configuración para la Federación XMPP implementa un proxy XMPP en el servidor perimetral y una puerta de enlace XMPP en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-134">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="9c2ca-135">**Habilitación de comunicaciones con usuarios**     remotos Habilite esta opción si desea que los usuarios de la organización que están fuera del firewall, como los teletrabajadores y los usuarios que viajan, puedan conectarse a Lync Server a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-135">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="9c2ca-136">**Habilitación de comunicaciones con usuarios públicos**     Habilite esta opción si desea que los usuarios internos puedan comunicarse con los contactos de proveedores de mi públicos, como los proporcionados por Windows Live, Yahoo \! y America Online (AOL).</span><span class="sxs-lookup"><span data-stu-id="9c2ca-136">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="9c2ca-137">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-137">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="9c2ca-138">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="9c2ca-138">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="9c2ca-139">Messenger hasta que se cierre la fecha del servicio.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-139">Messenger until the service shut down date.</span></span> <span data-ttu-id="9c2ca-140">Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="9c2ca-140">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="9c2ca-141">se ha anunciado.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-141">has been announced.</span></span> <span data-ttu-id="9c2ca-142">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-142">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="9c2ca-143">La capa de PIC es una licencia por usuario por mes que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="9c2ca-143">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="9c2ca-144">Service.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-144">Messenger.</span></span> <span data-ttu-id="9c2ca-145">La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente para el que se liquida.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-145">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="9c2ca-146">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-146">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="9c2ca-147">La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-147">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="9c2ca-148">La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con mi y voz.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-148">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="9c2ca-149">Además de habilitar la compatibilidad de acceso de usuarios externos, también debe configurar directivas para controlar el uso del acceso de usuarios externos en su organización antes de que los usuarios obtengan cualquier tipo de acceso para usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-149">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="9c2ca-150">Para obtener más información sobre cómo crear, configurar y aplicar directivas para el acceso de usuarios externos, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-150">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="9c2ca-151">**Para ver directivas de acceso externo con cmdlets de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="9c2ca-151">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="9c2ca-152">Puede ver las directivas de acceso externo mediante el shell de administración de Lync Server y el cmdlet **Get-CsExternalAccessPolicy** .</span><span class="sxs-lookup"><span data-stu-id="9c2ca-152">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="9c2ca-153">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c2ca-153">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9c2ca-154">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="9c2ca-154">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="9c2ca-155">Para ver información sobre todas las directivas de acceso externo escriba el comando siguiente en el shell de administración de Lync Server y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="9c2ca-155">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="9c2ca-156">Este comando devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="9c2ca-156">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="9c2ca-157">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9c2ca-157">In This Section</span></span>

  - [<span data-ttu-id="9c2ca-158">Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c2ca-158">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="9c2ca-159">Configurar directivas para controlar el acceso de usuarios federados de XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c2ca-159">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="9c2ca-160">Configurar directivas para controlar el acceso de usuarios remotos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c2ca-160">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="9c2ca-161">Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c2ca-161">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="9c2ca-162">Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c2ca-162">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="9c2ca-163">Restablecimiento o eliminación de directivas de acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c2ca-163">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

