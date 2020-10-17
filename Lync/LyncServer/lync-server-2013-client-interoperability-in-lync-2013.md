---
title: 'Lync Server 2013: interoperabilidad de clientes en Lync 2013'
description: 'Lync Server 2013: interoperabilidad de clientes en Lync 2013.'
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
ms.openlocfilehash: 8ea6e90d9479f03dd6d946787e70a2b3cc078699
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549616"
---
# <a name="client-interoperability-in-lync-2013"></a><span data-ttu-id="1b648-103">Interoperabilidad de clientes en Lync 2013</span><span class="sxs-lookup"><span data-stu-id="1b648-103">Client interoperability in Lync 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b648-104">_**Última modificación del tema:** 2016-03-04_</span><span class="sxs-lookup"><span data-stu-id="1b648-104">_**Topic Last Modified:** 2016-03-04_</span></span>

<span data-ttu-id="1b648-105">En este tema se describe la capacidad de los clientes de Microsoft Lync Server 2013 para coexistir e interactuar con clientes de versiones anteriores de Lync Server y Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="1b648-105">This topic discusses the ability of Microsoft Lync Server 2013 clients to coexist and interact with clients from earlier versions of Lync Server and Office Communications Server.</span></span>

<div>

## <a name="server-and-client-compatibility"></a><span data-ttu-id="1b648-106">Compatibilidad con servidores y clientes</span><span class="sxs-lookup"><span data-stu-id="1b648-106">Server and Client Compatibility</span></span>

<span data-ttu-id="1b648-107">En la siguiente tabla se muestran las combinaciones compatibles de versiones de cliente y versiones de servidor.</span><span class="sxs-lookup"><span data-stu-id="1b648-107">The following table shows the supported combinations of client versions and server versions.</span></span> <span data-ttu-id="1b648-108">Esta tabla indica si se admite el inicio de sesión cuando el cliente intenta conectarse al servidor indicado.</span><span class="sxs-lookup"><span data-stu-id="1b648-108">This table indicates whether sign-in is supported when the client attempts to connect to the server indicated.</span></span> <span data-ttu-id="1b648-109">Lync Server 2013 admite la versión de cliente anterior.</span><span class="sxs-lookup"><span data-stu-id="1b648-109">Lync Server 2013 supports the previous client version.</span></span> <span data-ttu-id="1b648-110">Además, a diferencia de las versiones anteriores, Lync Server 2010 admite los nuevos clientes de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="1b648-110">Also, unlike previous releases, Lync Server 2010 supports the new Lync 2013 clients.</span></span> <span data-ttu-id="1b648-111">Esto permite a las organizaciones que actualizan desde Lync Server 2010 implementar nuevos clientes independientes de las actualizaciones de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1b648-111">This allows organizations who are upgrading from Lync Server 2010 to roll out new clients independent of Lync Server upgrades.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b648-112">Cliente</span><span class="sxs-lookup"><span data-stu-id="1b648-112">Client</span></span></th>
<th><span data-ttu-id="1b648-113">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b648-113">Lync Server 2013</span></span></th>
<th><span data-ttu-id="1b648-114">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="1b648-114">Lync Server 2010</span></span></th>
<th><span data-ttu-id="1b648-115">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="1b648-115">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b648-116">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="1b648-116">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="1b648-117">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-117">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-118">Supported5</span><span class="sxs-lookup"><span data-stu-id="1b648-118">Supported5</span></span></p></td>
<td><p><span data-ttu-id="1b648-119">No compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-119">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b648-120">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="1b648-120">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="1b648-121">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-121">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-122">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-122">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-123">No se admite</span><span class="sxs-lookup"><span data-stu-id="1b648-123">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b648-124">Lync Web App 2013</span><span class="sxs-lookup"><span data-stu-id="1b648-124">Lync Web App 2013</span></span></p></td>
<td><p><span data-ttu-id="1b648-125">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-125">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-126">No se admite</span><span class="sxs-lookup"><span data-stu-id="1b648-126">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-127">No se admite</span><span class="sxs-lookup"><span data-stu-id="1b648-127">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b648-128">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="1b648-128">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="1b648-129">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-129">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-130">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-130">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-131">No se admite</span><span class="sxs-lookup"><span data-stu-id="1b648-131">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b648-132">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="1b648-132">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="1b648-133">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-133">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-134">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-134">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-135">No se admite</span><span class="sxs-lookup"><span data-stu-id="1b648-135">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b648-136">Lync 2010 Group Chat</span><span class="sxs-lookup"><span data-stu-id="1b648-136">Lync 2010 Group Chat</span></span></p></td>
<td><p><span data-ttu-id="1b648-137">Supported1</span><span class="sxs-lookup"><span data-stu-id="1b648-137">Supported1</span></span></p></td>
<td><p><span data-ttu-id="1b648-138">Supported2</span><span class="sxs-lookup"><span data-stu-id="1b648-138">Supported2</span></span></p></td>
<td><p><span data-ttu-id="1b648-139">No aplicable</span><span class="sxs-lookup"><span data-stu-id="1b648-139">Not Applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b648-140">Lync Web App 2010</span><span class="sxs-lookup"><span data-stu-id="1b648-140">Lync Web App 2010</span></span></p></td>
<td><p><span data-ttu-id="1b648-141">No compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-141">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-142">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-142">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-143">No se admite</span><span class="sxs-lookup"><span data-stu-id="1b648-143">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b648-144">Lync 2010 Attendee</span><span class="sxs-lookup"><span data-stu-id="1b648-144">Lync 2010 Attendee</span></span></p></td>
<td><p><span data-ttu-id="1b648-145">No Supported3</span><span class="sxs-lookup"><span data-stu-id="1b648-145">Not Supported3</span></span></p></td>
<td><p><span data-ttu-id="1b648-146">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-146">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-147">No se admite</span><span class="sxs-lookup"><span data-stu-id="1b648-147">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b648-148">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="1b648-148">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="1b648-149">Interoperable4</span><span class="sxs-lookup"><span data-stu-id="1b648-149">Interoperable4</span></span></p></td>
<td><p><span data-ttu-id="1b648-150">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-150">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-151">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-151">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b648-152">Operador de Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="1b648-152">Microsoft Office Communications Server 2007 R2 Attendant</span></span></p></td>
<td><p><span data-ttu-id="1b648-153">No compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-153">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-154">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-154">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-155">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-155">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b648-156">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="1b648-156">Office Communicator 2007</span></span></p></td>
<td><p><span data-ttu-id="1b648-157">No compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-157">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-158">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-158">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-159">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-159">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b648-160">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="1b648-160">Office Live Meeting 2007</span></span></p></td>
<td><p><span data-ttu-id="1b648-161">No compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-161">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-162">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-162">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-163">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-163">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b648-164">Aplicación Lync de la tienda Windows</span><span class="sxs-lookup"><span data-stu-id="1b648-164">Lync Windows Store app</span></span></p></td>
<td><p><span data-ttu-id="1b648-165">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-165">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-166">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-166">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-167">No se admite</span><span class="sxs-lookup"><span data-stu-id="1b648-167">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1b648-168">1Para obtener más información, consulte [Migration from Lync server 2010, Group chat o Office Communications server 2007 R2 Group chat to Lync server 2013, servidor de chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="1b648-168">1For details, see [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="1b648-169">2In Microsoft Lync Server 2010, la funcionalidad de chat en grupo estaba disponible con el servidor de chat en grupo, una aplicación de confianza de terceros para Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b648-169">2In Microsoft Lync Server 2010, group chat functionality was available with Group Chat Server, a third-party trusted application for Lync Server 2010.</span></span> <span data-ttu-id="1b648-170">Los clientes de Lync 2013 no son compatibles con Lync Server 2010, chat en grupo.</span><span class="sxs-lookup"><span data-stu-id="1b648-170">Lync 2013 clients are not compatible with Lync Server 2010, Group Chat.</span></span>

<span data-ttu-id="1b648-171">3Lync Web App 2013 ahora proporciona una experiencia completa para la reunión, incluido el audio y el vídeo del equipo, y se considera el reemplazo de Lync 2010 asistente.</span><span class="sxs-lookup"><span data-stu-id="1b648-171">3Lync Web App 2013 now provides a full in-meeting experience, including computer audio and video, and is considered the replacement for Lync 2010 Attendee.</span></span> <span data-ttu-id="1b648-172">Lync 2010 Attendee se conectará a Lync Server 2013 solo cuando use un explorador no admitido (Internet Explorer 6 o Internet Explorer 7) y Windows XP.</span><span class="sxs-lookup"><span data-stu-id="1b648-172">Lync 2010 Attendee will connect to Lync Server 2013 only when you are using an unsupported browser (Internet Explorer 6 or Internet Explorer 7) and Windows XP.</span></span>

<span data-ttu-id="1b648-173">las características de presencia y mensajería instantánea de 4The en Office Communicator 2007 R2 son compatibles con Lync Server 2013, pero las características de conferencia no lo son.</span><span class="sxs-lookup"><span data-stu-id="1b648-173">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="1b648-174">Durante la migración de Office Communications Server 2007 R2, Office Communicator 2007 R2 es apto para la presencia y la interoperabilidad de mi, pero los usuarios deben usar Lync Web App 2013 para unirse a reuniones de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b648-174">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

<span data-ttu-id="1b648-175">5 para conocer las limitaciones, consulte "compatibilidad con la característica de conferencia para clientes de Lync 2013 en Lync Server 2010 reuniones" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="1b648-175">5 For limitations, see "Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings" later in this topic.</span></span>

</div>

<div>

## <a name="interoperability-among-clients"></a><span data-ttu-id="1b648-176">Interoperabilidad entre clientes</span><span class="sxs-lookup"><span data-stu-id="1b648-176">Interoperability among Clients</span></span>

<span data-ttu-id="1b648-177">Con la versión 2013 de Lync Server, varias versiones de cliente pueden interactuar sin problemas en escenarios de punto a punto y de conferencia.</span><span class="sxs-lookup"><span data-stu-id="1b648-177">With the Lync Server 2013 release, various client versions can interact seamlessly in both peer-to-peer and conferencing scenarios.</span></span> <span data-ttu-id="1b648-178">En esta sección se describe la disponibilidad de la función cuando los usuarios interactúan con otros usuarios que hayan iniciado sesión usando un tipo de cliente diferente o una versión anterior del mismo cliente.</span><span class="sxs-lookup"><span data-stu-id="1b648-178">This section discusses feature availability when users interact with other users who are using different versions of clients and servers.</span></span>

<div>

## <a name="peer-to-peer-feature-support"></a><span data-ttu-id="1b648-179">Compatibilidad con la característica de punto a punto</span><span class="sxs-lookup"><span data-stu-id="1b648-179">Peer-to-Peer Feature Support</span></span>

<span data-ttu-id="1b648-p106">Las características de punto a punto son compatibles con los usuarios que están hospedados en versiones distintas del servidor y que utilicen diferentes versiones de cliente. La experiencia del usuario final y las características disponibles consistentes con las capacidades del cliente del usuario y la versión del servidor en el cual el usuario ha iniciado sesión. Dicho de otra manera:</span><span class="sxs-lookup"><span data-stu-id="1b648-p106">Peer-to-peer features are supported for users who are homed on different versions of the server and who are using different client versions. The end-user experience and available features are consistent with the capabilities of the user’s client and the version of the server the user is signed in to. In other words:</span></span>

  - <span data-ttu-id="1b648-183">Si un usuario ha iniciado sesión en Lync Server 2013 con un cliente antiguo, el usuario tendrá la misma experiencia en la que se usa.</span><span class="sxs-lookup"><span data-stu-id="1b648-183">If a user is signed in to Lync Server 2013 with an older client, the user will have the same experience he or she is used to.</span></span> <span data-ttu-id="1b648-184">Ninguna de las nuevas características que se incluyen en Lync Server 2013 estará disponible hasta que se actualice el cliente del usuario.</span><span class="sxs-lookup"><span data-stu-id="1b648-184">None of the new features introduced in Lync Server 2013 will be available until the user’s client is upgraded.</span></span> <span data-ttu-id="1b648-185">Algunos ejemplos son la vista de la galería de vídeos, vídeo HD, uso compartido de PowerPoint actualizado y la opción de silenciar el audio y vídeo de todos los asistentes tras la entrada de la reunión.</span><span class="sxs-lookup"><span data-stu-id="1b648-185">Examples include video gallery view, HD video, updated PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="1b648-186">Las nuevas características se describen en [nuevas características de conferencia en Lync server 2013](lync-server-2013-new-conferencing-features.md) y las novedades [para clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="1b648-186">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

  - <span data-ttu-id="1b648-187">Si un usuario ha iniciado sesión en Lync Server 2010 con un cliente de Lync 2013, las nuevas características que no son compatibles con Lync Server 2010 no estarán disponibles hasta que el usuario se mueva a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b648-187">If a user is signed in to Lync Server 2010 with a Lync 2013 client, any new features not supported by Lync Server 2010 will be unavailable until the user is moved to Lync Server 2013.</span></span>

<span data-ttu-id="1b648-188">En la tabla siguiente se compara la disponibilidad de las características de las sesiones punto a punto en las que el cliente ha iniciado sesión en Lync Server 2013 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b648-188">The following table compares feature availability in peer-to-peer sessions where the client is signed in to either Lync Server 2013 or Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1b648-189">Lync Web App y Lync 2010 Attendee son clientes de solo reunión que no se incluyen en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="1b648-189">Lync Web App and Lync 2010 Attendee are meeting-only clients and aren’t included in this table.</span></span>



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
<th><span data-ttu-id="1b648-190">Cliente</span><span class="sxs-lookup"><span data-stu-id="1b648-190">Client</span></span></th>
<th><span data-ttu-id="1b648-191">Mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="1b648-191">Instant Messaging</span></span></th>
<th><span data-ttu-id="1b648-192">Presencia</span><span class="sxs-lookup"><span data-stu-id="1b648-192">Presence</span></span></th>
<th><span data-ttu-id="1b648-193">Voz</span><span class="sxs-lookup"><span data-stu-id="1b648-193">Voice</span></span></th>
<th><span data-ttu-id="1b648-194">Vídeo</span><span class="sxs-lookup"><span data-stu-id="1b648-194">Video</span></span></th>
<th><span data-ttu-id="1b648-195">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="1b648-195">Application Sharing</span></span></th>
<th><span data-ttu-id="1b648-196">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="1b648-196">File Transfer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b648-197">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="1b648-197">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="1b648-198">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-199">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-200">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-200">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-201">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-201">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-202">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-203">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-203">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b648-204">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="1b648-204">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="1b648-205">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-205">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-206">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-207">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-208">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-209">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-210">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-210">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b648-211">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="1b648-211">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="1b648-212">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-213">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-214">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-215">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-216">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-217">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-217">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b648-218">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="1b648-218">Lync 2010 Attendant</span></span></p></td>
<td><p><span data-ttu-id="1b648-219">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-220">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-220">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-221">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-221">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b648-222">Lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="1b648-222">Lync 2010 Mobile</span></span></p></td>
<td><p><span data-ttu-id="1b648-223">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-224">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-224">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b648-225">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="1b648-225">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="1b648-226">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-227">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-227">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-228">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-228">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b648-229">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="1b648-229">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="1b648-230">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-230">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-231">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-231">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-232">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-233">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-233">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-234">Yes1</span><span class="sxs-lookup"><span data-stu-id="1b648-234">Yes1</span></span></p></td>
<td><p><span data-ttu-id="1b648-235">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-235">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b648-236">Mensajería instantánea pública (AOL, Yahoo!)</span><span class="sxs-lookup"><span data-stu-id="1b648-236">Public IM (AOL, Yahoo!)</span></span></p></td>
<td><p><span data-ttu-id="1b648-237">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-237">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-238">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-238">Yes</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b648-239">Mensajería instantánea pública (MSN, Windows Live Messenger)</span><span class="sxs-lookup"><span data-stu-id="1b648-239">Public IM (MSN, Windows Live Messenger)</span></span></p></td>
<td><p><span data-ttu-id="1b648-240">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-241">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-241">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-242">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-243">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-243">Yes</span></span></p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="1b648-244">A partir del 1 de septiembre de 2012, la licencia de suscripción de usuario de la conectividad de mensajería instantánea pública de Microsoft Lync (PIC USL) ya no está disponible para la compra de contratos nuevos o de renovación.</span><span class="sxs-lookup"><span data-stu-id="1b648-244">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="1b648-245">Los clientes con licencias activas podrán seguir federando a Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1b648-245">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="1b648-246">Messenger hasta la fecha de cierre del servicio.</span><span class="sxs-lookup"><span data-stu-id="1b648-246">Messenger until the service shutdown date.</span></span> <span data-ttu-id="1b648-247">Una fecha de finalización del ciclo de vida de junio de 2014 para AOL y Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1b648-247">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="1b648-248">se ha anunciado.</span><span class="sxs-lookup"><span data-stu-id="1b648-248">has been announced.</span></span> <span data-ttu-id="1b648-249">Para obtener más información, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">compatibilidad con la conectividad de mensajería instantánea pública en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1b648-249">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>..</span></span></P>
> <LI>
> <P><span data-ttu-id="1b648-250">La capa de PIC es una licencia por usuario, por mes, que es necesaria para que Lync Server u Office Communications Server se federe con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1b648-250">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="1b648-251">Service.</span><span class="sxs-lookup"><span data-stu-id="1b648-251">Messenger.</span></span> <span data-ttu-id="1b648-252">La capacidad de Microsoft para proporcionar este servicio ha estado supeditada al soporte de Yahoo!, el acuerdo subyacente que no se renovará.</span><span class="sxs-lookup"><span data-stu-id="1b648-252">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="1b648-253">Más que nunca, Lync es una herramienta eficaz para la conexión entre organizaciones y con personas de todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="1b648-253">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="1b648-254">La Federación con Windows Live Messenger no requiere licencias de usuario o de dispositivo adicionales aparte de la CAL de Lync Standard.</span><span class="sxs-lookup"><span data-stu-id="1b648-254">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="1b648-255">La Federación de Skype se agregará a esta lista, lo que permite a los usuarios de Lync llegar a cientos de millones de personas a través de mensajería instantánea y voz.</span><span class="sxs-lookup"><span data-stu-id="1b648-255">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="1b648-256">1 en Office Communicator 2007 R2, solo está disponible el uso compartido de escritorio (y no el uso compartido de programas).</span><span class="sxs-lookup"><span data-stu-id="1b648-256">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1b648-257">El uso compartido de escritorio entre Office Communicator 2007 R2 y Skype empresarial 2015 no se puede iniciar desde el cliente más reciente cuando se aplica la interfaz de usuario del cliente 2015 de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="1b648-257">Desktop sharing between Office Communicator 2007 R2 and Skype for Business 2015 cannot be initiated from the newer client when the Skype for Business 2015 client user interface is enforced.</span></span>



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a><span data-ttu-id="1b648-258">Compatibilidad con la característica de conferencia para clientes de Lync 2013 en reuniones de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="1b648-258">Conferencing Feature Support for Lync 2013 Clients in Lync Server 2010 Meetings</span></span>

<span data-ttu-id="1b648-259">Cuando los usuarios se unen a reuniones de Lync Server 2010 con un cliente de Lync 2013, tienen acceso a las características de cliente de Lync 2013 con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="1b648-259">When users join Lync Server 2010 meetings with a Lync 2013 client, they have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="1b648-260">En las opciones de administración de **participantes** , a las que se puede tener acceso seleccionando el icono de personas en la ventana de la reunión, la opción de **mensajería instantánea sin reunión** no funciona.</span><span class="sxs-lookup"><span data-stu-id="1b648-260">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="1b648-261">La vista de Galería no funciona en las videoconferencias.</span><span class="sxs-lookup"><span data-stu-id="1b648-261">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="1b648-262">El usuario solo ve el participante activo en lugar de todos los altavoces.</span><span class="sxs-lookup"><span data-stu-id="1b648-262">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="1b648-263">En la lista de opciones de **selección de un diseño** , la **vista de Galería** no está disponible</span><span class="sxs-lookup"><span data-stu-id="1b648-263">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="1b648-264">La lista de participantes se muestra de forma predeterminada en las videoconferencias.</span><span class="sxs-lookup"><span data-stu-id="1b648-264">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="1b648-265">Al hacer clic con el botón derecho en un usuario de la lista participantes, las opciones **bloquear la luz de vídeo** y **anclar al** participante de la galería no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="1b648-265">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a><span data-ttu-id="1b648-266">Compatibilidad con la característica de conferencias en reuniones de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b648-266">Conferencing Feature Support in Lync Server 2013 Meetings</span></span>

<span data-ttu-id="1b648-267">Lync Server 2013 proporciona nuevas características de conferencia que se ponen a disposición de los usuarios después de que sus cuentas se muevan a Lync Server 2013 y inician sesión con el cliente de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="1b648-267">Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="1b648-268">Algunos ejemplos son la vista de la galería de vídeos, vídeo HD, uso compartido de PowerPoint y la opción de silenciar todo el audio y vídeo de los asistentes tras la entrada de la reunión.</span><span class="sxs-lookup"><span data-stu-id="1b648-268">Examples include video gallery view, HD video, PowerPoint sharing, and the option to mute all attendee audio and video upon meeting entry.</span></span> <span data-ttu-id="1b648-269">Las nuevas características se describen en [nuevas características de conferencia en Lync server 2013](lync-server-2013-new-conferencing-features.md) y las novedades [para clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="1b648-269">The new features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="1b648-270">En las reuniones de Lync Server 2013, se admiten ciertas características de conferencia para los usuarios hospedados en distintas versiones del servidor y que usan clientes y versiones de cliente diferentes.</span><span class="sxs-lookup"><span data-stu-id="1b648-270">In Lync Server 2013 meetings, certain conferencing features are supported for users who are homed on different versions of the server and who are using different clients and client versions.</span></span> <span data-ttu-id="1b648-271">Cuando los clientes se unen a una reunión de 2013 de Lync Server, los usuarios tienen acceso a las características y funciones que se muestran en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="1b648-271">When clients join a Lync Server 2013 meeting, users have access to the features and capabilities shown in this table.</span></span>


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
<th><span data-ttu-id="1b648-272">Cliente</span><span class="sxs-lookup"><span data-stu-id="1b648-272">Client</span></span></th>
<th><span data-ttu-id="1b648-273">Mensajería instantánea punto a punto</span><span class="sxs-lookup"><span data-stu-id="1b648-273">Peer-to-peer IM</span></span></th>
<th><span data-ttu-id="1b648-274">Voz</span><span class="sxs-lookup"><span data-stu-id="1b648-274">Voice</span></span></th>
<th><span data-ttu-id="1b648-275">Vídeo</span><span class="sxs-lookup"><span data-stu-id="1b648-275">Video</span></span></th>
<th><span data-ttu-id="1b648-276">Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="1b648-276">Application Sharing</span></span></th>
<th><span data-ttu-id="1b648-277">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="1b648-277">PowerPoint</span></span></th>
<th><span data-ttu-id="1b648-278">Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="1b648-278">File Transfer</span></span></th>
<th><span data-ttu-id="1b648-279">Whiteboard</span><span class="sxs-lookup"><span data-stu-id="1b648-279">Whiteboard</span></span></th>
<th><span data-ttu-id="1b648-280">Sondeo</span><span class="sxs-lookup"><span data-stu-id="1b648-280">Polling</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b648-281">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="1b648-281">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="1b648-282">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-283">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-283">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-284">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-284">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-285">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-285">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-286">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-287">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-287">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-288">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-288">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-289">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-289">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b648-290">Lync 2013 Basic</span><span class="sxs-lookup"><span data-stu-id="1b648-290">Lync 2013 Basic</span></span></p></td>
<td><p><span data-ttu-id="1b648-291">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-291">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-292">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-292">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-293">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-293">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-294">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-295">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-295">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-296">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-296">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-297">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-297">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-298">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-298">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b648-299">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="1b648-299">Lync Web App</span></span></p></td>
<td><p><span data-ttu-id="1b648-300">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-300">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-301">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-301">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-302">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-303">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-303">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-304">Sí2</span><span class="sxs-lookup"><span data-stu-id="1b648-304">Yes2</span></span></p></td>
<td><p><span data-ttu-id="1b648-305">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-305">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-306">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-306">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-307">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-307">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b648-308">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="1b648-308">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="1b648-309">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-309">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-310">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-310">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-311">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-312">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-312">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-313">Yes3</span><span class="sxs-lookup"><span data-stu-id="1b648-313">Yes3</span></span></p></td>
<td><p><span data-ttu-id="1b648-314">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-314">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-315">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-315">Yes</span></span></p></td>
<td><p><span data-ttu-id="1b648-316">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-316">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b648-317">Office Communicator 2007 R2 4</span><span class="sxs-lookup"><span data-stu-id="1b648-317">Office Communicator 2007 R2 4</span></span></p></td>
<td><p><span data-ttu-id="1b648-318">Sí</span><span class="sxs-lookup"><span data-stu-id="1b648-318">Yes</span></span></p></td>
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


<span data-ttu-id="1b648-319">1 en Office Communicator 2007 R2, solo está disponible el uso compartido de escritorio (y no el uso compartido de programas).</span><span class="sxs-lookup"><span data-stu-id="1b648-319">1 In Office Communicator 2007 R2, only desktop sharing (and not program sharing) is available.</span></span>

<span data-ttu-id="1b648-320">2 Lync Server 2013 usa un mecanismo actualizado para cargar archivos de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="1b648-320">2 Lync Server 2013 uses an updated mechanism for uploading PowerPoint files.</span></span> <span data-ttu-id="1b648-321">Lync Web App los usuarios que se unen a una reunión programada originalmente en Lync Server 2010 pueden ver y navegar por las presentaciones de PowerPoint, pero no pueden cargar archivos de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="1b648-321">Lync Web App users who join a meeting that was originally scheduled on Lync Server 2010 can view and navigate PowerPoint presentations, but cannot upload PowerPoint files.</span></span>

<span data-ttu-id="1b648-322">3 si la reunión se programó en Lync Server 2013 y un cliente de Lync 2013 cargó las diapositivas de PowerPoint, los usuarios de Lync 2010 tienen acceso de solo vista a las diapositivas.</span><span class="sxs-lookup"><span data-stu-id="1b648-322">3 If the meeting was scheduled on Lync Server 2013 and PowerPoint slides were uploaded by a Lync 2013 client, Lync 2010 users have view-only access to the slides.</span></span> <span data-ttu-id="1b648-323">Por el contrario, si un usuario de Lync 2010 cargó las diapositivas de PowerPoint, los usuarios de Lync Server 2013 podrán ver y diapositivas y, si Office Web Apps Server está configurado, accederá a nuevas capacidades como, por ejemplo, la visualización de una mayor resolución, animaciones, transiciones de diapositivas y vídeo incrustado.</span><span class="sxs-lookup"><span data-stu-id="1b648-323">Conversely, if the PowerPoint slides were uploaded by a Lync 2010 user, Lync Server 2013 users will be able to view and slides and, if Office Web Apps Server is configured, access new capabilities such as higher resolution display, animations, slide transitions, and embedded video.</span></span> <span data-ttu-id="1b648-324">Para obtener más información, consulte Configuración de la [integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="1b648-324">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="1b648-325">las características de presencia y mensajería instantánea de 4The en Office Communicator 2007 R2 son compatibles con Lync Server 2013, pero las características de conferencia no lo son.</span><span class="sxs-lookup"><span data-stu-id="1b648-325">4The presence and IM features in Office Communicator 2007 R2 are compatible with Lync Server 2013, but conferencing features are not.</span></span> <span data-ttu-id="1b648-326">Durante la migración de Office Communications Server 2007 R2, Office Communicator 2007 R2 es apto para la presencia y la interoperabilidad de mi, pero los usuarios deben usar Lync Web App 2013 para unirse a reuniones de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b648-326">During migration from Office Communications Server 2007 R2, Office Communicator 2007 R2 is suitable for presence and IM interoperability, but users should use Lync Web App 2013 to join Lync Server 2013 meetings.</span></span>

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a><span data-ttu-id="1b648-327">Compatibilidad con el complemento de programación</span><span class="sxs-lookup"><span data-stu-id="1b648-327">Scheduling Add-in Support</span></span>

<span data-ttu-id="1b648-328">La compatibilidad del servidor con varios complementos de programación es consistente con la compatibilidad de versión del cliente y del servidor.</span><span class="sxs-lookup"><span data-stu-id="1b648-328">Server support for the various scheduling add-ins is consistent with server and client version compatibility.</span></span> <span data-ttu-id="1b648-329">En general, los siguientes complementos de programación se admiten en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b648-329">In general, the following scheduling add-ins are supported on Lync Server 2013.</span></span> <span data-ttu-id="1b648-330">Sin embargo, las versiones anteriores de los complementos no proporcionan nuevas características de complemento de Lync 2013, como la opción de silenciar todo el audio y vídeo de los asistentes tras la entrada de la reunión.</span><span class="sxs-lookup"><span data-stu-id="1b648-330">However, previous versions of add-ins do not provide new Lync 2013 add-in features, such as the option to mute all attendee audio and video upon meeting entry.</span></span>

  - <span data-ttu-id="1b648-331">**Complemento para reunión en línea para Lync 2013**     Proporciona las mismas características que el complemento de reunión en línea para Lync 2010, con la adición de controles de silencio de asistentes, que permiten a los organizadores de reuniones programar conferencias en las que el audio y el vídeo del asistente están silenciados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1b648-331">**Online Meeting Add-in for Lync 2013**   Provides the same features as the Online Meeting Add-in for Lync 2010, with the addition of attendee mute controls, which allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span> <span data-ttu-id="1b648-332">Los administradores también pueden personalizar las invitaciones de la organización para la reunión agregando un logo personalizado, una URL de ayuda, una dirección URL del aviso legal o un texto de pie de página personalizado.</span><span class="sxs-lookup"><span data-stu-id="1b648-332">Administrators can also customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span>

  - <span data-ttu-id="1b648-333">**Complemento para reunión en línea para Lync 2010**     Proporciona una programación para reuniones de Lync y elimina la capacidad de programar conferencias de Office Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="1b648-333">**Online Meeting Add-in for Lync 2010**   Provides scheduling for Lync meetings and removes the capability to schedule Office Live Meeting conferences.</span></span>

  - <span data-ttu-id="1b648-334">**Complemento de conferencia de**     Office Communicator 2007 R2 Proporciona una programación para las conferencias de Office Live Meeting y las conferencias de Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1b648-334">**Office Communicator 2007 R2 Conferencing Add-in**   Provides scheduling for both Office Live Meeting conferences and Office Communicator 2007 R2 conferences.</span></span> 

<div>


> [!NOTE]  
> <span data-ttu-id="1b648-335">Las conferencias de Live Meeting no se pueden programar en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b648-335">Live Meeting conferences cannot be scheduled on Lync Server 2013.</span></span>



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
<th><span data-ttu-id="1b648-336">Cliente de programación</span><span class="sxs-lookup"><span data-stu-id="1b648-336">Scheduling Client</span></span></th>
<th><span data-ttu-id="1b648-337">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b648-337">Lync Server 2013</span></span></th>
<th><span data-ttu-id="1b648-338">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="1b648-338">Lync Server 2010</span></span></th>
<th><span data-ttu-id="1b648-339">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="1b648-339">Office Communications Server 2007 R2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b648-340">Complemento para reunión en línea para Lync 2013 (se puede usar con Office 2013, Outlook 2010 y Outlook 2007)</span><span class="sxs-lookup"><span data-stu-id="1b648-340">Online Meeting Add-in for Lync 2013 (can be used with Office 2013, Outlook 2010, and Outlook 2007)</span></span></p></td>
<td><p><span data-ttu-id="1b648-341">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-341">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-342">Compatible (nuevas características del complemento no disponibles)</span><span class="sxs-lookup"><span data-stu-id="1b648-342">Supported (new add-in features not available)</span></span></p></td>
<td><p><span data-ttu-id="1b648-343">No se admite</span><span class="sxs-lookup"><span data-stu-id="1b648-343">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b648-344">Programador web de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="1b648-344">Lync 2013 Web Scheduler</span></span></p></td>
<td><p><span data-ttu-id="1b648-345">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-345">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-346">No se admite</span><span class="sxs-lookup"><span data-stu-id="1b648-346">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-347">No se admite</span><span class="sxs-lookup"><span data-stu-id="1b648-347">Not Supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b648-348">Complemento de conferencia en línea para Lync 2010</span><span class="sxs-lookup"><span data-stu-id="1b648-348">Online Meeting Add-in for Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="1b648-349">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-349">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-350">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-350">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-351">No se admite</span><span class="sxs-lookup"><span data-stu-id="1b648-351">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b648-352">Complemento para conferencias de Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="1b648-352">Office Communicator 2007 R2 Conferencing Add-in</span></span></p></td>
<td><p><span data-ttu-id="1b648-353">No compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-353">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-354">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-354">Supported</span></span></p></td>
<td><p><span data-ttu-id="1b648-355">Compatible</span><span class="sxs-lookup"><span data-stu-id="1b648-355">Supported</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a><span data-ttu-id="1b648-356">Ayuda para unirse a una conferencia</span><span class="sxs-lookup"><span data-stu-id="1b648-356">Support for Joining Meetings</span></span>

<span data-ttu-id="1b648-357">Todos los clientes que admite Lync Server 2013 pueden unirse a reuniones de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="1b648-357">All of the clients that Lync Server 2013 supports are allowed to join Lync 2013 meetings.</span></span> <span data-ttu-id="1b648-358">Dado que Lync Web App es un componente web del servidor, en los casos en que Lync Web App se usa para unirse a una reunión de Lync Server 2013, siempre se usa la versión más reciente de Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="1b648-358">Because Lync Web App is a web component of the server, in cases where Lync Web App is used to join a Lync Server 2013 meeting, the newer version of Lync Web App is always used.</span></span>

<span data-ttu-id="1b648-359">Los clientes de Lync 2013 pueden unirse a reuniones hospedadas en Lync 2010 y Office Communications Server 2007 R2 con funcionalidad de escalado.</span><span class="sxs-lookup"><span data-stu-id="1b648-359">Lync 2013 clients can join meetings hosted on Lync 2010 and Office Communications Server 2007 R2 with scaled-down functionality.</span></span> <span data-ttu-id="1b648-360">Las características de reunión están limitadas por la versión del servidor en el cual se hospeda la reunión.</span><span class="sxs-lookup"><span data-stu-id="1b648-360">In-meeting features are limited by the version of the server on which the meeting is hosted.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1b648-361">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1b648-361">See Also</span></span>


[<span data-ttu-id="1b648-362">Requisitos de aplicaciones de la tienda Windows Lync para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b648-362">Lync Windows Store app requirements for Lync Server 2013</span></span>](lync-server-2013-lync-windows-store-app-requirements.md)  
[<span data-ttu-id="1b648-363">Nuevas características de conferencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b648-363">New conferencing features in Lync Server 2013</span></span>](lync-server-2013-new-conferencing-features.md)  
[<span data-ttu-id="1b648-364">Novedades para clientes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b648-364">What's new for clients in Lync Server 2013</span></span>](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

