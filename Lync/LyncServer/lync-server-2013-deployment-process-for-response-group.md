---
title: 'Lync Server 2013: proceso de implementación de grupo de respuesta'
description: 'Lync Server 2013: proceso de implementación de grupo de respuesta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b50fb7903a2fcc301bbf435013b8f8df4e775a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551036"
---
# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="ba706-103">Proceso de implementación del grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba706-103">Deployment process for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba706-104">_**Última modificación del tema:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="ba706-104">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="ba706-105">En esta sección se proporciona información general sobre las fases y los pasos necesarios para implementar la aplicación grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="ba706-105">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="ba706-106">Proceso de implementación de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="ba706-106">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba706-107">Fase</span><span class="sxs-lookup"><span data-stu-id="ba706-107">Phase</span></span></th>
<th><span data-ttu-id="ba706-108">Pasos</span><span class="sxs-lookup"><span data-stu-id="ba706-108">Steps</span></span></th>
<th><span data-ttu-id="ba706-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="ba706-109">Permissions</span></span></th>
<th><span data-ttu-id="ba706-110">Documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="ba706-110">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba706-111">Instalar la aplicación de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="ba706-111">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="ba706-112">La aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="ba706-112">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="ba706-113">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ba706-113">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="ba706-114"><a href="lync-server-2013-deploying-enterprise-voice.md">Implementar la telefonía IP empresarial en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba706-114"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba706-115">Instalación de componentes para el grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="ba706-115">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="ba706-116">Los cmdlets de Lync Server, el panel de control de Lync Server, la herramienta de configuración de grupos de respuesta, la consola de inicio y de cierre de sesión de los agentes y el servicio Web de cliente del grupo de respuesta se instalan como parte de los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="ba706-116">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="ba706-117">Los servicios web se instalan al implementar un grupo de Enterprise Edition o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ba706-117">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="ba706-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ba706-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="ba706-119"><a href="lync-server-2013-deploying-lync-server.md">Implementar Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba706-119"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba706-120">Habilitar usuarios para Lync 2013 y Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="ba706-120">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="ba706-121">Habilite a los usuarios que van a ser agentes para Lync Server y Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ba706-121">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="ba706-122">Los usuarios deben estar habilitados antes de poder agregarlos a grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="ba706-122">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="ba706-123">Normalmente, los usuarios están habilitados para Lync Server durante la implementación de servidor Standard Edition o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="ba706-123">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="ba706-124">Los usuarios están habilitados para telefonía IP empresarial durante la implementación de la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="ba706-124">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="ba706-125">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="ba706-125">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="ba706-126">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba706-126">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="ba706-127">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba706-127">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ba706-128"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Deshabilitar o volver a habilitar la cuenta de usuario para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba706-128"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="ba706-129"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Habilitar a los usuarios para la telefonía IP empresarial en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba706-129"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba706-130">Creación y configuración de grupos de respuesta formados por grupos de agentes, colas y flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="ba706-130">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ba706-131">Use el panel de control de Lync Server o el shell de administración de Lync Server para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba706-131">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="ba706-132">Crear y configurar grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="ba706-132">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="ba706-133">Crear y configurar colas</span><span class="sxs-lookup"><span data-stu-id="ba706-133">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="ba706-134">De forma opcional, use el shell de administración de Lync Server para crear días laborables y horas laborables para el grupo de respuesta predefinido.</span><span class="sxs-lookup"><span data-stu-id="ba706-134">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="ba706-135">Use la herramienta de configuración del grupo de respuesta o el shell de administración de Lync Server para crear flujos de trabajo (grupos de extensiones o flujos de llamadas de respuesta de voz interactiva (IVR), incluido el horario laboral del grupo de respuesta personalizado y los días festivos.</span><span class="sxs-lookup"><span data-stu-id="ba706-135">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ba706-136">Puede obtener acceso a la herramienta de configuración del grupo de respuesta a través del panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ba706-136">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="ba706-137">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ba706-137">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ba706-138">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba706-138">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="ba706-139">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba706-139">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="ba706-140">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba706-140">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="ba706-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba706-141">CsAdministrator</span></span></p>
<p><span data-ttu-id="ba706-142">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="ba706-142">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="ba706-143"><a href="lync-server-2013-create-response-group-agent-groups.md">Crear grupos de agentes de grupo de respuesta Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba706-143"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="ba706-144"><a href="lync-server-2013-create-response-group-queues.md">Crear colas de grupo de respuesta en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba706-144"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="ba706-145"><a href="lync-server-2013-optional-define-response-group-business-hours.md">Opcional Definir el horario comercial del grupo de respuesta en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba706-145"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="ba706-146"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Opcional Definir conjuntos de días festivos para grupos de respuesta en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba706-146"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="ba706-147"><a href="lync-server-2013-create-or-modify-a-workflow.md">Crear o modificar un flujo de trabajo en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba706-147"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba706-148">(Opcional) Personalización de la configuración de nivel de aplicación</span><span class="sxs-lookup"><span data-stu-id="ba706-148">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="ba706-149">Use el shell de administración de Lync Server para personalizar la configuración predeterminada de la música en espera, el archivo de audio de música en espera predeterminado, el período de gracia de timbre del agente y la configuración del contexto de llamada.</span><span class="sxs-lookup"><span data-stu-id="ba706-149">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="ba706-150">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ba706-150">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ba706-151">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba706-151">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="ba706-152">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba706-152">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="ba706-153">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba706-153">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="ba706-154">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba706-154">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ba706-155"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Administración de la configuración del grupo de respuesta de nivel de aplicación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba706-155"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba706-156">(Opcional) Delegación de la administración de los grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="ba706-156">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="ba706-157">Asigne a los usuarios el rol CsResponseGroupManager para delegar la configuración de los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="ba706-157">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="ba706-158">A continuación, los administradores del grupo de respuesta pueden configurar los grupos de respuesta que tienen asignados.</span><span class="sxs-lookup"><span data-stu-id="ba706-158">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="ba706-159">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ba706-159">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ba706-160">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba706-160">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="ba706-161">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba706-161">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="ba706-162">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba706-162">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="ba706-163">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ba706-163">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ba706-164"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planeación del control de acceso basado en roles en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ba706-164"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba706-165">Comprobación del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="ba706-165">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="ba706-166">Compruebe los mensajes de contestador automático del grupo de búsqueda y los flujos de trabajo de respuestas de voz interactiva para asegurarse de que la configuración funcione según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="ba706-166">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
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

