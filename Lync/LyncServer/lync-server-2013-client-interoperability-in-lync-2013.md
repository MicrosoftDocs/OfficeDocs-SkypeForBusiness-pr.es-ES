---
title: 'Lync Server 2013: Interoperabilidad de clientes en Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b28d0de09a46a2be8b968e55c8f551e397da6ae8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="03c9a-102">Interoperabilidad de clientes en Lync 2013</span><span class="sxs-lookup"><span data-stu-id="03c9a-102">Client interoperability in Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03c9a-103">_**Última modificación del tema:** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="03c9a-103">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="03c9a-104">En este tema se describe la capacidad de los clientes de Microsoft Lync Server 2013 para coexistir e interactuar con clientes de versiones anteriores de Lync Server y Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="03c9a-104">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="03c9a-105">Compatibilidad de servidor y cliente</span><span class="sxs-lookup"><span data-stu-id="03c9a-105">Server and Client Compatibility</span></span>

<span data-ttu-id="03c9a-106">En la tabla siguiente se muestran las combinaciones compatibles de versiones de cliente y versiones de servidor.</span><span class="sxs-lookup"><span data-stu-id="03c9a-106">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="03c9a-107">Esta tabla indica si el inicio de sesión es compatible cuando el cliente intenta conectarse al servidor indicado.</span><span class="sxs-lookup"><span data-stu-id="03c9a-107">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="03c9a-108">Lync Server 2013 admite la versión de cliente anterior.</span><span class="sxs-lookup"><span data-stu-id="03c9a-108">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="03c9a-109">Además, a diferencia de las versiones anteriores, Lync Server 2010 admite los nuevos clientes de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="03c9a-109">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="03c9a-110">Esto permite a las organizaciones que están actualizando desde Lync Server 2010 implementar nuevos clientes independientes de las actualizaciones de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="03c9a-110">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03c9a-111">Cliente</span><span class="sxs-lookup"><span data-stu-id="03c9a-111">Client</span></span></th>
<th><span data-ttu-id="03c9a-112">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03c9a-112">Lync Server 2013</span></span></th>
<th><span data-ttu-id="03c9a-113">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="03c9a-113">Lync Server 2010</span></span></th>
<th><span data-ttu-id="03c9a-114">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="03c9a-114">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03c9a-115">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="03c9a-115">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="03c9a-116">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-116">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-117">Supported5</span><span class="sxs-lookup"><span data-stu-id="03c9a-117">Supported5</span></span></p></td>
<td><p><span data-ttu-id="03c9a-118">No compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-118">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c9a-119">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="03c9a-119">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="03c9a-120">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-120">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-121">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-122">No compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-122">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c9a-123">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="03c9a-123">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="03c9a-124">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-124">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-125">No compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-125">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-126">No compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-126">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c9a-127">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="03c9a-127">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="03c9a-128">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-128">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-129">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-130">No compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-130">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c9a-131">Operador de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="03c9a-131">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="03c9a-132">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-132">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-133">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-134">No compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-134">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c9a-135">Chat en grupo de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="03c9a-135">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="03c9a-136">Supported1</span><span class="sxs-lookup"><span data-stu-id="03c9a-136">Supported1</span></span></p></td>
<td><p><span data-ttu-id="03c9a-137">Supported2</span><span class="sxs-lookup"><span data-stu-id="03c9a-137">Supported2</span></span></p></td>
<td><p><span data-ttu-id="03c9a-138">No aplicable</span><span class="sxs-lookup"><span data-stu-id="03c9a-138">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c9a-139">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="03c9a-139">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="03c9a-140">No compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-140">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-141">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-141">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-142">No compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-142">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c9a-143">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="03c9a-143">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="03c9a-144">No Supported3</span><span class="sxs-lookup"><span data-stu-id="03c9a-144">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="03c9a-145">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-145">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-146">No compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-146">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c9a-147">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="03c9a-147">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="03c9a-148">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="03c9a-148">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="03c9a-149">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-149">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-150">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-150">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c9a-151">Operador de Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="03c9a-151">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="03c9a-152">No compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-152">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-153">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-153">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-154">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-154">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c9a-155">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="03c9a-155">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="03c9a-156">No compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-156">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-157">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-157">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-158">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-158">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c9a-159">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="03c9a-159">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="03c9a-160">No compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-160">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-161">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-161">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-162">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-162">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c9a-163">Aplicación de la Tienda Windows de Lync</span><span class="sxs-lookup"><span data-stu-id="03c9a-163">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="03c9a-164">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-164">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-165">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-166">No compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-166">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="03c9a-167">1Para obtener más información, consulte [migración desde Lync Server 2010, chat grupal u Office Communications server 2007 R2 conversación grupal a Lync server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="03c9a-167">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="03c9a-168">2In Microsoft Lync Server 2010, la funcionalidad de chats grupales estaba disponible con el servidor de chats grupales, una aplicación de confianza de terceros para Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="03c9a-168">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="03c9a-169">Los clientes de Lync 2013 no son compatibles con Lync Server 2010, chat grupal.</span><span class="sxs-lookup"><span data-stu-id="03c9a-169">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="03c9a-170">3Lync Web App 2013 ahora ofrece una experiencia de reunión completa, incluyendo el audio y el vídeo del equipo, y se considera el reemplazo de Lync 2010 asistente.</span><span class="sxs-lookup"><span data-stu-id="03c9a-170">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="03c9a-171">El Asistente de Lync 2010 se conectará a Lync Server 2013 solo cuando esté usando un explorador no admitido (Internet Explorer 6 o Internet Explorer 7) y Windows XP.</span><span class="sxs-lookup"><span data-stu-id="03c9a-171">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="03c9a-172">las características de presencia y mensajería instantánea de 4The en Office Communicator 2007 R2 son compatibles con Lync Server 2013, pero las características de conferencia no.</span><span class="sxs-lookup"><span data-stu-id="03c9a-172">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="03c9a-173">Durante la migración de Office Communications Server 2007 R2, Office Communicator 2007 R2 es apto para la presencia y la interoperabilidad de mensajes instantáneos, pero los usuarios deben usar Lync Web App 2013 para unirse a reuniones de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03c9a-173">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="03c9a-174">5 para obtener las limitaciones, consulte "soporte técnico de las características de conferencia para clientes de Lync 2013 en Lync Server 2010 reuniones" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="03c9a-174">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="03c9a-175">Interoperabilidad entre clientes</span><span class="sxs-lookup"><span data-stu-id="03c9a-175">Interoperability among Clients</span></span>

<span data-ttu-id="03c9a-176">Con la versión de Lync Server 2013, varias versiones de cliente pueden interactuar perfectamente en escenarios de punto a punto y de conferencia.</span><span class="sxs-lookup"><span data-stu-id="03c9a-176">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="03c9a-177">En esta sección se describe la disponibilidad de las características cuando los usuarios interactúan con otros usuarios que usan distintas versiones de clientes y servidores.</span><span class="sxs-lookup"><span data-stu-id="03c9a-177">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="03c9a-178">Compatibilidad con características de punto a punto</span><span class="sxs-lookup"><span data-stu-id="03c9a-178">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="03c9a-179">Las características de punto a punto son compatibles con los usuarios alojados en diferentes versiones del servidor y que están usando diferentes versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="03c9a-179">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions.</span></span> <span data-ttu-id="03c9a-180">La experiencia del usuario final y las características disponibles son coherentes con las capacidades del cliente del usuario y la versión del servidor en el que el usuario ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="03c9a-180">The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to.</span></span> <span data-ttu-id="03c9a-181">Dicho de otra manera:</span><span class="sxs-lookup"><span data-stu-id="03c9a-181">In other words:</span></span>

  - <span data-ttu-id="03c9a-182">Si un usuario ha iniciado sesión en Lync Server 2013 con un cliente antiguo, el usuario tendrá la misma experiencia a la que está acostumbrado.</span><span class="sxs-lookup"><span data-stu-id="03c9a-182">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="03c9a-183">Ninguna de las nuevas características introducidas en Lync Server 2013 estará disponible hasta que se actualice el cliente del usuario.</span><span class="sxs-lookup"><span data-stu-id="03c9a-183">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="03c9a-184">Algunos ejemplos son la vista de galería de vídeos, vídeo de alta definición, uso compartido de PowerPoint actualizado y la opción de silenciar el audio y vídeo de todos los asistentes al entrar en la reunión.</span><span class="sxs-lookup"><span data-stu-id="03c9a-184">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="03c9a-185">Las nuevas características se describen en [las nuevas características de conferencia de Lync server 2013](lync-server-2013-new-conferencing-features.md) y las novedades [de los clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="03c9a-185">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="03c9a-186">Si un usuario ha iniciado sesión en Lync Server 2010 con un cliente de Lync 2013, las nuevas características que no sean compatibles con Lync Server 2010 no estarán disponibles hasta que se mueva el usuario a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03c9a-186">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="03c9a-187">En la tabla siguiente se compara la disponibilidad de las características de las sesiones de punto a punto en las que el cliente ha iniciado sesión en Lync Server 2013 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="03c9a-187">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="03c9a-188">Lync Web App y Lync 2010 son clientes de solo reunión y no se incluyen en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="03c9a-188">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



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
<th><span data-ttu-id="03c9a-189">Cliente</span><span class="sxs-lookup"><span data-stu-id="03c9a-189">Client</span></span></th>
<th><span data-ttu-id="03c9a-190">Mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="03c9a-190">Instant Messaging</span></span></th>
<th><span data-ttu-id="03c9a-191">Presence</span><span class="sxs-lookup"><span data-stu-id="03c9a-191">Presence</span></span></th>
<th><span data-ttu-id="03c9a-192">Voz</span><span class="sxs-lookup"><span data-stu-id="03c9a-192">Voice</span></span></th>
<th><span data-ttu-id="03c9a-193">Vídeo</span><span class="sxs-lookup"><span data-stu-id="03c9a-193">Video</span></span></th>
<th><span data-ttu-id="03c9a-194">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="03c9a-194">Application Sharing</span></span></th>
<th><span data-ttu-id="03c9a-195">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="03c9a-195">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03c9a-196">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="03c9a-196">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="03c9a-197">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-197">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-198">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-199">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-200">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-201">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-202">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-202">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c9a-203">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="03c9a-203">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="03c9a-204">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-205">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-206">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-207">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-208">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-209">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-209">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c9a-210">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="03c9a-210">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="03c9a-211">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-212">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-213">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-214">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-215">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-216">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-216">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c9a-217">Operador de Lync 2010</span><span class="sxs-lookup"><span data-stu-id="03c9a-217">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="03c9a-218">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-218">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-219">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-220">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-220">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c9a-221">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="03c9a-221">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="03c9a-222">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-223">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-223">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c9a-224">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="03c9a-224">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="03c9a-225">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-226">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-227">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-227">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c9a-228">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="03c9a-228">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="03c9a-229">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-230">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-231">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-232">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-233">Sí1</span><span class="sxs-lookup"><span data-stu-id="03c9a-233">Yes1</span></span></p></td>
<td><p><span data-ttu-id="03c9a-234">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-234">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c9a-235">Mensajería instantánea pública (AOL, Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="03c9a-235">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="03c9a-236">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-237">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-237">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c9a-238">Mensajería instantánea pública (MSN, Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="03c9a-238">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="03c9a-239">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-239">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-240">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-241">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-242">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-242">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="03c9a-243">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de la conectividad de mensajería instantánea pública de Microsoft Lync (PIC USL) ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="03c9a-243">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="03c9a-244">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="03c9a-244">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="03c9a-245">Messenger hasta la fecha de cierre del servicio.</span><span class="sxs-lookup"><span data-stu-id="03c9a-245">Messenger until the service shutdown date.</span></span> <span data-ttu-id="03c9a-246">Una fecha de fin de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="03c9a-246">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="03c9a-247">ha sido anunciado.</span><span class="sxs-lookup"><span data-stu-id="03c9a-247">has been announced.</span></span> <span data-ttu-id="03c9a-248">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad de la conectividad de mensajería instantánea pública en Lync Server 2013</A>..</span><span class="sxs-lookup"><span data-stu-id="03c9a-248">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="03c9a-249">El PIC USL es una licencia por usuario y por mes de suscripción que es necesaria para que Lync Server o Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="03c9a-249">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="03c9a-250">Mensajería.</span><span class="sxs-lookup"><span data-stu-id="03c9a-250">Messenger.</span></span> <span data-ttu-id="03c9a-251">La capacidad de Microsoft para proporcionar este servicio está supeditada al soporte de Yahoo!, el contrato subyacente para el cual no se renovará.</span><span class="sxs-lookup"><span data-stu-id="03c9a-251">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="03c9a-252">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="03c9a-252">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="03c9a-253">La Federación con Windows Live Messenger no requiere licencias adicionales para usuarios y dispositivos más allá de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="03c9a-253">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="03c9a-254">La Federación de Skype se agrega a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas a través de la mensajería instantánea y la voz.</span><span class="sxs-lookup"><span data-stu-id="03c9a-254">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="03c9a-255">1 en Office Communicator 2007 R2, solo está disponible el uso compartido del escritorio (y no el uso compartido de programas).</span><span class="sxs-lookup"><span data-stu-id="03c9a-255">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="03c9a-256">El uso compartido de escritorio entre Office Communicator 2007 R2 y Skype empresarial 2015 no se puede iniciar desde el cliente más reciente cuando se aplica la interfaz de usuario del cliente 2015 de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="03c9a-256">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="03c9a-257">Compatibilidad con características de conferencia para clientes de Lync 2013 en reuniones de 2010 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="03c9a-257">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="03c9a-258">Cuando los usuarios se unen a reuniones de Lync Server 2010 con un cliente de Lync 2013, tienen acceso a las características de cliente de Lync 2013 con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="03c9a-258">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="03c9a-259">En las opciones de administración de **participantes** , a las que se puede acceder seleccionando el icono de personas en la ventana de la reunión, la opción **sin mensajería instantánea** no funciona.</span><span class="sxs-lookup"><span data-stu-id="03c9a-259">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="03c9a-260">La vista de Galería no funciona en las videoconferencias.</span><span class="sxs-lookup"><span data-stu-id="03c9a-260">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="03c9a-261">El usuario solo ve el orador activo en lugar de todos los altavoces.</span><span class="sxs-lookup"><span data-stu-id="03c9a-261">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="03c9a-262">En la lista de opciones de **diseño** , la **vista de Galería** no está disponible</span><span class="sxs-lookup"><span data-stu-id="03c9a-262">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="03c9a-263">La lista de participantes se muestra de forma predeterminada en las videoconferencias.</span><span class="sxs-lookup"><span data-stu-id="03c9a-263">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="03c9a-264">Al hacer clic con el botón derecho en un usuario de la lista participantes, las opciones **bloquear las imágenes destacadas** y **anclar a la Galería** no estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="03c9a-264">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="03c9a-265">Compatibilidad con características de conferencia en reuniones de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03c9a-265">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="03c9a-266">Lync Server 2013 proporciona nuevas características de conferencia que estarán disponibles para los usuarios después de que sus cuentas se muevan a Lync Server 2013 y que inicien sesión con el cliente de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="03c9a-266">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="03c9a-267">Algunos ejemplos son la vista de galería de vídeos, vídeo de alta definición, uso compartido de PowerPoint y la opción de silenciar el audio y vídeo de todos los asistentes al entrar en la reunión.</span><span class="sxs-lookup"><span data-stu-id="03c9a-267">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="03c9a-268">Las nuevas características se describen en [las nuevas características de conferencia de Lync server 2013](lync-server-2013-new-conferencing-features.md) y las novedades [de los clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="03c9a-268">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="03c9a-269">En las reuniones de Lync Server 2013, se admiten determinadas características de conferencia para los usuarios alojados en diferentes versiones del servidor y que están usando diferentes clientes y versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="03c9a-269">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="03c9a-270">Cuando los clientes se unan a una reunión de 2013 de Lync Server, los usuarios tendrán acceso a las características y capacidades que se muestran en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="03c9a-270">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


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
<th><span data-ttu-id="03c9a-271">Cliente</span><span class="sxs-lookup"><span data-stu-id="03c9a-271">Client</span></span></th>
<th><span data-ttu-id="03c9a-272">Mensajería instantánea de punto a punto</span><span class="sxs-lookup"><span data-stu-id="03c9a-272">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="03c9a-273">Voz</span><span class="sxs-lookup"><span data-stu-id="03c9a-273">Voice</span></span></th>
<th><span data-ttu-id="03c9a-274">Vídeo</span><span class="sxs-lookup"><span data-stu-id="03c9a-274">Video</span></span></th>
<th><span data-ttu-id="03c9a-275">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="03c9a-275">Application Sharing</span></span></th>
<th><span data-ttu-id="03c9a-276">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="03c9a-276">PowerPoint</span></span></th>
<th><span data-ttu-id="03c9a-277">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="03c9a-277">File Transfer</span></span></th>
<th><span data-ttu-id="03c9a-278">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="03c9a-278">Whiteboard</span></span></th>
<th><span data-ttu-id="03c9a-279">Sondeo</span><span class="sxs-lookup"><span data-stu-id="03c9a-279">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03c9a-280">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="03c9a-280">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="03c9a-281">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-281">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-282">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-283">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-284">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-285">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-286">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-287">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-288">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-288">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c9a-289">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="03c9a-289">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="03c9a-290">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-291">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-292">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-293">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-294">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-295">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-296">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-297">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-297">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c9a-298">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="03c9a-298">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="03c9a-299">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-299">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-300">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-301">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-302">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-303">Sí2</span><span class="sxs-lookup"><span data-stu-id="03c9a-303">Yes2</span></span></p></td>
<td><p><span data-ttu-id="03c9a-304">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-304">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-305">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-306">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-306">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c9a-307">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="03c9a-307">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="03c9a-308">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-309">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-310">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-311">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-312">Sí3</span><span class="sxs-lookup"><span data-stu-id="03c9a-312">Yes3</span></span></p></td>
<td><p><span data-ttu-id="03c9a-313">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-313">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-314">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="03c9a-315">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-315">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c9a-316">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="03c9a-316">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="03c9a-317">Sí</span><span class="sxs-lookup"><span data-stu-id="03c9a-317">Yes</span></span></p></td>
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


<span data-ttu-id="03c9a-318">1 en Office Communicator 2007 R2, solo está disponible el uso compartido del escritorio (y no el uso compartido de programas).</span><span class="sxs-lookup"><span data-stu-id="03c9a-318">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="03c9a-319">2 Lync Server 2013 usa un mecanismo actualizado para cargar archivos de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="03c9a-319">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="03c9a-320">Los usuarios de Lync Web App que se unen a una reunión que se programó originalmente en Lync Server 2010 pueden ver y navegar por las presentaciones de PowerPoint, pero no pueden cargar archivos de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="03c9a-320">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="03c9a-321">3 si la reunión se programó en Lync Server 2013 y se cargaron diapositivas de PowerPoint en un cliente de Lync 2013, los usuarios de Lync 2010 solo tienen acceso de vista a las diapositivas.</span><span class="sxs-lookup"><span data-stu-id="03c9a-321">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="03c9a-322">Por el contrario, si un usuario de Lync 2010 cargó las diapositivas de PowerPoint, los usuarios de Lync Server 2013 podrán ver y diapositivas y, si Office Web Apps Server está configurado, accederán a nuevas capacidades, como la visualización de mayor resolución, las animaciones, las transiciones de diapositivas y vídeo incorporado.</span><span class="sxs-lookup"><span data-stu-id="03c9a-322">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="03c9a-323">Para obtener más información, vea [configurar la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="03c9a-323">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="03c9a-324">las características de presencia y mensajería instantánea de 4The en Office Communicator 2007 R2 son compatibles con Lync Server 2013, pero las características de conferencia no.</span><span class="sxs-lookup"><span data-stu-id="03c9a-324">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="03c9a-325">Durante la migración de Office Communications Server 2007 R2, Office Communicator 2007 R2 es apto para la presencia y la interoperabilidad de mensajes instantáneos, pero los usuarios deben usar Lync Web App 2013 para unirse a reuniones de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03c9a-325">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="03c9a-326">Programación de la compatibilidad de complementos</span><span class="sxs-lookup"><span data-stu-id="03c9a-326">Scheduling Add-in Support</span></span>

<span data-ttu-id="03c9a-327">La compatibilidad del servidor para los distintos complementos de programación es coherente con la compatibilidad de versiones de servidor y cliente.</span><span class="sxs-lookup"><span data-stu-id="03c9a-327">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="03c9a-328">En general, los complementos de programación siguientes son compatibles con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03c9a-328">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="03c9a-329">Sin embargo, las versiones anteriores de complementos no proporcionan nuevas características de complemento de Lync 2013, como la opción de silenciar el audio y vídeo de todos los asistentes en la entrada de la reunión.</span><span class="sxs-lookup"><span data-stu-id="03c9a-329">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="03c9a-330">**Complemento de reunión en línea para Lync 2013**   proporciona las mismas características que el complemento de reunión en línea para Lync 2010, con la adición de controles de silencio de asistente, que permiten a los organizadores de reuniones programar conferencias en las que se ha silenciado el audio y el vídeo del asistente de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="03c9a-330">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="03c9a-331">Los administradores también pueden personalizar las invitaciones a reuniones de la organización agregando un logotipo personalizado, una dirección URL de soporte técnico, una dirección URL de renuncia legal o texto de pie de página personalizado.</span><span class="sxs-lookup"><span data-stu-id="03c9a-331">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="03c9a-332">**Complemento de reunión en línea para Lync 2010**   proporciona programación para reuniones de Lync y elimina la capacidad de programar conferencias de Office Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="03c9a-332">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="03c9a-333">**El complemento de conferencia de Office Communicator 2007 R2**   proporciona una programación para las conferencias de Office Live Meeting y las conferencias de Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="03c9a-333">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="03c9a-334">Las conferencias de Live Meeting no se pueden programar en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03c9a-334">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



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
<th><span data-ttu-id="03c9a-335">Cliente de programación</span><span class="sxs-lookup"><span data-stu-id="03c9a-335">Scheduling Client</span></span></th>
<th><span data-ttu-id="03c9a-336">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03c9a-336">Lync Server 2013</span></span></th>
<th><span data-ttu-id="03c9a-337">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="03c9a-337">Lync Server 2010</span></span></th>
<th><span data-ttu-id="03c9a-338">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="03c9a-338">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03c9a-339">Complemento de reunión en línea para Lync 2013 (se puede usar con Office 2013, Outlook 2010 y Outlook 2007)</span><span class="sxs-lookup"><span data-stu-id="03c9a-339">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="03c9a-340">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-340">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-341">Compatible (las nuevas características de complemento no están disponibles)</span><span class="sxs-lookup"><span data-stu-id="03c9a-341">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="03c9a-342">No compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-342">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c9a-343">Programador web de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="03c9a-343">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="03c9a-344">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-344">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-345">No compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-345">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-346">No compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-346">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03c9a-347">Complemento para conferencia en línea para Lync 2010</span><span class="sxs-lookup"><span data-stu-id="03c9a-347">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="03c9a-348">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-348">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-349">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-350">No compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-350">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03c9a-351">Complemento de conferencia de Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="03c9a-351">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="03c9a-352">No compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-352">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-353">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-353">Supported</span></span></p></td>
<td><p><span data-ttu-id="03c9a-354">Compatible</span><span class="sxs-lookup"><span data-stu-id="03c9a-354">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="03c9a-355">Compatibilidad para unirse a reuniones</span><span class="sxs-lookup"><span data-stu-id="03c9a-355">Support for Joining Meetings</span></span>

<span data-ttu-id="03c9a-356">Todos los clientes que admite Lync Server 2013 pueden unirse a reuniones de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="03c9a-356">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="03c9a-357">Puesto que Lync Web App es un componente web del servidor, en los casos en que Lync Web App se usa para unirse a una reunión de Lync Server 2013, se usa siempre la versión más reciente de Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="03c9a-357">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="03c9a-358">Los clientes de Lync 2013 pueden unirse a reuniones hospedadas en Lync 2010 y Office Communications Server 2007 R2 con la funcionalidad de escalado vertical.</span><span class="sxs-lookup"><span data-stu-id="03c9a-358">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="03c9a-359">Las características de la reunión están limitadas por la versión del servidor en el que se hospeda la reunión.</span><span class="sxs-lookup"><span data-stu-id="03c9a-359">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="03c9a-360">Vea también</span><span class="sxs-lookup"><span data-stu-id="03c9a-360">See Also</span></span>


[<span data-ttu-id="03c9a-361">Requisitos de la aplicación de la tienda Windows de Lync para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03c9a-361">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="03c9a-362">Nuevas funciones de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03c9a-362">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="03c9a-363">Novedades para clientes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03c9a-363">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

