---
title: 'Lync Server 2013: ver el estado de la configuración global de un bosque'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7922fe79d97a1fa83fdaa5afbc1eeddee8523e37
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535587"
---
# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="9cc22-102">Ver el estado de la configuración global de un bosque en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cc22-102">View status of global settings for a forest in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cc22-103">_**Última modificación del tema:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="9cc22-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="9cc22-104">Los administradores deben revisar la configuración global de una implementación de Lync Server 2013 mensualmente.</span><span class="sxs-lookup"><span data-stu-id="9cc22-104">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="9cc22-105">El objetivo sería revisar la configuración implementada con un conjunto de configuraciones conocidas, una configuración de línea base para ayudar a garantizar que la configuración sea válida y para determinar si se debe actualizar la documentación de línea base.</span><span class="sxs-lookup"><span data-stu-id="9cc22-105">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="9cc22-106">Los cambios en la configuración global deben implementarse a través de un proceso de control de cambio que debe incluir la documentación de la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="9cc22-106">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="9cc22-107">En las siguientes secciones se describen las opciones globales que deben revisarse:</span><span class="sxs-lookup"><span data-stu-id="9cc22-107">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="9cc22-108">Comprobar la configuración general</span><span class="sxs-lookup"><span data-stu-id="9cc22-108">Check general settings</span></span>

<span data-ttu-id="9cc22-109">Compruebe la configuración general, incluidos los dominios admitidos del Protocolo de inicio de sesión (SIP) para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9cc22-109">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="9cc22-110">La información del dominio SIP se puede devolver mediante Windows PowerShell y el cmdlet **Get-CsSipDomain** .</span><span class="sxs-lookup"><span data-stu-id="9cc22-110">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="9cc22-111">Para devolver esta información, ejecute el `Get-CsSipDomain` comando de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9cc22-111">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="9cc22-112">Get-CsSipDomain devolverá información similar a la siguiente para todos los dominios SIP autorizados:</span><span class="sxs-lookup"><span data-stu-id="9cc22-112">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="9cc22-113">Nombre de identidad IsDefault</span><span class="sxs-lookup"><span data-stu-id="9cc22-113">Identity Name IsDefault</span></span>

<span data-ttu-id="9cc22-114">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="9cc22-114">\-------- ---- ---------</span></span>

<span data-ttu-id="9cc22-115">fabrikam.com fabrikam.com true</span><span class="sxs-lookup"><span data-stu-id="9cc22-115">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="9cc22-116">na.fabrikam.com na.fabrikam.com false</span><span class="sxs-lookup"><span data-stu-id="9cc22-116">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="9cc22-117">Si la propiedad IsDefault se establece en true, el dominio correspondiente es su dominio SIP predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9cc22-117">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="9cc22-118">Puede usar el cmdlet Set-CsSipDomain para cambiar el dominio SIP predeterminado de su organización.</span><span class="sxs-lookup"><span data-stu-id="9cc22-118">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="9cc22-119">Sin embargo, no se puede eliminar simplemente el dominio SIP predeterminado, ya que esto le dejaría sin un dominio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9cc22-119">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="9cc22-120">Si deseara eliminar el dominio fabrikam.com (como se muestra en el ejemplo anterior), primero tendría que configurar na.fabrikam.com para que sea su dominio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9cc22-120">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="9cc22-121">Comprobar la configuración de la reunión</span><span class="sxs-lookup"><span data-stu-id="9cc22-121">Check meeting settings</span></span>

<span data-ttu-id="9cc22-122">La configuración de reunión incluye definiciones de directivas de reuniones y soporte para la participación de usuarios anónimos en reuniones.</span><span class="sxs-lookup"><span data-stu-id="9cc22-122">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="9cc22-123">Las opciones de configuración de reuniones se pueden recuperar con Windows PowerShell y el cmdlet **Get-CsMeetingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9cc22-123">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="9cc22-124">Por ejemplo, este comando devuelve información sobre las opciones de configuración de reunión global:</span><span class="sxs-lookup"><span data-stu-id="9cc22-124">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="9cc22-125">Get-CsMeetingConfiguration la identidad "global" las opciones de configuración de reuniones también se pueden configurar en el ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="9cc22-125">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="9cc22-126">Por ello, es posible que desee usar el siguiente comando, que devuelve información sobre todas las opciones de configuración de reuniones:</span><span class="sxs-lookup"><span data-stu-id="9cc22-126">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="9cc22-127">El cmdlet **Get-CsMeetingConfiguration** devuelve información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="9cc22-127">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="9cc22-128">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="9cc22-128">Identity : Global</span></span>

<span data-ttu-id="9cc22-129">PstnCallersBypassLobby: true</span><span class="sxs-lookup"><span data-stu-id="9cc22-129">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="9cc22-130">EnableAssignedConferenceType: true</span><span class="sxs-lookup"><span data-stu-id="9cc22-130">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="9cc22-131">DesignateAsPresenter: compañía</span><span class="sxs-lookup"><span data-stu-id="9cc22-131">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="9cc22-132">AssignedConferenceTypeByDefault: true</span><span class="sxs-lookup"><span data-stu-id="9cc22-132">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="9cc22-133">AdmitAnonymousUsersByDefault: true</span><span class="sxs-lookup"><span data-stu-id="9cc22-133">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="9cc22-134">De nuevo, el último elemento de la lista, **AdmitAnonymousUsersByDefault**, habilita o deshabilita la posibilidad de que los usuarios anónimos participen en las reuniones.</span><span class="sxs-lookup"><span data-stu-id="9cc22-134">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="9cc22-135">Al comprobar las opciones de configuración de reuniones, es posible que le resulte útil comparar la configuración actual con los equivalentes predeterminados.</span><span class="sxs-lookup"><span data-stu-id="9cc22-135">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="9cc22-136">Para ver las opciones de configuración de reunión predeterminadas, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9cc22-136">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="9cc22-137">El comando anterior crea una instancia de solo memoria de las opciones de configuración de reunión global, una instancia que usa el valor predeterminado para cada propiedad.</span><span class="sxs-lookup"><span data-stu-id="9cc22-137">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="9cc22-138">No se crea ninguna configuración de reunión real al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="9cc22-138">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="9cc22-139">Sin embargo, todos los valores de propiedad predeterminados se mostrarán en pantalla.</span><span class="sxs-lookup"><span data-stu-id="9cc22-139">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="9cc22-140">Comprobar los servidores perimetrales y su configuración</span><span class="sxs-lookup"><span data-stu-id="9cc22-140">Check Edge Servers and their settings</span></span>

<span data-ttu-id="9cc22-141">La información del servidor perimetral se puede recuperar con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9cc22-141">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="9cc22-142">Este comando devuelve información sobre todos los servidores perimetrales configurados para su uso en la organización:</span><span class="sxs-lookup"><span data-stu-id="9cc22-142">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="9cc22-143">La información devuelta incluye todo el FQDN y la configuración de puerto de cada servidor perimetral:</span><span class="sxs-lookup"><span data-stu-id="9cc22-143">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="9cc22-144">Identidad: EdgeServer: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9cc22-144">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="9cc22-145">Registrar: registrar: LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9cc22-145">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="9cc22-146">AccessEdgeInternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="9cc22-146">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="9cc22-147">AccessEdgeExternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="9cc22-147">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="9cc22-148">AccessEdgeClientPort: 443</span><span class="sxs-lookup"><span data-stu-id="9cc22-148">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="9cc22-149">DataPsomServerPort: 8057</span><span class="sxs-lookup"><span data-stu-id="9cc22-149">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="9cc22-150">DataPsomClientPort: 444</span><span class="sxs-lookup"><span data-stu-id="9cc22-150">DataPsomClientPort : 444</span></span>

<span data-ttu-id="9cc22-151">MediaRelayAuthEdgePort: 5062</span><span class="sxs-lookup"><span data-stu-id="9cc22-151">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="9cc22-152">MediaRelayAuthInternalTurnTcpPort: 443</span><span class="sxs-lookup"><span data-stu-id="9cc22-152">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="9cc22-153">MediaRelayAuthExternalTurnTcpPort: 445</span><span class="sxs-lookup"><span data-stu-id="9cc22-153">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="9cc22-154">MediaRelayAuthInternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="9cc22-154">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="9cc22-155">MediaRelayAuthExternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="9cc22-155">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="9cc22-156">MediaCommunicationPortStart: 50000</span><span class="sxs-lookup"><span data-stu-id="9cc22-156">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="9cc22-157">MediaComunicationPortCount: 10000</span><span class="sxs-lookup"><span data-stu-id="9cc22-157">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="9cc22-158">AccessEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9cc22-158">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="9cc22-159">DataEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9cc22-159">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="9cc22-160">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="9cc22-160">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="9cc22-161">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="9cc22-161">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="9cc22-162">ExternalMrasFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9cc22-162">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="9cc22-163">DependentServiceList: {registrar: LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="9cc22-163">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="9cc22-164">ConferencingServer: LYNC-SE. fabrikam</span><span class="sxs-lookup"><span data-stu-id="9cc22-164">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="9cc22-165">com, MediationServer: LYNC-SE.</span><span class="sxs-lookup"><span data-stu-id="9cc22-165">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="9cc22-166">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="9cc22-166">fabrikam.com}</span></span>

<span data-ttu-id="9cc22-167">ServiceId: fabrikam.com-EdgeServer-2</span><span class="sxs-lookup"><span data-stu-id="9cc22-167">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="9cc22-168">SiteId: sitio:fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="9cc22-168">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="9cc22-169">PoolFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9cc22-169">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="9cc22-170">Versión: 5</span><span class="sxs-lookup"><span data-stu-id="9cc22-170">Version : 5</span></span>

<span data-ttu-id="9cc22-171">Rol: EdgeServer</span><span class="sxs-lookup"><span data-stu-id="9cc22-171">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="9cc22-172">Comprobar la configuración de la Federación</span><span class="sxs-lookup"><span data-stu-id="9cc22-172">Check federation settings</span></span>

<span data-ttu-id="9cc22-173">Compruebe la configuración de la Federación, por ejemplo si está configurada y, si la respuesta es "sí", el nombre de dominio completo y el puerto.</span><span class="sxs-lookup"><span data-stu-id="9cc22-173">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="9cc22-174">La Federación se habilita y deshabilita mediante el uso de la colección global de opciones de configuración perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="9cc22-174">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="9cc22-175">Entre otras cosas, esto significa que la Federación está configurada en todo o nada: la Federación está habilitada para toda la organización o la Federación está deshabilitada para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="9cc22-175">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="9cc22-176">Las opciones de configuración perimetral de acceso se pueden devolver mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9cc22-176">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="9cc22-177">Para ello, ejecute el siguiente comando de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9cc22-177">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="9cc22-178">A su vez, ese comando devolverá datos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="9cc22-178">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="9cc22-179">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="9cc22-179">Identity : Global</span></span>

<span data-ttu-id="9cc22-180">AllowAnonymousUsers: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-180">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="9cc22-181">AllowFederatedUsers: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-181">AllowFederatedUsers : False</span></span>

<span data-ttu-id="9cc22-182">AllowOutsideUsers: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-182">AllowOutsideUsers : False</span></span>

<span data-ttu-id="9cc22-183">BeClearingHouse: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-183">BeClearingHouse : False</span></span>

<span data-ttu-id="9cc22-184">EnablePartnerDiscovery: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-184">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="9cc22-185">EnableArchivingDisclaimer: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-185">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="9cc22-186">KeepCrlsUpToDateForPeers: true</span><span class="sxs-lookup"><span data-stu-id="9cc22-186">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="9cc22-187">MarkSourceVerifiableOnOutgoingMessages: true</span><span class="sxs-lookup"><span data-stu-id="9cc22-187">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="9cc22-188">OutgoingTlsCountForFederatedPartners: 4</span><span class="sxs-lookup"><span data-stu-id="9cc22-188">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="9cc22-189">RoutingMethod: UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="9cc22-189">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="9cc22-190">Si la propiedad **AllowFederatedUsers** está establecida en true, significa que la Federación está habilitada para su organización.</span><span class="sxs-lookup"><span data-stu-id="9cc22-190">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="9cc22-191">(Si se establece **AllowFederatedUsers** en true, también significa que, en un escenario de dominio dividido, los usuarios locales podrán comunicarse sin problemas con los usuarios de la nube).</span><span class="sxs-lookup"><span data-stu-id="9cc22-191">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="9cc22-192">Para recuperar el FQDN y la configuración del puerto para el servidor perimetral, vea la tarea anterior (servidores perimetrales y su configuración).</span><span class="sxs-lookup"><span data-stu-id="9cc22-192">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="9cc22-193">Habilitar la Federación solo en el ámbito global significa que los usuarios pueden comunicarse potencialmente con usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="9cc22-193">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="9cc22-194">Para determinar si los usuarios individuales pueden comunicarse realmente con los usuarios federados, es necesario que examine la Directiva de acceso de usuarios externos asignada a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="9cc22-194">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="9cc22-195">La información de acceso de usuarios externos se puede devolver mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9cc22-195">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="9cc22-196">Por ejemplo, este comando devuelve información de la Directiva de acceso de usuario externo global:</span><span class="sxs-lookup"><span data-stu-id="9cc22-196">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="9cc22-197">Y este comando devuelve información de todas las directivas de acceso de usuarios externos:</span><span class="sxs-lookup"><span data-stu-id="9cc22-197">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="9cc22-198">La información devuelta será similar a esta:</span><span class="sxs-lookup"><span data-stu-id="9cc22-198">The returned information will resemble this:</span></span>

<span data-ttu-id="9cc22-199">Identidad: falso</span><span class="sxs-lookup"><span data-stu-id="9cc22-199">Identity : False</span></span>

<span data-ttu-id="9cc22-200">Descriptiva</span><span class="sxs-lookup"><span data-stu-id="9cc22-200">Description :</span></span>

<span data-ttu-id="9cc22-201">EnableFederationAccess: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-201">EnableFederationAccess : False</span></span>

<span data-ttu-id="9cc22-202">EnablePublicCloudAccess: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-202">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="9cc22-203">EnablePublicCloudAccessAudioVideoAccess: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-203">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="9cc22-204">EnableOutsideAccess: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-204">EnableOutsideAccess : False</span></span>

<span data-ttu-id="9cc22-205">Si **EnableFederationAccess** se establece en true, los usuarios administrados por la directiva determinada podrán comunicarse con los usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="9cc22-205">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="9cc22-206">Comprobar la configuración de archivado</span><span class="sxs-lookup"><span data-stu-id="9cc22-206">Check archiving settings</span></span>

<span data-ttu-id="9cc22-207">Compruebe la configuración de archivado para las comunicaciones internas y federadas. Antes de comprobar la configuración de la archivación interna y externa, debe comprobar que el archivado esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="9cc22-207">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="9cc22-208">Las opciones de configuración de archivado se pueden comprobar mediante Windows PowerShell y el cmdlet Get-CsArchivingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="9cc22-208">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="9cc22-209">Tenga en cuenta que la configuración de archivado también se puede configurar en el ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="9cc22-209">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="9cc22-210">Para devolver información acerca de toda la configuración de archivado, use este comando:</span><span class="sxs-lookup"><span data-stu-id="9cc22-210">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="9cc22-211">El cmdlet Get-CsArchivingConfiguration devuelve datos similares a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9cc22-211">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="9cc22-212">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="9cc22-212">Identity : Global</span></span>

<span data-ttu-id="9cc22-213">EnableArchiving: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-213">EnableArchiving : False</span></span>

<span data-ttu-id="9cc22-214">EnablePurging: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-214">EnablePurging : False</span></span>

<span data-ttu-id="9cc22-215">PurgeExportedArchivesOnly: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-215">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="9cc22-216">BlockOnArchiveFailure: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-216">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="9cc22-217">KeepArchivingDataForDays: 14</span><span class="sxs-lookup"><span data-stu-id="9cc22-217">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="9cc22-218">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="9cc22-218">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="9cc22-219">ArchiveDuplicateMessages: true</span><span class="sxs-lookup"><span data-stu-id="9cc22-219">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="9cc22-220">Cachepurgeinterval: 24</span><span class="sxs-lookup"><span data-stu-id="9cc22-220">CachePurgingInterval : 24</span></span>

<span data-ttu-id="9cc22-221">Si la propiedad EnableArchiving está establecida en false, significa que no se archivará ninguna sesión de comunicación.</span><span class="sxs-lookup"><span data-stu-id="9cc22-221">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="9cc22-222">Si sólo desea archivar sesiones de mensajería instantánea, use un comando como el siguiente para habilitar el archivado de sesiones de mensajería instantánea:</span><span class="sxs-lookup"><span data-stu-id="9cc22-222">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="9cc22-223">Para archivar sesiones de conferencia y sesiones de mensajería instantánea, use este comando:</span><span class="sxs-lookup"><span data-stu-id="9cc22-223">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="9cc22-224">Si quiere comparar la configuración de archivado actual con la configuración predeterminada, ejecute el siguiente comando de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9cc22-224">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="9cc22-225">Ese comando crea una instancia de solo memoria de las opciones de configuración de archivado global.</span><span class="sxs-lookup"><span data-stu-id="9cc22-225">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="9cc22-226">No es una colección real de opciones de configuración que usa Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9cc22-226">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="9cc22-227">Sin embargo, muestra los valores predeterminados de todas las propiedades de configuración de archivado.</span><span class="sxs-lookup"><span data-stu-id="9cc22-227">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="9cc22-228">También puede usar este comando para devolver el FQDN de los servidores de archivado:</span><span class="sxs-lookup"><span data-stu-id="9cc22-228">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="9cc22-229">Una vez que haya comprobado que el archivado está habilitado, puede ver las directivas de archivado para determinar si las sesiones de comunicación internas y externas se archivan.</span><span class="sxs-lookup"><span data-stu-id="9cc22-229">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="9cc22-230">La información de la Directiva de archivado se puede recuperar con el cmdlet Get-CsArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="9cc22-230">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="9cc22-231">Por ejemplo, este comando devuelve información sobre la Directiva de archivado global:</span><span class="sxs-lookup"><span data-stu-id="9cc22-231">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="9cc22-232">Como las directivas de archivado también se pueden configurar en el sitio y el ámbito por usuario, es posible que también desee usar este comando, que devuelve información sobre todas las directivas de archivado:</span><span class="sxs-lookup"><span data-stu-id="9cc22-232">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="9cc22-233">La información que recibe de Get-CsArchivingPolicy será similar a esta:</span><span class="sxs-lookup"><span data-stu-id="9cc22-233">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="9cc22-234">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="9cc22-234">Identity : Global</span></span>

<span data-ttu-id="9cc22-235">Descriptiva</span><span class="sxs-lookup"><span data-stu-id="9cc22-235">Description :</span></span>

<span data-ttu-id="9cc22-236">ArchiveInternal: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-236">ArchiveInternal : False</span></span>

<span data-ttu-id="9cc22-237">ArchiveExternal: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-237">ArchiveExternal : False</span></span>

<span data-ttu-id="9cc22-238">Tenga en cuenta que, de forma predeterminada, los archivados internos y externos están deshabilitados en una directiva de archivado.</span><span class="sxs-lookup"><span data-stu-id="9cc22-238">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="9cc22-239">Comprobar la configuración de CDR</span><span class="sxs-lookup"><span data-stu-id="9cc22-239">Check CDR settings</span></span>

<span data-ttu-id="9cc22-240">Compruebe la configuración de registro de detalles de llamadas (CDR) para el registro detallado de llamadas de voz, de conferencia y de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="9cc22-240">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="9cc22-241">Se puede devolver información detallada sobre la configuración de CDR mediante el cmdlet **Get-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9cc22-241">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="9cc22-242">Por ejemplo, este comando devuelve información sobre la colección global de opciones de configuración de CDR:</span><span class="sxs-lookup"><span data-stu-id="9cc22-242">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="9cc22-243">Como CDR también se puede configurar en el ámbito de sitio, es posible que también desee ejecutar este comando, que devuelve información sobre todas las opciones de configuración de CDR:</span><span class="sxs-lookup"><span data-stu-id="9cc22-243">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="9cc22-244">El cmdlet Get-CsCdrConfiguration devuelve información similar a la siguiente para cada colección de opciones de configuración de CDR:</span><span class="sxs-lookup"><span data-stu-id="9cc22-244">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="9cc22-245">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="9cc22-245">Identity : Global</span></span>

<span data-ttu-id="9cc22-246">EnableCDR: true</span><span class="sxs-lookup"><span data-stu-id="9cc22-246">EnableCDR : True</span></span>

<span data-ttu-id="9cc22-247">EnablePurging: true</span><span class="sxs-lookup"><span data-stu-id="9cc22-247">EnablePurging : True</span></span>

<span data-ttu-id="9cc22-248">KeepCallDetailForDays: 60</span><span class="sxs-lookup"><span data-stu-id="9cc22-248">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="9cc22-249">KeepErrorReportForDays: 60</span><span class="sxs-lookup"><span data-stu-id="9cc22-249">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="9cc22-250">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="9cc22-250">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="9cc22-251">Se puede devolver información similar para la supervisión de QoE mediante el cmdlet Get-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9cc22-251">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="9cc22-252">Por ejemplo, este comando devuelve información sobre la colección global de opciones de configuración de QoE:</span><span class="sxs-lookup"><span data-stu-id="9cc22-252">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="9cc22-253">Esta información será similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="9cc22-253">That information will resemble this:</span></span>

<span data-ttu-id="9cc22-254">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="9cc22-254">Identity : Global</span></span>

<span data-ttu-id="9cc22-255">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="9cc22-255">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="9cc22-256">EnablePurging: true</span><span class="sxs-lookup"><span data-stu-id="9cc22-256">EnablePurging : True</span></span>

<span data-ttu-id="9cc22-257">KeepQoEDataForDays: 60</span><span class="sxs-lookup"><span data-stu-id="9cc22-257">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="9cc22-258">PurgeHourOfDay: 1</span><span class="sxs-lookup"><span data-stu-id="9cc22-258">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="9cc22-259">EnableExternalConsumer: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-259">EnableExternalConsumer : False</span></span>

<span data-ttu-id="9cc22-260">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="9cc22-260">ExternalConsumerName :</span></span>

<span data-ttu-id="9cc22-261">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="9cc22-261">ExternalConsumerURL :</span></span>

<span data-ttu-id="9cc22-262">EnableQoE: true</span><span class="sxs-lookup"><span data-stu-id="9cc22-262">EnableQoE : True</span></span>

<span data-ttu-id="9cc22-263">Si desea comparar la configuración actual de CDR con la configuración predeterminada de CDR, puede revisar los valores predeterminados mediante la ejecución de este comando:</span><span class="sxs-lookup"><span data-stu-id="9cc22-263">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="9cc22-264">Del mismo modo, los valores predeterminados para la supervisión de QoE se pueden recuperar con este comando:</span><span class="sxs-lookup"><span data-stu-id="9cc22-264">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="9cc22-265">También puede devolver el FQDN de los servidores de supervisión mediante la ejecución de este comando:</span><span class="sxs-lookup"><span data-stu-id="9cc22-265">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="9cc22-266">Comprobar la configuración de voz</span><span class="sxs-lookup"><span data-stu-id="9cc22-266">Check voice settings</span></span>

<span data-ttu-id="9cc22-267">La configuración de voz suele ser importante para los administradores en las directivas de voz y rutas de voz: las directivas de voz contienen la configuración que determina las capacidades que se exponen a los usuarios individuales (como la capacidad de desviar o transferir las llamadas), mientras que las rutas de voz determinan cómo se enrutan las llamadas (y si) a través de la RTC.</span><span class="sxs-lookup"><span data-stu-id="9cc22-267">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="9cc22-268">La información de la Directiva de voz se puede recuperar con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9cc22-268">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="9cc22-269">Por ejemplo, este comando devuelve información sobre la Directiva de voz global:</span><span class="sxs-lookup"><span data-stu-id="9cc22-269">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="9cc22-270">Y este comando devuelve información sobre todas las directivas de voz configuradas para su uso en la organización:</span><span class="sxs-lookup"><span data-stu-id="9cc22-270">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="9cc22-271">La información devuelta por el cmdlet Get-CsVoicePolicy es similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="9cc22-271">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="9cc22-272">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="9cc22-272">Identity : Global</span></span>

<span data-ttu-id="9cc22-273">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="9cc22-273">PstnUsages : {}</span></span>

<span data-ttu-id="9cc22-274">Descriptiva</span><span class="sxs-lookup"><span data-stu-id="9cc22-274">Description :</span></span>

<span data-ttu-id="9cc22-275">AllowSimulRing: true</span><span class="sxs-lookup"><span data-stu-id="9cc22-275">AllowSimulRing : True</span></span>

<span data-ttu-id="9cc22-276">AllowCallForwarding: true</span><span class="sxs-lookup"><span data-stu-id="9cc22-276">AllowCallForwarding : True</span></span>

<span data-ttu-id="9cc22-277">AllowPSTNReRouting: true</span><span class="sxs-lookup"><span data-stu-id="9cc22-277">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="9cc22-278">Nombre: DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="9cc22-278">Name : DefaultPolicy</span></span>

<span data-ttu-id="9cc22-279">EnableDelegation: true</span><span class="sxs-lookup"><span data-stu-id="9cc22-279">EnableDelegation : True</span></span>

<span data-ttu-id="9cc22-280">EnableTeamCall: true</span><span class="sxs-lookup"><span data-stu-id="9cc22-280">EnableTeamCall : True</span></span>

<span data-ttu-id="9cc22-281">EnableCallTransfer: true</span><span class="sxs-lookup"><span data-stu-id="9cc22-281">EnableCallTransfer : True</span></span>

<span data-ttu-id="9cc22-282">EnableCallPark: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-282">EnableCallPark : False</span></span>

<span data-ttu-id="9cc22-283">EnableMaliciousCallTracing: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-283">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="9cc22-284">EnableBWPolicyOverride: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-284">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="9cc22-285">PreventPSTNTollBypass: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-285">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="9cc22-286">También puede crear consultas que devuelvan un subconjunto de las directivas de voz.</span><span class="sxs-lookup"><span data-stu-id="9cc22-286">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="9cc22-287">Por ejemplo, este comando devuelve todas las directivas de voz que permiten el desvío de llamadas:</span><span class="sxs-lookup"><span data-stu-id="9cc22-287">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="9cc22-288">Y este comando devuelve todas las directivas de voz que no permiten el desvío de llamadas:</span><span class="sxs-lookup"><span data-stu-id="9cc22-288">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="9cc22-289">En Windows PowerShell, use el cmdlet Get-CsVoiceRouting para devolver información sobre las rutas de voz:</span><span class="sxs-lookup"><span data-stu-id="9cc22-289">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="9cc22-290">Este comando devuelve información como esta para todas las rutas de voz:</span><span class="sxs-lookup"><span data-stu-id="9cc22-290">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="9cc22-291">Identidad: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="9cc22-291">Identity : LocalRoute</span></span>

<span data-ttu-id="9cc22-292">Prioridad: 0</span><span class="sxs-lookup"><span data-stu-id="9cc22-292">Priority : 0</span></span>

<span data-ttu-id="9cc22-293">Descriptiva</span><span class="sxs-lookup"><span data-stu-id="9cc22-293">Description :</span></span>

<span data-ttu-id="9cc22-294">NumberPattern: ^ ( \\ + 1 \[ 0-9 \] {10} ) $</span><span class="sxs-lookup"><span data-stu-id="9cc22-294">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="9cc22-295">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="9cc22-295">PstnUsages : {}</span></span>

<span data-ttu-id="9cc22-296">PstnGatewayList : {}</span><span class="sxs-lookup"><span data-stu-id="9cc22-296">PstnGatewayList : {}</span></span>

<span data-ttu-id="9cc22-297">Nombre: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="9cc22-297">Name : LocalRoute</span></span>

<span data-ttu-id="9cc22-298">SuppressCallerId</span><span class="sxs-lookup"><span data-stu-id="9cc22-298">SuppressCallerId :</span></span>

<span data-ttu-id="9cc22-299">AlternateCallerId</span><span class="sxs-lookup"><span data-stu-id="9cc22-299">AlternateCallerId :</span></span>

<span data-ttu-id="9cc22-300">Lync Server le permite crear rutas de voz que no tienen un uso de RTC y no especifican una puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="9cc22-300">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="9cc22-301">Sin embargo, en realidad no puede enrutar las llamadas a través de una ruta de voz que no tenga estos dos valores de propiedad configurados.</span><span class="sxs-lookup"><span data-stu-id="9cc22-301">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="9cc22-302">Por ello, es posible que le resulte útil ejecutar periódicamente este comando, que devuelve la identidad de cualquier ruta de voz que no tenga uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="9cc22-302">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="9cc22-303">De forma similar, este comando devuelve la identidad de cualquier ruta de voz que no se haya configurado para tener una puerta de enlace RTC:</span><span class="sxs-lookup"><span data-stu-id="9cc22-303">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="9cc22-304">Comprobar la configuración del operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="9cc22-304">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="9cc22-305">Compruebe la configuración del operador de conferencia para las conferencias de acceso telefónico local RTC.</span><span class="sxs-lookup"><span data-stu-id="9cc22-305">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="9cc22-306">La configuración del operador de conferencia solo puede recuperarse con el cmdlet **Get-CsDialInConferencingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9cc22-306">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="9cc22-307">Esta configuración no está disponible en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9cc22-307">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="9cc22-308">Para ver la configuración del operador de conferencia, use un comando de Windows PowerShell similar al siguiente, que devuelve la colección global de opciones de configuración del operador de Conferencia:</span><span class="sxs-lookup"><span data-stu-id="9cc22-308">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="9cc22-309">Tenga en cuenta que la configuración del operador de conferencia también se puede configurar en el ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="9cc22-309">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="9cc22-310">Para obtener información acerca de todas las opciones de configuración del operador de conferencia, use este comando en su lugar:</span><span class="sxs-lookup"><span data-stu-id="9cc22-310">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="9cc22-311">El cmdlet Get-CsDialInConferencingConfiguration devuelve datos similares a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9cc22-311">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="9cc22-312">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="9cc22-312">Identity : Global</span></span>

<span data-ttu-id="9cc22-313">EntryExitAnnouncementsType: UseNames</span><span class="sxs-lookup"><span data-stu-id="9cc22-313">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="9cc22-314">EnableNameRecording: true</span><span class="sxs-lookup"><span data-stu-id="9cc22-314">EnableNameRecording : True</span></span>

<span data-ttu-id="9cc22-315">EntryExitAnnouncementsEnabledByDefault: false</span><span class="sxs-lookup"><span data-stu-id="9cc22-315">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="9cc22-316">Si EntryExitAnnouncementsEnabledByDefault se establece en false, significa que los anuncios de conferencia están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="9cc22-316">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="9cc22-317">Para habilitar los anuncios de entrada y salida, ejecute un comando de Windows PowerShell similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="9cc22-317">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9cc22-318">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9cc22-318">See Also</span></span>


[<span data-ttu-id="9cc22-319">Get-CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="9cc22-319">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="9cc22-320">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9cc22-320">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="9cc22-321">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="9cc22-321">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="9cc22-322">Get-CsAccessEdgeConfiguration</span><span class="sxs-lookup"><span data-stu-id="9cc22-322">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="9cc22-323">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="9cc22-323">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="9cc22-324">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9cc22-324">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="9cc22-325">Get-CsCdrConfiguration</span><span class="sxs-lookup"><span data-stu-id="9cc22-325">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="9cc22-326">Get-CsQoEConfiguration</span><span class="sxs-lookup"><span data-stu-id="9cc22-326">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="9cc22-327">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="9cc22-327">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="9cc22-328">Get-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="9cc22-328">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="9cc22-329">Get-CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9cc22-329">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

