---
title: Proceso de implementación para la integración de la mensajería unificada local
description: Proceso de implementación para la integración de la mensajería unificada local.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c1b8f528edb970893198ed06b821535a398f09d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569526"
---
# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="aec61-103">Proceso de implementación para la integración de la mensajería unificada local y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aec61-103">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aec61-104">_**Última modificación del tema:** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="aec61-104">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="aec61-105">Si desea integrar la mensajería unificada (UM) de Exchange con Lync Server 2013, debe realizar las tareas descritas en este tema.</span><span class="sxs-lookup"><span data-stu-id="aec61-105">If you want to integrate Exchange Unified Messaging (UM) with Lync Server 2013, you must perform the tasks described in this topic.</span></span> <span data-ttu-id="aec61-106">Además, asegúrese de revisar los procedimientos recomendados de planeación e implementación que se describen en [directrices para integrar la mensajería unificada local y Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="aec61-106">Also be sure that you review the planning and deployment best practices described in [Guidelines for integrating on-premises Unified Messaging and Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span></span> <span data-ttu-id="aec61-107">En este tema se supone que ha implementado Lync Server 2013 con un servidor de mediación combinado y que ha habilitado usuarios para Lync Server 2013, pero no necesariamente que haya realizado todos los pasos de implementación y configuración para habilitar Enterprise Voice, tal y como se describe en [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="aec61-107">This topic assumes that you have deployed Lync Server 2013 with a collocated Mediation Server and that you have enabled users for Lync Server 2013, but not necessarily that you have performed all deployment and configuration steps to enable Enterprise Voice, as described in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="unified-messaging-integration-process"></a><span data-ttu-id="aec61-108">Proceso de integración de la mensajería unificada</span><span class="sxs-lookup"><span data-stu-id="aec61-108">Unified Messaging Integration Process</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="aec61-109">Es importante que se coordine con los administradores de Exchange de la organización para confirmar las tareas que realizará cada uno para ayudar a garantizar una integración correcta y sin problemas.</span><span class="sxs-lookup"><span data-stu-id="aec61-109">It is important that you coordinate with your organization’s Exchange administrators to confirm the tasks that each of you will perform to help ensure a smooth, successful integration.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aec61-110">Fase</span><span class="sxs-lookup"><span data-stu-id="aec61-110">Phase</span></span></th>
<th><span data-ttu-id="aec61-111">Pasos</span><span class="sxs-lookup"><span data-stu-id="aec61-111">Steps</span></span></th>
<th><span data-ttu-id="aec61-112">Grupos y roles necesarios</span><span class="sxs-lookup"><span data-stu-id="aec61-112">Required groups and roles</span></span></th>
<th><span data-ttu-id="aec61-113">Documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="aec61-113">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aec61-114">Implementar una de las siguientes aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="aec61-114">Deploy one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="aec61-115">Microsoft Exchange Server 2007 Service Pack 1 (SP2) o el último Service Pack</span><span class="sxs-lookup"><span data-stu-id="aec61-115">Microsoft Exchange Server 2007 Service Pack 1 (SP2) or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="aec61-116">Microsoft Exchange Server 2010 o Service Pack más reciente</span><span class="sxs-lookup"><span data-stu-id="aec61-116">Microsoft Exchange Server 2010 or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="aec61-117">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="aec61-117">Microsoft Exchange Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aec61-118">Si usa Microsoft Exchange Server 2013, instale los siguientes roles de Exchange Server en el mismo bosque o en un bosque diferente que Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="aec61-118">If you are using Microsoft Exchange Server 2013, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="aec61-119">Acceso de clientes</span><span class="sxs-lookup"><span data-stu-id="aec61-119">Client Access</span></span></p></li>
<li><p><span data-ttu-id="aec61-120">Buzón de correo</span><span class="sxs-lookup"><span data-stu-id="aec61-120">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="aec61-121">Si Microsoft Exchange Server 2013 y mensajería unificada de Exchange están instalados en bosques distintos, configure cada bosque de Exchange para que confíe en el bosque de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aec61-121">If Microsoft Exchange Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p>
<p><span data-ttu-id="aec61-122">Si usa Exchange 2010, instale los siguientes roles de servidor de Exchange en el mismo bosque o en un bosque diferente que Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="aec61-122">If you are using Exchange 2010, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="aec61-123">Mensajería unificada</span><span class="sxs-lookup"><span data-stu-id="aec61-123">Unified Messaging</span></span></p></li>
<li><p><span data-ttu-id="aec61-124">Transporte de concentradores</span><span class="sxs-lookup"><span data-stu-id="aec61-124">Hub Transport</span></span></p></li>
<li><p><span data-ttu-id="aec61-125">Acceso de clientes</span><span class="sxs-lookup"><span data-stu-id="aec61-125">Client Access</span></span></p></li>
<li><p><span data-ttu-id="aec61-126">Buzón de correo</span><span class="sxs-lookup"><span data-stu-id="aec61-126">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="aec61-127">Si Lync Server 2013 y mensajería unificada de Exchange están instalados en bosques distintos, configure cada bosque de Exchange para que confíe en el bosque de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aec61-127">If Lync Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p></td>
<td><p><span data-ttu-id="aec61-128">Administradores de organización (si es el primer servidor de Exchange Server en la organización)</span><span class="sxs-lookup"><span data-stu-id="aec61-128">Enterprise administrators (if this is the first Exchange Server in the organization)</span></span></p>
<p><span data-ttu-id="aec61-129">-O-</span><span class="sxs-lookup"><span data-stu-id="aec61-129">-OR-</span></span></p>
<p><span data-ttu-id="aec61-130">Administrador de organización de Exchange (si no es el primer servidor de Exchange Server en la organización)</span><span class="sxs-lookup"><span data-stu-id="aec61-130">Exchange Organization administrator (if this is not the first Exchange Server in the organization)</span></span></p></td>
<td><p><span data-ttu-id="aec61-131">Consulte la documentación correspondiente a la versión de Exchange Server:</span><span class="sxs-lookup"><span data-stu-id="aec61-131">See the appropriate documentation for your version of Exchange Server:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="aec61-132">Documentación de implementación de Exchange Server 2007 en <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a> .</span><span class="sxs-lookup"><span data-stu-id="aec61-132">Exchange Server 2007 deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="aec61-133">Exchange Server 2010 o la documentación de implementación de Service Pack más reciente en <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a> .</span><span class="sxs-lookup"><span data-stu-id="aec61-133">Exchange Server 2010 or latest service pack deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="aec61-134">Planeación e implementación de Microsoft Exchange Server 2013 en <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a> .</span><span class="sxs-lookup"><span data-stu-id="aec61-134">Microsoft Exchange Server 2013 Planning and Deployment at <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aec61-135">Instalar los certificados.</span><span class="sxs-lookup"><span data-stu-id="aec61-135">Install certificates.</span></span></p></td>
<td><p><span data-ttu-id="aec61-136">Descargue e instale certificados para cada servidor de mensajería unificada de Exchange de una entidad de certificación (CA) raíz de confianza.</span><span class="sxs-lookup"><span data-stu-id="aec61-136">Download and install certificates for each Exchange UM server from a trusted root certificate authority (CA).</span></span> <span data-ttu-id="aec61-137">Los certificados son necesarios para la seguridad de nivel de transporte mutuo (MTLS) entre los servidores que ejecutan la mensajería unificada de Exchange y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aec61-137">The certificates are required for mutual Transport Level Security (MTLS) between the servers running Exchange UM and Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="aec61-138">Administradores</span><span class="sxs-lookup"><span data-stu-id="aec61-138">Administrators</span></span></p></td>
<td><p><span data-ttu-id="aec61-139"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurar certificados en el servidor que ejecuta la mensajería unificada de Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="aec61-139"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aec61-140">Cree y configure un nuevo plan de marcado SIP de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="aec61-140">Create and configure a new Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="aec61-141">En el servidor de mensajería unificada de Exchange, cree un plan de marcado SIP en función de los requisitos de implementación específicos de la organización.</span><span class="sxs-lookup"><span data-stu-id="aec61-141">On the Exchange UM server, create a SIP dial plan based on your organization’s specific deployment requirements.</span></span></p></td>
<td><p><span data-ttu-id="aec61-142">Administrador de organización de Exchange</span><span class="sxs-lookup"><span data-stu-id="aec61-142">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="aec61-143">Para Exchange 2007 SP1 o el último Service Pack, vea &quot; Cómo crear un plan de marcado URI de SIP de mensajería unificada &quot; en <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a> .</span><span class="sxs-lookup"><span data-stu-id="aec61-143">For Exchange 2007 SP1 or latest service pack, see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span></span></p>
<p><span data-ttu-id="aec61-144">Para Exchange 2010 o el Service Pack más reciente, vea &quot; crear un plan de marcado de mensajería unificada &quot; en <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a> .</span><span class="sxs-lookup"><span data-stu-id="aec61-144">For Exchange 2010 or latest service pack, see &quot;Create a UM Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>.</span></span></p>
<p><span data-ttu-id="aec61-145">Para Exchange 2013, vea Mensajería unificada en <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="aec61-145">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aec61-146">Configure las opciones de seguridad para el plan de marcado SIP de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="aec61-146">Configure security settings for the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="aec61-147">Para cifrar el tráfico de telefonía IP empresarial, configure la configuración de seguridad en el plan de marcado SIP de mensajería unificada de Exchange como <strong>SIP protegida</strong> o <strong>protegida</strong>.</span><span class="sxs-lookup"><span data-stu-id="aec61-147">To encrypt Enterprise Voice traffic, configure the security settings on the Exchange UM SIP dial plan as <strong>SIP Secured</strong> or <strong>Secured</strong>.</span></span> <span data-ttu-id="aec61-148">Este es un paso especialmente importante si ha implementado o tiene previsto implementar dispositivos Lync Phone Edition en su entorno.</span><span class="sxs-lookup"><span data-stu-id="aec61-148">This is an especially important step if you have deployed or plan to deploy Lync Phone Edition devices in your environment.</span></span> <span data-ttu-id="aec61-149">Para que los dispositivos de Lync Phone Edition funcionen en un entorno con integración de mensajería unificada de Exchange, la configuración de cifrado de Lync Server debe alinearse con la configuración de seguridad del plan de marcado de MU de Exchange.</span><span class="sxs-lookup"><span data-stu-id="aec61-149">For Lync Phone Edition devices to function in an environment with Exchange UM integration, Lync Server encryption settings must align with the Exchange UM dial plan security settings.</span></span> <span data-ttu-id="aec61-150">Para obtener información detallada, consulte la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="aec61-150">For details, refer to the Deployment documentation.</span></span></p></td>
<td><p><span data-ttu-id="aec61-151">Administrador de organización de Exchange</span><span class="sxs-lookup"><span data-stu-id="aec61-151">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="aec61-152"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurar la mensajería unificada en Microsoft Exchange para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="aec61-152"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="aec61-153">Para Exchange 2007 SP1 o el último Service Pack, vea también:</span><span class="sxs-lookup"><span data-stu-id="aec61-153">For Exchange 2007 SP1 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="aec61-154">&quot;Cómo configurar la seguridad en un plan de marcado de mensajería unificada &quot; en <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a> .</span><span class="sxs-lookup"><span data-stu-id="aec61-154">&quot;How to Configure Security on a Unified Messaging Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</span></span></p>
<p><span data-ttu-id="aec61-155">En el caso de Exchange 2010 o el último service pack, véase también:</span><span class="sxs-lookup"><span data-stu-id="aec61-155">For Exchange 2010 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="aec61-156">&quot;Configurar la seguridad de VoIP en un plan de marcado de mensajería unificada &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a> .</span><span class="sxs-lookup"><span data-stu-id="aec61-156">&quot;Configure VoIP Security on a UM Dial Plan&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</span></span></p>
<p><span data-ttu-id="aec61-157">Para Exchange 2013, vea Mensajería unificada en <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="aec61-157">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aec61-158">Agregar servidores de mensajería unificada al plan de marcado SIP de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="aec61-158">Add Unified Messaging servers to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="aec61-159">Para que un servidor de mensajería unificada recién instalado pueda contestar y procesar llamadas entrantes, dicho servidor se debe agregar a un plan de marcado de MU.</span><span class="sxs-lookup"><span data-stu-id="aec61-159">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span></span> <span data-ttu-id="aec61-160">En este caso, agregue el servidor al plan de marcado SIP de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="aec61-160">In this case, add the server to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="aec61-161">Administradores</span><span class="sxs-lookup"><span data-stu-id="aec61-161">Administrators</span></span></p>
<p><span data-ttu-id="aec61-162">Administradores de Exchange Server</span><span class="sxs-lookup"><span data-stu-id="aec61-162">Exchange Server administrators</span></span></p></td>
<td><p><span data-ttu-id="aec61-163">Para Exchange 2007 SP1 o el último Service Pack, vea &quot; Cómo agregar un servidor de mensajería unificada a un plan &quot; de marcado en <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a> .</span><span class="sxs-lookup"><span data-stu-id="aec61-163">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add Unified Messaging Server to a Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>.</span></span></p>
<p><span data-ttu-id="aec61-164">Para Exchange 2010 o el Service Pack más reciente, consulte &quot; ver o configurar las propiedades de un servidor de mensajería unificada &quot; en <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a> .</span><span class="sxs-lookup"><span data-stu-id="aec61-164">For Exchange 2010 or latest service pack, see &quot;View or Configure the Properties of a UM Server&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>.</span></span></p>
<p><span data-ttu-id="aec61-165">Para Exchange 2013, vea Mensajería unificada en <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="aec61-165">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aec61-166">Configurar buzones de correo con direcciones SIP.</span><span class="sxs-lookup"><span data-stu-id="aec61-166">Configure mailboxes with SIP addresses.</span></span></p></td>
<td><p><span data-ttu-id="aec61-167">Asigne direcciones SIP a los buzones de correo de los usuarios de Enterprise Voice que van a usar las características de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="aec61-167">Assign SIP addresses to the mailboxes of Enterprise Voice users who will be using Exchange UM features.</span></span></p></td>
<td><p><span data-ttu-id="aec61-168">Administrador de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aec61-168">Lync Server 2013 administrator</span></span></p>
<p><span data-ttu-id="aec61-169">Administrador de destinatarios de Exchange</span><span class="sxs-lookup"><span data-stu-id="aec61-169">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="aec61-170">Para Exchange 2007 SP1 o el Service Pack más reciente, vea &quot; Cómo agregar, quitar o modificar una dirección SIP para un usuario de UM-Enabled &quot; en <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a> .</span><span class="sxs-lookup"><span data-stu-id="aec61-170">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add, Remove, or Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span></span></p>
<p><span data-ttu-id="aec61-171">Para Exchange 2010 o el Service Pack más reciente, vea &quot; Modify a SIP address for a UM-Enabled User &quot; en <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a> .</span><span class="sxs-lookup"><span data-stu-id="aec61-171">For Exchange 2010 or latest service pack, see &quot;Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</span></span></p>
<p><span data-ttu-id="aec61-172">Para Exchange 2013, vea Mensajería unificada en <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="aec61-172">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aec61-173">Ejecutar el script exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="aec61-173">Run the exchucutil.ps1 script.</span></span></p></td>
<td><p><span data-ttu-id="aec61-174">En el servidor que ejecuta los servicios de mensajería unificada de Exchange, abra el shell de administración de Exchange y ejecute el script de exchucutil.ps1, que hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aec61-174">On the server running Exchange UM services, open the Exchange Management Shell and run the exchucutil.ps1 script, which does the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="aec61-175">Concede el permiso Lync Server 2013 para leer los objetos de servicios de dominio de Active Directory de mensajería unificada de Exchange, en concreto, los planes de marcado SIP creados en la tarea anterior.</span><span class="sxs-lookup"><span data-stu-id="aec61-175">Grants Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects, specifically, the SIP dial plans created in the previous task.</span></span></p></li>
<li><p><span data-ttu-id="aec61-176">Crea un objeto de puerta de enlace IP de mensajería unificada en Active Directory para cada grupo de servidores de Lync Server 2013 Enterprise Edition o servidor Standard Edition que hospeda usuarios habilitados para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="aec61-176">Creates a Unified Messaging IP gateway object in Active Directory for each Lync Server 2013 Enterprise Edition pool or Standard Edition server that hosts users who are enabled for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="aec61-177">Crea un grupo de extensiones de mensajería unificada de Exchange para cada puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="aec61-177">Creates an Exchange UM hunt group for each gateway.</span></span> <span data-ttu-id="aec61-178">El identificador piloto del grupo de búsqueda será el nombre del plan de marcado asociado a la puerta de enlace correspondiente.</span><span class="sxs-lookup"><span data-stu-id="aec61-178">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span></span> <span data-ttu-id="aec61-179">Se deberá establecer una asignación 1:1 en caso de que exista más de un plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="aec61-179">These need to be mapped 1:1 if there is more than one dial plan.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aec61-180">Administrador de organización de Exchange</span><span class="sxs-lookup"><span data-stu-id="aec61-180">Exchange Organization administrator</span></span></p>
<p><span data-ttu-id="aec61-181">Administrador de destinatarios de Exchange</span><span class="sxs-lookup"><span data-stu-id="aec61-181">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="aec61-182"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurar la mensajería unificada en Microsoft Exchange para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="aec61-182"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aec61-183">Configure los planes de marcado de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aec61-183">Configure Lync Server 2013 dial plans.</span></span></p></td>
<td><p><span data-ttu-id="aec61-184">Si está integrando con Exchange 2007 SP1 o el Service Pack más reciente o Exchange 2010, cree un nuevo plan de marcado de telefonía IP empresarial con un nombre que coincida con el nombre de dominio completo (FQDN) del plan de marcado de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="aec61-184">If you are integrating with Exchange 2007 SP1 or latest service pack, or Exchange 2010, create a new Enterprise Voice dial plan with a name that matches the Exchange UM dial plan fully qualified domain name (FQDN).</span></span></p>



> [!NOTE]
> <span data-ttu-id="aec61-185">Tendrá que hacerlo para cada plan de marcado de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="aec61-185">You will need to do this for each UM Dial plan.</span></span>


<p><span data-ttu-id="aec61-186">Si está integrando con Exchange 2010 SP1, asegúrese de que se hayan configurado los planes de marcado de Enterprise Voice de nivel global/sitio o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="aec61-186">If you are integrating with Exchange 2010 SP1, ensure that suitable global/site-level or pool-level Enterprise Voice dial plans have been configured.</span></span></p>



> [!NOTE]
> <span data-ttu-id="aec61-187">Si está integrando con Exchange 2010 SP1, no es necesario que coinciden los nombres del plan de marcado de Lync Server y el plan de marcado SIP de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="aec61-187">If you are integrating with Exchange 2010 SP1, the Lync Server dial plan and Exchange UM SIP dial plan names do not need to match.</span></span>

</td>
<td><p><span data-ttu-id="aec61-188">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="aec61-188">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="aec61-189"><a href="lync-server-2013-configuring-dial-plans.md">Configurar planes de marcado en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="aec61-189"><a href="lync-server-2013-configuring-dial-plans.md">Configuring dial plans in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aec61-190">Ejecute la herramienta de integración de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="aec61-190">Run the Exchange UM Integration tool.</span></span></p></td>
<td><p><span data-ttu-id="aec61-191">En Lync Server 2013, ejecute <strong>ocsumutil.exe</strong>, que:</span><span class="sxs-lookup"><span data-stu-id="aec61-191">On the Lync Server 2013, run <strong>ocsumutil.exe</strong>, which:</span></span></p>
<ul>
<li><p><span data-ttu-id="aec61-192">Crea los objetos de contacto de acceso de suscriptor y operador automático.</span><span class="sxs-lookup"><span data-stu-id="aec61-192">Creates Subscriber Access and Auto Attendant contact objects.</span></span></p></li>
<li><p><span data-ttu-id="aec61-193">Valida que hay un plan de marcado de telefonía IP empresarial con un nombre que coincide con el FQDN del plan de marcado de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="aec61-193">Validates that there is an Enterprise Voice dial plan with a name that matches the Exchange UM dial plan FQDN.</span></span> <span data-ttu-id="aec61-194">Si ejecuta Exchange 2010 SP1 o posterior, no es necesario que los nombres del plan de marcado sean coincidentes y puede omitir la advertencia de la herramienta sobre esto.</span><span class="sxs-lookup"><span data-stu-id="aec61-194">If you are running Exchange 2010 SP1 or later, the dial plan names do not need to match, and you can ignore the tool’s warning about this.</span></span></p></li>
</ul>
<p><span data-ttu-id="aec61-195">Esta herramienta busca en Active Directory la configuración de mensajería unificada de Exchange y permite al administrador de 2013 de Lync Server ver, crear y editar objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="aec61-195">This tool works by scanning the Active Directory for Exchange UM settings and allowing the Lync Server 2013 administrator to view, create, and edit contact objects.</span></span></p></td>
<td><p><span data-ttu-id="aec61-196">RTCUniversalServerAdmins <em>y</em> RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="aec61-196">RTCUniversalServerAdmins <em>and</em> RTCUniversalUserAdmins</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="aec61-197">Para ejecutar ocsumutil.exe correctamente, el usuario debe pertenecer a ambos grupos.</span><span class="sxs-lookup"><span data-stu-id="aec61-197">To run ocsumutil.exe successfully, the user must belong to both of these groups.</span></span>





> [!NOTE]
> <span data-ttu-id="aec61-198">Para crear objetos de contacto, el usuario que ejecute ocsumutil.exe debe poseer el permiso adecuado en la unidad organizativa de Active Directory en la que los nuevos objetos de contacto están almacenados.</span><span class="sxs-lookup"><span data-stu-id="aec61-198">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span></span> <span data-ttu-id="aec61-199">Este permiso se puede conceder mediante la ejecución del cmdlet <STRONG>Grant-CsOUPermission</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="aec61-199">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span></span> <span data-ttu-id="aec61-200">Para obtener más información, vea la documentación referente a Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="aec61-200">For details, see the Lync Server Management Shell documentation.</span></span>

</td>
<td><p><span data-ttu-id="aec61-201"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configurar Lync Server 2013 para trabajar con la mensajería unificada en Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="aec61-201"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aec61-202">Si procede, realizar otros pasos de configuración de Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="aec61-202">If necessary, perform other Enterprise Voice configuration steps.</span></span></p></td>
<td><p><span data-ttu-id="aec61-203">En caso de que Enterprise Voice todavía no se haya configurado en los servidores o usuarios, lleve a cabo una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="aec61-203">If you have not already configured Enterprise Voice settings on your servers or users, do one or more of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="aec61-204">Implementar y configurar</span><span class="sxs-lookup"><span data-stu-id="aec61-204">Deploy and configure</span></span></p>
<p><span data-ttu-id="aec61-205">Puertas de enlace y servidores de mediación de la red telefónica conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="aec61-205">Public switched telephone network (PSTN) gateways and Mediation Servers</span></span></p></li>
<li><p><span data-ttu-id="aec61-206">Definir directivas de voz, registros de uso de RTC y rutas de llamadas realizadas.</span><span class="sxs-lookup"><span data-stu-id="aec61-206">Define voice policies, PSTN usage records, and outbound call routes.</span></span></p></li>
<li><p><span data-ttu-id="aec61-207">Habilitar a los usuarios para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="aec61-207">Enable users for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="aec61-208">De forma alternativa, configurar usuarios específicos con planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="aec61-208">Optionally, configure specific users with dial plans.</span></span></p></li>
</ul>
<p><span data-ttu-id="aec61-209">Según cuáles sean las características de Enterprise Voice que se habiliten, es posible que sea necesario realizar más pasos de configuración.</span><span class="sxs-lookup"><span data-stu-id="aec61-209">Other configuration steps may be required depending on the Enterprise Voice features that you enable.</span></span></p></td>
<td><p><span data-ttu-id="aec61-210">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="aec61-210">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="aec61-211">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="aec61-211">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="aec61-212">Consulte los temas de las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="aec61-212">See topics in the following sections:</span></span></p>
<ul>
<li><p><span data-ttu-id="aec61-213"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configurar directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="aec61-213"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="aec61-214"><a href="lync-server-2013-deploying-enterprise-voice.md">Implementar la telefonía IP empresarial en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="aec61-214"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aec61-215">Habilite a los usuarios de Enterprise Voice para la mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="aec61-215">Enable Enterprise Voice users for Exchange UM.</span></span></p></td>
<td><p><span data-ttu-id="aec61-216">En el servidor de mensajería unificada de Exchange, asegúrese de que se ha creado una directiva de buzón de mensajería unificada y que cada usuario tiene una asignación de número de extensión única y, a continuación, habilite al usuario para la mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="aec61-216">On the Exchange UM server, ensure that a Unified Messaging mailbox policy has been created and that each user has a unique extension number assignment, and then enable the user for Unified Messaging.</span></span></p></td>
<td><p><span data-ttu-id="aec61-217">Administrador de destinatarios de Exchange</span><span class="sxs-lookup"><span data-stu-id="aec61-217">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="aec61-218">Para Exchange 2007 SP1 o el último Service Pack, vea &quot; Cómo habilitar a un usuario para la mensajería unificada &quot; en <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a> .</span><span class="sxs-lookup"><span data-stu-id="aec61-218">For Exchange 2007 SP1 or latest service pack, see &quot;How to Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span></span></p>
<p><span data-ttu-id="aec61-219">Para Exchange 2010 o el Service Pack más reciente, consulte &quot; habilitar a un usuario para mensajería unificada &quot; en <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a> .</span><span class="sxs-lookup"><span data-stu-id="aec61-219">For Exchange 2010 or latest service pack, see &quot;Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span></span></p>
<p><span data-ttu-id="aec61-220">Para Exchange 2013, vea Mensajería unificada en <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</span><span class="sxs-lookup"><span data-stu-id="aec61-220">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

