---
title: 'Lync Server 2013: proceso de implementación para la recogida de llamadas grupales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0ed92300ae3445019b7b6fc0bba4d73b91c980e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="ef651-102">Proceso de implementación para la recogida de llamadas grupales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef651-102">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef651-103">_**Última modificación del tema:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="ef651-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="ef651-104">En esta sección se proporciona información general sobre los pasos necesarios para implementar la recogida de llamadas de grupo.</span><span class="sxs-lookup"><span data-stu-id="ef651-104">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="ef651-105">Debe implementar Enterprise Edition o Standard Edition con Enterprise Voice antes de configurar la atención de llamadas grupales.</span><span class="sxs-lookup"><span data-stu-id="ef651-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="ef651-106">Los componentes requeridos por la atención de llamadas grupales están instalados y habilitados al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="ef651-106">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="ef651-107">Proceso de implementación de recogida de llamadas grupales</span><span class="sxs-lookup"><span data-stu-id="ef651-107">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef651-108">Fase</span><span class="sxs-lookup"><span data-stu-id="ef651-108">Phase</span></span></th>
<th><span data-ttu-id="ef651-109">Pasos</span><span class="sxs-lookup"><span data-stu-id="ef651-109">Steps</span></span></th>
<th><span data-ttu-id="ef651-110">Grupos y roles necesarios</span><span class="sxs-lookup"><span data-stu-id="ef651-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="ef651-111">Documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="ef651-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef651-112">Habilitar la herramienta del kit de recursos de SEFAUtil en la topología</span><span class="sxs-lookup"><span data-stu-id="ef651-112">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ef651-113">Use el cmdlet <strong>New-CsTrustedApplicationPool</strong> para crear un nuevo grupo de aplicaciones de confianza.</span><span class="sxs-lookup"><span data-stu-id="ef651-113">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="ef651-114">Use el cmdlet <strong>New-CsTrustedApplication</strong> para especificar la herramienta SEFAUtil como aplicación de confianza.</span><span class="sxs-lookup"><span data-stu-id="ef651-114">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="ef651-115">Ejecute el cmdlet <strong>enable-CsTopology</strong> para habilitar la topología.</span><span class="sxs-lookup"><span data-stu-id="ef651-115">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="ef651-116">Instale las herramientas del kit de recursos en un servidor front-end que se encuentra en el grupo de aplicaciones de confianza creado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="ef651-116">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="ef651-117">Compruebe que SEFAUtil se está ejecutando correctamente; para ello, ejecute el para mostrar la configuración de desvío de llamadas de un usuario en la implementación.</span><span class="sxs-lookup"><span data-stu-id="ef651-117">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ef651-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ef651-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="ef651-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Implementar la herramienta SEFAUtil en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ef651-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef651-120">Configurar intervalos de números de llamada de llamadas en la tabla de órbitas de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="ef651-120">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="ef651-121">Use el cmdlet <strong>New-CSCallParkOrbit</strong> para crear intervalos de números de atención de llamadas en la tabla de órbitas de estacionamiento de llamadas y asignar el tipo GroupPickup a los intervalos de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ef651-121">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ef651-122">Debe usar el shell de administración de Lync Server para crear, modificar, quitar y ver intervalos de números de llamada de llamadas de grupo en la tabla de órbitas de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ef651-122">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="ef651-123">Los intervalos de números de llamada de grupo no están disponibles en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ef651-123">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="ef651-124">Para la integración perfecta con los planes de marcado existentes, los intervalos de números se suelen configurar como un bloque de extensiones virtuales.</span><span class="sxs-lookup"><span data-stu-id="ef651-124">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="ef651-125">No se admite la asignación de números de llamada directa (DID) como números de intervalo en la tabla de órbitas de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ef651-125">Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="ef651-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ef651-126">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ef651-127">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="ef651-127">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="ef651-128">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ef651-128">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="ef651-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ef651-129">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ef651-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configurar números de grupo de atención de llamadas en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ef651-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef651-131">Asignar un número de llamada de llamada a los usuarios y habilitar la atención de llamadas grupales para los usuarios</span><span class="sxs-lookup"><span data-stu-id="ef651-131">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="ef651-132">Use el parámetro/enablegrouppickup de la herramienta del kit de recursos de SEFAUtil para habilitar la atención de llamadas grupales y asignar un número de llamada para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ef651-132">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="ef651-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Habilitar la atención de llamadas grupales para los usuarios en Lync Server 2013 y asignar un número de grupo</a></span><span class="sxs-lookup"><span data-stu-id="ef651-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef651-134">Notificar a los usuarios el número de atención de llamadas que tienen asignado y cualquier otro número de interés</span><span class="sxs-lookup"><span data-stu-id="ef651-134">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="ef651-135">Como cualquier usuario puede recuperar una llamada realizada a un usuario de llamada de llamada de grupo, es posible que los usuarios deseen supervisar más de un grupo.</span><span class="sxs-lookup"><span data-stu-id="ef651-135">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="ef651-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Comunicar las asignaciones de atención de llamadas grupales a los usuarios en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ef651-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef651-137">Comprobar la implementación de llamada de grupo</span><span class="sxs-lookup"><span data-stu-id="ef651-137">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="ef651-138">Pruebe la colocación y recuperación de llamadas para asegurarse de que la configuración funciona como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="ef651-138">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="ef651-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Opcional Comprobar la implementación de la llamada de grupo en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ef651-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

