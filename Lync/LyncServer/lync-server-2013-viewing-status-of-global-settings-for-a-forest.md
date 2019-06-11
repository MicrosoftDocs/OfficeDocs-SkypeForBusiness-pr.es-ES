---
title: 'Lync Server 2013: visualización del estado de la configuración global de un bosque'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2215e0514f019e94467a204ae86e604dcc0da61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="e0f59-102">Ver el estado de la configuración global de un bosque en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0f59-102">View status of global settings for a forest in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0f59-103">_**Última modificación del tema:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="e0f59-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="e0f59-104">Los administradores deben revisar la configuración global de una implementación de Lync Server 2013 mensualmente.</span><span class="sxs-lookup"><span data-stu-id="e0f59-104">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="e0f59-105">El objetivo sería revisar la configuración implementada con un conjunto de configuraciones conocidas, una configuración de línea base para ayudar a garantizar que la configuración sea válida y para determinar si se debe actualizar la documentación de línea base.</span><span class="sxs-lookup"><span data-stu-id="e0f59-105">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="e0f59-106">Los cambios en la configuración global deben implementarse a través de un proceso de control de cambio que debe incluir la documentación de la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="e0f59-106">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="e0f59-107">La configuración global que debe revisarse se describe en las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e0f59-107">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="e0f59-108">Comprobar la configuración general</span><span class="sxs-lookup"><span data-stu-id="e0f59-108">Check general settings</span></span>

<span data-ttu-id="e0f59-109">Compruebe la configuración general, incluidos los dominios del Protocolo de inicio de sesión (SIP) compatibles con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0f59-109">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="e0f59-110">La información del dominio SIP se puede devolver mediante Windows PowerShell y el cmdlet **Get-CsSipDomain** .</span><span class="sxs-lookup"><span data-stu-id="e0f59-110">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="e0f59-111">Para devolver esta información, ejecute el `Get-CsSipDomain` comando de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0f59-111">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="e0f59-112">Get-CsSipDomain devolverá información similar a esta para todos los dominios SIP autorizados:</span><span class="sxs-lookup"><span data-stu-id="e0f59-112">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="e0f59-113">Nombre de identidad IsDefault</span><span class="sxs-lookup"><span data-stu-id="e0f59-113">Identity Name IsDefault</span></span>

<span data-ttu-id="e0f59-114">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="e0f59-114"></span></span>

<span data-ttu-id="e0f59-115">fabrikam.com fabrikam.com verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-115">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="e0f59-116">na.fabrikam.com na.fabrikam.com falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-116">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="e0f59-117">Si la propiedad IsDefault se establece en true, el dominio correspondiente es su dominio SIP predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e0f59-117">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="e0f59-118">Puede usar el cmdlet Set-CsSipDomain para cambiar el dominio SIP predeterminado de su organización.</span><span class="sxs-lookup"><span data-stu-id="e0f59-118">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="e0f59-119">Sin embargo, no puede eliminar simplemente el dominio SIP predeterminado porque le dejaría sin un dominio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e0f59-119">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="e0f59-120">Si desea eliminar el dominio fabrikam.com (tal como se muestra en el ejemplo anterior), primero deberá configurar na.fabrikam.com para que sea su dominio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e0f59-120">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="e0f59-121">Comprobar la configuración de la reunión</span><span class="sxs-lookup"><span data-stu-id="e0f59-121">Check meeting settings</span></span>

<span data-ttu-id="e0f59-122">La configuración de la reunión incluye definiciones de la Directiva de reunión y soporte técnico para la participación de usuarios anónimos en reuniones.</span><span class="sxs-lookup"><span data-stu-id="e0f59-122">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="e0f59-123">La configuración de la reunión se puede recuperar mediante Windows PowerShell y el cmdlet **Get-CsMeetingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="e0f59-123">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="e0f59-124">Por ejemplo, este comando devuelve información acerca de la configuración global de la reunión:</span><span class="sxs-lookup"><span data-stu-id="e0f59-124">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="e0f59-125">Las opciones de configuración de reunión "globales" de Get-CsMeetingConfiguration también se pueden configurar en el ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="e0f59-125">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="e0f59-126">Por eso, es posible que desee usar el siguiente comando, que devuelve información acerca de todas las opciones de configuración de la reunión:</span><span class="sxs-lookup"><span data-stu-id="e0f59-126">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="e0f59-127">El cmdlet **Get-CsMeetingConfiguration** devuelve información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="e0f59-127">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="e0f59-128">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="e0f59-128">Identity : Global</span></span>

<span data-ttu-id="e0f59-129">PstnCallersBypassLobby: verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-129">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="e0f59-130">EnableAssignedConferenceType: verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-130">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="e0f59-131">DesignateAsPresenter: compañía</span><span class="sxs-lookup"><span data-stu-id="e0f59-131">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="e0f59-132">AssignedConferenceTypeByDefault: verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-132">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="e0f59-133">AdmitAnonymousUsersByDefault: verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-133">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="e0f59-134">De nuevo, el último elemento de la lista, **AdmitAnonymousUsersByDefault**, habilita o deshabilita la posibilidad de que los usuarios anónimos participen en reuniones.</span><span class="sxs-lookup"><span data-stu-id="e0f59-134">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="e0f59-135">Al comprobar la configuración de la reunión, es posible que le resulte útil comparar la configuración actual con los equivalentes predeterminados.</span><span class="sxs-lookup"><span data-stu-id="e0f59-135">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="e0f59-136">Para ver la configuración de la reunión predeterminada, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e0f59-136">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="e0f59-137">El comando anterior crea una instancia en memoria únicamente de la configuración de la reunión global, una instancia que usa el valor predeterminado para cada propiedad.</span><span class="sxs-lookup"><span data-stu-id="e0f59-137">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="e0f59-138">No se crean valores de configuración de reuniones reales al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="e0f59-138">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="e0f59-139">Sin embargo, todos los valores de propiedad predeterminados se mostrarán en pantalla.</span><span class="sxs-lookup"><span data-stu-id="e0f59-139">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="e0f59-140">Comprobar los servidores perimetrales y su configuración</span><span class="sxs-lookup"><span data-stu-id="e0f59-140">Check Edge Servers and their settings</span></span>

<span data-ttu-id="e0f59-141">La información del servidor perimetral se puede recuperar mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0f59-141">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="e0f59-142">Este comando devuelve información acerca de todos los servidores perimetrales configurados para su uso en su organización:</span><span class="sxs-lookup"><span data-stu-id="e0f59-142">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="e0f59-143">La información devuelta incluye todo el FQDN y la configuración de puerto de cada servidor perimetral:</span><span class="sxs-lookup"><span data-stu-id="e0f59-143">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="e0f59-144">Identidad: EdgeServer: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="e0f59-144">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="e0f59-145">Registrar: registrar: LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="e0f59-145">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="e0f59-146">AccessEdgeInternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="e0f59-146">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="e0f59-147">AccessEdgeExternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="e0f59-147">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="e0f59-148">AccessEdgeClientPort: 443</span><span class="sxs-lookup"><span data-stu-id="e0f59-148">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="e0f59-149">DataPsomServerPort: 8057</span><span class="sxs-lookup"><span data-stu-id="e0f59-149">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="e0f59-150">DataPsomClientPort: 444</span><span class="sxs-lookup"><span data-stu-id="e0f59-150">DataPsomClientPort : 444</span></span>

<span data-ttu-id="e0f59-151">MediaRelayAuthEdgePort: 5062</span><span class="sxs-lookup"><span data-stu-id="e0f59-151">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="e0f59-152">MediaRelayAuthInternalTurnTcpPort: 443</span><span class="sxs-lookup"><span data-stu-id="e0f59-152">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="e0f59-153">MediaRelayAuthExternalTurnTcpPort: 445</span><span class="sxs-lookup"><span data-stu-id="e0f59-153">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="e0f59-154">MediaRelayAuthInternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="e0f59-154">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="e0f59-155">MediaRelayAuthExternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="e0f59-155">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="e0f59-156">MediaCommunicationPortStart: 50000</span><span class="sxs-lookup"><span data-stu-id="e0f59-156">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="e0f59-157">MediaComunicationPortCount: 10000</span><span class="sxs-lookup"><span data-stu-id="e0f59-157">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="e0f59-158">AccessEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="e0f59-158">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="e0f59-159">DataEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="e0f59-159">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="e0f59-160">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="e0f59-160">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="e0f59-161">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="e0f59-161">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="e0f59-162">ExternalMrasFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="e0f59-162">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="e0f59-163">DependentServiceList: {registrar: LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="e0f59-163">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="e0f59-164">ConferencingServer: LYNC-SE. fabrikam</span><span class="sxs-lookup"><span data-stu-id="e0f59-164">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="e0f59-165">com, MediationServer: LYNC-SE.</span><span class="sxs-lookup"><span data-stu-id="e0f59-165">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="e0f59-166">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="e0f59-166">fabrikam.com}</span></span>

<span data-ttu-id="e0f59-167">ServiceId: fabrikam.com-EdgeServer-2</span><span class="sxs-lookup"><span data-stu-id="e0f59-167">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="e0f59-168">SiteId: sitio:fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="e0f59-168">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="e0f59-169">PoolFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="e0f59-169">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="e0f59-170">Versión: 5</span><span class="sxs-lookup"><span data-stu-id="e0f59-170">Version : 5</span></span>

<span data-ttu-id="e0f59-171">Rol: EdgeServer</span><span class="sxs-lookup"><span data-stu-id="e0f59-171">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="e0f59-172">Comprobar la configuración de la Federación</span><span class="sxs-lookup"><span data-stu-id="e0f59-172">Check federation settings</span></span>

<span data-ttu-id="e0f59-173">Compruebe la configuración de la Federación, como si está configurada y, si la respuesta es "sí", el FQDN y el puerto.</span><span class="sxs-lookup"><span data-stu-id="e0f59-173">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="e0f59-174">La Federación se habilita y deshabilita mediante la recopilación global de la configuración de los límites de acceso.</span><span class="sxs-lookup"><span data-stu-id="e0f59-174">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="e0f59-175">Entre otras cosas, esto significa que la Federación está configurada de forma todo o nada: la Federación está habilitada para toda la organización o la Federación está deshabilitada para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="e0f59-175">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="e0f59-176">La configuración de la configuración perimetral de Access se puede devolver mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0f59-176">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="e0f59-177">Para ello, ejecute el siguiente comando de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e0f59-177">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="e0f59-178">A su vez, ese comando devolverá datos similares a este:</span><span class="sxs-lookup"><span data-stu-id="e0f59-178">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="e0f59-179">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="e0f59-179">Identity : Global</span></span>

<span data-ttu-id="e0f59-180">AllowAnonymousUsers: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-180">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="e0f59-181">AllowFederatedUsers: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-181">AllowFederatedUsers : False</span></span>

<span data-ttu-id="e0f59-182">AllowOutsideUsers: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-182">AllowOutsideUsers : False</span></span>

<span data-ttu-id="e0f59-183">BeClearingHouse: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-183">BeClearingHouse : False</span></span>

<span data-ttu-id="e0f59-184">EnablePartnerDiscovery: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-184">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="e0f59-185">EnableArchivingDisclaimer: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-185">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="e0f59-186">KeepCrlsUpToDateForPeers: verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-186">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="e0f59-187">MarkSourceVerifiableOnOutgoingMessages: verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-187">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="e0f59-188">OutgoingTlsCountForFederatedPartners: 4</span><span class="sxs-lookup"><span data-stu-id="e0f59-188">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="e0f59-189">RoutingMethod : UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="e0f59-189">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="e0f59-190">Si la propiedad **AllowFederatedUsers** se establece en true, significa que la Federación está habilitada para su organización.</span><span class="sxs-lookup"><span data-stu-id="e0f59-190">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="e0f59-191">(Al establecer **AllowFederatedUsers** en true, también significa que, en un escenario de dominio dividido, los usuarios locales podrán comunicarse sin problemas con los usuarios de la nube).</span><span class="sxs-lookup"><span data-stu-id="e0f59-191">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="e0f59-192">Para recuperar el FQDN y la configuración del puerto de su servidor perimetral, consulte la tarea anterior (servidores perimetrales y su configuración).</span><span class="sxs-lookup"><span data-stu-id="e0f59-192">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="e0f59-193">Habilitar la Federación solo en el ámbito global significa que los usuarios pueden comunicarse potencialmente con usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="e0f59-193">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="e0f59-194">Para determinar si los usuarios individuales pueden comunicarse realmente con los usuarios federados, debe examinar la Directiva de acceso de usuarios externos asignada a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="e0f59-194">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="e0f59-195">La información de acceso de usuarios externos se puede devolver mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0f59-195">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="e0f59-196">Por ejemplo, este comando devuelve información para la Directiva de acceso de usuario externo global:</span><span class="sxs-lookup"><span data-stu-id="e0f59-196">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="e0f59-197">Y este comando devuelve información para todas las directivas de acceso de usuarios externos:</span><span class="sxs-lookup"><span data-stu-id="e0f59-197">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="e0f59-198">La información devuelta tendrá este aspecto:</span><span class="sxs-lookup"><span data-stu-id="e0f59-198">The returned information will resemble this:</span></span>

<span data-ttu-id="e0f59-199">Identidad: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-199">Identity : False</span></span>

<span data-ttu-id="e0f59-200">Texto</span><span class="sxs-lookup"><span data-stu-id="e0f59-200">Description :</span></span>

<span data-ttu-id="e0f59-201">EnableFederationAccess: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-201">EnableFederationAccess : False</span></span>

<span data-ttu-id="e0f59-202">EnablePublicCloudAccess: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-202">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="e0f59-203">EnablePublicCloudAccessAudioVideoAccess: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-203">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="e0f59-204">EnableOutsideAccess: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-204">EnableOutsideAccess : False</span></span>

<span data-ttu-id="e0f59-205">Si **EnableFederationAccess** se establece en true, los usuarios administrados por la directiva determinada pueden comunicarse con los usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="e0f59-205">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="e0f59-206">Comprobar la configuración de archivado</span><span class="sxs-lookup"><span data-stu-id="e0f59-206">Check archiving settings</span></span>

<span data-ttu-id="e0f59-207">Comprobar la configuración de archivado de las comunicaciones internas y federadas. Antes de comprobar la configuración de los archivados internos y externos, debe comprobar que el archivado está habilitado.</span><span class="sxs-lookup"><span data-stu-id="e0f59-207">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="e0f59-208">Las opciones de configuración de archivado se pueden comprobar mediante Windows PowerShell y el cmdlet Get-CsArchivingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="e0f59-208">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="e0f59-209">Tenga en cuenta que la configuración de archivado también se puede configurar en el ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="e0f59-209">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="e0f59-210">Para obtener información acerca de toda la configuración de archivado, use este comando:</span><span class="sxs-lookup"><span data-stu-id="e0f59-210">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="e0f59-211">El cmdlet Get-CsArchivingConfiguration devuelve datos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="e0f59-211">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="e0f59-212">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="e0f59-212">Identity : Global</span></span>

<span data-ttu-id="e0f59-213">EnableArchiving: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-213">EnableArchiving : False</span></span>

<span data-ttu-id="e0f59-214">EnablePurging: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-214">EnablePurging : False</span></span>

<span data-ttu-id="e0f59-215">PurgeExportedArchivesOnly: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-215">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="e0f59-216">BlockOnArchiveFailure: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-216">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="e0f59-217">KeepArchivingDataForDays: 14</span><span class="sxs-lookup"><span data-stu-id="e0f59-217">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="e0f59-218">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="e0f59-218">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="e0f59-219">ArchiveDuplicateMessages: verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-219">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="e0f59-220">CachePurgingInterval: 24</span><span class="sxs-lookup"><span data-stu-id="e0f59-220">CachePurgingInterval : 24</span></span>

<span data-ttu-id="e0f59-221">Si la propiedad EnableArchiving se establece en false, significa que no se archivará ninguna sesión de comunicación.</span><span class="sxs-lookup"><span data-stu-id="e0f59-221">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="e0f59-222">Si desea archivar solo las sesiones de mensajería instantánea, use un comando como el siguiente para habilitar el archivado de sesiones de mensajería instantánea:</span><span class="sxs-lookup"><span data-stu-id="e0f59-222">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="e0f59-223">Para archivar sesiones de conferencia y sesiones de mensajería instantánea, use este comando:</span><span class="sxs-lookup"><span data-stu-id="e0f59-223">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="e0f59-224">Si quiere comparar la configuración de archivado actual con la configuración predeterminada, ejecute el siguiente comando de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e0f59-224">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="e0f59-225">Ese comando crea una instancia de solo memoria de los valores de configuración de archivado global.</span><span class="sxs-lookup"><span data-stu-id="e0f59-225">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="e0f59-226">Esta no es una colección real de opciones de configuración usadas por Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e0f59-226">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="e0f59-227">Sin embargo, muestra los valores predeterminados para todas las propiedades de configuración de archivado.</span><span class="sxs-lookup"><span data-stu-id="e0f59-227">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="e0f59-228">También puede usar este comando para devolver el FQDN de los servidores de archivado:</span><span class="sxs-lookup"><span data-stu-id="e0f59-228">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="e0f59-229">Después de comprobar que el archivado está habilitado, puede ver las directivas de archivado para determinar si las sesiones de comunicación interna y externa se van a archivar.</span><span class="sxs-lookup"><span data-stu-id="e0f59-229">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="e0f59-230">La información de la Directiva de archivado se puede recuperar mediante el cmdlet Get-CsArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="e0f59-230">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="e0f59-231">Por ejemplo, este comando devuelve información sobre la Directiva de archivado global:</span><span class="sxs-lookup"><span data-stu-id="e0f59-231">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="e0f59-232">Como las directivas de archivado también se pueden configurar en el sitio y en el ámbito de cada usuario, también es posible que desee usar este comando, que devuelve información acerca de todas las directivas de archivado:</span><span class="sxs-lookup"><span data-stu-id="e0f59-232">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="e0f59-233">La información que recibe de Get-CsArchivingPolicy se parecerá a esta:</span><span class="sxs-lookup"><span data-stu-id="e0f59-233">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="e0f59-234">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="e0f59-234">Identity : Global</span></span>

<span data-ttu-id="e0f59-235">Texto</span><span class="sxs-lookup"><span data-stu-id="e0f59-235">Description :</span></span>

<span data-ttu-id="e0f59-236">ArchiveInternal: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-236">ArchiveInternal : False</span></span>

<span data-ttu-id="e0f59-237">ArchiveExternal: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-237">ArchiveExternal : False</span></span>

<span data-ttu-id="e0f59-238">Tenga en cuenta que, de forma predeterminada, el archivado interno y externo están deshabilitados en una directiva de archivado.</span><span class="sxs-lookup"><span data-stu-id="e0f59-238">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="e0f59-239">Comprobar la configuración de CDR</span><span class="sxs-lookup"><span data-stu-id="e0f59-239">Check CDR settings</span></span>

<span data-ttu-id="e0f59-240">Comprobar la configuración de registro de detalles de llamadas (CDR) para la grabación de detalles de llamadas de punto a punto, Conferencia y Conferencia.</span><span class="sxs-lookup"><span data-stu-id="e0f59-240">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="e0f59-241">Para obtener información detallada sobre la configuración de CDR, puede usar el cmdlet **Get-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="e0f59-241">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="e0f59-242">Por ejemplo, este comando devuelve información acerca de la colección global de opciones de configuración de CDR:</span><span class="sxs-lookup"><span data-stu-id="e0f59-242">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="e0f59-243">Como CDR también se puede configurar en el ámbito del sitio, es posible que también desee ejecutar este comando, que devuelve información acerca de todas las opciones de configuración de CDR:</span><span class="sxs-lookup"><span data-stu-id="e0f59-243">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="e0f59-244">El cmdlet Get-CsCdrConfiguration devuelve información similar a la siguiente para cada colección de opciones de configuración de CDR:</span><span class="sxs-lookup"><span data-stu-id="e0f59-244">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="e0f59-245">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="e0f59-245">Identity : Global</span></span>

<span data-ttu-id="e0f59-246">EnableCDR: verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-246">EnableCDR : True</span></span>

<span data-ttu-id="e0f59-247">EnablePurging: verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-247">EnablePurging : True</span></span>

<span data-ttu-id="e0f59-248">KeepCallDetailForDays: 60</span><span class="sxs-lookup"><span data-stu-id="e0f59-248">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="e0f59-249">KeepErrorReportForDays: 60</span><span class="sxs-lookup"><span data-stu-id="e0f59-249">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="e0f59-250">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="e0f59-250">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="e0f59-251">Se puede devolver información similar para la supervisión de QoE mediante el cmdlet Get-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="e0f59-251">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="e0f59-252">Por ejemplo, este comando devuelve información acerca de la colección global de parámetros de configuración de QoE:</span><span class="sxs-lookup"><span data-stu-id="e0f59-252">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="e0f59-253">Esta información se parecerá a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="e0f59-253">That information will resemble this:</span></span>

<span data-ttu-id="e0f59-254">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="e0f59-254">Identity : Global</span></span>

<span data-ttu-id="e0f59-255">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="e0f59-255">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="e0f59-256">EnablePurging: verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-256">EnablePurging : True</span></span>

<span data-ttu-id="e0f59-257">KeepQoEDataForDays: 60</span><span class="sxs-lookup"><span data-stu-id="e0f59-257">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="e0f59-258">PurgeHourOfDay: 1</span><span class="sxs-lookup"><span data-stu-id="e0f59-258">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="e0f59-259">EnableExternalConsumer: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-259">EnableExternalConsumer : False</span></span>

<span data-ttu-id="e0f59-260">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="e0f59-260">ExternalConsumerName :</span></span>

<span data-ttu-id="e0f59-261">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="e0f59-261">ExternalConsumerURL :</span></span>

<span data-ttu-id="e0f59-262">EnableQoE: verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-262">EnableQoE : True</span></span>

<span data-ttu-id="e0f59-263">Si desea comparar la configuración actual de CDR con la configuración de CDR predeterminada, puede revisar los valores predeterminados ejecutando este comando:</span><span class="sxs-lookup"><span data-stu-id="e0f59-263">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="e0f59-264">Del mismo modo, los valores predeterminados para la supervisión de QoE se pueden recuperar con este comando:</span><span class="sxs-lookup"><span data-stu-id="e0f59-264">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="e0f59-265">También puede devolver el FQDN de los servidores de supervisión ejecutando este comando:</span><span class="sxs-lookup"><span data-stu-id="e0f59-265">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="e0f59-266">Comprobar la configuración de voz</span><span class="sxs-lookup"><span data-stu-id="e0f59-266">Check voice settings</span></span>

<span data-ttu-id="e0f59-267">La configuración de voz generalmente importante para los administradores se encuentra en directivas de voz y rutas de voz: las directivas de voz contienen la configuración que determina las capacidades que se exponen a los usuarios individuales (como la capacidad de desviar o transferir llamadas), mientras las rutas de voz determinan cómo (y si) las llamadas se enrutan a través de la RTC.</span><span class="sxs-lookup"><span data-stu-id="e0f59-267">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="e0f59-268">La información de la Directiva de voz se puede recuperar mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e0f59-268">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="e0f59-269">Por ejemplo, este comando devuelve información sobre la Directiva de voz global:</span><span class="sxs-lookup"><span data-stu-id="e0f59-269">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="e0f59-270">Y este comando devuelve información acerca de todas las directivas de voz configuradas para su uso en la organización:</span><span class="sxs-lookup"><span data-stu-id="e0f59-270">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="e0f59-271">La información devuelta por el cmdlet Get-CsVoicePolicy se asemeja a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e0f59-271">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="e0f59-272">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="e0f59-272">Identity : Global</span></span>

<span data-ttu-id="e0f59-273">PstnUsages :{}</span><span class="sxs-lookup"><span data-stu-id="e0f59-273">PstnUsages : {}</span></span>

<span data-ttu-id="e0f59-274">Texto</span><span class="sxs-lookup"><span data-stu-id="e0f59-274">Description :</span></span>

<span data-ttu-id="e0f59-275">AllowSimulRing: verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-275">AllowSimulRing : True</span></span>

<span data-ttu-id="e0f59-276">AllowCallForwarding: verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-276">AllowCallForwarding : True</span></span>

<span data-ttu-id="e0f59-277">AllowPSTNReRouting: verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-277">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="e0f59-278">Nombre: DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="e0f59-278">Name : DefaultPolicy</span></span>

<span data-ttu-id="e0f59-279">EnableDelegation: verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-279">EnableDelegation : True</span></span>

<span data-ttu-id="e0f59-280">EnableTeamCall: verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-280">EnableTeamCall : True</span></span>

<span data-ttu-id="e0f59-281">EnableCallTransfer: verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-281">EnableCallTransfer : True</span></span>

<span data-ttu-id="e0f59-282">EnableCallPark: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-282">EnableCallPark : False</span></span>

<span data-ttu-id="e0f59-283">EnableMaliciousCallTracing: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-283">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="e0f59-284">EnableBWPolicyOverride: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-284">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="e0f59-285">PreventPSTNTollBypass: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-285">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="e0f59-286">También puede crear consultas que devuelvan un subconjunto de las directivas de voz.</span><span class="sxs-lookup"><span data-stu-id="e0f59-286">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="e0f59-287">Por ejemplo, este comando devuelve todas las directivas de voz que permiten el desvío de llamadas:</span><span class="sxs-lookup"><span data-stu-id="e0f59-287">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="e0f59-288">Y este comando devuelve todas las directivas de voz que no permiten el desvío de llamadas:</span><span class="sxs-lookup"><span data-stu-id="e0f59-288">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="e0f59-289">En Windows PowerShell, use el cmdlet Get-CsVoiceRouting para obtener información sobre las rutas de voz:</span><span class="sxs-lookup"><span data-stu-id="e0f59-289">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="e0f59-290">Ese comando devuelve información como esta para todas las rutas de voz:</span><span class="sxs-lookup"><span data-stu-id="e0f59-290">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="e0f59-291">Identidad: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="e0f59-291">Identity : LocalRoute</span></span>

<span data-ttu-id="e0f59-292">Prioridad: 0</span><span class="sxs-lookup"><span data-stu-id="e0f59-292">Priority : 0</span></span>

<span data-ttu-id="e0f59-293">Texto</span><span class="sxs-lookup"><span data-stu-id="e0f59-293">Description :</span></span>

<span data-ttu-id="e0f59-294">NumberPattern: ^ (\\+ 1\[0-9\]{10}) $</span><span class="sxs-lookup"><span data-stu-id="e0f59-294">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="e0f59-295">PstnUsages :{}</span><span class="sxs-lookup"><span data-stu-id="e0f59-295">PstnUsages : {}</span></span>

<span data-ttu-id="e0f59-296">PstnGatewayList :{}</span><span class="sxs-lookup"><span data-stu-id="e0f59-296">PstnGatewayList : {}</span></span>

<span data-ttu-id="e0f59-297">Nombre: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="e0f59-297">Name : LocalRoute</span></span>

<span data-ttu-id="e0f59-298">SuppressCallerId :</span><span class="sxs-lookup"><span data-stu-id="e0f59-298">SuppressCallerId :</span></span>

<span data-ttu-id="e0f59-299">AlternateCallerId :</span><span class="sxs-lookup"><span data-stu-id="e0f59-299">AlternateCallerId :</span></span>

<span data-ttu-id="e0f59-300">Lync Server le permite crear rutas de voz que no tienen uso de RTC y no especifican una puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="e0f59-300">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="e0f59-301">Sin embargo, no puede enrutar llamadas a través de una ruta de voz que no tenga estos dos valores de propiedad configurados.</span><span class="sxs-lookup"><span data-stu-id="e0f59-301">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="e0f59-302">Por eso, es posible que le resulte útil ejecutar periódicamente este comando, que devuelve la identidad de cualquier ruta de voz que no tenga uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="e0f59-302">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="e0f59-303">De forma similar, este comando devuelve la identidad de cualquier ruta de voz que no se haya configurado para tener una puerta de enlace RTC:</span><span class="sxs-lookup"><span data-stu-id="e0f59-303">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="e0f59-304">Comprobar la configuración del operador de conferencias</span><span class="sxs-lookup"><span data-stu-id="e0f59-304">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="e0f59-305">Comprobar la configuración del operador de conferencias para conferencias de acceso telefónico local RTC.</span><span class="sxs-lookup"><span data-stu-id="e0f59-305">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="e0f59-306">La configuración del operador de conferencia solo se puede recuperar usando el cmdlet **Get-CsDialInConferencingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="e0f59-306">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="e0f59-307">Esta configuración no está disponible en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e0f59-307">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="e0f59-308">Para ver la configuración del operador de conferencias, use un comando de Windows PowerShell similar al siguiente, que devuelve la colección global de configuración del operador de Conferencia:</span><span class="sxs-lookup"><span data-stu-id="e0f59-308">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="e0f59-309">Tenga en cuenta que la configuración del operador de conferencia también se puede configurar en el ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="e0f59-309">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="e0f59-310">Para obtener información acerca de todas las opciones de configuración del operador de conferencia, use este comando:</span><span class="sxs-lookup"><span data-stu-id="e0f59-310">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="e0f59-311">El cmdlet Get-CsDialInConferencingConfiguration devuelve datos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="e0f59-311">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="e0f59-312">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="e0f59-312">Identity : Global</span></span>

<span data-ttu-id="e0f59-313">EntryExitAnnouncementsType : UseNames</span><span class="sxs-lookup"><span data-stu-id="e0f59-313">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="e0f59-314">EnableNameRecording: verdadero</span><span class="sxs-lookup"><span data-stu-id="e0f59-314">EnableNameRecording : True</span></span>

<span data-ttu-id="e0f59-315">EntryExitAnnouncementsEnabledByDefault: falso</span><span class="sxs-lookup"><span data-stu-id="e0f59-315">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="e0f59-316">Si EntryExitAnnouncementsEnabledByDefault se establece en false, significa que los anuncios de conferencia están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="e0f59-316">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="e0f59-317">Para habilitar los anuncios de entrada y salida, ejecute un comando de Windows PowerShell similar a este:</span><span class="sxs-lookup"><span data-stu-id="e0f59-317">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e0f59-318">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0f59-318">See Also</span></span>


[<span data-ttu-id="e0f59-319">Get-CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="e0f59-319">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="e0f59-320">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e0f59-320">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="e0f59-321">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="e0f59-321">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="e0f59-322">Get-CsAccessEdgeConfiguration</span><span class="sxs-lookup"><span data-stu-id="e0f59-322">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="e0f59-323">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="e0f59-323">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="e0f59-324">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e0f59-324">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="e0f59-325">Get-CsCdrConfiguration</span><span class="sxs-lookup"><span data-stu-id="e0f59-325">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="e0f59-326">Get-CsQoEConfiguration</span><span class="sxs-lookup"><span data-stu-id="e0f59-326">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="e0f59-327">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="e0f59-327">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="e0f59-328">Get-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="e0f59-328">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="e0f59-329">Get-CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="e0f59-329">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

