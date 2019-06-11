---
title: 'Lync Server 2013: proceso de implementación para el grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2151532b31f3c1660be98d11ac9d9c337ffecb64
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="cc733-102">Proceso de implementación para un grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc733-102">Deployment process for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc733-103">_**Última modificación del tema:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="cc733-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="cc733-104">Esta sección proporciona una descripción general de las fases y los pasos necesarios para implementar la aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="cc733-104">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="cc733-105">Proceso de implementación de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="cc733-105">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc733-106">Fase</span><span class="sxs-lookup"><span data-stu-id="cc733-106">Phase</span></span></th>
<th><span data-ttu-id="cc733-107">Pasos</span><span class="sxs-lookup"><span data-stu-id="cc733-107">Steps</span></span></th>
<th><span data-ttu-id="cc733-108">Permisos</span><span class="sxs-lookup"><span data-stu-id="cc733-108">Permissions</span></span></th>
<th><span data-ttu-id="cc733-109">Documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="cc733-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc733-110">Instalar la aplicación de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="cc733-110">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="cc733-111">La aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="cc733-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="cc733-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="cc733-112">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="cc733-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Implementación de telefonía IP empresarial en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cc733-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc733-114">Instalar componentes para grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="cc733-114">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="cc733-115">Los cmdlets de Lync Server, el panel de control de Lync Server, la herramienta de configuración de grupos de respuesta, la consola de inicio de sesión y cierre de sesión de los agentes y el servicio Web cliente de grupo de respuesta se instalan como parte de los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="cc733-115">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="cc733-116">Los servicios web se instalan al implementar un grupo de servidores Enterprise Edition o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cc733-116">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="cc733-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="cc733-117">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="cc733-118"><a href="lync-server-2013-deploying-lync-server.md">Implementar Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cc733-118"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc733-119">Habilitar usuarios para Lync 2013 y para telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="cc733-119">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="cc733-120">Habilitar usuarios que serán agentes de Lync Server y Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="cc733-120">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="cc733-121">Estos usuarios necesitan estar habilitados para agregarlos a grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="cc733-121">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="cc733-122">Normalmente, los usuarios están habilitados para Lync Server durante la implementación de servidor Standard Edition o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="cc733-122">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="cc733-123">Los usuarios están habilitados para telefonía IP empresarial durante la implementación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="cc733-123">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="cc733-124">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="cc733-124">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="cc733-125">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="cc733-125">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="cc733-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="cc733-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="cc733-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Deshabilitar o volver a habilitar la cuenta de usuario para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cc733-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="cc733-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Habilitar usuarios para telefonía IP empresarial en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cc733-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc733-129">Crear y configurar grupos de respuesta formados por grupos de agentes, colas y flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="cc733-129">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="cc733-130">Use el panel de control de Lync Server o el shell de administración de Lync Server para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cc733-130">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="cc733-131">Crear y configurar grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="cc733-131">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="cc733-132">Crear y configurar colas</span><span class="sxs-lookup"><span data-stu-id="cc733-132">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="cc733-133">De manera opcional, use el shell de administración de Lync Server para crear vacaciones y días laborables de grupo de respuesta predefinidos.</span><span class="sxs-lookup"><span data-stu-id="cc733-133">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="cc733-134">Use la herramienta de configuración de grupos de respuesta o el shell de administración de Lync Server para crear flujos de trabajo (grupos de captura o flujos de llamada de voz interactiva (IVR), incluidos los días laborables y las horas laborables de grupo de respuesta personalizado.</span><span class="sxs-lookup"><span data-stu-id="cc733-134">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="cc733-135">Puede acceder a la herramienta de configuración de grupos de respuesta a través del panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cc733-135">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="cc733-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="cc733-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="cc733-137">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="cc733-137">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="cc733-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="cc733-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="cc733-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="cc733-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="cc733-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="cc733-140">CsAdministrator</span></span></p>
<p><span data-ttu-id="cc733-141">AdministradorGrupoRespuestaCs</span><span class="sxs-lookup"><span data-stu-id="cc733-141">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="cc733-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Crear grupos de agentes de grupos de respuesta en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cc733-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="cc733-143"><a href="lync-server-2013-create-response-group-queues.md">Crear colas de grupo de respuesta en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cc733-143"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="cc733-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">Faculta Definir las horas de trabajo del grupo de respuesta en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cc733-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="cc733-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Faculta Definir conjuntos de días festivos de grupos de respuesta en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cc733-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="cc733-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Crear o modificar un flujo de trabajo en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cc733-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc733-147">(Opcional) Personalizar la configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="cc733-147">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="cc733-148">Use el shell de administración de Lync Server para personalizar la configuración predeterminada de música en espera, el archivo de audio de música activa predeterminada, el período de gracia de timbre de timbre y la configuración de contexto de llamada.</span><span class="sxs-lookup"><span data-stu-id="cc733-148">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="cc733-149">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="cc733-149">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="cc733-150">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="cc733-150">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="cc733-151">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="cc733-151">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="cc733-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="cc733-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="cc733-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="cc733-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="cc733-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Administrar la configuración de grupo de respuesta de nivel de aplicación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cc733-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc733-155">(Opcional) Delegar la administración de los grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="cc733-155">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="cc733-156">Asigne a los usuarios el rol CsResponseGroupManager para delegar la configuración de grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="cc733-156">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="cc733-157">Los administradores de grupos de respuesta pueden configurar los grupos de respuesta que tienen asignados.</span><span class="sxs-lookup"><span data-stu-id="cc733-157">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="cc733-158">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="cc733-158">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="cc733-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="cc733-159">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="cc733-160">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="cc733-160">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="cc733-161">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="cc733-161">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="cc733-162">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="cc733-162">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="cc733-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planeación del control de acceso basado en roles en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="cc733-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc733-164">Comprobar la implementación del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="cc733-164">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="cc733-165">Compruebe los mensajes de contestador automático del grupo de búsqueda y los flujos de trabajo de respuestas de voz interactiva para asegurarse de que la configuración funcione según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="cc733-165">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

