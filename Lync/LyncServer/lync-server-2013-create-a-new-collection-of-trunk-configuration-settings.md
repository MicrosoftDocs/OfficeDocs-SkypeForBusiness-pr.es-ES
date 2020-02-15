---
title: 'Lync Server 2013: crear una nueva colección de opciones de configuración de tronco'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04392b4157f0c1a12b0bcfa9e7125183a76864cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="d6eb6-102">Crear una nueva colección de opciones de configuración de tronco en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6eb6-102">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6eb6-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d6eb6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d6eb6-p101">Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estos valores determinan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d6eb6-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="d6eb6-106">Si se debe habilitar el desvío de medios en los troncos.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="d6eb6-107">Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="d6eb6-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="d6eb6-108">Si se requiere o no el cifrado del protocolo de tiempo real seguro (SRTP) en cada tronco.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="d6eb6-109">Al instalar Microsoft Lync Server 2013, se crea una colección global de opciones de configuración de tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="d6eb6-110">Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).</span><span class="sxs-lookup"><span data-stu-id="d6eb6-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="d6eb6-111">Al crear opciones de configuración de tronco SIP mediante el panel de control de Lync Server, están disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d6eb6-111">When creating SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6eb6-112">Valor de IU</span><span class="sxs-lookup"><span data-stu-id="d6eb6-112">UI Setting</span></span></th>
<th><span data-ttu-id="d6eb6-113">Parámetro de PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6eb6-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="d6eb6-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6eb6-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6eb6-115">Name</span><span class="sxs-lookup"><span data-stu-id="d6eb6-115">Name</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-116">Identidad</span><span class="sxs-lookup"><span data-stu-id="d6eb6-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-p103">Identificador único para la colección. Esta propiedad es de solo lectura; no puede cambiar la Identidad de una colección o las opciones de configuración de troncos.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6eb6-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6eb6-119">Description</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6eb6-120">Description</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-121">Proporciona una manera para que los administradores almacenen información adicional acerca de la configuración (por ejemplo, el propósito de la configuración de troncos).</span><span class="sxs-lookup"><span data-stu-id="d6eb6-121">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6eb6-122">Cantidad máxima de cuadros de diálogo admitidos</span><span class="sxs-lookup"><span data-stu-id="d6eb6-122">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-123">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="d6eb6-123">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-124">La cantidad máxima de respuestas bifurcadas que puede recibir una puerta de enlace RTC, IP-PBX o SBC en el proveedor de servicio para una invitación enviada al Servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-124">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6eb6-125">Nivel de compatibilidad con el cifrado</span><span class="sxs-lookup"><span data-stu-id="d6eb6-125">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-126">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="d6eb6-126">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-127">Indica el nivel de apoyo para proteger el tráfico de medios entre el Servidor de mediación y la puerta de enlace RTC, IP-PBX, o SBC en el proveedor de servicio.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-127">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="d6eb6-128">Para los casos de desvío de medios, este valor debe ser compatible con la configuración de EncryptionLevel en la configuración de medios.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-128">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="d6eb6-129">La configuración de medios se establece con los cmdlets <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> y <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">set-CsMediaConfiguration</a> .</span><span class="sxs-lookup"><span data-stu-id="d6eb6-129">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="d6eb6-130">Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="d6eb6-130">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="d6eb6-131">Requeridos: debe usarse el cifrado SRTP.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-131">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="d6eb6-132">Opcional: el SRTP se utilizará si la puerta de enlace lo admite.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-132">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="d6eb6-133">No admitido: el cifrado SRTP no está admitido y, por lo tanto, no se utilizará.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-133">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="d6eb6-p105">El SRTPMode se utiliza solo si la puerta de enlace está configurada para usar la Seguridad de la capa de transporte (TLS). Si la puerta de enlace está configurada con el Protocolo de control de transporte (TCP) como transporte, el SRTPMode se configura internamente como No admitido.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6eb6-136">Hacer referencia al soporte</span><span class="sxs-lookup"><span data-stu-id="d6eb6-136">Refer support</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-137">Parámetro enable3pccrefer</span><span class="sxs-lookup"><span data-stu-id="d6eb6-137">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="d6eb6-138">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="d6eb6-138">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-139">Si se configura en <strong>Habilitar enviar referencia a la puerta de enlace</strong>, indica que el tronco admite la recepción de Solicitudes de referencia desde el Servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-139">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="d6eb6-140">Si está establecido como <strong>Habilitar la referencia mediante un control de llamadas de terceros</strong>, indica que el protocolo 3pcc puede ser utilizado para permitir llamadas transferidas para desviar el sitio hospedado.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-140">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="d6eb6-141">3pcc también se conoce como &quot;control de terceros&quot; y se produce cuando se usa un tercero para conectar un par de llamadores (por ejemplo, un operador que realiza una llamada de la persona a a la persona B).</span><span class="sxs-lookup"><span data-stu-id="d6eb6-141">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6eb6-142">Habilitar el desvío de medios</span><span class="sxs-lookup"><span data-stu-id="d6eb6-142">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-143">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="d6eb6-143">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-p107">Indica si la omisión de medios se encuentra habilitado para este tronco. La omisión de medios solo puede estar habilitada si el <strong>Procesamiento de medios centralizado</strong> también está habilitado.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6eb6-146">Procesamiento de medios centralizado</span><span class="sxs-lookup"><span data-stu-id="d6eb6-146">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-147">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="d6eb6-147">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-p108">Indica si existe un punto de terminación de medios conocido. (Un ejemplo de punto de terminación de medios conocido puede ser una puerta de enlace RTC donde una terminación de medios tiene la misma IP que la terminación de señal).</span><span class="sxs-lookup"><span data-stu-id="d6eb6-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6eb6-150">Habilitar el cierre RTP</span><span class="sxs-lookup"><span data-stu-id="d6eb6-150">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-151">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="d6eb6-151">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-p109">Indica si los troncos admiten o no el cierre RTP. El cierre RTP es una tecnología que permite la conectividad RTP/RTCP mediante un firewall o dispositivo NAT (traductor de direcciones de red).</span><span class="sxs-lookup"><span data-stu-id="d6eb6-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6eb6-154">Habilitar el historial de desvío de llamadas</span><span class="sxs-lookup"><span data-stu-id="d6eb6-154">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-155">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="d6eb6-155">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-156">Indica si la información del historial de llamadas se reenviará mediante el tronco.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-156">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6eb6-157">Habilitar los datos de reenvío de la identidad p-asserted</span><span class="sxs-lookup"><span data-stu-id="d6eb6-157">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-158">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="d6eb6-158">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-p110">Indica si el encabezado de la identidad p-asserted (PAI) se reenviará junto con la llamada. El encabezado PAI proporciona una forma de verificar la identidad de la persona que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6eb6-161">Habilitar el temporizador de desvío de conmutación por error saliente</span><span class="sxs-lookup"><span data-stu-id="d6eb6-161">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-162">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="d6eb6-162">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-p111">Indica que si las llamadas salientes no son respondidas por la puerta de enlace dentro de los 10 segundos se enrutarán al siguiente tronco disponible; si no existen troncos adicionales, la llamada se perderá automáticamente. En una organización con redes y respuestas de puerta de enlace lentas, esto puede tener como resultado que se pierdan innecesariamente las llamadas.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6eb6-165">Usos asociados de la RTC</span><span class="sxs-lookup"><span data-stu-id="d6eb6-165">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-166">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="d6eb6-166">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-167">Recopilación de los usos de RTC asignados al tronco.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-167">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6eb6-168">Número traducido para probar</span><span class="sxs-lookup"><span data-stu-id="d6eb6-168">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-169">N/D</span><span class="sxs-lookup"><span data-stu-id="d6eb6-169">N/A</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-170">Número telefónico que puede utilizarse para realizar una prueba ad hoc de la configuración del tronco.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-170">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6eb6-171">Reglas asociadas de traducción</span><span class="sxs-lookup"><span data-stu-id="d6eb6-171">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-172">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="d6eb6-172">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-173">Recopilación de reglas de traducción de números telefónicos que se aplican a las llamadas administradas por el Enrutamiento de salida (llamadas enrutadas a destinos PBX o RTC).</span><span class="sxs-lookup"><span data-stu-id="d6eb6-173">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6eb6-174">Reglas de traducción de los números llamados</span><span class="sxs-lookup"><span data-stu-id="d6eb6-174">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-175">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="d6eb6-175">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-176">Colección de reglas de traducción para números de llamada saliente asignadas al tronco.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-176">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6eb6-177">Número de teléfono que se debe probar</span><span class="sxs-lookup"><span data-stu-id="d6eb6-177">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-178">N/D</span><span class="sxs-lookup"><span data-stu-id="d6eb6-178">N/A</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-179">Número telefónico que puede utilizarse para realizar una prueba ad hoc de las reglas de traducción.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-179">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6eb6-180">Número de llamada</span><span class="sxs-lookup"><span data-stu-id="d6eb6-180">Calling number</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-181">N/D</span><span class="sxs-lookup"><span data-stu-id="d6eb6-181">N/A</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-182">Indica que el número de teléfono que se debe probar es el número telefónico de la persona que llama.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-182">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6eb6-183">Número llamado</span><span class="sxs-lookup"><span data-stu-id="d6eb6-183">Called number</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-184">N/D</span><span class="sxs-lookup"><span data-stu-id="d6eb6-184">N/A</span></span></p></td>
<td><p><span data-ttu-id="d6eb6-185">Indica que el número de teléfono que se debe probar es el número telefónico de la persona llamada.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-185">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="d6eb6-186">Los cmdlets de Lync Server CsTrunkConfiguration admiten propiedades adicionales que no se muestran en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-186">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="d6eb6-187">Para obtener más información, consulte el tema de ayuda del cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="d6eb6-187">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="d6eb6-188">Para crear nuevas opciones de configuración de tronco con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="d6eb6-188">To create new trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d6eb6-189">En el panel de control de Lync Server, haga clic en **enrutamiento de voz**y, a continuación, en **configuración de tronco**.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-189">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="d6eb6-190">En la pestaña **Configuración de tronco**, haga clic en **Nuevo** y luego haga clic en **Tronco de sitio** para crear el nuevo parámetro en el ámbito del sitio o en **Tronco de grupo** para crear el nuevo parámetro en el ámbito del servicio.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-190">On the **Trunk Configuration** tab, click **New**, and then click **Site trunk** to create the new settings at the site scope, or **Pool trunk** to create the new settings at the service scope.</span></span>

3.  <span data-ttu-id="d6eb6-p113">En el cuadro de diálogo **Seleccionar un sitio** o **Seleccionar un servicio** (el cuadro de diálogo que aparece depende de si va a crear parámetros de ámbito de sitio o ámbito de servicio) seleccione la ubicación para los nuevos parámetros de configuración y luego haga clic en **Aceptar**. Si el cuadro de diálogo está en blanco, significa que no hay lugar para crear los nuevos parámetros; por ejemplo, si el cuadro de diálogo **Seleccionar un sitio** está en blanco significa que todos los sitios ya se han asignado una colección de sitios de configuración del tronco y cada sitio (y cada servicio) solo puede alojar una de esas colecciones. En ese caso, puede eliminar la colección existente y crear una nueva o simplemente cambiar la colección existente.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-p113">In the **Select a Site** or the **Select a Service** dialog box (the dialog box that appears will depend on whether you are creating site-scoped or service-scoped settings) select the location for the new configuration settings and then click **OK**. If the dialog box is blank, that means there is no place to create the new settings; for example, if the **Select a Site** dialog box is blank that means that all of your sites have already been assigned a collection of trunk configuration sites, and each site (and each service) can only host one such collection. In that case, you can either delete the existing collection and create a new collection, or simply modify the existing collection.</span></span>

4.  <span data-ttu-id="d6eb6-194">En el cuadro de diálogo **Nueva configuración de tronco**, relacione las selecciones adecuadas y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-194">In the **New Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

5.  <span data-ttu-id="d6eb6-p114">La propiedad **Estado** de la colección se actualizará a **No confirmado**. Para confirmar los cambios y eliminar la colección, haga clic en **Confirmar** y luego en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

6.  <span data-ttu-id="d6eb6-197">En el cuadro de diálogo **Configuración de voz sin confirmar**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

7.  <span data-ttu-id="d6eb6-198">En el cuadro de diálogo **Panel de control de Microsoft Lync Server 2013**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d6eb6-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

