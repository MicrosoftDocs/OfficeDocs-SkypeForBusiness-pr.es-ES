---
title: 'Lync Server 2013: ver el estado de la configuración global de un bosque'
description: 'Lync Server 2013: ver el estado de la configuración global de un bosque.'
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
ms.openlocfilehash: d9f722ea66f6c54c816703bd1af1d3def57bbd84
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567596"
---
# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="49d5d-103">Ver el estado de la configuración global de un bosque en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49d5d-103">View status of global settings for a forest in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49d5d-104">_**Última modificación del tema:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="49d5d-104">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="49d5d-105">Los administradores deben revisar la configuración global de una implementación de Lync Server 2013 mensualmente.</span><span class="sxs-lookup"><span data-stu-id="49d5d-105">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="49d5d-106">El objetivo sería revisar la configuración implementada con un conjunto de configuraciones conocidas, una configuración de línea base para ayudar a garantizar que la configuración sea válida y para determinar si se debe actualizar la documentación de línea base.</span><span class="sxs-lookup"><span data-stu-id="49d5d-106">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="49d5d-107">Los cambios en la configuración global deben implementarse a través de un proceso de control de cambio que debe incluir la documentación de la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="49d5d-107">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="49d5d-108">En las siguientes secciones se describen las opciones globales que deben revisarse:</span><span class="sxs-lookup"><span data-stu-id="49d5d-108">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="49d5d-109">Comprobar la configuración general</span><span class="sxs-lookup"><span data-stu-id="49d5d-109">Check general settings</span></span>

<span data-ttu-id="49d5d-110">Compruebe la configuración general, incluidos los dominios admitidos del Protocolo de inicio de sesión (SIP) para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="49d5d-110">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="49d5d-111">La información del dominio SIP se puede devolver mediante Windows PowerShell y el cmdlet **Get-CsSipDomain** .</span><span class="sxs-lookup"><span data-stu-id="49d5d-111">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="49d5d-112">Para devolver esta información, ejecute el `Get-CsSipDomain` comando de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49d5d-112">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="49d5d-113">Get-CsSipDomain devolverá información similar a la siguiente para todos los dominios SIP autorizados:</span><span class="sxs-lookup"><span data-stu-id="49d5d-113">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="49d5d-114">Nombre de identidad IsDefault</span><span class="sxs-lookup"><span data-stu-id="49d5d-114">Identity Name IsDefault</span></span>

<span data-ttu-id="49d5d-115">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="49d5d-115">\-------- ---- ---------</span></span>

<span data-ttu-id="49d5d-116">fabrikam.com fabrikam.com true</span><span class="sxs-lookup"><span data-stu-id="49d5d-116">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="49d5d-117">na.fabrikam.com na.fabrikam.com false</span><span class="sxs-lookup"><span data-stu-id="49d5d-117">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="49d5d-118">Si la propiedad IsDefault se establece en true, el dominio correspondiente es su dominio SIP predeterminado.</span><span class="sxs-lookup"><span data-stu-id="49d5d-118">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="49d5d-119">Puede usar el cmdlet Set-CsSipDomain para cambiar el dominio SIP predeterminado de su organización.</span><span class="sxs-lookup"><span data-stu-id="49d5d-119">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="49d5d-120">Sin embargo, no se puede eliminar simplemente el dominio SIP predeterminado, ya que esto le dejaría sin un dominio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="49d5d-120">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="49d5d-121">Si deseara eliminar el dominio fabrikam.com (como se muestra en el ejemplo anterior), primero tendría que configurar na.fabrikam.com para que sea su dominio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="49d5d-121">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="49d5d-122">Comprobar la configuración de la reunión</span><span class="sxs-lookup"><span data-stu-id="49d5d-122">Check meeting settings</span></span>

<span data-ttu-id="49d5d-123">La configuración de reunión incluye definiciones de directivas de reuniones y soporte para la participación de usuarios anónimos en reuniones.</span><span class="sxs-lookup"><span data-stu-id="49d5d-123">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="49d5d-124">Las opciones de configuración de reuniones se pueden recuperar con Windows PowerShell y el cmdlet **Get-CsMeetingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="49d5d-124">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="49d5d-125">Por ejemplo, este comando devuelve información sobre las opciones de configuración de reunión global:</span><span class="sxs-lookup"><span data-stu-id="49d5d-125">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="49d5d-126">Get-CsMeetingConfiguration la identidad "global" las opciones de configuración de reuniones también se pueden configurar en el ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="49d5d-126">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="49d5d-127">Por ello, es posible que desee usar el siguiente comando, que devuelve información sobre todas las opciones de configuración de reuniones:</span><span class="sxs-lookup"><span data-stu-id="49d5d-127">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="49d5d-128">El cmdlet **Get-CsMeetingConfiguration** devuelve información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="49d5d-128">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="49d5d-129">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="49d5d-129">Identity : Global</span></span>

<span data-ttu-id="49d5d-130">PstnCallersBypassLobby: true</span><span class="sxs-lookup"><span data-stu-id="49d5d-130">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="49d5d-131">EnableAssignedConferenceType: true</span><span class="sxs-lookup"><span data-stu-id="49d5d-131">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="49d5d-132">DesignateAsPresenter: compañía</span><span class="sxs-lookup"><span data-stu-id="49d5d-132">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="49d5d-133">AssignedConferenceTypeByDefault: true</span><span class="sxs-lookup"><span data-stu-id="49d5d-133">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="49d5d-134">AdmitAnonymousUsersByDefault: true</span><span class="sxs-lookup"><span data-stu-id="49d5d-134">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="49d5d-135">De nuevo, el último elemento de la lista, **AdmitAnonymousUsersByDefault**, habilita o deshabilita la posibilidad de que los usuarios anónimos participen en las reuniones.</span><span class="sxs-lookup"><span data-stu-id="49d5d-135">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="49d5d-136">Al comprobar las opciones de configuración de reuniones, es posible que le resulte útil comparar la configuración actual con los equivalentes predeterminados.</span><span class="sxs-lookup"><span data-stu-id="49d5d-136">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="49d5d-137">Para ver las opciones de configuración de reunión predeterminadas, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="49d5d-137">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="49d5d-138">El comando anterior crea una instancia de solo memoria de las opciones de configuración de reunión global, una instancia que usa el valor predeterminado para cada propiedad.</span><span class="sxs-lookup"><span data-stu-id="49d5d-138">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="49d5d-139">No se crea ninguna configuración de reunión real al ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="49d5d-139">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="49d5d-140">Sin embargo, todos los valores de propiedad predeterminados se mostrarán en pantalla.</span><span class="sxs-lookup"><span data-stu-id="49d5d-140">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="49d5d-141">Comprobar los servidores perimetrales y su configuración</span><span class="sxs-lookup"><span data-stu-id="49d5d-141">Check Edge Servers and their settings</span></span>

<span data-ttu-id="49d5d-142">La información del servidor perimetral se puede recuperar con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49d5d-142">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="49d5d-143">Este comando devuelve información sobre todos los servidores perimetrales configurados para su uso en la organización:</span><span class="sxs-lookup"><span data-stu-id="49d5d-143">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="49d5d-144">La información devuelta incluye todo el FQDN y la configuración de puerto de cada servidor perimetral:</span><span class="sxs-lookup"><span data-stu-id="49d5d-144">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="49d5d-145">Identidad: EdgeServer: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="49d5d-145">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="49d5d-146">Registrar: registrar: LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="49d5d-146">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="49d5d-147">AccessEdgeInternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="49d5d-147">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="49d5d-148">AccessEdgeExternalSipPort: 5061</span><span class="sxs-lookup"><span data-stu-id="49d5d-148">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="49d5d-149">AccessEdgeClientPort: 443</span><span class="sxs-lookup"><span data-stu-id="49d5d-149">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="49d5d-150">DataPsomServerPort: 8057</span><span class="sxs-lookup"><span data-stu-id="49d5d-150">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="49d5d-151">DataPsomClientPort: 444</span><span class="sxs-lookup"><span data-stu-id="49d5d-151">DataPsomClientPort : 444</span></span>

<span data-ttu-id="49d5d-152">MediaRelayAuthEdgePort: 5062</span><span class="sxs-lookup"><span data-stu-id="49d5d-152">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="49d5d-153">MediaRelayAuthInternalTurnTcpPort: 443</span><span class="sxs-lookup"><span data-stu-id="49d5d-153">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="49d5d-154">MediaRelayAuthExternalTurnTcpPort: 445</span><span class="sxs-lookup"><span data-stu-id="49d5d-154">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="49d5d-155">MediaRelayAuthInternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="49d5d-155">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="49d5d-156">MediaRelayAuthExternalTurnUdpPort: 3478</span><span class="sxs-lookup"><span data-stu-id="49d5d-156">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="49d5d-157">MediaCommunicationPortStart: 50000</span><span class="sxs-lookup"><span data-stu-id="49d5d-157">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="49d5d-158">MediaComunicationPortCount: 10000</span><span class="sxs-lookup"><span data-stu-id="49d5d-158">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="49d5d-159">AccessEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="49d5d-159">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="49d5d-160">DataEdgeExternalFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="49d5d-160">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="49d5d-161">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="49d5d-161">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="49d5d-162">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="49d5d-162">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="49d5d-163">ExternalMrasFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="49d5d-163">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="49d5d-164">DependentServiceList: {registrar: LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="49d5d-164">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="49d5d-165">ConferencingServer: LYNC-SE. fabrikam</span><span class="sxs-lookup"><span data-stu-id="49d5d-165">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="49d5d-166">com, MediationServer: LYNC-SE.</span><span class="sxs-lookup"><span data-stu-id="49d5d-166">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="49d5d-167">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="49d5d-167">fabrikam.com}</span></span>

<span data-ttu-id="49d5d-168">ServiceId: fabrikam.com-EdgeServer-2</span><span class="sxs-lookup"><span data-stu-id="49d5d-168">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="49d5d-169">SiteId: sitio:fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="49d5d-169">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="49d5d-170">PoolFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="49d5d-170">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="49d5d-171">Versión: 5</span><span class="sxs-lookup"><span data-stu-id="49d5d-171">Version : 5</span></span>

<span data-ttu-id="49d5d-172">Rol: EdgeServer</span><span class="sxs-lookup"><span data-stu-id="49d5d-172">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="49d5d-173">Comprobar la configuración de la Federación</span><span class="sxs-lookup"><span data-stu-id="49d5d-173">Check federation settings</span></span>

<span data-ttu-id="49d5d-174">Compruebe la configuración de la Federación, por ejemplo si está configurada y, si la respuesta es "sí", el nombre de dominio completo y el puerto.</span><span class="sxs-lookup"><span data-stu-id="49d5d-174">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="49d5d-175">La Federación se habilita y deshabilita mediante el uso de la colección global de opciones de configuración perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="49d5d-175">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="49d5d-176">Entre otras cosas, esto significa que la Federación está configurada en todo o nada: la Federación está habilitada para toda la organización o la Federación está deshabilitada para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="49d5d-176">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="49d5d-177">Las opciones de configuración perimetral de acceso se pueden devolver mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49d5d-177">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="49d5d-178">Para ello, ejecute el siguiente comando de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="49d5d-178">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="49d5d-179">A su vez, ese comando devolverá datos similares a estos:</span><span class="sxs-lookup"><span data-stu-id="49d5d-179">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="49d5d-180">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="49d5d-180">Identity : Global</span></span>

<span data-ttu-id="49d5d-181">AllowAnonymousUsers: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-181">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="49d5d-182">AllowFederatedUsers: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-182">AllowFederatedUsers : False</span></span>

<span data-ttu-id="49d5d-183">AllowOutsideUsers: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-183">AllowOutsideUsers : False</span></span>

<span data-ttu-id="49d5d-184">BeClearingHouse: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-184">BeClearingHouse : False</span></span>

<span data-ttu-id="49d5d-185">EnablePartnerDiscovery: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-185">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="49d5d-186">EnableArchivingDisclaimer: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-186">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="49d5d-187">KeepCrlsUpToDateForPeers: true</span><span class="sxs-lookup"><span data-stu-id="49d5d-187">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="49d5d-188">MarkSourceVerifiableOnOutgoingMessages: true</span><span class="sxs-lookup"><span data-stu-id="49d5d-188">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="49d5d-189">OutgoingTlsCountForFederatedPartners: 4</span><span class="sxs-lookup"><span data-stu-id="49d5d-189">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="49d5d-190">RoutingMethod: UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="49d5d-190">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="49d5d-191">Si la propiedad **AllowFederatedUsers** está establecida en true, significa que la Federación está habilitada para su organización.</span><span class="sxs-lookup"><span data-stu-id="49d5d-191">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="49d5d-192">(Si se establece **AllowFederatedUsers** en true, también significa que, en un escenario de dominio dividido, los usuarios locales podrán comunicarse sin problemas con los usuarios de la nube).</span><span class="sxs-lookup"><span data-stu-id="49d5d-192">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="49d5d-193">Para recuperar el FQDN y la configuración del puerto para el servidor perimetral, vea la tarea anterior (servidores perimetrales y su configuración).</span><span class="sxs-lookup"><span data-stu-id="49d5d-193">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="49d5d-194">Habilitar la Federación solo en el ámbito global significa que los usuarios pueden comunicarse potencialmente con usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="49d5d-194">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="49d5d-195">Para determinar si los usuarios individuales pueden comunicarse realmente con los usuarios federados, es necesario que examine la Directiva de acceso de usuarios externos asignada a ese usuario.</span><span class="sxs-lookup"><span data-stu-id="49d5d-195">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="49d5d-196">La información de acceso de usuarios externos se puede devolver mediante Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49d5d-196">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="49d5d-197">Por ejemplo, este comando devuelve información de la Directiva de acceso de usuario externo global:</span><span class="sxs-lookup"><span data-stu-id="49d5d-197">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="49d5d-198">Y este comando devuelve información de todas las directivas de acceso de usuarios externos:</span><span class="sxs-lookup"><span data-stu-id="49d5d-198">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="49d5d-199">La información devuelta será similar a esta:</span><span class="sxs-lookup"><span data-stu-id="49d5d-199">The returned information will resemble this:</span></span>

<span data-ttu-id="49d5d-200">Identidad: falso</span><span class="sxs-lookup"><span data-stu-id="49d5d-200">Identity : False</span></span>

<span data-ttu-id="49d5d-201">Descriptiva</span><span class="sxs-lookup"><span data-stu-id="49d5d-201">Description :</span></span>

<span data-ttu-id="49d5d-202">EnableFederationAccess: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-202">EnableFederationAccess : False</span></span>

<span data-ttu-id="49d5d-203">EnablePublicCloudAccess: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-203">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="49d5d-204">EnablePublicCloudAccessAudioVideoAccess: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-204">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="49d5d-205">EnableOutsideAccess: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-205">EnableOutsideAccess : False</span></span>

<span data-ttu-id="49d5d-206">Si **EnableFederationAccess** se establece en true, los usuarios administrados por la directiva determinada podrán comunicarse con los usuarios federados.</span><span class="sxs-lookup"><span data-stu-id="49d5d-206">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="49d5d-207">Comprobar la configuración de archivado</span><span class="sxs-lookup"><span data-stu-id="49d5d-207">Check archiving settings</span></span>

<span data-ttu-id="49d5d-208">Compruebe la configuración de archivado para las comunicaciones internas y federadas. Antes de comprobar la configuración de la archivación interna y externa, debe comprobar que el archivado esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="49d5d-208">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="49d5d-209">Las opciones de configuración de archivado se pueden comprobar mediante Windows PowerShell y el cmdlet Get-CsArchivingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="49d5d-209">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="49d5d-210">Tenga en cuenta que la configuración de archivado también se puede configurar en el ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="49d5d-210">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="49d5d-211">Para devolver información acerca de toda la configuración de archivado, use este comando:</span><span class="sxs-lookup"><span data-stu-id="49d5d-211">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="49d5d-212">El cmdlet Get-CsArchivingConfiguration devuelve datos similares a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="49d5d-212">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="49d5d-213">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="49d5d-213">Identity : Global</span></span>

<span data-ttu-id="49d5d-214">EnableArchiving: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-214">EnableArchiving : False</span></span>

<span data-ttu-id="49d5d-215">EnablePurging: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-215">EnablePurging : False</span></span>

<span data-ttu-id="49d5d-216">PurgeExportedArchivesOnly: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-216">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="49d5d-217">BlockOnArchiveFailure: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-217">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="49d5d-218">KeepArchivingDataForDays: 14</span><span class="sxs-lookup"><span data-stu-id="49d5d-218">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="49d5d-219">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="49d5d-219">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="49d5d-220">ArchiveDuplicateMessages: true</span><span class="sxs-lookup"><span data-stu-id="49d5d-220">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="49d5d-221">Cachepurgeinterval: 24</span><span class="sxs-lookup"><span data-stu-id="49d5d-221">CachePurgingInterval : 24</span></span>

<span data-ttu-id="49d5d-222">Si la propiedad EnableArchiving está establecida en false, significa que no se archivará ninguna sesión de comunicación.</span><span class="sxs-lookup"><span data-stu-id="49d5d-222">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="49d5d-223">Si sólo desea archivar sesiones de mensajería instantánea, use un comando como el siguiente para habilitar el archivado de sesiones de mensajería instantánea:</span><span class="sxs-lookup"><span data-stu-id="49d5d-223">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="49d5d-224">Para archivar sesiones de conferencia y sesiones de mensajería instantánea, use este comando:</span><span class="sxs-lookup"><span data-stu-id="49d5d-224">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="49d5d-225">Si quiere comparar la configuración de archivado actual con la configuración predeterminada, ejecute el siguiente comando de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="49d5d-225">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="49d5d-226">Ese comando crea una instancia de solo memoria de las opciones de configuración de archivado global.</span><span class="sxs-lookup"><span data-stu-id="49d5d-226">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="49d5d-227">No es una colección real de opciones de configuración que usa Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49d5d-227">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="49d5d-228">Sin embargo, muestra los valores predeterminados de todas las propiedades de configuración de archivado.</span><span class="sxs-lookup"><span data-stu-id="49d5d-228">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="49d5d-229">También puede usar este comando para devolver el FQDN de los servidores de archivado:</span><span class="sxs-lookup"><span data-stu-id="49d5d-229">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="49d5d-230">Una vez que haya comprobado que el archivado está habilitado, puede ver las directivas de archivado para determinar si las sesiones de comunicación internas y externas se archivan.</span><span class="sxs-lookup"><span data-stu-id="49d5d-230">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="49d5d-231">La información de la Directiva de archivado se puede recuperar con el cmdlet Get-CsArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="49d5d-231">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="49d5d-232">Por ejemplo, este comando devuelve información sobre la Directiva de archivado global:</span><span class="sxs-lookup"><span data-stu-id="49d5d-232">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="49d5d-233">Como las directivas de archivado también se pueden configurar en el sitio y el ámbito por usuario, es posible que también desee usar este comando, que devuelve información sobre todas las directivas de archivado:</span><span class="sxs-lookup"><span data-stu-id="49d5d-233">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="49d5d-234">La información que recibe de Get-CsArchivingPolicy será similar a esta:</span><span class="sxs-lookup"><span data-stu-id="49d5d-234">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="49d5d-235">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="49d5d-235">Identity : Global</span></span>

<span data-ttu-id="49d5d-236">Descriptiva</span><span class="sxs-lookup"><span data-stu-id="49d5d-236">Description :</span></span>

<span data-ttu-id="49d5d-237">ArchiveInternal: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-237">ArchiveInternal : False</span></span>

<span data-ttu-id="49d5d-238">ArchiveExternal: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-238">ArchiveExternal : False</span></span>

<span data-ttu-id="49d5d-239">Tenga en cuenta que, de forma predeterminada, los archivados internos y externos están deshabilitados en una directiva de archivado.</span><span class="sxs-lookup"><span data-stu-id="49d5d-239">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="49d5d-240">Comprobar la configuración de CDR</span><span class="sxs-lookup"><span data-stu-id="49d5d-240">Check CDR settings</span></span>

<span data-ttu-id="49d5d-241">Compruebe la configuración de registro de detalles de llamadas (CDR) para el registro detallado de llamadas de voz, de conferencia y de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="49d5d-241">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="49d5d-242">Se puede devolver información detallada sobre la configuración de CDR mediante el cmdlet **Get-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="49d5d-242">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="49d5d-243">Por ejemplo, este comando devuelve información sobre la colección global de opciones de configuración de CDR:</span><span class="sxs-lookup"><span data-stu-id="49d5d-243">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="49d5d-244">Como CDR también se puede configurar en el ámbito de sitio, es posible que también desee ejecutar este comando, que devuelve información sobre todas las opciones de configuración de CDR:</span><span class="sxs-lookup"><span data-stu-id="49d5d-244">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="49d5d-245">El cmdlet Get-CsCdrConfiguration devuelve información similar a la siguiente para cada colección de opciones de configuración de CDR:</span><span class="sxs-lookup"><span data-stu-id="49d5d-245">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="49d5d-246">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="49d5d-246">Identity : Global</span></span>

<span data-ttu-id="49d5d-247">EnableCDR: true</span><span class="sxs-lookup"><span data-stu-id="49d5d-247">EnableCDR : True</span></span>

<span data-ttu-id="49d5d-248">EnablePurging: true</span><span class="sxs-lookup"><span data-stu-id="49d5d-248">EnablePurging : True</span></span>

<span data-ttu-id="49d5d-249">KeepCallDetailForDays: 60</span><span class="sxs-lookup"><span data-stu-id="49d5d-249">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="49d5d-250">KeepErrorReportForDays: 60</span><span class="sxs-lookup"><span data-stu-id="49d5d-250">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="49d5d-251">PurgeHourOfDay: 2</span><span class="sxs-lookup"><span data-stu-id="49d5d-251">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="49d5d-252">Se puede devolver información similar para la supervisión de QoE mediante el cmdlet Get-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="49d5d-252">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="49d5d-253">Por ejemplo, este comando devuelve información sobre la colección global de opciones de configuración de QoE:</span><span class="sxs-lookup"><span data-stu-id="49d5d-253">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="49d5d-254">Esta información será similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="49d5d-254">That information will resemble this:</span></span>

<span data-ttu-id="49d5d-255">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="49d5d-255">Identity : Global</span></span>

<span data-ttu-id="49d5d-256">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="49d5d-256">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="49d5d-257">EnablePurging: true</span><span class="sxs-lookup"><span data-stu-id="49d5d-257">EnablePurging : True</span></span>

<span data-ttu-id="49d5d-258">KeepQoEDataForDays: 60</span><span class="sxs-lookup"><span data-stu-id="49d5d-258">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="49d5d-259">PurgeHourOfDay: 1</span><span class="sxs-lookup"><span data-stu-id="49d5d-259">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="49d5d-260">EnableExternalConsumer: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-260">EnableExternalConsumer : False</span></span>

<span data-ttu-id="49d5d-261">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="49d5d-261">ExternalConsumerName :</span></span>

<span data-ttu-id="49d5d-262">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="49d5d-262">ExternalConsumerURL :</span></span>

<span data-ttu-id="49d5d-263">EnableQoE: true</span><span class="sxs-lookup"><span data-stu-id="49d5d-263">EnableQoE : True</span></span>

<span data-ttu-id="49d5d-264">Si desea comparar la configuración actual de CDR con la configuración predeterminada de CDR, puede revisar los valores predeterminados mediante la ejecución de este comando:</span><span class="sxs-lookup"><span data-stu-id="49d5d-264">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="49d5d-265">Del mismo modo, los valores predeterminados para la supervisión de QoE se pueden recuperar con este comando:</span><span class="sxs-lookup"><span data-stu-id="49d5d-265">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="49d5d-266">También puede devolver el FQDN de los servidores de supervisión mediante la ejecución de este comando:</span><span class="sxs-lookup"><span data-stu-id="49d5d-266">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="49d5d-267">Comprobar la configuración de voz</span><span class="sxs-lookup"><span data-stu-id="49d5d-267">Check voice settings</span></span>

<span data-ttu-id="49d5d-268">La configuración de voz suele ser importante para los administradores en las directivas de voz y rutas de voz: las directivas de voz contienen la configuración que determina las capacidades que se exponen a los usuarios individuales (como la capacidad de desviar o transferir las llamadas), mientras que las rutas de voz determinan cómo se enrutan las llamadas (y si) a través de la RTC.</span><span class="sxs-lookup"><span data-stu-id="49d5d-268">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="49d5d-269">La información de la Directiva de voz se puede recuperar con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49d5d-269">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="49d5d-270">Por ejemplo, este comando devuelve información sobre la Directiva de voz global:</span><span class="sxs-lookup"><span data-stu-id="49d5d-270">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="49d5d-271">Y este comando devuelve información sobre todas las directivas de voz configuradas para su uso en la organización:</span><span class="sxs-lookup"><span data-stu-id="49d5d-271">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="49d5d-272">La información devuelta por el cmdlet Get-CsVoicePolicy es similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="49d5d-272">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="49d5d-273">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="49d5d-273">Identity : Global</span></span>

<span data-ttu-id="49d5d-274">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="49d5d-274">PstnUsages : {}</span></span>

<span data-ttu-id="49d5d-275">Descriptiva</span><span class="sxs-lookup"><span data-stu-id="49d5d-275">Description :</span></span>

<span data-ttu-id="49d5d-276">AllowSimulRing: true</span><span class="sxs-lookup"><span data-stu-id="49d5d-276">AllowSimulRing : True</span></span>

<span data-ttu-id="49d5d-277">AllowCallForwarding: true</span><span class="sxs-lookup"><span data-stu-id="49d5d-277">AllowCallForwarding : True</span></span>

<span data-ttu-id="49d5d-278">AllowPSTNReRouting: true</span><span class="sxs-lookup"><span data-stu-id="49d5d-278">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="49d5d-279">Nombre: DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="49d5d-279">Name : DefaultPolicy</span></span>

<span data-ttu-id="49d5d-280">EnableDelegation: true</span><span class="sxs-lookup"><span data-stu-id="49d5d-280">EnableDelegation : True</span></span>

<span data-ttu-id="49d5d-281">EnableTeamCall: true</span><span class="sxs-lookup"><span data-stu-id="49d5d-281">EnableTeamCall : True</span></span>

<span data-ttu-id="49d5d-282">EnableCallTransfer: true</span><span class="sxs-lookup"><span data-stu-id="49d5d-282">EnableCallTransfer : True</span></span>

<span data-ttu-id="49d5d-283">EnableCallPark: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-283">EnableCallPark : False</span></span>

<span data-ttu-id="49d5d-284">EnableMaliciousCallTracing: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-284">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="49d5d-285">EnableBWPolicyOverride: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-285">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="49d5d-286">PreventPSTNTollBypass: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-286">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="49d5d-287">También puede crear consultas que devuelvan un subconjunto de las directivas de voz.</span><span class="sxs-lookup"><span data-stu-id="49d5d-287">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="49d5d-288">Por ejemplo, este comando devuelve todas las directivas de voz que permiten el desvío de llamadas:</span><span class="sxs-lookup"><span data-stu-id="49d5d-288">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="49d5d-289">Y este comando devuelve todas las directivas de voz que no permiten el desvío de llamadas:</span><span class="sxs-lookup"><span data-stu-id="49d5d-289">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="49d5d-290">En Windows PowerShell, use el cmdlet Get-CsVoiceRouting para devolver información sobre las rutas de voz:</span><span class="sxs-lookup"><span data-stu-id="49d5d-290">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="49d5d-291">Este comando devuelve información como esta para todas las rutas de voz:</span><span class="sxs-lookup"><span data-stu-id="49d5d-291">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="49d5d-292">Identidad: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="49d5d-292">Identity : LocalRoute</span></span>

<span data-ttu-id="49d5d-293">Prioridad: 0</span><span class="sxs-lookup"><span data-stu-id="49d5d-293">Priority : 0</span></span>

<span data-ttu-id="49d5d-294">Descriptiva</span><span class="sxs-lookup"><span data-stu-id="49d5d-294">Description :</span></span>

<span data-ttu-id="49d5d-295">NumberPattern: ^ ( \\ + 1 \[ 0-9 \] {10} ) $</span><span class="sxs-lookup"><span data-stu-id="49d5d-295">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="49d5d-296">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="49d5d-296">PstnUsages : {}</span></span>

<span data-ttu-id="49d5d-297">PstnGatewayList : {}</span><span class="sxs-lookup"><span data-stu-id="49d5d-297">PstnGatewayList : {}</span></span>

<span data-ttu-id="49d5d-298">Nombre: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="49d5d-298">Name : LocalRoute</span></span>

<span data-ttu-id="49d5d-299">SuppressCallerId</span><span class="sxs-lookup"><span data-stu-id="49d5d-299">SuppressCallerId :</span></span>

<span data-ttu-id="49d5d-300">AlternateCallerId</span><span class="sxs-lookup"><span data-stu-id="49d5d-300">AlternateCallerId :</span></span>

<span data-ttu-id="49d5d-301">Lync Server le permite crear rutas de voz que no tienen un uso de RTC y no especifican una puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="49d5d-301">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="49d5d-302">Sin embargo, en realidad no puede enrutar las llamadas a través de una ruta de voz que no tenga estos dos valores de propiedad configurados.</span><span class="sxs-lookup"><span data-stu-id="49d5d-302">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="49d5d-303">Por ello, es posible que le resulte útil ejecutar periódicamente este comando, que devuelve la identidad de cualquier ruta de voz que no tenga uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="49d5d-303">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="49d5d-304">De forma similar, este comando devuelve la identidad de cualquier ruta de voz que no se haya configurado para tener una puerta de enlace RTC:</span><span class="sxs-lookup"><span data-stu-id="49d5d-304">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="49d5d-305">Comprobar la configuración del operador de conferencia</span><span class="sxs-lookup"><span data-stu-id="49d5d-305">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="49d5d-306">Compruebe la configuración del operador de conferencia para las conferencias de acceso telefónico local RTC.</span><span class="sxs-lookup"><span data-stu-id="49d5d-306">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="49d5d-307">La configuración del operador de conferencia solo puede recuperarse con el cmdlet **Get-CsDialInConferencingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="49d5d-307">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="49d5d-308">Esta configuración no está disponible en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49d5d-308">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="49d5d-309">Para ver la configuración del operador de conferencia, use un comando de Windows PowerShell similar al siguiente, que devuelve la colección global de opciones de configuración del operador de Conferencia:</span><span class="sxs-lookup"><span data-stu-id="49d5d-309">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="49d5d-310">Tenga en cuenta que la configuración del operador de conferencia también se puede configurar en el ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="49d5d-310">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="49d5d-311">Para obtener información acerca de todas las opciones de configuración del operador de conferencia, use este comando en su lugar:</span><span class="sxs-lookup"><span data-stu-id="49d5d-311">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="49d5d-312">El cmdlet Get-CsDialInConferencingConfiguration devuelve datos similares a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="49d5d-312">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="49d5d-313">Identidad: global</span><span class="sxs-lookup"><span data-stu-id="49d5d-313">Identity : Global</span></span>

<span data-ttu-id="49d5d-314">EntryExitAnnouncementsType: UseNames</span><span class="sxs-lookup"><span data-stu-id="49d5d-314">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="49d5d-315">EnableNameRecording: true</span><span class="sxs-lookup"><span data-stu-id="49d5d-315">EnableNameRecording : True</span></span>

<span data-ttu-id="49d5d-316">EntryExitAnnouncementsEnabledByDefault: false</span><span class="sxs-lookup"><span data-stu-id="49d5d-316">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="49d5d-317">Si EntryExitAnnouncementsEnabledByDefault se establece en false, significa que los anuncios de conferencia están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="49d5d-317">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="49d5d-318">Para habilitar los anuncios de entrada y salida, ejecute un comando de Windows PowerShell similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="49d5d-318">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="49d5d-319">Consulte también</span><span class="sxs-lookup"><span data-stu-id="49d5d-319">See Also</span></span>


[<span data-ttu-id="49d5d-320">Get-CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="49d5d-320">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="49d5d-321">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="49d5d-321">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="49d5d-322">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="49d5d-322">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="49d5d-323">Get-CsAccessEdgeConfiguration</span><span class="sxs-lookup"><span data-stu-id="49d5d-323">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="49d5d-324">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="49d5d-324">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="49d5d-325">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="49d5d-325">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="49d5d-326">Get-CsCdrConfiguration</span><span class="sxs-lookup"><span data-stu-id="49d5d-326">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="49d5d-327">Get-CsQoEConfiguration</span><span class="sxs-lookup"><span data-stu-id="49d5d-327">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="49d5d-328">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="49d5d-328">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="49d5d-329">Get-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="49d5d-329">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="49d5d-330">Get-CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="49d5d-330">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

