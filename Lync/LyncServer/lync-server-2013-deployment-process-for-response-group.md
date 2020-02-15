---
title: 'Lync Server 2013: proceso de implementación de grupo de respuesta'
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
ms.openlocfilehash: dfc249ec8df233e6c22c9d5c1b54b81e23c5a173
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="a0911-102">Proceso de implementación del grupo de respuesta en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0911-102">Deployment process for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0911-103">_**Última modificación del tema:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="a0911-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="a0911-104">En esta sección se proporciona información general sobre las fases y los pasos necesarios para implementar la aplicación grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="a0911-104">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="a0911-105">Proceso de implementación de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="a0911-105">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0911-106">Fase</span><span class="sxs-lookup"><span data-stu-id="a0911-106">Phase</span></span></th>
<th><span data-ttu-id="a0911-107">Pasos</span><span class="sxs-lookup"><span data-stu-id="a0911-107">Steps</span></span></th>
<th><span data-ttu-id="a0911-108">Permisos</span><span class="sxs-lookup"><span data-stu-id="a0911-108">Permissions</span></span></th>
<th><span data-ttu-id="a0911-109">Documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="a0911-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0911-110">Instalar la aplicación de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="a0911-110">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="a0911-111">La aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="a0911-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="a0911-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a0911-112">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="a0911-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Implementar la telefonía IP empresarial en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a0911-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0911-114">Instalación de componentes para el grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="a0911-114">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="a0911-115">Los cmdlets de Lync Server, el panel de control de Lync Server, la herramienta de configuración de grupos de respuesta, la consola de inicio y de cierre de sesión de los agentes y el servicio Web de cliente del grupo de respuesta se instalan como parte de los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="a0911-115">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="a0911-116">Los servicios web se instalan al implementar un grupo de Enterprise Edition o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a0911-116">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="a0911-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a0911-117">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="a0911-118"><a href="lync-server-2013-deploying-lync-server.md">Implementar Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a0911-118"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0911-119">Habilitar usuarios para Lync 2013 y Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="a0911-119">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="a0911-120">Habilite a los usuarios que van a ser agentes para Lync Server y Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="a0911-120">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="a0911-121">Los usuarios deben estar habilitados antes de poder agregarlos a grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="a0911-121">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="a0911-122">Normalmente, los usuarios están habilitados para Lync Server durante la implementación de servidor Standard Edition o Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="a0911-122">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="a0911-123">Los usuarios están habilitados para telefonía IP empresarial durante la implementación de la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="a0911-123">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="a0911-124">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a0911-124">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="a0911-125">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0911-125">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="a0911-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0911-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0911-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Deshabilitar o volver a habilitar la cuenta de usuario para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a0911-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="a0911-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Habilitar a los usuarios para la telefonía IP empresarial en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a0911-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0911-129">Creación y configuración de grupos de respuesta formados por grupos de agentes, colas y flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="a0911-129">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a0911-130">Use el panel de control de Lync Server o el shell de administración de Lync Server para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a0911-130">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="a0911-131">Crear y configurar grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="a0911-131">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="a0911-132">Crear y configurar colas</span><span class="sxs-lookup"><span data-stu-id="a0911-132">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="a0911-133">De forma opcional, use el shell de administración de Lync Server para crear días laborables y horas laborables para el grupo de respuesta predefinido.</span><span class="sxs-lookup"><span data-stu-id="a0911-133">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="a0911-134">Use la herramienta de configuración del grupo de respuesta o el shell de administración de Lync Server para crear flujos de trabajo (grupos de extensiones o flujos de llamadas de respuesta de voz interactiva (IVR), incluido el horario laboral del grupo de respuesta personalizado y los días festivos.</span><span class="sxs-lookup"><span data-stu-id="a0911-134">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="a0911-135">Puede obtener acceso a la herramienta de configuración del grupo de respuesta a través del panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a0911-135">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="a0911-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a0911-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a0911-137">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0911-137">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="a0911-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0911-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="a0911-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0911-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="a0911-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0911-140">CsAdministrator</span></span></p>
<p><span data-ttu-id="a0911-141">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="a0911-141">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="a0911-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Crear grupos de agentes de grupo de respuesta Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a0911-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="a0911-143"><a href="lync-server-2013-create-response-group-queues.md">Crear colas de grupo de respuesta en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a0911-143"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="a0911-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">Opcional Definir el horario comercial del grupo de respuesta en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a0911-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="a0911-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Opcional Definir conjuntos de días festivos para grupos de respuesta en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a0911-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="a0911-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Crear o modificar un flujo de trabajo en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a0911-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0911-147">(Opcional) Personalización de la configuración de nivel de aplicación</span><span class="sxs-lookup"><span data-stu-id="a0911-147">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="a0911-148">Use el shell de administración de Lync Server para personalizar la configuración predeterminada de la música en espera, el archivo de audio de música en espera predeterminado, el período de gracia de timbre del agente y la configuración del contexto de llamada.</span><span class="sxs-lookup"><span data-stu-id="a0911-148">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="a0911-149">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a0911-149">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a0911-150">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0911-150">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="a0911-151">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0911-151">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="a0911-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0911-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="a0911-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0911-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0911-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Administración de la configuración del grupo de respuesta de nivel de aplicación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a0911-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0911-155">(Opcional) Delegación de la administración de los grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="a0911-155">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="a0911-156">Asigne a los usuarios el rol CsResponseGroupManager para delegar la configuración de los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="a0911-156">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="a0911-157">A continuación, los administradores del grupo de respuesta pueden configurar los grupos de respuesta que tienen asignados.</span><span class="sxs-lookup"><span data-stu-id="a0911-157">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="a0911-158">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a0911-158">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="a0911-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0911-159">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="a0911-160">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0911-160">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="a0911-161">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0911-161">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="a0911-162">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0911-162">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0911-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planeación del control de acceso basado en roles en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a0911-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0911-164">Comprobación del grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="a0911-164">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="a0911-165">Compruebe los mensajes de contestador automático del grupo de búsqueda y los flujos de trabajo de respuestas de voz interactiva para asegurarse de que la configuración funcione según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="a0911-165">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
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

