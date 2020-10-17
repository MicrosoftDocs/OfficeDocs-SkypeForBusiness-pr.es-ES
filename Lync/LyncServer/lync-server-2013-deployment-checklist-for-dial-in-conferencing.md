---
title: Lync Server 2013 lista de comprobación para la implementación de la Conferencia de acceso telefónico local
description: Lync Server 2013 lista de comprobación para la implementación de la Conferencia de acceso telefónico local.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 743b5120bf011ab8467679bea9869a46231b0835
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568366"
---
# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="6cd75-103">Lista de comprobación para la implementación de la Conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6cd75-103">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cd75-104">_**Última modificación del tema:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="6cd75-104">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="6cd75-105">Los componentes necesarios para conferencias de acceso telefónico local se implementan al implementar la carga de trabajo de conferencias.</span><span class="sxs-lookup"><span data-stu-id="6cd75-105">The components required for dial-in conferencing are deployed when you deploy the conferencing workload.</span></span> <span data-ttu-id="6cd75-106">Para poder configurar la Conferencia de acceso telefónico local, debe implementar la telefonía IP empresarial o un servidor de mediación y una puerta de enlace de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="6cd75-106">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and a public switched telephone network (PSTN) gateway.</span></span>

<span data-ttu-id="6cd75-107">Todos los pasos indicados en la tabla siguiente deben realizarse antes de que los usuarios puedan obtener acceso telefónico desde la RTC para unirse a una conferencia de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="6cd75-107">All the steps in the following table must be performed before users can dial in from the PSTN to join an audio/video conference.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6cd75-108">Si va a migrar desde Office Communications Server 2007 R2, debe aplicar las actualizaciones más recientes en el entorno de Office Communications Server 2007 R2 antes de implementar la Conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="6cd75-108">If you are migrating from Office Communications Server 2007 R2, you must apply the latest updates to your Office Communications Server 2007 R2 environment before deploying dial-in conferencing.</span></span>



</div>

### <a name="dial-in-conferencing-deployment-process"></a><span data-ttu-id="6cd75-109">Proceso de implementación de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="6cd75-109">Dial-in Conferencing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6cd75-110">Fase</span><span class="sxs-lookup"><span data-stu-id="6cd75-110">Phase</span></span></th>
<th><span data-ttu-id="6cd75-111">Pasos</span><span class="sxs-lookup"><span data-stu-id="6cd75-111">Steps</span></span></th>
<th><span data-ttu-id="6cd75-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="6cd75-112">Permissions</span></span></th>
<th><span data-ttu-id="6cd75-113">Documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="6cd75-113">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6cd75-114"><strong>Crear una topología que incluya la carga de trabajo de conferencias, incluido un servidor de mediación y una puerta de enlace RTC e implementar el grupo de servidores front-end o el servidor Standard Edition</strong></span><span class="sxs-lookup"><span data-stu-id="6cd75-114"><strong>Create a topology that includes the Conferencing workload, including a Mediation Server and PSTN gateway, and deploy the Front End pool or Standard Edition server</strong></span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="6cd75-115">Ejecute el generador de topologías para configurar la topología.</span><span class="sxs-lookup"><span data-stu-id="6cd75-115">Run Topology Builder to configure your topology.</span></span> <span data-ttu-id="6cd75-116">Mientras configura la topología, seleccione la opción de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="6cd75-116">While configuring the topology, select the dial-in conferencing option.</span></span></p></li>
<li><p><span data-ttu-id="6cd75-117">Publique la topología e implemente el grupo de servidores front-end o el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6cd75-117">Publish the topology and deploy the Front End pool or Standard Edition server.</span></span></p></li>
<li><p><span data-ttu-id="6cd75-118">Si es necesario, cree un servidor de mediación independiente y asócielo a una puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="6cd75-118">If necessary, create a stand-alone Mediation Server and associate it with a PSTN gateway.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6cd75-119">Este paso solo es necesario si no implementa la telefonía IP empresarial y no combinar el servidor de mediación con el servidor Standard Edition o el servidor de EditionFront de empresa.</span><span class="sxs-lookup"><span data-stu-id="6cd75-119">This step is required only if you do not deploy Enterprise Voice and do not collocate the Mediation Server with the Enterprise EditionFront End Server or Standard Edition server.</span></span> <span data-ttu-id="6cd75-120">Si implementa la telefonía IP empresarial, instale y configure los servidores de mediación y las puertas de enlace RTC como parte de la implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="6cd75-120">If you deploy Enterprise Voice, you install and configure Mediation Servers and PSTN gateways as part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="6cd75-121">Si combinar el servidor de mediación, instale y configure el servidor de mediación como parte de la implementación del servidor Standard Edition o el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="6cd75-121">If you collocate the Mediation Server, you install and configure the Mediation Server as part of the Front End pool or Standard Edition server deployment.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="6cd75-122">Administradores de dominio</span><span class="sxs-lookup"><span data-stu-id="6cd75-122">Domain Admins</span></span></p>
<p><span data-ttu-id="6cd75-123">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6cd75-123">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="6cd75-124">Administrador</span><span class="sxs-lookup"><span data-stu-id="6cd75-124">Administrator</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6cd75-125"><a href="lync-server-2013-deploying-lync-server.md">Implementar Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6cd75-125"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="6cd75-126">Para crear un grupo de servidores de mediación independiente: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">implementación de servidores de mediación y definición de pares en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6cd75-126">To create a stand-alone Mediation Server pool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd75-127"><strong>Configurar planes de marcado</strong></span><span class="sxs-lookup"><span data-stu-id="6cd75-127"><strong>Configure dial plans</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd75-128">Un plan de marcado es un conjunto de reglas de normalización de números de teléfono que convierten los números de teléfono marcados desde una ubicación determinada a un formato estándar único (E.164) para la autorización telefónica y el enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6cd75-128">A dial plan is a set of phone number normalization rules that translate phone numbers dialed from a specific location to a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="6cd75-129">El mismo número de teléfono marcado desde diferentes ubicaciones puede, basándose en los respectivos planes de marcado, resolverse en diferentes números E.164, según cada ubicación.</span><span class="sxs-lookup"><span data-stu-id="6cd75-129">The same phone number dialed from different locations can, based on the respective dial plans, resolve to different E.164 numbers, as appropriate to each location.</span></span> <span data-ttu-id="6cd75-130">Si implementa la telefonía IP empresarial, puede configurar planes de marcado como parte de esa implementación y debe asegurarse de que los planes de marcado también admiten las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="6cd75-130">If you deploy Enterprise Voice, you set up dial plans as part of that deployment, and you need to make sure that the dial plans also accommodate dial-in conferencing.</span></span> <span data-ttu-id="6cd75-131">Si no implementa la telefonía IP empresarial, debe configurar planes de marcado para las conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="6cd75-131">If you do not deploy Enterprise Voice, you need to set up dial plans for dial-in conferencing.</span></span></p>
<p><span data-ttu-id="6cd75-132">Use el panel de control de Lync Server 2013 o el shell de administración de Lync Server para configurar planes de marcado de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6cd75-132">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial plans as follows:</span></span></p>
<ol>
<li><p><span data-ttu-id="6cd75-133">Cree uno o más planes de marcado para enrutar números de teléfono de acceso.</span><span class="sxs-lookup"><span data-stu-id="6cd75-133">Create one or more dial plans for routing dial-in access phone numbers.</span></span></p></li>
<li><p><span data-ttu-id="6cd75-p105">Asigne un plan de marcado predeterminado a cada grupo de servidores. Defina <strong>Región de conferencia de acceso telefónico local</strong> en la ubicación geográfica a la que debe aplicarse el plan de marcado. La región asocia el plan de marcado con números de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="6cd75-p105">Assign a default dial plan to each pool. Set the <strong>Dial-in conferencing region</strong> to the geographic location to which the dial plan applies. The region associates the dial plan with dial-in access numbers.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="6cd75-137">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6cd75-137">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="6cd75-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="6cd75-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="6cd75-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-140">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="6cd75-141"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configurar planes de marcado para las conferencias de acceso telefónico local en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6cd75-141"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configure dial plans for dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd75-142"><strong>Asegurarse de que los planes de marcado tienen regiones asignadas</strong></span><span class="sxs-lookup"><span data-stu-id="6cd75-142"><strong>Make sure that dial plans are assigned regions</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd75-143">Ejecute los cmdlets <strong>Get-CsDialPlan</strong> y <strong>set-CsDialPlan</strong> para asegurarse de que todos los planes de marcado tengan una región asignada.</span><span class="sxs-lookup"><span data-stu-id="6cd75-143">Run the <strong>Get-CsDialPlan</strong> and <strong>Set-CsDialPlan</strong> cmdlets to make sure that all dial plans have a region assigned.</span></span></p></td>
<td><p><span data-ttu-id="6cd75-144">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6cd75-144">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="6cd75-145">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-145">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="6cd75-146">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-146">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="6cd75-147">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-147">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="6cd75-148"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Asegurarse de que los planes de marcado Lync Server 2013 tienen regiones asignadas</a></span><span class="sxs-lookup"><span data-stu-id="6cd75-148"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Make sure dial plans Lync Server 2013 have assigned regions</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd75-149"><strong>(Opcional) Comprobar o modificar los requisitos del número de identificación personal de los usuarios (PIN)</strong></span><span class="sxs-lookup"><span data-stu-id="6cd75-149"><strong>(Optional) Verify or modify user personal identification number (PIN) requirements</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd75-150">Use el panel de control de Lync Server 2013 o el shell de administración de Lync Server para ver o modificar la <strong>Directiva de PIN</strong>de conferencia.</span><span class="sxs-lookup"><span data-stu-id="6cd75-150">Use Lync Server 2013 Control Panel or Lync Server Management Shell to view or modify the Conferencing <strong>PIN Policy</strong>.</span></span> <span data-ttu-id="6cd75-151">Puede especificar la longitud mínima del PIN, el número máximo de intentos de inicio de sesión, la expiración del PIN y si es posible usar patrones comunes.</span><span class="sxs-lookup"><span data-stu-id="6cd75-151">You can specify minimum PIN length, maximum number of logon attempts, PIN expiration, and whether common patterns are allowable.</span></span></p></td>
<td><p><span data-ttu-id="6cd75-152">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6cd75-152">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="6cd75-153">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-153">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="6cd75-154">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-154">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="6cd75-155"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">Opcional Comprobar la configuración de la Directiva de PIN en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6cd75-155"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Optional) Verify PIN policy settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd75-156"><strong>Configurar la directiva de conferencias para admitir conferencias de acceso telefónico local</strong></span><span class="sxs-lookup"><span data-stu-id="6cd75-156"><strong>Configure conferencing policy to support dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd75-157">Use el panel de control de Lync Server 2013 o el shell de administración de Lync Server para configurar las opciones de <strong>Directiva de conferencia</strong> .</span><span class="sxs-lookup"><span data-stu-id="6cd75-157">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure <strong>Conferencing Policy</strong> settings.</span></span> <span data-ttu-id="6cd75-158">Especifique si:</span><span class="sxs-lookup"><span data-stu-id="6cd75-158">Specify whether:</span></span></p>
<ul>
<li><p><span data-ttu-id="6cd75-159">Está habilitado el acceso telefónico a conferencias por RTC.</span><span class="sxs-lookup"><span data-stu-id="6cd75-159">PSTN conference dial-in is enabled.</span></span></p></li>
<li><p><span data-ttu-id="6cd75-160">Los usuarios pueden invitar a participantes anónimos.</span><span class="sxs-lookup"><span data-stu-id="6cd75-160">Users can invite anonymous participants.</span></span></p></li>
<li><p><span data-ttu-id="6cd75-p108">Los usuarios no autenticados pueden unirse a una conferencia mediante llamadas de salida. Mediante las llamadas de salida, el servidor de conferencia llama al usuario y el usuario responde al teléfono para unirse a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="6cd75-p108">Unauthenticated users can join a conference by using dial-out phoning. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="6cd75-163">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6cd75-163">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="6cd75-164">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-164">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="6cd75-165">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-165">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="6cd75-166"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configurar la Directiva de conferencias para el acceso telefónico en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6cd75-166"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configure conferencing policy for dial-in in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd75-167"><strong>Configurar números de acceso telefónico</strong></span><span class="sxs-lookup"><span data-stu-id="6cd75-167"><strong>Configure dial-in access numbers</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd75-168">Use el panel de control de Lync Server 2013 o el shell de administración de Lync Server para configurar los números de acceso telefónico local que los usuarios llaman para llamar a una conferencia y especificar las regiones que asocian el número de acceso con los planes de marcado adecuados.</span><span class="sxs-lookup"><span data-stu-id="6cd75-168">Use Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial-in access numbers that users call to dial in to a conference, and specify the regions that associate the access number with the appropriate dial plans.</span></span> <span data-ttu-id="6cd75-169">Los tres primeros números de acceso de la región especificada por el plan de marcado del organizador se incluyen en la invitación a la conferencia.</span><span class="sxs-lookup"><span data-stu-id="6cd75-169">The first three access numbers for the region specified by the organizer's dial plan are included in the conference invitation.</span></span> <span data-ttu-id="6cd75-170">Todos los números de acceso están disponibles en la página Configuración de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="6cd75-170">All access numbers are available on the Dial-in Conferencing Settings page.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6cd75-171">Después de crear los números de acceso telefónico local, puede usar el cmdlet <STRONG>set-CsDialInConferencingAccessNumber</STRONG> para modificar el nombre para mostrar de los objetos de contacto de Active Directory de modo que los usuarios puedan identificar más fácilmente el número de acceso correcto.</span><span class="sxs-lookup"><span data-stu-id="6cd75-171">After you create dial-in access numbers, you can use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name of the Active Directory contact objects so that users can more easily identify the correct access number.</span></span>


</div></td>
<td><p><span data-ttu-id="6cd75-172">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6cd75-172">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="6cd75-173">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-173">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="6cd75-174">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-174">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="6cd75-175"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configurar los números de acceso de conferencia de acceso telefónico local en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6cd75-175"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configure dial-in conferencing access numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd75-176"><strong>(Opcional) Comprobar la configuración de conferencia de acceso telefónico local</strong></span><span class="sxs-lookup"><span data-stu-id="6cd75-176"><strong>(Optional) Verify dial-in conferencing settings</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd75-177">Use el cmdlet <strong>Get-CsDialinConferencingAccessNumber</strong> para buscar planes de marcado que tengan una región de conferencia de acceso telefónico local que no sea usada por ningún número de acceso, así como números de acceso que no tengan asignada ninguna región.</span><span class="sxs-lookup"><span data-stu-id="6cd75-177">Use the <strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet to search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have no region assigned.</span></span></p></td>
<td><p><span data-ttu-id="6cd75-178">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6cd75-178">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="6cd75-179">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-179">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="6cd75-180">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-180">CsAdministrator</span></span></p>
<p><span data-ttu-id="6cd75-181">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-181">CsViewOnlyAdministrator</span></span></p>
<p><span data-ttu-id="6cd75-182">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="6cd75-182">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="6cd75-183"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">Opcional Comprobar la configuración de conferencia de acceso telefónico local en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6cd75-183"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Optional) Verify dial-in conferencing settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd75-184"><strong>(Opcional) Modificar la asignación de teclas de comandos DTMF</strong></span><span class="sxs-lookup"><span data-stu-id="6cd75-184"><strong>(Optional) Modify key mapping of DTMF commands</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd75-185">Use el cmdlet <strong>Set-CsDialinConferencingDtmfConfiguration</strong> para modificar las teclas usadas para comandos de tono de marcado de frecuencia múltiple (DTMF) que los participantes pueden usar para controlar la configuración de la conferencia (como activar y desactivar el audio o bloquear y desbloquear la conferencia).</span><span class="sxs-lookup"><span data-stu-id="6cd75-185">Use the <strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet to modify the keys used for dual-tone multifrequency (DTMF) commands, which participants can use to control conference settings (such as mute and unmute or lock and unlock).</span></span></p></td>
<td><p><span data-ttu-id="6cd75-186">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6cd75-186">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="6cd75-187">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-187">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="6cd75-188">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-188">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="6cd75-189"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">Opcional Modificar la asignación de teclas para comandos DTMF en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6cd75-189"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd75-190"><strong>(Opcional) Modificar el comportamiento de los anuncios al unirse y abandonar conferencias</strong></span><span class="sxs-lookup"><span data-stu-id="6cd75-190"><strong>(Optional) Modify conference join and leave announcement behavior</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd75-191">Use el cmdlet <strong>Set-CsDialinConferencingConfiguration</strong> para cambiar el funcionamiento de los anuncios cuando los participantes se unen a conferencias o las abandonan.</span><span class="sxs-lookup"><span data-stu-id="6cd75-191">Use the <strong>Set-CsDialinConferencingConfiguration</strong> to change how announcements work when participants join and leave conferences.</span></span></p></td>
<td><p><span data-ttu-id="6cd75-192">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6cd75-192">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="6cd75-193">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-193">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="6cd75-194">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-194">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="6cd75-195"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">Opcional Habilitar y deshabilitar la Unión a Conferencia y dejar anuncios en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6cd75-195"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd75-196"><strong>(Opcional) Comprobar la conferencia de acceso telefónico local</strong></span><span class="sxs-lookup"><span data-stu-id="6cd75-196"><strong>(Optional) Verify dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd75-197">Use el cmdlet <strong>Test-CsDialInConferencing</strong> para comprobar si los números de acceso del grupo de servidores especificado funcionan correctamente.</span><span class="sxs-lookup"><span data-stu-id="6cd75-197">Use the <strong>Test-CsDialInConferencing</strong> cmdlet to test that the access numbers for the specified pool work correctly.</span></span></p></td>
<td><p><span data-ttu-id="6cd75-198">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6cd75-198">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="6cd75-199">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-199">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="6cd75-200">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-200">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="6cd75-201"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">Opcional Comprobar la Conferencia de acceso telefónico local en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6cd75-201"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Optional) Verify dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd75-202"><strong>Implementación del complemento de conferencia en línea para Lync 2013</strong></span><span class="sxs-lookup"><span data-stu-id="6cd75-202"><strong>Deploy the Online Meeting Add-in for Lync 2013</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd75-203">Implemente el complemento de conferencia en línea para Lync 2013 para que los usuarios puedan programar conferencias que admitan conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="6cd75-203">Deploy the Online Meeting Add-in for Lync 2013 so that users can schedule conferences that support dial-in conferencing.</span></span> <span data-ttu-id="6cd75-204">El complemento para reunión en línea para Lync 2013 se instala automáticamente al instalar Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6cd75-204">The Online Meeting Add-in for Lync 2013 is installed automatically when you install Lync 2013.</span></span></p></td>
<td><p><span data-ttu-id="6cd75-205">Administradores</span><span class="sxs-lookup"><span data-stu-id="6cd75-205">Administrators</span></span></p></td>
<td><p><span data-ttu-id="6cd75-206"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Implementación del complemento de conferencia en línea para Lync 2013</a></span><span class="sxs-lookup"><span data-stu-id="6cd75-206"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Deploy the Online Meeting Add-in for Lync 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd75-207"><strong>Configurar la cuenta de usuario</strong></span><span class="sxs-lookup"><span data-stu-id="6cd75-207"><strong>Configure user account settings</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd75-208">Use el panel de control de Lync Server 2013 o el shell de administración de Lync Server para configurar el <strong>URI de línea</strong> de telefonía como un número de teléfono único y normalizado (por ejemplo, Tel: + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="6cd75-208">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure the telephony <strong>Line URI</strong> as a unique, normalized phone number (for example, tel:+14255550200).</span></span></p></td>
<td><p><span data-ttu-id="6cd75-209">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6cd75-209">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="6cd75-210">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-210">CsAdministrator</span></span></p>
<p><span data-ttu-id="6cd75-211">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="6cd75-211">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="6cd75-212"><a href="lync-server-2013-configure-user-account-settings.md">Configurar las opciones de cuenta de usuario en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6cd75-212"><a href="lync-server-2013-configure-user-account-settings.md">Configure user account settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6cd75-213">Recomenda Configurar directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="6cd75-213">(Recommended) Configure conference directories</span></span></p></td>
<td><p><span data-ttu-id="6cd75-214">Use el cmdlet <strong>New-CsConferenceDirectory</strong> para crear un directorio de conferencia para cada 999 usuarios del grupo.</span><span class="sxs-lookup"><span data-stu-id="6cd75-214">Use the <strong>New-CsConferenceDirectory</strong> cmdlet to create one conference directory for every 999 users in the pool.</span></span></p></td>
<td><p><span data-ttu-id="6cd75-215">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6cd75-215">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="6cd75-216"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Requisitos de conferencia de acceso telefónico local en Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(recomendado) crear directorios de conferencia</a></span><span class="sxs-lookup"><span data-stu-id="6cd75-216"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Recommended) Create Conference Directories</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cd75-217"><strong>(Opcional) Dar la bienvenida a los usuarios a la conferencia de acceso telefónico local y definir el PIN inicial</strong></span><span class="sxs-lookup"><span data-stu-id="6cd75-217"><strong>(Optional) Welcome users to dial-in conferencing and set the initial PIN</strong></span></span></p></td>
<td><p><span data-ttu-id="6cd75-218">Use el script <strong>set-CsPinSendCAWelcomeMail</strong> para establecer los pin iniciales de los usuarios y enviar un correo electrónico de bienvenida que contenga el PIN inicial y un vínculo a la página de configuración de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="6cd75-218">Use the <strong>Set-CsPinSendCAWelcomeMail</strong> script to set users' initial PINs and send a welcome email that contains the initial PIN and a link to the Dial-in Conferencing Settings page.</span></span></p></td>
<td><p><span data-ttu-id="6cd75-219">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6cd75-219">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="6cd75-220"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">Opcional Le damos la bienvenida a los usuarios a conferencias de acceso telefónico local en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="6cd75-220"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

