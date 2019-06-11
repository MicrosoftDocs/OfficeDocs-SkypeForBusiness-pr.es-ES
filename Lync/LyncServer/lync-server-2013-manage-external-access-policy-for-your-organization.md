---
title: 'Lync Server 2013: Administrar la directiva de acceso de la organización'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10a08e096d517d2ac53866df763ab2f553480da5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a><span data-ttu-id="71f3a-102">Administrar la directiva de acceso de la organización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71f3a-102">Manage external access policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71f3a-103">_**Última modificación del tema:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="71f3a-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="71f3a-104">Después de implementar uno o varios servidores perimetrales, debe habilitar los tipos de acceso externo que será compatible con su organización.</span><span class="sxs-lookup"><span data-stu-id="71f3a-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="71f3a-105">De forma predeterminada, no hay ninguna directiva configurada para admitir el acceso de usuarios externos, incluido el acceso de usuarios remotos, acceso de usuarios federados, incluso si ya ha habilitado la compatibilidad de acceso de usuarios externos para su organización.</span><span class="sxs-lookup"><span data-stu-id="71f3a-105">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization.</span></span> <span data-ttu-id="71f3a-106">Para controlar el uso del acceso de usuarios externos, debe configurar una o más directivas, especificando el tipo de acceso de usuarios externos admitido para cada Directiva.</span><span class="sxs-lookup"><span data-stu-id="71f3a-106">To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy.</span></span> <span data-ttu-id="71f3a-107">Los siguientes ámbitos de directivas están disponibles para la creación y la configuración.</span><span class="sxs-lookup"><span data-stu-id="71f3a-107">The following policy scopes are available for creation and configuration.</span></span> <span data-ttu-id="71f3a-108">De forma predeterminada, se crea la directiva global, pero no se puede eliminar.</span><span class="sxs-lookup"><span data-stu-id="71f3a-108">By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="71f3a-109">**Directiva global se**   crea la directiva global al implementar los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="71f3a-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="71f3a-110">De forma predeterminada, no hay ninguna opción de acceso de usuario externo habilitada en la directiva global.</span><span class="sxs-lookup"><span data-stu-id="71f3a-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="71f3a-111">Para admitir el acceso de usuarios externos en el nivel global, configure la directiva global para que admita uno o varios tipos de opciones de acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="71f3a-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="71f3a-112">La directiva global se aplica a todos los usuarios de la organización, pero las directivas del sitio y las directivas de usuario invalidan la directiva global.</span><span class="sxs-lookup"><span data-stu-id="71f3a-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="71f3a-113">Si elimina la directiva global, no la quitará.</span><span class="sxs-lookup"><span data-stu-id="71f3a-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="71f3a-114">En su lugar, lo restablecerá a la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="71f3a-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="71f3a-115">**Directiva de sitio**   puede crear y configurar una o varias directivas de sitio para limitar la compatibilidad con el acceso de usuarios externos a sitios específicos.</span><span class="sxs-lookup"><span data-stu-id="71f3a-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="71f3a-116">La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="71f3a-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="71f3a-117">Por ejemplo, si habilita el acceso de usuarios remotos en la directiva global, puede especificar una directiva de sitio que deshabilite el acceso de usuarios remotos para un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="71f3a-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="71f3a-118">De forma predeterminada, se aplica una directiva de sitio a todos los usuarios de ese sitio, pero puede asignar una directiva de usuario a un usuario para que anule la configuración de directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="71f3a-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="71f3a-119">**Directiva de usuario**   puede crear y configurar una o más directivas de usuario para limitar la compatibilidad del acceso de usuarios remotos a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="71f3a-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="71f3a-120">La configuración de la Directiva de usuario reemplaza la directiva global y la de sitio, pero solo para los usuarios específicos a los que se asigna la Directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="71f3a-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="71f3a-121">Por ejemplo, si habilita el acceso de usuarios remotos en la directiva global y la Directiva de sitio, puede especificar una directiva de usuario que deshabilite el acceso de usuarios remotos y, a continuación, asignar esa Directiva de usuario a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="71f3a-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="71f3a-122">Si crea una directiva de usuario, debe aplicarla a uno o más usuarios para que tenga efecto.</span><span class="sxs-lookup"><span data-stu-id="71f3a-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="71f3a-123">La configuración de directiva de Lync Server que se aplica a un nivel de Directiva puede invalidar la configuración que se aplica a otro nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="71f3a-123">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="71f3a-124">La prioridad de la Directiva de Lync Server es: la Directiva de usuario (más influencia) reemplaza a una directiva de sitio y, después, una directiva de sitio invalida una directiva global (menor influencia).</span><span class="sxs-lookup"><span data-stu-id="71f3a-124">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="71f3a-125">Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="71f3a-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>



</div>

<span data-ttu-id="71f3a-126">Estas opciones incluyen los siguientes tipos de acceso externo:</span><span class="sxs-lookup"><span data-stu-id="71f3a-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="71f3a-127">**Habilitar comunicaciones con usuarios**   federados: habilite esta opción si desea permitir el acceso de usuarios a dominios federados de socios federados.</span><span class="sxs-lookup"><span data-stu-id="71f3a-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="71f3a-128">Esta opción configura la posibilidad de que los usuarios se comuniquen con otros dominios federados SIP, así como con proveedores hospedados como Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="71f3a-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft Office 365.</span></span> <span data-ttu-id="71f3a-129">Si selecciona esta opción, podrá seleccionar la opción para permitir la comunicación con dominios federados de XMPP.</span><span class="sxs-lookup"><span data-stu-id="71f3a-129">Selecting this setting allows you to select the option to allow communication with XMPP federated domains.</span></span>
    
    <span data-ttu-id="71f3a-130">Como opción, puede seleccionar **Habilitar comunicaciones con los socios de XMPP federados** si, en primer lugar, selecciona **habilitar las comunicaciones con usuarios federados**.</span><span class="sxs-lookup"><span data-stu-id="71f3a-130">As an option, you can select **Enable communications with XMPP federated partners** if you first select **Enable communications with federated users**.</span></span> <span data-ttu-id="71f3a-131">La Federación XMPP es una federación con organizaciones que usan el protocolo de presencia y mensajería extensible (XMPP).</span><span class="sxs-lookup"><span data-stu-id="71f3a-131">XMPP federation is a federation with organizations that use extensible messaging and presence protocol (XMPP).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="71f3a-132">Si habilita la Federación XMPP, también debe seleccionar implementar la <STRONG>Federación XMPP</STRONG> en la sección configuración de grupos perimetrales del generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="71f3a-132">If you enable XMPP federation, you must also select to deploy <STRONG>XMPP federation</STRONG> in the Edge pools configuration section of Topology Builder.</span></span> <span data-ttu-id="71f3a-133">La configuración para la Federación XMPP implementa un proxy XMPP en el servidor perimetral y una puerta de enlace XMPP en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="71f3a-133">Configuring for XMPP federation deploys an XMPP Proxy on the Edge Server and an XMPP gateway on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="71f3a-134">**Habilitar las comunicaciones con usuarios**   remotos habilite esta opción si desea que los usuarios de su organización que estén fuera del firewall, como los teletrabajadores y los usuarios que viajan, puedan conectarse a Lync Server a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="71f3a-134">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

  - <span data-ttu-id="71f3a-135">**Habilitar las comunicaciones con usuarios**   públicos habilite esta opción si quiere que los usuarios internos puedan comunicarse con los contactos del proveedor de mensajería instantánea pública, como los que proporcionan Windows Live\!, Yahoo y America Online (AOL).</span><span class="sxs-lookup"><span data-stu-id="71f3a-135">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts, such as those provided by Windows Live, Yahoo\!, and America Online (AOL).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="71f3a-136">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de conectividad de mensajería instantánea pública de Microsoft Lync ("PIC USL") ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="71f3a-136">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="71f3a-137">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="71f3a-137">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="71f3a-138">Messenger hasta que se cierre la fecha del servicio.</span><span class="sxs-lookup"><span data-stu-id="71f3a-138">Messenger until the service shut down date.</span></span> <span data-ttu-id="71f3a-139">Una fecha de fin de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="71f3a-139">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="71f3a-140">ha sido anunciado.</span><span class="sxs-lookup"><span data-stu-id="71f3a-140">has been announced.</span></span> <span data-ttu-id="71f3a-141">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="71f3a-141">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="71f3a-142">El PIC USL es una licencia por usuario por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="71f3a-142">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="71f3a-143">Mensajería.</span><span class="sxs-lookup"><span data-stu-id="71f3a-143">Messenger.</span></span> <span data-ttu-id="71f3a-144">La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el que se está pospuesto.</span><span class="sxs-lookup"><span data-stu-id="71f3a-144">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="71f3a-145">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="71f3a-145">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="71f3a-146">La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="71f3a-146">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="71f3a-147">La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas con la mensajería instantánea y la voz.</span><span class="sxs-lookup"><span data-stu-id="71f3a-147">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="71f3a-148">Además de habilitar la compatibilidad de acceso de usuarios externos, también debe configurar directivas para controlar el uso del acceso de usuarios externos de su organización antes de que los usuarios tengan acceso a cualquier tipo de acceso de usuario externo.</span><span class="sxs-lookup"><span data-stu-id="71f3a-148">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="71f3a-149">Para obtener detalles sobre la creación, la configuración y la aplicación de directivas para el acceso de usuarios externos, vea <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar o deshabilitar el acceso de usuarios remotos en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="71f3a-149">For details about creating, configuring, and applying policies for external user access see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="71f3a-150">**Para ver las directivas de acceso externas mediante cmdlets de Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="71f3a-150">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="71f3a-151">Puede ver las directivas de acceso externas mediante el shell de administración de Lync Server y el cmdlet **Get-CsExternalAccessPolicy** .</span><span class="sxs-lookup"><span data-stu-id="71f3a-151">You can view external access policies by using Lync Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="71f3a-152">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71f3a-152">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="71f3a-153">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="71f3a-153">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="71f3a-154">Para ver información sobre todas las directivas de acceso externo, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="71f3a-154">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsExternalAccessPolicy
    
    <span data-ttu-id="71f3a-155">Este comando devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="71f3a-155">This command returns information similar to the following:</span></span>
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a><span data-ttu-id="71f3a-156">En esta sección</span><span class="sxs-lookup"><span data-stu-id="71f3a-156">In This Section</span></span>

  - [<span data-ttu-id="71f3a-157">Configurar directivas para controlar el acceso de usuarios federados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71f3a-157">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [<span data-ttu-id="71f3a-158">Configurar directivas para controlar el acceso de usuarios federados de XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71f3a-158">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [<span data-ttu-id="71f3a-159">Configurar directivas para el control del acceso de usuarios remotos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71f3a-159">Configure policies to control remote user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [<span data-ttu-id="71f3a-160">Configurar directivas para controlar el acceso de usuarios públicos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71f3a-160">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [<span data-ttu-id="71f3a-161">Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71f3a-161">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="71f3a-162">Restablecer o eliminar las directivas de acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71f3a-162">Resetting or deleting external user access policies in Lync Server 2013</span></span>](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

