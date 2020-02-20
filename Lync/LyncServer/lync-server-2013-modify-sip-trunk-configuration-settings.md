---
title: 'Lync Server 2013: modificar las opciones de configuración del tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify SIP trunk configuration settings
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49733703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e51772b977d89a6417dbae73e79ffed4bd7db60d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="f108a-102">Modificar las opciones de configuración de tronco SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f108a-102">Modify SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f108a-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="f108a-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="f108a-p101">Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estos valores determinan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f108a-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="f108a-106">Si se debe habilitar el desvío de medios en los troncos.</span><span class="sxs-lookup"><span data-stu-id="f108a-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="f108a-107">Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="f108a-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="f108a-108">Si se requiere o no el cifrado del protocolo de tiempo real seguro (SRTP) en cada tronco.</span><span class="sxs-lookup"><span data-stu-id="f108a-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="f108a-109">Al instalar Microsoft Lync Server 2013, se crea una colección global de opciones de configuración de tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="f108a-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="f108a-110">Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).</span><span class="sxs-lookup"><span data-stu-id="f108a-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="f108a-111">Cualquiera de estas colecciones se puede modificar más adelante con el panel de control de Lync Server o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f108a-111">Any of these collections can later be modified using either Lync Server Control Panel or Windows PowerShell.</span></span>

<span data-ttu-id="f108a-112">Al modificar las opciones de configuración del tronco SIP mediante el panel de control de Lync Server, están disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f108a-112">When modifying SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f108a-113">Valor de IU</span><span class="sxs-lookup"><span data-stu-id="f108a-113">UI Setting</span></span></th>
<th><span data-ttu-id="f108a-114">Parámetro de PowerShell</span><span class="sxs-lookup"><span data-stu-id="f108a-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="f108a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="f108a-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f108a-116">Name</span><span class="sxs-lookup"><span data-stu-id="f108a-116">Name</span></span></p></td>
<td><p><span data-ttu-id="f108a-117">Identidad</span><span class="sxs-lookup"><span data-stu-id="f108a-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="f108a-p103">Identificador único para la colección. Esta propiedad es de solo lectura; no puede cambiar la Identidad de una colección o las opciones de configuración de troncos.</span><span class="sxs-lookup"><span data-stu-id="f108a-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f108a-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="f108a-120">Description</span></span></p></td>
<td><p><span data-ttu-id="f108a-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="f108a-121">Description</span></span></p></td>
<td><p><span data-ttu-id="f108a-122">Proporciona una manera para que los administradores almacenen información adicional acerca de la configuración (por ejemplo, el propósito de la configuración de troncos).</span><span class="sxs-lookup"><span data-stu-id="f108a-122">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f108a-123">Cantidad máxima de cuadros de diálogo admitidos</span><span class="sxs-lookup"><span data-stu-id="f108a-123">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="f108a-124">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="f108a-124">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="f108a-125">La cantidad máxima de respuestas bifurcadas que puede recibir una puerta de enlace RTC, IP-PBX o SBC en el proveedor de servicio para una invitación enviada al Servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="f108a-125">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f108a-126">Nivel de compatibilidad con el cifrado</span><span class="sxs-lookup"><span data-stu-id="f108a-126">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="f108a-127">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="f108a-127">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="f108a-128">Indica el nivel de apoyo para proteger el tráfico de medios entre el Servidor de mediación y la puerta de enlace RTC, IP-PBX, o SBC en el proveedor de servicio.</span><span class="sxs-lookup"><span data-stu-id="f108a-128">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="f108a-129">Para los casos de desvío de medios, este valor debe ser compatible con la configuración de EncryptionLevel en la configuración de medios.</span><span class="sxs-lookup"><span data-stu-id="f108a-129">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="f108a-130">La configuración de medios se establece con los cmdlets <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> y <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">set-CsMediaConfiguration</a> .</span><span class="sxs-lookup"><span data-stu-id="f108a-130">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="f108a-131">Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="f108a-131">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="f108a-132">Requeridos: debe usarse el cifrado SRTP.</span><span class="sxs-lookup"><span data-stu-id="f108a-132">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="f108a-133">Opcional: el SRTP se utilizará si la puerta de enlace lo admite.</span><span class="sxs-lookup"><span data-stu-id="f108a-133">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="f108a-134">No admitido: el cifrado SRTP no está admitido y, por lo tanto, no se utilizará.</span><span class="sxs-lookup"><span data-stu-id="f108a-134">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="f108a-p105">El SRTPMode se utiliza solo si la puerta de enlace está configurada para usar la Seguridad de la capa de transporte (TLS). Si la puerta de enlace está configurada con el Protocolo de control de transporte (TCP) como transporte, el SRTPMode se configura internamente como No admitido.</span><span class="sxs-lookup"><span data-stu-id="f108a-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f108a-137">Hacer referencia al soporte</span><span class="sxs-lookup"><span data-stu-id="f108a-137">Refer support</span></span></p></td>
<td><p><span data-ttu-id="f108a-138">Parámetro enable3pccrefer</span><span class="sxs-lookup"><span data-stu-id="f108a-138">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="f108a-139">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="f108a-139">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="f108a-140">Si se configura en <strong>Habilitar enviar referencia a la puerta de enlace</strong>, indica que el tronco admite la recepción de Solicitudes de referencia desde el Servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="f108a-140">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="f108a-141">Si está establecido como <strong>Habilitar la referencia mediante un control de llamadas de terceros</strong>, indica que el protocolo 3pcc puede ser utilizado para permitir llamadas transferidas para desviar el sitio hospedado.</span><span class="sxs-lookup"><span data-stu-id="f108a-141">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="f108a-142">3pcc también se conoce como &quot;control de terceros&quot; y se produce cuando se usa un tercero para conectar un par de llamadores (por ejemplo, un operador que realiza una llamada de la persona a a la persona B).</span><span class="sxs-lookup"><span data-stu-id="f108a-142">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f108a-143">Habilitar el desvío de medios</span><span class="sxs-lookup"><span data-stu-id="f108a-143">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="f108a-144">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="f108a-144">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="f108a-p107">Indica si la omisión de medios se encuentra habilitado para este tronco. La omisión de medios solo puede estar habilitada si el <strong>Procesamiento de medios centralizado</strong> también está habilitado.</span><span class="sxs-lookup"><span data-stu-id="f108a-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f108a-147">Procesamiento de medios centralizado</span><span class="sxs-lookup"><span data-stu-id="f108a-147">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="f108a-148">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="f108a-148">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="f108a-p108">Indica si existe un punto de terminación de medios conocido. (Un ejemplo de punto de terminación de medios conocido puede ser una puerta de enlace RTC donde una terminación de medios tiene la misma IP que la terminación de señal).</span><span class="sxs-lookup"><span data-stu-id="f108a-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f108a-151">Habilitar el cierre RTP</span><span class="sxs-lookup"><span data-stu-id="f108a-151">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="f108a-152">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="f108a-152">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="f108a-p109">Indica si los troncos admiten o no el cierre RTP. El cierre RTP es una tecnología que permite la conectividad RTP/RTCP mediante un firewall o dispositivo NAT (traductor de direcciones de red).</span><span class="sxs-lookup"><span data-stu-id="f108a-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f108a-155">Habilitar el historial de desvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="f108a-155">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="f108a-156">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="f108a-156">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="f108a-157">Indica si la información del historial de llamadas se reenviará mediante el tronco.</span><span class="sxs-lookup"><span data-stu-id="f108a-157">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f108a-158">Habilitar los datos de reenvío de la identidad p-asserted</span><span class="sxs-lookup"><span data-stu-id="f108a-158">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="f108a-159">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="f108a-159">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="f108a-p110">Indica si el encabezado de la identidad p-asserted (PAI) se reenviará junto con la llamada. El encabezado PAI proporciona una forma de verificar la identidad de la persona que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="f108a-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f108a-162">Habilitar el temporizador de desvío de conmutación por error saliente</span><span class="sxs-lookup"><span data-stu-id="f108a-162">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="f108a-163">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="f108a-163">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="f108a-p111">Indica que si las llamadas salientes no son respondidas por la puerta de enlace dentro de los 10 segundos se enrutarán al siguiente tronco disponible; si no existen troncos adicionales, la llamada se perderá automáticamente. En una organización con redes y respuestas de puerta de enlace lentas, esto puede tener como resultado que se pierdan innecesariamente las llamadas.</span><span class="sxs-lookup"><span data-stu-id="f108a-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f108a-166">Usos asociados de la RTC</span><span class="sxs-lookup"><span data-stu-id="f108a-166">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="f108a-167">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="f108a-167">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="f108a-168">Recopilación de los usos de RTC asignados al tronco.</span><span class="sxs-lookup"><span data-stu-id="f108a-168">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f108a-169">Número traducido para probar</span><span class="sxs-lookup"><span data-stu-id="f108a-169">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="f108a-170">N/D</span><span class="sxs-lookup"><span data-stu-id="f108a-170">N/A</span></span></p></td>
<td><p><span data-ttu-id="f108a-171">Número telefónico que puede utilizarse para realizar una prueba ad hoc de la configuración del tronco.</span><span class="sxs-lookup"><span data-stu-id="f108a-171">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f108a-172">Reglas asociadas de traducción</span><span class="sxs-lookup"><span data-stu-id="f108a-172">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="f108a-173">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="f108a-173">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="f108a-174">Recopilación de reglas de traducción de números telefónicos que se aplican a las llamadas administradas por el Enrutamiento de salida (llamadas enrutadas a destinos PBX o RTC).</span><span class="sxs-lookup"><span data-stu-id="f108a-174">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f108a-175">Reglas de traducción de los números llamados</span><span class="sxs-lookup"><span data-stu-id="f108a-175">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="f108a-176">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="f108a-176">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="f108a-177">Colección de reglas de traducción para números de llamada saliente asignadas al tronco.</span><span class="sxs-lookup"><span data-stu-id="f108a-177">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f108a-178">Número de teléfono que se debe probar</span><span class="sxs-lookup"><span data-stu-id="f108a-178">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="f108a-179">N/D</span><span class="sxs-lookup"><span data-stu-id="f108a-179">N/A</span></span></p></td>
<td><p><span data-ttu-id="f108a-180">Número telefónico que puede utilizarse para realizar una prueba ad hoc de las reglas de traducción.</span><span class="sxs-lookup"><span data-stu-id="f108a-180">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f108a-181">Número de llamada</span><span class="sxs-lookup"><span data-stu-id="f108a-181">Calling number</span></span></p></td>
<td><p><span data-ttu-id="f108a-182">N/D</span><span class="sxs-lookup"><span data-stu-id="f108a-182">N/A</span></span></p></td>
<td><p><span data-ttu-id="f108a-183">Indica que el número de teléfono que se debe probar es el número telefónico de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="f108a-183">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f108a-184">Número llamado</span><span class="sxs-lookup"><span data-stu-id="f108a-184">Called number</span></span></p></td>
<td><p><span data-ttu-id="f108a-185">N/D</span><span class="sxs-lookup"><span data-stu-id="f108a-185">N/A</span></span></p></td>
<td><p><span data-ttu-id="f108a-186">Indica que el número de teléfono que se debe probar es el número telefónico de la persona llamada.</span><span class="sxs-lookup"><span data-stu-id="f108a-186">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f108a-187">Los cmdlets de Lync Server CsTrunkConfiguration admiten propiedades adicionales que no se muestran en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f108a-187">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="f108a-188">Para obtener más información, consulte el tema de ayuda del cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">set-CsTrunkConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="f108a-188">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="f108a-189">Para modificar las opciones de configuración del tronco SIP mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f108a-189">To modify SIP trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f108a-190">En el panel de control de Lync Server, haga clic en **enrutamiento de voz**y, a continuación, en **configuración de tronco**.</span><span class="sxs-lookup"><span data-stu-id="f108a-190">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="f108a-p113">En la pestaña **Configuración de tronco** haga doble clic en las opciones de configuración de troncos que se modificarán. Tenga en cuenta que solo puede editar un grupo de opciones de configuración a la vez. Si desea realizar los mismos cambios en varias colecciones, utilice Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f108a-p113">On the **Trunk Configuration** tab, double-click the trunk configuration settings to be modified. Note that you can only edit one collection of settings at a time. If you would like to make the same changes on multiple collections, use Windows PowerShell instead.</span></span>

3.  <span data-ttu-id="f108a-194">En el cuadro de diálogo **Editar configuración de tronco** , realice las selecciones apropiadas y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f108a-194">In the **Edit Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

4.  <span data-ttu-id="f108a-p114">La propiedad **Estado** de la recopilación se actualizará a **Sin confirmar**. Para confirmar los cambios y para eliminar la recopilación, haga clic en **Confirmar** y, a continuación, haga clic en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="f108a-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

5.  <span data-ttu-id="f108a-197">En el cuadro de diálogo **Configuración de voz sin confirmar**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f108a-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="f108a-198">En el cuadro de diálogo **Panel de control de Microsoft Lync Server 2013**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f108a-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

