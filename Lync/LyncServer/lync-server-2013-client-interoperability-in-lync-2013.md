---
title: 'Lync Server 2013: Interoperabilidad de clientes en Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8ccc6239ffa0216e36839a7e58b510d8c8c3240
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="05424-102">Interoperabilidad de clientes en Lync 2013</span><span class="sxs-lookup"><span data-stu-id="05424-102">Client interoperability in Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05424-103">_**Última modificación del tema:** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="05424-103">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="05424-104">En este tema se describe la capacidad de los clientes de Microsoft Lync Server 2013 para coexistir e interactuar con clientes de versiones anteriores de Lync Server y Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="05424-104">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="05424-105">Compatibilidad de servidor y cliente</span><span class="sxs-lookup"><span data-stu-id="05424-105">Server and Client Compatibility</span></span>

<span data-ttu-id="05424-106">En la tabla siguiente se muestran las combinaciones compatibles de versiones de cliente y versiones de servidor.</span><span class="sxs-lookup"><span data-stu-id="05424-106">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="05424-107">Esta tabla indica si el inicio de sesión es compatible cuando el cliente intenta conectarse al servidor indicado.</span><span class="sxs-lookup"><span data-stu-id="05424-107">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="05424-108">Lync Server 2013 admite la versión de cliente anterior.</span><span class="sxs-lookup"><span data-stu-id="05424-108">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="05424-109">Además, a diferencia de las versiones anteriores, Lync Server 2010 admite los nuevos clientes de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="05424-109">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="05424-110">Esto permite a las organizaciones que están actualizando desde Lync Server 2010 implementar nuevos clientes independientes de las actualizaciones de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="05424-110">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05424-111">Cliente</span><span class="sxs-lookup"><span data-stu-id="05424-111">Client</span></span></th>
<th><span data-ttu-id="05424-112">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05424-112">Lync Server 2013</span></span></th>
<th><span data-ttu-id="05424-113">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="05424-113">Lync Server 2010</span></span></th>
<th><span data-ttu-id="05424-114">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="05424-114">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05424-115">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="05424-115">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="05424-116">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-116">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-117">Supported5</span><span class="sxs-lookup"><span data-stu-id="05424-117">Supported5</span></span></p></td>
<td><p><span data-ttu-id="05424-118">No compatible</span><span class="sxs-lookup"><span data-stu-id="05424-118">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05424-119">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="05424-119">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="05424-120">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-120">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-121">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-122">No compatible</span><span class="sxs-lookup"><span data-stu-id="05424-122">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05424-123">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="05424-123">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="05424-124">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-124">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-125">No compatible</span><span class="sxs-lookup"><span data-stu-id="05424-125">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-126">No compatible</span><span class="sxs-lookup"><span data-stu-id="05424-126">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05424-127">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="05424-127">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="05424-128">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-128">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-129">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-130">No compatible</span><span class="sxs-lookup"><span data-stu-id="05424-130">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05424-131">Operador de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="05424-131">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="05424-132">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-132">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-133">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-134">No compatible</span><span class="sxs-lookup"><span data-stu-id="05424-134">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05424-135">Chat en grupo de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="05424-135">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="05424-136">Supported1</span><span class="sxs-lookup"><span data-stu-id="05424-136">Supported1</span></span></p></td>
<td><p><span data-ttu-id="05424-137">Supported2</span><span class="sxs-lookup"><span data-stu-id="05424-137">Supported2</span></span></p></td>
<td><p><span data-ttu-id="05424-138">No aplicable</span><span class="sxs-lookup"><span data-stu-id="05424-138">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05424-139">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="05424-139">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="05424-140">No compatible</span><span class="sxs-lookup"><span data-stu-id="05424-140">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-141">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-141">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-142">No compatible</span><span class="sxs-lookup"><span data-stu-id="05424-142">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05424-143">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="05424-143">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="05424-144">No Supported3</span><span class="sxs-lookup"><span data-stu-id="05424-144">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="05424-145">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-145">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-146">No compatible</span><span class="sxs-lookup"><span data-stu-id="05424-146">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05424-147">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="05424-147">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="05424-148">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="05424-148">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="05424-149">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-149">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-150">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-150">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05424-151">Operador de Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="05424-151">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="05424-152">No compatible</span><span class="sxs-lookup"><span data-stu-id="05424-152">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-153">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-153">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-154">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-154">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05424-155">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="05424-155">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="05424-156">No compatible</span><span class="sxs-lookup"><span data-stu-id="05424-156">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-157">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-157">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-158">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-158">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05424-159">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="05424-159">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="05424-160">No compatible</span><span class="sxs-lookup"><span data-stu-id="05424-160">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-161">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-161">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-162">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-162">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05424-163">Aplicación de la Tienda Windows de Lync</span><span class="sxs-lookup"><span data-stu-id="05424-163">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="05424-164">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-164">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-165">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-166">No compatible</span><span class="sxs-lookup"><span data-stu-id="05424-166">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="05424-167">1Para obtener más información, consulte [migración desde Lync Server 2010, chat grupal u Office Communications server 2007 R2 conversación grupal a Lync server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="05424-167">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="05424-168">2In Microsoft Lync Server 2010, la funcionalidad de chats grupales estaba disponible con el servidor de chats grupales, una aplicación de confianza de terceros para Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="05424-168">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="05424-169">Los clientes de Lync 2013 no son compatibles con Lync Server 2010, chat grupal.</span><span class="sxs-lookup"><span data-stu-id="05424-169">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="05424-170">3Lync Web App 2013 ahora ofrece una experiencia de reunión completa, incluyendo el audio y el vídeo del equipo, y se considera el reemplazo de Lync 2010 asistente.</span><span class="sxs-lookup"><span data-stu-id="05424-170">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="05424-171">El Asistente de Lync 2010 se conectará a Lync Server 2013 solo cuando esté usando un explorador no admitido (Internet Explorer 6 o Internet Explorer 7) y Windows XP.</span><span class="sxs-lookup"><span data-stu-id="05424-171">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="05424-172">las características de presencia y mensajería instantánea de 4The en Office Communicator 2007 R2 son compatibles con Lync Server 2013, pero las características de conferencia no.</span><span class="sxs-lookup"><span data-stu-id="05424-172">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="05424-173">Durante la migración de Office Communications Server 2007 R2, Office Communicator 2007 R2 es apto para la presencia y la interoperabilidad de mensajes instantáneos, pero los usuarios deben usar Lync Web App 2013 para unirse a reuniones de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05424-173">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="05424-174">5 para obtener las limitaciones, consulte "soporte técnico de las características de conferencia para clientes de Lync 2013 en Lync Server 2010 reuniones" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="05424-174">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="05424-175">Interoperabilidad entre clientes</span><span class="sxs-lookup"><span data-stu-id="05424-175">Interoperability among Clients</span></span>

<span data-ttu-id="05424-176">Con la versión de Lync Server 2013, varias versiones de cliente pueden interactuar perfectamente en escenarios de punto a punto y de conferencia.</span><span class="sxs-lookup"><span data-stu-id="05424-176">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="05424-177">En esta sección se describe la disponibilidad de las características cuando los usuarios interactúan con otros usuarios que usan distintas versiones de clientes y servidores.</span><span class="sxs-lookup"><span data-stu-id="05424-177">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="05424-178">Compatibilidad con características de punto a punto</span><span class="sxs-lookup"><span data-stu-id="05424-178">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="05424-179">Las características de punto a punto son compatibles con los usuarios alojados en diferentes versiones del servidor y que están usando diferentes versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="05424-179">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions.</span></span> <span data-ttu-id="05424-180">La experiencia del usuario final y las características disponibles son coherentes con las capacidades del cliente del usuario y la versión del servidor en el que el usuario ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="05424-180">The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to.</span></span> <span data-ttu-id="05424-181">Dicho de otra manera:</span><span class="sxs-lookup"><span data-stu-id="05424-181">In other words:</span></span>

  - <span data-ttu-id="05424-182">Si un usuario ha iniciado sesión en Lync Server 2013 con un cliente antiguo, el usuario tendrá la misma experiencia a la que está acostumbrado.</span><span class="sxs-lookup"><span data-stu-id="05424-182">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="05424-183">Ninguna de las nuevas características introducidas en Lync Server 2013 estará disponible hasta que se actualice el cliente del usuario.</span><span class="sxs-lookup"><span data-stu-id="05424-183">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="05424-184">Algunos ejemplos son la vista de galería de vídeos, vídeo de alta definición, uso compartido de PowerPoint actualizado y la opción de silenciar el audio y vídeo de todos los asistentes al entrar en la reunión.</span><span class="sxs-lookup"><span data-stu-id="05424-184">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="05424-185">Las nuevas características se describen en [las nuevas características de conferencia de Lync server 2013](lync-server-2013-new-conferencing-features.md) y las novedades [de los clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="05424-185">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="05424-186">Si un usuario ha iniciado sesión en Lync Server 2010 con un cliente de Lync 2013, las nuevas características que no sean compatibles con Lync Server 2010 no estarán disponibles hasta que se mueva el usuario a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05424-186">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="05424-187">En la tabla siguiente se compara la disponibilidad de las características de las sesiones de punto a punto en las que el cliente ha iniciado sesión en Lync Server 2013 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="05424-187">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="05424-188">Lync Web App y Lync 2010 son clientes de solo reunión y no se incluyen en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="05424-188">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



</div>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05424-189">Cliente</span><span class="sxs-lookup"><span data-stu-id="05424-189">Client</span></span></th>
<th><span data-ttu-id="05424-190">Mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="05424-190">Instant Messaging</span></span></th>
<th><span data-ttu-id="05424-191">Presencia</span><span class="sxs-lookup"><span data-stu-id="05424-191">Presence</span></span></th>
<th><span data-ttu-id="05424-192">Voz</span><span class="sxs-lookup"><span data-stu-id="05424-192">Voice</span></span></th>
<th><span data-ttu-id="05424-193">Vídeo</span><span class="sxs-lookup"><span data-stu-id="05424-193">Video</span></span></th>
<th><span data-ttu-id="05424-194">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="05424-194">Application Sharing</span></span></th>
<th><span data-ttu-id="05424-195">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="05424-195">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05424-196">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="05424-196">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="05424-197">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-197">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-198">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-199">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-200">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-201">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-202">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-202">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05424-203">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="05424-203">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="05424-204">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-205">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-206">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-207">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-208">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-209">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-209">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05424-210">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="05424-210">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="05424-211">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-212">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-213">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-214">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-215">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-216">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-216">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05424-217">Operador de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="05424-217">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="05424-218">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-218">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-219">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-220">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-220">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05424-221">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="05424-221">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="05424-222">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-223">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-223">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05424-224">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="05424-224">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="05424-225">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-226">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-227">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-227">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05424-228">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="05424-228">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="05424-229">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-230">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-231">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-232">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-233">Sí1</span><span class="sxs-lookup"><span data-stu-id="05424-233">Yes1</span></span></p></td>
<td><p><span data-ttu-id="05424-234">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-234">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05424-235">Mensajería instantánea pública (AOL, Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="05424-235">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="05424-236">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-237">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-237">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05424-238">Mensajería instantánea pública (MSN, Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="05424-238">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="05424-239">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-239">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-240">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-241">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-242">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-242">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="05424-243">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de la conectividad de mensajería instantánea pública de Microsoft Lync (PIC USL) ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="05424-243">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="05424-244">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="05424-244">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="05424-245">Messenger hasta la fecha de cierre del servicio.</span><span class="sxs-lookup"><span data-stu-id="05424-245">Messenger until the service shutdown date.</span></span> <span data-ttu-id="05424-246">Una fecha de fin de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="05424-246">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="05424-247">ha sido anunciado.</span><span class="sxs-lookup"><span data-stu-id="05424-247">has been announced.</span></span> <span data-ttu-id="05424-248">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>..</span><span class="sxs-lookup"><span data-stu-id="05424-248">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="05424-249">El PIC USL es una licencia por usuario y por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="05424-249">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="05424-250">Mensajería.</span><span class="sxs-lookup"><span data-stu-id="05424-250">Messenger.</span></span> <span data-ttu-id="05424-251">La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el cual no se renovará.</span><span class="sxs-lookup"><span data-stu-id="05424-251">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="05424-252">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="05424-252">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="05424-253">La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="05424-253">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="05424-254">La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas a través de la mensajería instantánea y la voz.</span><span class="sxs-lookup"><span data-stu-id="05424-254">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="05424-255">1 en Office Communicator 2007 R2, solo está disponible el uso compartido del escritorio (y no el uso compartido de programas).</span><span class="sxs-lookup"><span data-stu-id="05424-255">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="05424-256">El uso compartido de escritorio entre Office Communicator 2007 R2 y Skype empresarial 2015 no se puede iniciar desde el cliente más reciente cuando se aplica la interfaz de usuario del cliente 2015 de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="05424-256">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="05424-257">Compatibilidad con características de conferencia para clientes de Lync 2013 en reuniones de 2010 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="05424-257">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="05424-258">Cuando los usuarios se unen a reuniones de Lync Server 2010 con un cliente de Lync 2013, tienen acceso a las características de cliente de Lync 2013 con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="05424-258">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="05424-259">En las opciones de administración de **participantes** , a las que se puede acceder seleccionando el icono de personas en la ventana de la reunión, la opción **sin mensajería instantánea** no funciona.</span><span class="sxs-lookup"><span data-stu-id="05424-259">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="05424-260">La vista de Galería no funciona en las videoconferencias.</span><span class="sxs-lookup"><span data-stu-id="05424-260">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="05424-261">El usuario solo ve el orador activo en lugar de todos los altavoces.</span><span class="sxs-lookup"><span data-stu-id="05424-261">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="05424-262">En la lista de opciones de **diseño** , la **vista de Galería** no está disponible</span><span class="sxs-lookup"><span data-stu-id="05424-262">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="05424-263">La lista de participantes se muestra de forma predeterminada en las videoconferencias.</span><span class="sxs-lookup"><span data-stu-id="05424-263">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="05424-264">Al hacer clic con el botón derecho en un usuario de la lista participantes, las opciones **bloquear las imágenes destacadas** y **anclar a la Galería** no estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="05424-264">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="05424-265">Compatibilidad con características de conferencia en reuniones de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05424-265">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="05424-266">Lync Server 2013 proporciona nuevas características de conferencia que estarán disponibles para los usuarios después de que sus cuentas se muevan a Lync Server 2013 y que inicien sesión con el cliente de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="05424-266">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="05424-267">Algunos ejemplos son la vista de galería de vídeos, vídeo de alta definición, uso compartido de PowerPoint y la opción de silenciar el audio y vídeo de todos los asistentes al entrar en la reunión.</span><span class="sxs-lookup"><span data-stu-id="05424-267">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="05424-268">Las nuevas características se describen en [las nuevas características de conferencia de Lync server 2013](lync-server-2013-new-conferencing-features.md) y las novedades [de los clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="05424-268">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="05424-269">En las reuniones de Lync Server 2013, se admiten determinadas características de conferencia para los usuarios alojados en diferentes versiones del servidor y que están usando diferentes clientes y versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="05424-269">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="05424-270">Cuando los clientes se unan a una reunión de 2013 de Lync Server, los usuarios tendrán acceso a las características y capacidades que se muestran en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="05424-270">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05424-271">Cliente</span><span class="sxs-lookup"><span data-stu-id="05424-271">Client</span></span></th>
<th><span data-ttu-id="05424-272">Mensajería instantánea de punto a punto</span><span class="sxs-lookup"><span data-stu-id="05424-272">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="05424-273">Voz</span><span class="sxs-lookup"><span data-stu-id="05424-273">Voice</span></span></th>
<th><span data-ttu-id="05424-274">Vídeo</span><span class="sxs-lookup"><span data-stu-id="05424-274">Video</span></span></th>
<th><span data-ttu-id="05424-275">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="05424-275">Application Sharing</span></span></th>
<th><span data-ttu-id="05424-276">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="05424-276">PowerPoint</span></span></th>
<th><span data-ttu-id="05424-277">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="05424-277">File Transfer</span></span></th>
<th><span data-ttu-id="05424-278">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="05424-278">Whiteboard</span></span></th>
<th><span data-ttu-id="05424-279">Sondeo</span><span class="sxs-lookup"><span data-stu-id="05424-279">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05424-280">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="05424-280">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="05424-281">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-281">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-282">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-283">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-284">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-285">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-286">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-287">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-288">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-288">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05424-289">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="05424-289">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="05424-290">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-291">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-292">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-293">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-294">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-295">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-296">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-297">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-297">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05424-298">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="05424-298">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="05424-299">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-300">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-301">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-302">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-303">Sí2</span><span class="sxs-lookup"><span data-stu-id="05424-303">Yes2</span></span></p></td>
<td><p><span data-ttu-id="05424-304">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-304">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-305">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-306">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-306">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05424-307">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="05424-307">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="05424-308">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-309">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-310">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-311">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-312">Sí3</span><span class="sxs-lookup"><span data-stu-id="05424-312">Yes3</span></span></p></td>
<td><p><span data-ttu-id="05424-313">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-313">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-314">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="05424-315">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-315">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05424-316">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="05424-316">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="05424-317">Sí</span><span class="sxs-lookup"><span data-stu-id="05424-317">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="05424-318">1 en Office Communicator 2007 R2, solo está disponible el uso compartido del escritorio (y no el uso compartido de programas).</span><span class="sxs-lookup"><span data-stu-id="05424-318">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="05424-319">2 Lync Server 2013 usa un mecanismo actualizado para cargar archivos de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="05424-319">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="05424-320">Los usuarios de Lync Web App que se unen a una reunión que se programó originalmente en Lync Server 2010 pueden ver y navegar por las presentaciones de PowerPoint, pero no pueden cargar archivos de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="05424-320">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="05424-321">3 si la reunión se programó en Lync Server 2013 y se cargaron diapositivas de PowerPoint en un cliente de Lync 2013, los usuarios de Lync 2010 solo tienen acceso de vista a las diapositivas.</span><span class="sxs-lookup"><span data-stu-id="05424-321">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="05424-322">Por el contrario, si un usuario de Lync 2010 cargó las diapositivas de PowerPoint, los usuarios de Lync Server 2013 podrán ver y diapositivas y, si Office Web Apps Server está configurado, accederán a nuevas capacidades, como la visualización de mayor resolución, las animaciones, las transiciones de diapositivas y vídeo incorporado.</span><span class="sxs-lookup"><span data-stu-id="05424-322">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="05424-323">Para obtener más información, vea [configurar la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="05424-323">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="05424-324">las características de presencia y mensajería instantánea de 4The en Office Communicator 2007 R2 son compatibles con Lync Server 2013, pero las características de conferencia no.</span><span class="sxs-lookup"><span data-stu-id="05424-324">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="05424-325">Durante la migración de Office Communications Server 2007 R2, Office Communicator 2007 R2 es apto para la presencia y la interoperabilidad de mensajes instantáneos, pero los usuarios deben usar Lync Web App 2013 para unirse a reuniones de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05424-325">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="05424-326">Programación de la compatibilidad de complementos</span><span class="sxs-lookup"><span data-stu-id="05424-326">Scheduling Add-in Support</span></span>

<span data-ttu-id="05424-327">La compatibilidad del servidor para los distintos complementos de programación es coherente con la compatibilidad de versiones de servidor y cliente.</span><span class="sxs-lookup"><span data-stu-id="05424-327">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="05424-328">En general, los complementos de programación siguientes son compatibles con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05424-328">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="05424-329">Sin embargo, las versiones anteriores de complementos no proporcionan nuevas características de complemento de Lync 2013, como la opción de silenciar el audio y vídeo de todos los asistentes en la entrada de la reunión.</span><span class="sxs-lookup"><span data-stu-id="05424-329">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="05424-330">**Complemento de reunión en línea para Lync 2013**   proporciona las mismas características que el complemento de reunión en línea para Lync 2010, con la adición de controles de silencio de asistente, que permiten a los organizadores de reuniones programar conferencias en las que se ha silenciado el audio y el vídeo de los asistentes programas.</span><span class="sxs-lookup"><span data-stu-id="05424-330">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="05424-331">Los administradores también pueden personalizar las invitaciones a reuniones de la organización agregando un logotipo personalizado, una dirección URL de soporte técnico, una dirección URL de renuncia legal o texto de pie de página personalizado.</span><span class="sxs-lookup"><span data-stu-id="05424-331">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="05424-332">**Complemento de reunión en línea para Lync 2010**   proporciona programación para reuniones de Lync y elimina la capacidad de programar conferencias de Office Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="05424-332">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="05424-333">**El complemento de conferencia de Office Communicator 2007 R2**   proporciona una programación para las conferencias de Office Live Meeting y las conferencias de Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="05424-333">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="05424-334">Las conferencias de Live Meeting no se pueden programar en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05424-334">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



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
<th><span data-ttu-id="05424-335">Cliente de programación</span><span class="sxs-lookup"><span data-stu-id="05424-335">Scheduling Client</span></span></th>
<th><span data-ttu-id="05424-336">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05424-336">Lync Server 2013</span></span></th>
<th><span data-ttu-id="05424-337">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="05424-337">Lync Server 2010</span></span></th>
<th><span data-ttu-id="05424-338">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="05424-338">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05424-339">Complemento de reunión en línea para Lync 2013 (se puede usar con Office 2013, Outlook 2010 y Outlook 2007)</span><span class="sxs-lookup"><span data-stu-id="05424-339">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="05424-340">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-340">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-341">Compatible (las nuevas características de complemento no están disponibles)</span><span class="sxs-lookup"><span data-stu-id="05424-341">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="05424-342">No compatible</span><span class="sxs-lookup"><span data-stu-id="05424-342">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05424-343">Programador web de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="05424-343">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="05424-344">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-344">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-345">No compatible</span><span class="sxs-lookup"><span data-stu-id="05424-345">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-346">No compatible</span><span class="sxs-lookup"><span data-stu-id="05424-346">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05424-347">Complemento para conferencia en línea para Lync 2010</span><span class="sxs-lookup"><span data-stu-id="05424-347">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="05424-348">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-348">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-349">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-350">No compatible</span><span class="sxs-lookup"><span data-stu-id="05424-350">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05424-351">Complemento de conferencia de Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="05424-351">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="05424-352">No compatible</span><span class="sxs-lookup"><span data-stu-id="05424-352">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-353">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-353">Supported</span></span></p></td>
<td><p><span data-ttu-id="05424-354">Compatible</span><span class="sxs-lookup"><span data-stu-id="05424-354">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="05424-355">Compatibilidad para unirse a reuniones</span><span class="sxs-lookup"><span data-stu-id="05424-355">Support for Joining Meetings</span></span>

<span data-ttu-id="05424-356">Todos los clientes que admite Lync Server 2013 pueden unirse a reuniones de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="05424-356">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="05424-357">Puesto que Lync Web App es un componente web del servidor, en los casos en que Lync Web App se usa para unirse a una reunión de Lync Server 2013, se usa siempre la versión más reciente de Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="05424-357">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="05424-358">Los clientes de Lync 2013 pueden unirse a reuniones hospedadas en Lync 2010 y Office Communications Server 2007 R2 con la funcionalidad de escalado vertical.</span><span class="sxs-lookup"><span data-stu-id="05424-358">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="05424-359">Las características de la reunión están limitadas por la versión del servidor en el que se hospeda la reunión.</span><span class="sxs-lookup"><span data-stu-id="05424-359">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="05424-360">Vea también</span><span class="sxs-lookup"><span data-stu-id="05424-360">See Also</span></span>


[<span data-ttu-id="05424-361">Requisitos de la aplicación de la tienda Windows de Lync para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05424-361">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="05424-362">Nuevas funciones de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05424-362">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="05424-363">Novedades para clientes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05424-363">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

