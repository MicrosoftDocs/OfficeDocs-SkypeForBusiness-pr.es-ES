---
title: Proceso de implementación para integrar la mensajería unificada local
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7147a83bad1ed8b5cacc369d8d64e71fcaac32b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="3ea6f-102">Proceso de implementación de la integración de la mensajería unificada local y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ea6f-102">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ea6f-103">_**Última modificación del tema:** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="3ea6f-103">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="3ea6f-104">Si desea integrar la mensajería unificada de Exchange (UM) con Lync Server 2013, debe realizar las tareas descritas en este tema.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-104">If you want to integrate Exchange Unified Messaging (UM) with Lync Server 2013, you must perform the tasks described in this topic.</span></span> <span data-ttu-id="3ea6f-105">Además, asegúrese de revisar las prácticas recomendadas de planeamiento e implementación descritas en [directrices para integrar la mensajería unificada local y Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="3ea6f-105">Also be sure that you review the planning and deployment best practices described in [Guidelines for integrating on-premises Unified Messaging and Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span></span> <span data-ttu-id="3ea6f-106">En este tema se supone que ha implementado Lync Server 2013 con un servidor de mediación en el que ha habilitado usuarios para Lync Server 2013, pero no necesariamente que haya realizado todos los pasos de implementación y configuración para habilitar la telefonía IP empresarial, como se describe en [implementación de telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-106">This topic assumes that you have deployed Lync Server 2013 with a collocated Mediation Server and that you have enabled users for Lync Server 2013, but not necessarily that you have performed all deployment and configuration steps to enable Enterprise Voice, as described in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="unified-messaging-integration-process"></a><span data-ttu-id="3ea6f-107">Proceso de integración de la mensajería unificada</span><span class="sxs-lookup"><span data-stu-id="3ea6f-107">Unified Messaging Integration Process</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="3ea6f-108">Es importante estar coordinado con los administradores de Exchange de la organización para constatar qué tareas va a realizar cada uno a fin de que la integración se realice de forma correcta y sin fisuras.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-108">It is important that you coordinate with your organization’s Exchange administrators to confirm the tasks that each of you will perform to help ensure a smooth, successful integration.</span></span>



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
<th><span data-ttu-id="3ea6f-109">Fase</span><span class="sxs-lookup"><span data-stu-id="3ea6f-109">Phase</span></span></th>
<th><span data-ttu-id="3ea6f-110">Pasos</span><span class="sxs-lookup"><span data-stu-id="3ea6f-110">Steps</span></span></th>
<th><span data-ttu-id="3ea6f-111">Grupos y roles necesarios</span><span class="sxs-lookup"><span data-stu-id="3ea6f-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="3ea6f-112">Documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="3ea6f-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ea6f-113">Implementar una de las siguientes aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="3ea6f-113">Deploy one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3ea6f-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) o el Service Pack más reciente</span><span class="sxs-lookup"><span data-stu-id="3ea6f-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="3ea6f-115">Microsoft Exchange Server 2010 o Service Pack más reciente</span><span class="sxs-lookup"><span data-stu-id="3ea6f-115">Microsoft Exchange Server 2010 or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="3ea6f-116">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ea6f-116">Microsoft Exchange Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3ea6f-117">Si usa Microsoft Exchange Server 2013, instale los siguientes roles de servidor de Exchange en el mismo bosque o en un bosque diferente que Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="3ea6f-117">If you are using Microsoft Exchange Server 2013, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="3ea6f-118">Acceso de clientes</span><span class="sxs-lookup"><span data-stu-id="3ea6f-118">Client Access</span></span></p></li>
<li><p><span data-ttu-id="3ea6f-119">Buzón de correo</span><span class="sxs-lookup"><span data-stu-id="3ea6f-119">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="3ea6f-120">Si Microsoft Exchange Server 2013 y mensajería unificada de Exchange se instalan en bosques diferentes, configure cada bosque de Exchange para que confíe en el bosque de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-120">If Microsoft Exchange Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p>
<p><span data-ttu-id="3ea6f-121">Si usa Exchange 2010, instale los siguientes roles de servidor de Exchange en el mismo bosque o en un bosque diferente que Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="3ea6f-121">If you are using Exchange 2010, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="3ea6f-122">Mensajería unificada</span><span class="sxs-lookup"><span data-stu-id="3ea6f-122">Unified Messaging</span></span></p></li>
<li><p><span data-ttu-id="3ea6f-123">Transporte de concentradores</span><span class="sxs-lookup"><span data-stu-id="3ea6f-123">Hub Transport</span></span></p></li>
<li><p><span data-ttu-id="3ea6f-124">Acceso de clientes</span><span class="sxs-lookup"><span data-stu-id="3ea6f-124">Client Access</span></span></p></li>
<li><p><span data-ttu-id="3ea6f-125">Buzón de correo</span><span class="sxs-lookup"><span data-stu-id="3ea6f-125">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="3ea6f-126">Si Lync Server 2013 y mensajería unificada de Exchange se instalan en bosques diferentes, configure cada bosque de Exchange para que confíe en el bosque de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-126">If Lync Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-127">Administradores de organización (si es el primer servidor de Exchange Server en la organización)</span><span class="sxs-lookup"><span data-stu-id="3ea6f-127">Enterprise administrators (if this is the first Exchange Server in the organization)</span></span></p>
<p><span data-ttu-id="3ea6f-128">O BIEN:</span><span class="sxs-lookup"><span data-stu-id="3ea6f-128">-OR-</span></span></p>
<p><span data-ttu-id="3ea6f-129">Administrador de organización de Exchange (si no es el primer servidor de Exchange Server en la organización)</span><span class="sxs-lookup"><span data-stu-id="3ea6f-129">Exchange Organization administrator (if this is not the first Exchange Server in the organization)</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-130">Consulte la documentación correspondiente a la versión de Exchange Server:</span><span class="sxs-lookup"><span data-stu-id="3ea6f-130">See the appropriate documentation for your version of Exchange Server:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3ea6f-131">Documentación de implementación de Exchange Server <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>2007 en.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-131">Exchange Server 2007 deployment documentation at <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3ea6f-132">Exchange Server 2010 o la documentación de implementación del Service <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>Pack más reciente en.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-132">Exchange Server 2010 or latest service pack deployment documentation at <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="3ea6f-133">Microsoft Exchange Server 2013 Planning and Deployment en <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-133">Microsoft Exchange Server 2013 Planning and Deployment at <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea6f-134">Instalar los certificados.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-134">Install certificates.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-135">Descargue e instale certificados para cada servidor de mensajería unificada de Exchange de una entidad de certificación (CA) raíz de confianza.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-135">Download and install certificates for each Exchange UM server from a trusted root certificate authority (CA).</span></span> <span data-ttu-id="3ea6f-136">Los certificados son necesarios para la seguridad del nivel de transporte mutuo (MTLS) entre los servidores que ejecutan la mensajería unificada de Exchange y Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-136">The certificates are required for mutual Transport Level Security (MTLS) between the servers running Exchange UM and Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-137">Administradores</span><span class="sxs-lookup"><span data-stu-id="3ea6f-137">Administrators</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurar certificados en el servidor que ejecuta la mensajería unificada de Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="3ea6f-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea6f-139">Cree y configure un nuevo plan de marcado SIP de Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-139">Create and configure a new Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-140">En el servidor de mensajería unificada de Exchange, cree un plan de marcado SIP basado en los requisitos de implementación específicos de su organización.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-140">On the Exchange UM server, create a SIP dial plan based on your organization’s specific deployment requirements.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-141">Administrador de organización de Exchange</span><span class="sxs-lookup"><span data-stu-id="3ea6f-141">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-142">Para Exchange 2007 SP1 o el Service Pack más reciente &quot;, vea cómo crear un plan&quot; de marcado URI del SIP <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>de mensajería unificada en.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-142">For Exchange 2007 SP1 or latest service pack, see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span></span></p>
<p><span data-ttu-id="3ea6f-143">Para Exchange 2010 o el Service Pack más reciente &quot;, consulte crear un plan&quot; de <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>marcado de MU en.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-143">For Exchange 2010 or latest service pack, see &quot;Create a UM Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>.</span></span></p>
<p><span data-ttu-id="3ea6f-144">Para Exchange 2013, consulte mensajería unificada <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>en.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-144">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea6f-145">Configure las opciones de seguridad para el plan de marcado SIP de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-145">Configure security settings for the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-146">Para cifrar el tráfico de voz empresarial, establezca la configuración de seguridad en el plan de marcado SIP de mensajería unificada de Exchange como <strong>SIP protegido</strong> o <strong>seguro</strong>.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-146">To encrypt Enterprise Voice traffic, configure the security settings on the Exchange UM SIP dial plan as <strong>SIP Secured</strong> or <strong>Secured</strong>.</span></span> <span data-ttu-id="3ea6f-147">Este es un paso especialmente importante si ha implementado o tiene previsto implementar dispositivos de Lync Phone Edition en su entorno.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-147">This is an especially important step if you have deployed or plan to deploy Lync Phone Edition devices in your environment.</span></span> <span data-ttu-id="3ea6f-148">Para que los dispositivos de Lync Phone Edition funcionen en un entorno con integración de MU de Exchange, la configuración de cifrado de Lync Server debe alinearse con la configuración de seguridad del plan de marcado de MU de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-148">For Lync Phone Edition devices to function in an environment with Exchange UM integration, Lync Server encryption settings must align with the Exchange UM dial plan security settings.</span></span> <span data-ttu-id="3ea6f-149">Para obtener información detallada, consulte la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-149">For details, refer to the Deployment documentation.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-150">Administrador de organización de Exchange</span><span class="sxs-lookup"><span data-stu-id="3ea6f-150">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurar la mensajería unificada en Microsoft Exchange para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3ea6f-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="3ea6f-152">Para Exchange 2007 SP1 o el Service Pack más reciente, vea también:</span><span class="sxs-lookup"><span data-stu-id="3ea6f-152">For Exchange 2007 SP1 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="3ea6f-153">&quot;Cómo configurar la seguridad en un plan&quot; de marcado de mensajería <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>unificada en.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-153">&quot;How to Configure Security on a Unified Messaging Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</span></span></p>
<p><span data-ttu-id="3ea6f-154">En el caso de Exchange 2010 o el último service pack, véase también:</span><span class="sxs-lookup"><span data-stu-id="3ea6f-154">For Exchange 2010 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="3ea6f-155">&quot;Configurar la seguridad de VoIP en un plan&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>de marcado de MU</span><span class="sxs-lookup"><span data-stu-id="3ea6f-155">&quot;Configure VoIP Security on a UM Dial Plan&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</span></span></p>
<p><span data-ttu-id="3ea6f-156">Para Exchange 2013, consulte mensajería unificada <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>en.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-156">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea6f-157">Agregue servidores de mensajería unificada al plan de marcado SIP de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-157">Add Unified Messaging servers to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-158">Para que un servidor de mensajería unificada recién instalado pueda responder y procesar llamadas entrantes, es necesario agregarlo a un plan de marcado de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-158">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span></span> <span data-ttu-id="3ea6f-159">En este caso, agregue el servidor al plan de marcado SIP de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-159">In this case, add the server to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-160">Administradores</span><span class="sxs-lookup"><span data-stu-id="3ea6f-160">Administrators</span></span></p>
<p><span data-ttu-id="3ea6f-161">Administradores de Exchange Server</span><span class="sxs-lookup"><span data-stu-id="3ea6f-161">Exchange Server administrators</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-162">Para Exchange 2007 SP1 o el Service Pack más reciente &quot;, vea cómo agregar un servidor de mensajería unificada&quot; a <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>un plan de marcado en.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-162">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add Unified Messaging Server to a Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>.</span></span></p>
<p><span data-ttu-id="3ea6f-163">Para Exchange 2010 o el Service Pack más reciente &quot;, consulte ver o configurar las propiedades de un&quot; servidor <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>de mensajería unificada en.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-163">For Exchange 2010 or latest service pack, see &quot;View or Configure the Properties of a UM Server&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>.</span></span></p>
<p><span data-ttu-id="3ea6f-164">Para Exchange 2013, consulte mensajería unificada <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>en.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-164">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea6f-165">Configurar buzones de correo con direcciones SIP.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-165">Configure mailboxes with SIP addresses.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-166">Asigne direcciones SIP a los buzones de usuarios de telefonía IP que usarán las características de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-166">Assign SIP addresses to the mailboxes of Enterprise Voice users who will be using Exchange UM features.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-167">Administrador de 2013 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="3ea6f-167">Lync Server 2013 administrator</span></span></p>
<p><span data-ttu-id="3ea6f-168">Administrador de destinatarios de Exchange</span><span class="sxs-lookup"><span data-stu-id="3ea6f-168">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-169">Para Exchange 2007 SP1 o el Service Pack más reciente &quot;, vea cómo agregar, quitar o modificar una dirección SIP para un usuario&quot; habilitado para um <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>en.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-169">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add, Remove, or Modify a SIP Address for a UM-Enabled User&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span></span></p>
<p><span data-ttu-id="3ea6f-170">Para Exchange 2010 o el Service Pack más reciente &quot;, consulte modificar una dirección SIP para un usuario&quot; habilitado <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>para um en.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-170">For Exchange 2010 or latest service pack, see &quot;Modify a SIP Address for a UM-Enabled User&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</span></span></p>
<p><span data-ttu-id="3ea6f-171">Para Exchange 2013, consulte mensajería unificada <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>en.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-171">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea6f-172">Ejecutar el script exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-172">Run the exchucutil.ps1 script.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-173">En el servidor que ejecuta los servicios de mensajería unificada de Exchange, abra el shell de administración de Exchange y ejecute el script ExchUCUtil. ps1, que hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ea6f-173">On the server running Exchange UM services, open the Exchange Management Shell and run the exchucutil.ps1 script, which does the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3ea6f-174">Concede el permiso de Lync Server 2013 para leer objetos de servicios de dominio de Active Directory UM de Exchange, específicamente, los planes de marcado SIP creados en la tarea anterior.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-174">Grants Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects, specifically, the SIP dial plans created in the previous task.</span></span></p></li>
<li><p><span data-ttu-id="3ea6f-175">Crea un objeto de puerta de enlace IP de mensajería unificada en Active Directory para cada grupo de servidores de Lync Server 2013 Enterprise Edition o servidor Standard Edition que hospeda usuarios que están habilitados para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-175">Creates a Unified Messaging IP gateway object in Active Directory for each Lync Server 2013 Enterprise Edition pool or Standard Edition server that hosts users who are enabled for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="3ea6f-176">Crea un grupo de captura de mensajería unificada de Exchange para cada puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-176">Creates an Exchange UM hunt group for each gateway.</span></span> <span data-ttu-id="3ea6f-177">El identificador piloto del grupo de extensiones será el nombre del plan de marcado asociado a la puerta de enlace correspondiente.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-177">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span></span> <span data-ttu-id="3ea6f-178">Es necesario establecer una asignación 1:1 si existe más de un plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-178">These need to be mapped 1:1 if there is more than one dial plan.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="3ea6f-179">Administrador de organización de Exchange</span><span class="sxs-lookup"><span data-stu-id="3ea6f-179">Exchange Organization administrator</span></span></p>
<p><span data-ttu-id="3ea6f-180">Administrador de destinatarios de Exchange</span><span class="sxs-lookup"><span data-stu-id="3ea6f-180">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurar la mensajería unificada en Microsoft Exchange para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3ea6f-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea6f-182">Configure los planes de marcado de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-182">Configure Lync Server 2013 dial plans.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-183">Si está integrando con Exchange 2007 SP1 o el Service Pack más reciente o Exchange 2010, cree un nuevo plan de marcado de voz empresarial con un nombre que coincida con el nombre de dominio completo del plan de marcado de Exchange UM (FQDN).</span><span class="sxs-lookup"><span data-stu-id="3ea6f-183">If you are integrating with Exchange 2007 SP1 or latest service pack, or Exchange 2010, create a new Enterprise Voice dial plan with a name that matches the Exchange UM dial plan fully qualified domain name (FQDN).</span></span></p>



> [!NOTE]
> <span data-ttu-id="3ea6f-184">Deberá hacer esto para cada plan de marcado de mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-184">You will need to do this for each UM Dial plan.</span></span>


<p><span data-ttu-id="3ea6f-185">Si está integrando con el SP1 de Exchange 2010, asegúrese de que los planes de marcado de voz empresariales de nivel global/sitio o de grupo se hayan configurado de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-185">If you are integrating with Exchange 2010 SP1, ensure that suitable global/site-level or pool-level Enterprise Voice dial plans have been configured.</span></span></p>



> [!NOTE]
> <span data-ttu-id="3ea6f-186">Si está integrando con Exchange 2010 SP1, no es necesario que coincidan los nombres del plan de marcado de Lync Server y del plan de marcado SIP de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-186">If you are integrating with Exchange 2010 SP1, the Lync Server dial plan and Exchange UM SIP dial plan names do not need to match.</span></span>

</td>
<td><p><span data-ttu-id="3ea6f-187">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3ea6f-187">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-188"><a href="lync-server-2013-configuring-dial-plans.md">Configurar planes de marcado en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3ea6f-188"><a href="lync-server-2013-configuring-dial-plans.md">Configuring dial plans in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea6f-189">Ejecute la herramienta de integración de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-189">Run the Exchange UM Integration tool.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-190">En Lync Server 2013, ejecute <strong>OCSUMUtil. exe</strong>, que:</span><span class="sxs-lookup"><span data-stu-id="3ea6f-190">On the Lync Server 2013, run <strong>ocsumutil.exe</strong>, which:</span></span></p>
<ul>
<li><p><span data-ttu-id="3ea6f-191">Crea los objetos de contacto de acceso de suscriptor y operador automático.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-191">Creates Subscriber Access and Auto Attendant contact objects.</span></span></p></li>
<li><p><span data-ttu-id="3ea6f-192">Valida que haya un plan de marcado de voz de empresa con un nombre que coincida con el FQDN del plan de marcado de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-192">Validates that there is an Enterprise Voice dial plan with a name that matches the Exchange UM dial plan FQDN.</span></span> <span data-ttu-id="3ea6f-193">Si está ejecutando Exchange 2010 SP1 o posterior, no es necesario que los nombres del plan de marcado coincidan y puede ignorar la advertencia de la herramienta sobre este.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-193">If you are running Exchange 2010 SP1 or later, the dial plan names do not need to match, and you can ignore the tool’s warning about this.</span></span></p></li>
</ul>
<p><span data-ttu-id="3ea6f-194">Esta herramienta explora la configuración de mensajería unificada de Active Directory para Exchange y permite que el administrador de 2013 de Lync Server vea, cree y edite objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-194">This tool works by scanning the Active Directory for Exchange UM settings and allowing the Lync Server 2013 administrator to view, create, and edit contact objects.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-195">RTCUniversalServerAdmins <em>y</em> RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3ea6f-195">RTCUniversalServerAdmins <em>and</em> RTCUniversalUserAdmins</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="3ea6f-196">Para ejecutar ocsumutil.exe correctamente, el usuario debe pertenecer a ambos grupos.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-196">To run ocsumutil.exe successfully, the user must belong to both of these groups.</span></span>





> [!NOTE]
> <span data-ttu-id="3ea6f-197">Para crear objetos de contacto, el usuario que ejecute ocsumutil.exe necesita tener el permiso adecuado en la unidad organizativa de Active Directory donde están almacenados los nuevos objetos contacto.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-197">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span></span> <span data-ttu-id="3ea6f-198">Este permiso se puede conceder si se ejecuta el cmdlet <STRONG>Grant-CsOUPermission</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-198">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span></span> <span data-ttu-id="3ea6f-199">Para obtener más información, consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-199">For details, see the Lync Server Management Shell documentation.</span></span>

</td>
<td><p><span data-ttu-id="3ea6f-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configurar Lync Server 2013 para trabajar con la mensajería unificada en Microsoft Exchange Server</a></span><span class="sxs-lookup"><span data-stu-id="3ea6f-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ea6f-201">Si es necesario, realice otros pasos de configuración de voz empresarial.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-201">If necessary, perform other Enterprise Voice configuration steps.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-202">Si aún no ha configurado la configuración de voz de empresa en sus servidores o usuarios, siga uno o varios de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="3ea6f-202">If you have not already configured Enterprise Voice settings on your servers or users, do one or more of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3ea6f-203">Implementar y configurar</span><span class="sxs-lookup"><span data-stu-id="3ea6f-203">Deploy and configure</span></span></p>
<p><span data-ttu-id="3ea6f-204">puertas de enlace de red telefónica conmutada (RTC) y servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-204">Public switched telephone network (PSTN) gateways and Mediation Servers</span></span></p></li>
<li><p><span data-ttu-id="3ea6f-205">Definir directivas de voz, registros de uso de RTC y rutas de llamadas realizadas.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-205">Define voice policies, PSTN usage records, and outbound call routes.</span></span></p></li>
<li><p><span data-ttu-id="3ea6f-206">Habilitar a los usuarios para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-206">Enable users for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="3ea6f-207">De forma alternativa, configurar usuarios específicos con planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-207">Optionally, configure specific users with dial plans.</span></span></p></li>
</ul>
<p><span data-ttu-id="3ea6f-208">Puede que se requieran otros pasos de configuración según las características de Enterprise Voice que habilite.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-208">Other configuration steps may be required depending on the Enterprise Voice features that you enable.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-209">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3ea6f-209">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="3ea6f-210">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="3ea6f-210">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-211">Consulte los temas de las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="3ea6f-211">See topics in the following sections:</span></span></p>
<ul>
<li><p><span data-ttu-id="3ea6f-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuración de directivas de voz, registros de uso de RTC y rutas de voz en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3ea6f-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="3ea6f-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Implementación de telefonía IP empresarial en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3ea6f-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ea6f-214">Habilite los usuarios de telefonía IP empresarial para la mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-214">Enable Enterprise Voice users for Exchange UM.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-215">En el servidor de mensajería unificada de Exchange, asegúrese de que se ha creado una directiva de buzón de mensajería unificada y de que cada usuario tiene una asignación de número de extensión única y, después, habilite al usuario para la mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-215">On the Exchange UM server, ensure that a Unified Messaging mailbox policy has been created and that each user has a unique extension number assignment, and then enable the user for Unified Messaging.</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-216">Administrador de destinatarios de Exchange</span><span class="sxs-lookup"><span data-stu-id="3ea6f-216">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="3ea6f-217">Para Exchange 2007 SP1 o el Service Pack más reciente &quot;, vea cómo habilitar un usuario para mensajería&quot; unificada en <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-217">For Exchange 2007 SP1 or latest service pack, see &quot;How to Enable a User for Unified Messaging&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span></span></p>
<p><span data-ttu-id="3ea6f-218">Para Exchange 2010 o el Service Pack más reciente &quot;, vea Habilitar un usuario para&quot; mensajería <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>unificada en.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-218">For Exchange 2010 or latest service pack, see &quot;Enable a User for Unified Messaging&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span></span></p>
<p><span data-ttu-id="3ea6f-219">Para Exchange 2013, consulte mensajería unificada <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>en.</span><span class="sxs-lookup"><span data-stu-id="3ea6f-219">For Exchange 2013, see Unified Messaging at <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

