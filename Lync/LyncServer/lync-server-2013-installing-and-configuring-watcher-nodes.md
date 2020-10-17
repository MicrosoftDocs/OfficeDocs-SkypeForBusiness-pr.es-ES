---
title: 'Lync Server 2013: instalar y configurar nodos de monitor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 980dc8c92488e3806cd6c1bf15970a79af6fa2b4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534947"
---
# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="d49f5-102">Instalación y configuración de nodos de monitor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d49f5-102">Installing and configuring watcher nodes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d49f5-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="d49f5-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="d49f5-104">Los *nodos de monitor* son equipos que ejecutan periódicamente transacciones sintéticas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d49f5-104">*Watcher nodes* are computers that periodically run Lync Server synthetic transactions.</span></span> <span data-ttu-id="d49f5-105">*Las transacciones sintéticas* son cmdlets de Windows PowerShell que comprueban que los escenarios clave de usuario final (como la capacidad de iniciar sesión en el sistema o la capacidad de intercambiar mensajes instantáneos) funcionan según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="d49f5-105">*Synthetic transactions* are Windows PowerShell cmdlets that verify that key end user scenarios—such as the ability to sign in to the system, or the ability to exchange instant messages—are working as expected.</span></span> <span data-ttu-id="d49f5-106">Para Lync Server 2013, System Center Operations Manager puede ejecutar las transacciones sintéticas que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d49f5-106">For Lync Server 2013, System Center Operations Manager can run the synthetic transactions shown in the following table.</span></span> <span data-ttu-id="d49f5-107">Existen tres tipos distintos de transacción sintética en la tabla:</span><span class="sxs-lookup"><span data-stu-id="d49f5-107">There are three different synthetic transaction types shown in the table:</span></span>

  - <span data-ttu-id="d49f5-108">**Valor predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="d49f5-108">**Default**.</span></span> <span data-ttu-id="d49f5-109">Estas son las transacciones sintéticas que se ejecutarán de forma predeterminada con un nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="d49f5-109">These are the synthetic transactions that a watcher node will run by default.</span></span> <span data-ttu-id="d49f5-110">Al crear un nuevo nodo de monitor, tiene la opción de especificar qué transacciones sintéticas se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="d49f5-110">When you create a new watcher node, you have the option of specifying which synthetic transactions that node will run.</span></span> <span data-ttu-id="d49f5-111">(Este es el propósito del parámetro tests usado por el cmdlet **New-CsWatcherNodeConfiguration** ). Si no usa el parámetro tests cuando se crea el nodo de monitor, se ejecutarán automáticamente todas las transacciones sintéticas predeterminadas y no se ejecutará ninguna de las transacciones sintéticas que no sean predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="d49f5-111">(That's the purpose of the Tests parameter used by the **New-CsWatcherNodeConfiguration** cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="d49f5-112">Esto significa que, por ejemplo, el nodo de monitor se configurará para ejecutar la prueba de Test-CsAddressBookService, pero no se configurará para ejecutar la prueba de Test-CsExumConnectivity.</span><span class="sxs-lookup"><span data-stu-id="d49f5-112">That means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>

  - <span data-ttu-id="d49f5-113">**No predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="d49f5-113">**Non-default**.</span></span> <span data-ttu-id="d49f5-114">Como su nombre indica, las transacciones sintéticas no predeterminadas son pruebas que los nodos de monitor no se ejecutan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d49f5-114">As the name implies, Non-default synthetic transactions are tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="d49f5-115">Sin embargo, el nodo de monitor se puede habilitar para ejecutar cualquiera de las transacciones sintéticas que no son predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="d49f5-115">However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="d49f5-116">Puede hacerlo cuando cree el nodo de monitor (mediante el cmdlet **New-CsWatcherNodeConfiguration** ) o en cualquier momento después.</span><span class="sxs-lookup"><span data-stu-id="d49f5-116">You can do this when you create the watcher node (by using the **New-CsWatcherNodeConfiguration** cmdlet), or at any time after that.</span></span> <span data-ttu-id="d49f5-117">Muchas de las transacciones sintéticas no predeterminadas requieren pasos de configuración adicionales.</span><span class="sxs-lookup"><span data-stu-id="d49f5-117">Many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="d49f5-118">Para obtener más información, consulte [instrucciones de configuración especiales para transacciones sintéticas en Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="d49f5-118">For details, see [Special setup instructions for synthetic transactions in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span></span>

  - <span data-ttu-id="d49f5-119">**Ampliado**.</span><span class="sxs-lookup"><span data-stu-id="d49f5-119">**Extended**.</span></span> <span data-ttu-id="d49f5-120">Las pruebas extendidas son un tipo especial de transacción sintética no predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d49f5-120">Extended tests are a special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="d49f5-121">A diferencia de otras transacciones sintéticas, las pruebas extendidas se pueden ejecutar varias veces durante cada pasada.</span><span class="sxs-lookup"><span data-stu-id="d49f5-121">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="d49f5-122">Esto puede ser útil cuando se comprueba el comportamiento como varias rutas de voz de red telefónica conmutada (RTC) para un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="d49f5-122">This can be useful when verifying behavior such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="d49f5-123">Esto se puede configurar simplemente agregando varias instancias de una prueba extendida a un nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="d49f5-123">This can be configured simply by adding multiple instances of an Extended test to a watcher node.</span></span>

<span data-ttu-id="d49f5-124">Para obtener información detallada sobre el proceso de agregar otras transacciones sintéticas a un nodo de monitor, consulte [administrar nodos de monitor en Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="d49f5-124">For details about the process of adding other synthetic transactions to a watcher node, see [Managing watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span></span> <span data-ttu-id="d49f5-125">Puede usar el shell de administración de Lync Server para quitar transacciones sintéticas de un nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="d49f5-125">You can use the Lync Server Management Shell to remove synthetic transactions from a watcher node.</span></span>

<span data-ttu-id="d49f5-126">Las transacciones sintéticas disponibles para los nodos de monitor son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="d49f5-126">The synthetic transactions available to watcher nodes include the following:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d49f5-127">Nombre del cmdlet (nombre de la prueba)</span><span class="sxs-lookup"><span data-stu-id="d49f5-127">Cmdlet Name (Test Name)</span></span></th>
<th><span data-ttu-id="d49f5-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="d49f5-128">Description</span></span></th>
<th><span data-ttu-id="d49f5-129">Tipo de transacción sintética</span><span class="sxs-lookup"><span data-stu-id="d49f5-129">Synthetic Transaction Type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d49f5-130">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="d49f5-130">Test-CsAddressBookService (ABS)</span></span></p></td>
<td><p><span data-ttu-id="d49f5-131">Confirma que los usuarios pueden buscar usuarios que no estén en su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="d49f5-131">Confirms that users are able to look up users that aren’t in their contact list.</span></span></p></td>
<td><p><span data-ttu-id="d49f5-132">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="d49f5-132">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49f5-133">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="d49f5-133">Test-CsAddressBookWebQuery (ABWQ)</span></span></p></td>
<td><p><span data-ttu-id="d49f5-134">Confirma que los usuarios pueden buscar usuarios que no estén en su lista de contactos mediante HTTP.</span><span class="sxs-lookup"><span data-stu-id="d49f5-134">Confirms that users are able to look up users that aren’t in their contact list via HTTP.</span></span></p></td>
<td><p><span data-ttu-id="d49f5-135">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="d49f5-135">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49f5-136">Test-CsIM (IM)</span><span class="sxs-lookup"><span data-stu-id="d49f5-136">Test-CsIM (IM)</span></span></p></td>
<td><p><span data-ttu-id="d49f5-137">Confirma que los usuarios pueden enviar mensajes instantáneos punto a punto.</span><span class="sxs-lookup"><span data-stu-id="d49f5-137">Confirms that users are able to send peer-to-peer instant messages.</span></span></p></td>
<td><p><span data-ttu-id="d49f5-138">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="d49f5-138">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49f5-139">Test-CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="d49f5-139">Test-CsP2PAV (P2PAV)</span></span></p></td>
<td><p><span data-ttu-id="d49f5-140">Confirma que los usuarios pueden realizar llamadas de audio punto a punto (solo señalización).</span><span class="sxs-lookup"><span data-stu-id="d49f5-140">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span></p></td>
<td><p><span data-ttu-id="d49f5-141">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="d49f5-141">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49f5-142">Test-CsPresence (Presence)</span><span class="sxs-lookup"><span data-stu-id="d49f5-142">Test-CsPresence (Presence)</span></span></p></td>
<td><p><span data-ttu-id="d49f5-143">Confirma que los usuarios pueden ver la presencia de otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="d49f5-143">Confirms that users are able to view other users’ presence.</span></span></p></td>
<td><p><span data-ttu-id="d49f5-144">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="d49f5-144">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49f5-145">Test-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="d49f5-145">Test-CsRegistration (Registration)</span></span></p></td>
<td><p><span data-ttu-id="d49f5-146">Confirma que los usuarios pueden iniciar sesión en Lync.</span><span class="sxs-lookup"><span data-stu-id="d49f5-146">Confirms that users are able sign in to Lync.</span></span></p></td>
<td><p><span data-ttu-id="d49f5-147">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="d49f5-147">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49f5-148">Test-CsAudioConferencingProvider (ACP)</span><span class="sxs-lookup"><span data-stu-id="d49f5-148">Test-CsAudioConferencingProvider (ACP)</span></span></p></td>
<td><p><span data-ttu-id="d49f5-149">No se usa con la versión local de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d49f5-149">Not used with the on-premises version of Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="d49f5-150">Extendido</span><span class="sxs-lookup"><span data-stu-id="d49f5-150">Extended</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49f5-151">Test-CsPstnPeerToPeerCall (RTC)</span><span class="sxs-lookup"><span data-stu-id="d49f5-151">Test-CsPstnPeerToPeerCall (PSTN)</span></span></p></td>
<td><p><span data-ttu-id="d49f5-152">Confirma que los usuarios pueden hacer y recibir llamadas con gente ajena a la empresa (números de RTC).</span><span class="sxs-lookup"><span data-stu-id="d49f5-152">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span></p></td>
<td><p><span data-ttu-id="d49f5-153">No predeterminada, ampliada</span><span class="sxs-lookup"><span data-stu-id="d49f5-153">Non-default, Extended</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49f5-154">Test-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="d49f5-154">Test-CsAVConference (AvConference)</span></span></p></td>
<td><p><span data-ttu-id="d49f5-155">Confirma que los usuarios pueden crear conferencias de audio/vídeo y participar en ellas.</span><span class="sxs-lookup"><span data-stu-id="d49f5-155">Confirms that users are able to create and participate in an audio/video conference.</span></span></p></td>
<td><p><span data-ttu-id="d49f5-156">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="d49f5-156">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49f5-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="d49f5-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="d49f5-158">Confirma que los servidores perimetrales A/V pueden aceptar conexiones para las llamadas punto a punto y las llamadas de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d49f5-158">Confirms that the A/V Edge servers are able to accept connections for peer-to-peer calls and conference calls.</span></span></p></td>
<td><p><span data-ttu-id="d49f5-159">No predeterminado</span><span class="sxs-lookup"><span data-stu-id="d49f5-159">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49f5-160">Test-CsDataConference (congresos)</span><span class="sxs-lookup"><span data-stu-id="d49f5-160">Test-CsDataConference (DataConference)</span></span></p></td>
<td><p><span data-ttu-id="d49f5-161">Confirma que los usuarios pueden participar en una conferencia de colaboración de datos, una reunión en línea que engloba actividades como pizarras y sondeos.</span><span class="sxs-lookup"><span data-stu-id="d49f5-161">Confirms that users can participate in a data collaboration conference, an online meeting that includes activities such as whiteboards and polls.</span></span></p></td>
<td><p><span data-ttu-id="d49f5-162">No predeterminado</span><span class="sxs-lookup"><span data-stu-id="d49f5-162">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49f5-163">Test-CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="d49f5-163">Test-CsExumConnectivity (ExumConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="d49f5-164">Confirma que un usuario puede conectarse a la mensajería unificada (UM) de Exchange.</span><span class="sxs-lookup"><span data-stu-id="d49f5-164">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="d49f5-165">No predeterminado</span><span class="sxs-lookup"><span data-stu-id="d49f5-165">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49f5-166">Test-CsGroupIM (GroupIM)</span><span class="sxs-lookup"><span data-stu-id="d49f5-166">Test-CsGroupIM (GroupIM)</span></span></p></td>
<td><p><span data-ttu-id="d49f5-167">Confirma que los usuarios pueden enviar mensajes instantáneos durante las conferencias y participar en conversaciones de mensajes instantáneos con tres o más personas.</span><span class="sxs-lookup"><span data-stu-id="d49f5-167">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span></p></td>
<td><p><span data-ttu-id="d49f5-168">Predeterminado</span><span class="sxs-lookup"><span data-stu-id="d49f5-168">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49f5-169">Test-CsGroupIM – TestJoinLauncher (JoinLauncher)</span><span class="sxs-lookup"><span data-stu-id="d49f5-169">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span></span></p></td>
<td><p><span data-ttu-id="d49f5-170">Confirma que los usuarios pueden crear reuniones programadas y unirse a ellas a través de un vínculo de dirección web.</span><span class="sxs-lookup"><span data-stu-id="d49f5-170">Confirms that users are able to create and join scheduled meetings via a web address link.</span></span></p></td>
<td><p><span data-ttu-id="d49f5-171">No predeterminado</span><span class="sxs-lookup"><span data-stu-id="d49f5-171">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49f5-172">Test-CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="d49f5-172">Test-CsMCXP2PIM (MCXP2PIM)</span></span></p></td>
<td><p><span data-ttu-id="d49f5-173">Confirma que los usuarios de dispositivos móviles pueden registrarse y enviar mensajes instantáneos.</span><span class="sxs-lookup"><span data-stu-id="d49f5-173">Confirms that mobile device users are able to register and send instant messages.</span></span></p></td>
<td><p><span data-ttu-id="d49f5-174">No predeterminado</span><span class="sxs-lookup"><span data-stu-id="d49f5-174">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49f5-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="d49f5-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span></p></td>
<td><p><span data-ttu-id="d49f5-176">Confirma que los usuarios pueden intercambiar mensajes mediante el servicio de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d49f5-176">Confirms that users can exchange messages by using the Persistent Chat service.</span></span></p></td>
<td><p><span data-ttu-id="d49f5-177">No predeterminado</span><span class="sxs-lookup"><span data-stu-id="d49f5-177">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49f5-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="d49f5-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span></p></td>
<td><p><span data-ttu-id="d49f5-179">Confirma que se puede acceder a los contactos de un usuario a través del almacén de contactos unificados.</span><span class="sxs-lookup"><span data-stu-id="d49f5-179">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="d49f5-180">El almacén de contactos unificado permite a los usuarios mantener un único conjunto de contactos a los que se puede tener acceso mediante Lync 2013, Outlook o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="d49f5-180">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Lync 2013, Outlook, and/or Outlook Web Access.</span></span></p></td>
<td><p><span data-ttu-id="d49f5-181">No predeterminado</span><span class="sxs-lookup"><span data-stu-id="d49f5-181">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49f5-182">Test-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="d49f5-182">Test-CsXmppIM (XmppIM)</span></span></p></td>
<td><p><span data-ttu-id="d49f5-183">Confirma que se pueden enviar mensajes instantáneos por la puerta de enlace XMPP (protocolo extensible de mensajería y presencia).</span><span class="sxs-lookup"><span data-stu-id="d49f5-183">Confirms that an instant message can be sent across the XMPP (Extensible Messaging and Presence Protocol) gateway.</span></span></p></td>
<td><p><span data-ttu-id="d49f5-184">No predeterminado</span><span class="sxs-lookup"><span data-stu-id="d49f5-184">Non-default</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d49f5-185">No es necesario instalar los nodos de monitor para poder usar System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d49f5-185">You do not need to install watcher nodes in order to use System Center Operations Manager.</span></span> <span data-ttu-id="d49f5-186">Si no instala estos nodos, podrá seguir consigo alertas en tiempo real de los componentes de Lync Server 2013 cuando se produzca un problema.</span><span class="sxs-lookup"><span data-stu-id="d49f5-186">If you do not install these nodes, you can still get real-time alerts from Lync Server 2013 components when an issue occurs.</span></span> <span data-ttu-id="d49f5-187">(El módulo de administración de componentes y usuarios no usa nodos de monitor). Sin embargo, los nodos de monitor son necesarios si desea supervisar los escenarios de un extremo a otro mediante el módulo de administración de supervisión activa.</span><span class="sxs-lookup"><span data-stu-id="d49f5-187">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d49f5-188">Los administradores también pueden ejecutar las transacciones sintéticas manualmente, sin tener que usar o instalar Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d49f5-188">Administrators can also run synthetic transactions manually, without needing to use, or install, Operations Manager.</span></span> <span data-ttu-id="d49f5-189">Para obtener más información sobre los distintos cmdlets de Test-Cs, vea el <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Índice de cmdlets de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d49f5-189">For details about the various Test-Cs cmdlets, see the <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlets index</A>.</span></span>



</div>

<span data-ttu-id="d49f5-190">Las transacciones sintéticas pueden consumir una gran cantidad de memoria y tiempo de procesador del equipo, según cuál sea la envergadura de su implementación.</span><span class="sxs-lookup"><span data-stu-id="d49f5-190">Depending on the size of your deployment, synthetic transactions may use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="d49f5-191">Por ello, se recomienda tener un equipo dedicado como nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="d49f5-191">For this reason, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="d49f5-192">Por ejemplo, no debe configurar un servidor front-end para que actúe como un nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="d49f5-192">For example, you should not configure a Front End Server to act as a watcher node.</span></span> <span data-ttu-id="d49f5-193">Los nodos de monitor deben cumplir las siguientes especificaciones de hardware:</span><span class="sxs-lookup"><span data-stu-id="d49f5-193">Watcher nodes should meet the following hardware specifications:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d49f5-194">Un nodo de monitor de Microsoft Lync Server 2010 heredado no se puede combinar en el mismo equipo con un nodo de monitor de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d49f5-194">A legacy Microsoft Lync Server 2010 watcher node cannot be collocated on the same machine with a Lync Server 2013 watcher node.</span></span> <span data-ttu-id="d49f5-195">Esto se debe a que los archivos del sistema principales para Lync Server 2010 y Lync Server 2013 no se pueden instalar en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="d49f5-195">This is because the core system files for Lync Server 2010 and Lync Server 2013 cannot be installed on the same computer.</span></span><BR><span data-ttu-id="d49f5-196">Sin embargo, los nodos de monitor de 2013 de Lync Server pueden supervisar simultáneamente Lync Server 2013 y Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d49f5-196">However, Lync Server 2013 watcher nodes can simultaneously monitor both Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="d49f5-197">Las transacciones sintéticas predeterminadas se admiten en ambas versiones de producto.</span><span class="sxs-lookup"><span data-stu-id="d49f5-197">The Default synthetic transactions are supported on both product versions.</span></span>



</div>

<span data-ttu-id="d49f5-198">Los nodos de monitor de 2013 de Lync Server se pueden implementar dentro o fuera de una empresa para ayudar a comprobar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d49f5-198">Lync Server 2013 watcher nodes may be deployed inside or outside of an enterprise to help verify:</span></span>

  - <span></span>  
    <span data-ttu-id="d49f5-199">La conectividad con los grupos de servidores de usuarios de la empresa.</span><span class="sxs-lookup"><span data-stu-id="d49f5-199">Connectivity to pools for users inside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="d49f5-200">La conectividad a través de redes perimetrales de los usuarios remotos que trabajan fuera de la empresa.</span><span class="sxs-lookup"><span data-stu-id="d49f5-200">Connectivity through perimeter networks for remote users who work outside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="d49f5-201">La conectividad con aplicaciones de sucursal.</span><span class="sxs-lookup"><span data-stu-id="d49f5-201">Connectivity to branch office appliances.</span></span>

  - <span></span>  
    <span data-ttu-id="d49f5-202">Conectividad con Lync Server 2010 dentro de la empresa y a través de redes perimetrales.</span><span class="sxs-lookup"><span data-stu-id="d49f5-202">Connectivity to Lync Server 2010 inside the enterprise and through perimeter networks.</span></span>

<span data-ttu-id="d49f5-203">Existen distintas opciones de autenticación desde dentro y fuera de la empresa que ayudan a simplificar las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="d49f5-203">Different authentication options are available for inside and outside of the enterprise to help simplify administration.</span></span> <span data-ttu-id="d49f5-204">Para obtener más información, consulte [configuración de un nodo de monitor para ejecutar transacciones sintéticas en Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="d49f5-204">For details, see [Configuring a watcher node to run synthetic transactions in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span></span>

<span data-ttu-id="d49f5-205">Para configurar un equipo para que actúe como un nodo de monitor, debe completar los siguientes pasos después de haber instalado System Center Operations Manager e importado los paquetes de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d49f5-205">To configure a computer to act as a watcher node, you must complete the following steps after you have installed System Center Operations Manager and imported the Lync Server 2013 management packs.</span></span>

<span data-ttu-id="d49f5-206">Antes de instalar los archivos principales de Lync Server 2013 y los archivos del agente de System Center, también debe asegurarse de que el equipo del nodo de monitor cumpla todos los requisitos previos para instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d49f5-206">Before you install the Lync Server 2013 core files and the System Center agent files, you should also make sure that the watcher node computer meets all the prerequisites for installing Lync Server 2013.</span></span> <span data-ttu-id="d49f5-207">Además, dicho equipo debe tener instalados los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="d49f5-207">In addition, the watcher node computer should also have the following items installed:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d49f5-208">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="d49f5-208">Hardware component</span></span></th>
<th><span data-ttu-id="d49f5-209">Requisito mínimo</span><span class="sxs-lookup"><span data-stu-id="d49f5-209">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d49f5-210">CPU</span><span class="sxs-lookup"><span data-stu-id="d49f5-210">CPU</span></span></p></td>
<td><p><span data-ttu-id="d49f5-211">Uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d49f5-211">One of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d49f5-212">procesador de 64 bits, Quad-Core, 2,33 GHz o superior</span><span class="sxs-lookup"><span data-stu-id="d49f5-212">64-bit processor, quad-core, 2.33 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="d49f5-213">procesador de 2 vías de 64 bits, doble núcleo, 2,33 GHz o superior</span><span class="sxs-lookup"><span data-stu-id="d49f5-213">64-bit 2-way processor, dual-core, 2.33 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49f5-214">Memoria</span><span class="sxs-lookup"><span data-stu-id="d49f5-214">Memory</span></span></p></td>
<td><p><span data-ttu-id="d49f5-215">8 GB</span><span class="sxs-lookup"><span data-stu-id="d49f5-215">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49f5-216">Sistema operativo de red</span><span class="sxs-lookup"><span data-stu-id="d49f5-216">Network operating system</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d49f5-217">1 adaptador de red de 1 Gbps</span><span class="sxs-lookup"><span data-stu-id="d49f5-217">1 network adapter 1 Gbps</span></span></p></li>
<li><p><span data-ttu-id="d49f5-218">Windows Server 2008 R2, Windows Server 2012 o</span><span class="sxs-lookup"><span data-stu-id="d49f5-218">Windows Server 2008 R2, Windows Server 2012, or</span></span></p>
<p><span data-ttu-id="d49f5-219">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d49f5-219">Windows Server 2012 R2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


  - <span data-ttu-id="d49f5-220">La versión completa de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="d49f5-220">The full version of .NET Framework 4.5.</span></span>

  - <span data-ttu-id="d49f5-221">Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="d49f5-221">Windows Identity Foundation.</span></span>

  - <span data-ttu-id="d49f5-222">Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="d49f5-222">Windows PowerShell 3.0.</span></span>

<span data-ttu-id="d49f5-223">Cuando se cumplan todos estos requisitos previos, podrá configurar el nodo de monitor del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="d49f5-223">As soon as all these prerequisites have been met, you can configure the watcher node by:</span></span>

  - <span data-ttu-id="d49f5-224">Instalar los archivos principales de Lync Server 2013 en el equipo del nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="d49f5-224">Installing the Lync Server 2013 core files on the watcher node computer.</span></span>

  - <span data-ttu-id="d49f5-225">Instalar el agente de System Center Operations Manager en el equipo del nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="d49f5-225">Installing System Center Operations Manager agent on the watcher node computer.</span></span>

  - <span data-ttu-id="d49f5-226">Ejecute el archivo ejecutable Watchernode.msi.</span><span class="sxs-lookup"><span data-stu-id="d49f5-226">Running the Watchernode.msi executable file.</span></span>

  - <span data-ttu-id="d49f5-227">Use los cmdlets de **CsWatcherNodeConfiguration** para configurar usuarios de prueba para que los utilice el nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="d49f5-227">Using the **CsWatcherNodeConfiguration** cmdlets to configure test users to be employed by the watcher node.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

