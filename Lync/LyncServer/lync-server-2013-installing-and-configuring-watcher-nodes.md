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
ms.openlocfilehash: 0cd57e3b78e3e16ac9d640536771cf2b5b90773a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a><span data-ttu-id="28fdf-102">Instalación y configuración de nodos de monitor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28fdf-102">Installing and configuring watcher nodes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28fdf-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="28fdf-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="28fdf-104">Los *nodos de monitor* son equipos que ejecutan periódicamente transacciones sintéticas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28fdf-104">*Watcher nodes* are computers that periodically run Lync Server synthetic transactions.</span></span> <span data-ttu-id="28fdf-105">*Las transacciones sintéticas* son cmdlets de Windows PowerShell que comprueban que los escenarios clave de usuario final (como la capacidad de iniciar sesión en el sistema o la capacidad de intercambiar mensajes instantáneos) funcionan según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="28fdf-105">*Synthetic transactions* are Windows PowerShell cmdlets that verify that key end user scenarios—such as the ability to sign in to the system, or the ability to exchange instant messages—are working as expected.</span></span> <span data-ttu-id="28fdf-106">Para Lync Server 2013, System Center Operations Manager puede ejecutar las transacciones sintéticas que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="28fdf-106">For Lync Server 2013, System Center Operations Manager can run the synthetic transactions shown in the following table.</span></span> <span data-ttu-id="28fdf-107">Existen tres tipos distintos de transacción sintética en la tabla:</span><span class="sxs-lookup"><span data-stu-id="28fdf-107">There are three different synthetic transaction types shown in the table:</span></span>

  - <span data-ttu-id="28fdf-108">**Valor predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="28fdf-108">**Default**.</span></span> <span data-ttu-id="28fdf-109">Estas son las transacciones sintéticas que se ejecutarán de forma predeterminada con un nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="28fdf-109">These are the synthetic transactions that a watcher node will run by default.</span></span> <span data-ttu-id="28fdf-110">Al crear un nuevo nodo de monitor, tiene la opción de especificar qué transacciones sintéticas se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="28fdf-110">When you create a new watcher node, you have the option of specifying which synthetic transactions that node will run.</span></span> <span data-ttu-id="28fdf-111">(Este es el propósito del parámetro tests usado por el cmdlet **New-CsWatcherNodeConfiguration** ). Si no usa el parámetro tests cuando se crea el nodo de monitor, se ejecutarán automáticamente todas las transacciones sintéticas predeterminadas y no se ejecutará ninguna de las transacciones sintéticas que no sean predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="28fdf-111">(That's the purpose of the Tests parameter used by the **New-CsWatcherNodeConfiguration** cmdlet.) If you do not use the Tests parameter when the watcher node is created, it will automatically run all the Default synthetic transactions and will not run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="28fdf-112">Esto significa que, por ejemplo, el nodo de monitor se configurará para ejecutar la prueba test-CsAddressBookService, pero no se configurará para ejecutar la prueba test-CsExumConnectivity.</span><span class="sxs-lookup"><span data-stu-id="28fdf-112">That means, for example, that the watcher node will be configured to run the Test-CsAddressBookService test, but will not be configured to run the Test-CsExumConnectivity test.</span></span>

  - <span data-ttu-id="28fdf-113">**No predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="28fdf-113">**Non-default**.</span></span> <span data-ttu-id="28fdf-114">Como su nombre indica, las transacciones sintéticas no predeterminadas son pruebas que los nodos de monitor no se ejecutan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="28fdf-114">As the name implies, Non-default synthetic transactions are tests that watcher nodes do not run by default.</span></span> <span data-ttu-id="28fdf-115">Sin embargo, el nodo de monitor se puede habilitar para ejecutar cualquiera de las transacciones sintéticas que no son predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="28fdf-115">However, the watcher node can be enabled to run any of the Non-default synthetic transactions.</span></span> <span data-ttu-id="28fdf-116">Puede hacerlo cuando cree el nodo de monitor (mediante el cmdlet **New-CsWatcherNodeConfiguration** ) o en cualquier momento después.</span><span class="sxs-lookup"><span data-stu-id="28fdf-116">You can do this when you create the watcher node (by using the **New-CsWatcherNodeConfiguration** cmdlet), or at any time after that.</span></span> <span data-ttu-id="28fdf-117">Muchas de las transacciones sintéticas no predeterminadas requieren pasos de configuración adicionales.</span><span class="sxs-lookup"><span data-stu-id="28fdf-117">Many of the Non-default synthetic transactions require extra setup steps.</span></span> <span data-ttu-id="28fdf-118">Para obtener más información, consulte [instrucciones de configuración especiales para transacciones sintéticas en Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="28fdf-118">For details, see [Special setup instructions for synthetic transactions in Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).</span></span>

  - <span data-ttu-id="28fdf-119">**Ampliado**.</span><span class="sxs-lookup"><span data-stu-id="28fdf-119">**Extended**.</span></span> <span data-ttu-id="28fdf-120">Las pruebas extendidas son un tipo especial de transacción sintética no predeterminada.</span><span class="sxs-lookup"><span data-stu-id="28fdf-120">Extended tests are a special type of Non-default synthetic transaction.</span></span> <span data-ttu-id="28fdf-121">A diferencia de otras transacciones sintéticas, las pruebas extendidas se pueden ejecutar varias veces durante cada pasada.</span><span class="sxs-lookup"><span data-stu-id="28fdf-121">Unlike other synthetic transactions, Extended tests can be run multiple times during each pass.</span></span> <span data-ttu-id="28fdf-122">Esto puede ser útil cuando se comprueba el comportamiento como varias rutas de voz de red telefónica conmutada (RTC) para un grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="28fdf-122">This can be useful when verifying behavior such as multiple public switched telephone network (PSTN) voice routes for a pool.</span></span> <span data-ttu-id="28fdf-123">Esto se puede configurar simplemente agregando varias instancias de una prueba extendida a un nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="28fdf-123">This can be configured simply by adding multiple instances of an Extended test to a watcher node.</span></span>

<span data-ttu-id="28fdf-124">Para obtener información detallada sobre el proceso de agregar otras transacciones sintéticas a un nodo de monitor, consulte [administrar nodos de monitor en Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="28fdf-124">For details about the process of adding other synthetic transactions to a watcher node, see [Managing watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md).</span></span> <span data-ttu-id="28fdf-125">Puede usar el shell de administración de Lync Server para quitar transacciones sintéticas de un nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="28fdf-125">You can use the Lync Server Management Shell to remove synthetic transactions from a watcher node.</span></span>

<span data-ttu-id="28fdf-126">Las transacciones sintéticas disponibles para los nodos de monitor son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="28fdf-126">The synthetic transactions available to watcher nodes include the following:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="28fdf-127">Nombre del cmdlet (nombre de la prueba)</span><span class="sxs-lookup"><span data-stu-id="28fdf-127">Cmdlet Name (Test Name)</span></span></th>
<th><span data-ttu-id="28fdf-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="28fdf-128">Description</span></span></th>
<th><span data-ttu-id="28fdf-129">Tipo de transacción sintética</span><span class="sxs-lookup"><span data-stu-id="28fdf-129">Synthetic Transaction Type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28fdf-130">Test-CsAddressBookService (ABS)</span><span class="sxs-lookup"><span data-stu-id="28fdf-130">Test-CsAddressBookService (ABS)</span></span></p></td>
<td><p><span data-ttu-id="28fdf-131">Confirma que los usuarios pueden buscar usuarios que no estén en su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="28fdf-131">Confirms that users are able to look up users that aren’t in their contact list.</span></span></p></td>
<td><p><span data-ttu-id="28fdf-132">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="28fdf-132">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28fdf-133">Test-CsAddressBookWebQuery (ABWQ)</span><span class="sxs-lookup"><span data-stu-id="28fdf-133">Test-CsAddressBookWebQuery (ABWQ)</span></span></p></td>
<td><p><span data-ttu-id="28fdf-134">Confirma que los usuarios pueden buscar usuarios que no estén en su lista de contactos mediante HTTP.</span><span class="sxs-lookup"><span data-stu-id="28fdf-134">Confirms that users are able to look up users that aren’t in their contact list via HTTP.</span></span></p></td>
<td><p><span data-ttu-id="28fdf-135">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="28fdf-135">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28fdf-136">Test-CsIM (IM)</span><span class="sxs-lookup"><span data-stu-id="28fdf-136">Test-CsIM (IM)</span></span></p></td>
<td><p><span data-ttu-id="28fdf-137">Confirma que los usuarios pueden enviar mensajes instantáneos punto a punto.</span><span class="sxs-lookup"><span data-stu-id="28fdf-137">Confirms that users are able to send peer-to-peer instant messages.</span></span></p></td>
<td><p><span data-ttu-id="28fdf-138">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="28fdf-138">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28fdf-139">Test-CsP2PAV (P2PAV)</span><span class="sxs-lookup"><span data-stu-id="28fdf-139">Test-CsP2PAV (P2PAV)</span></span></p></td>
<td><p><span data-ttu-id="28fdf-140">Confirma que los usuarios pueden realizar llamadas de audio punto a punto (solo señalización).</span><span class="sxs-lookup"><span data-stu-id="28fdf-140">Confirms that users are able to place peer-to-peer audio calls (signaling only).</span></span></p></td>
<td><p><span data-ttu-id="28fdf-141">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="28fdf-141">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28fdf-142">Test-CsPresence (Presence)</span><span class="sxs-lookup"><span data-stu-id="28fdf-142">Test-CsPresence (Presence)</span></span></p></td>
<td><p><span data-ttu-id="28fdf-143">Confirma que los usuarios pueden ver la presencia de otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="28fdf-143">Confirms that users are able to view other users’ presence.</span></span></p></td>
<td><p><span data-ttu-id="28fdf-144">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="28fdf-144">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28fdf-145">Test-CsRegistration (Registration)</span><span class="sxs-lookup"><span data-stu-id="28fdf-145">Test-CsRegistration (Registration)</span></span></p></td>
<td><p><span data-ttu-id="28fdf-146">Confirma que los usuarios pueden iniciar sesión en Lync.</span><span class="sxs-lookup"><span data-stu-id="28fdf-146">Confirms that users are able sign in to Lync.</span></span></p></td>
<td><p><span data-ttu-id="28fdf-147">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="28fdf-147">Default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28fdf-148">Test-CsAudioConferencingProvider (ACP)</span><span class="sxs-lookup"><span data-stu-id="28fdf-148">Test-CsAudioConferencingProvider (ACP)</span></span></p></td>
<td><p><span data-ttu-id="28fdf-149">No se usa con la versión local de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28fdf-149">Not used with the on-premises version of Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="28fdf-150">Extendido</span><span class="sxs-lookup"><span data-stu-id="28fdf-150">Extended</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28fdf-151">Test-CsPstnPeerToPeerCall (RTC)</span><span class="sxs-lookup"><span data-stu-id="28fdf-151">Test-CsPstnPeerToPeerCall (PSTN)</span></span></p></td>
<td><p><span data-ttu-id="28fdf-152">Confirma que los usuarios pueden hacer y recibir llamadas con gente ajena a la empresa (números de RTC).</span><span class="sxs-lookup"><span data-stu-id="28fdf-152">Confirms that users are able to place and receive calls with people outside of the enterprise (PSTN numbers).</span></span></p></td>
<td><p><span data-ttu-id="28fdf-153">No predeterminada, ampliada</span><span class="sxs-lookup"><span data-stu-id="28fdf-153">Non-default, Extended</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28fdf-154">Test-CsAVConference (AvConference)</span><span class="sxs-lookup"><span data-stu-id="28fdf-154">Test-CsAVConference (AvConference)</span></span></p></td>
<td><p><span data-ttu-id="28fdf-155">Confirma que los usuarios pueden crear conferencias de audio/vídeo y participar en ellas.</span><span class="sxs-lookup"><span data-stu-id="28fdf-155">Confirms that users are able to create and participate in an audio/video conference.</span></span></p></td>
<td><p><span data-ttu-id="28fdf-156">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="28fdf-156">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28fdf-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span><span class="sxs-lookup"><span data-stu-id="28fdf-157">Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="28fdf-158">Confirma que los servidores perimetrales A/V pueden aceptar conexiones para las llamadas punto a punto y las llamadas de conferencia.</span><span class="sxs-lookup"><span data-stu-id="28fdf-158">Confirms that the A/V Edge servers are able to accept connections for peer-to-peer calls and conference calls.</span></span></p></td>
<td><p><span data-ttu-id="28fdf-159">No predeterminado</span><span class="sxs-lookup"><span data-stu-id="28fdf-159">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28fdf-160">Test-CsDataConference (congresos)</span><span class="sxs-lookup"><span data-stu-id="28fdf-160">Test-CsDataConference (DataConference)</span></span></p></td>
<td><p><span data-ttu-id="28fdf-161">Confirma que los usuarios pueden participar en una conferencia de colaboración de datos, una reunión en línea que engloba actividades como pizarras y sondeos.</span><span class="sxs-lookup"><span data-stu-id="28fdf-161">Confirms that users can participate in a data collaboration conference, an online meeting that includes activities such as whiteboards and polls.</span></span></p></td>
<td><p><span data-ttu-id="28fdf-162">No predeterminado</span><span class="sxs-lookup"><span data-stu-id="28fdf-162">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28fdf-163">Test-CsExumConnectivity (ExumConnectivity)</span><span class="sxs-lookup"><span data-stu-id="28fdf-163">Test-CsExumConnectivity (ExumConnectivity)</span></span></p></td>
<td><p><span data-ttu-id="28fdf-164">Confirma que un usuario puede conectarse a la mensajería unificada (UM) de Exchange.</span><span class="sxs-lookup"><span data-stu-id="28fdf-164">Confirms that a user can connect to Exchange Unified Messaging (UM).</span></span></p></td>
<td><p><span data-ttu-id="28fdf-165">No predeterminado</span><span class="sxs-lookup"><span data-stu-id="28fdf-165">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28fdf-166">Test-CsGroupIM (GroupIM)</span><span class="sxs-lookup"><span data-stu-id="28fdf-166">Test-CsGroupIM (GroupIM)</span></span></p></td>
<td><p><span data-ttu-id="28fdf-167">Confirma que los usuarios pueden enviar mensajes instantáneos durante las conferencias y participar en conversaciones de mensajes instantáneos con tres o más personas.</span><span class="sxs-lookup"><span data-stu-id="28fdf-167">Confirms that users are able to send instant messages in conferences and participate in instant message conversations with three or more people.</span></span></p></td>
<td><p><span data-ttu-id="28fdf-168">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="28fdf-168">Default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28fdf-169">Test-CsGroupIM – TestJoinLauncher (JoinLauncher)</span><span class="sxs-lookup"><span data-stu-id="28fdf-169">Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</span></span></p></td>
<td><p><span data-ttu-id="28fdf-170">Confirma que los usuarios pueden crear reuniones programadas y unirse a ellas a través de un vínculo de dirección web.</span><span class="sxs-lookup"><span data-stu-id="28fdf-170">Confirms that users are able to create and join scheduled meetings via a web address link.</span></span></p></td>
<td><p><span data-ttu-id="28fdf-171">No predeterminado</span><span class="sxs-lookup"><span data-stu-id="28fdf-171">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28fdf-172">Test-CsMCXP2PIM (MCXP2PIM)</span><span class="sxs-lookup"><span data-stu-id="28fdf-172">Test-CsMCXP2PIM (MCXP2PIM)</span></span></p></td>
<td><p><span data-ttu-id="28fdf-173">Confirma que los usuarios de dispositivos móviles pueden registrarse y enviar mensajes instantáneos.</span><span class="sxs-lookup"><span data-stu-id="28fdf-173">Confirms that mobile device users are able to register and send instant messages.</span></span></p></td>
<td><p><span data-ttu-id="28fdf-174">No predeterminado</span><span class="sxs-lookup"><span data-stu-id="28fdf-174">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28fdf-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span><span class="sxs-lookup"><span data-stu-id="28fdf-175">Test-CsPersistentChatMessage (PersistentChatMessage)</span></span></p></td>
<td><p><span data-ttu-id="28fdf-176">Confirma que los usuarios pueden intercambiar mensajes mediante el servicio de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="28fdf-176">Confirms that users can exchange messages by using the Persistent Chat service.</span></span></p></td>
<td><p><span data-ttu-id="28fdf-177">No predeterminado</span><span class="sxs-lookup"><span data-stu-id="28fdf-177">Non-default</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28fdf-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span><span class="sxs-lookup"><span data-stu-id="28fdf-178">Test-CsUnifiedContactStore (UnifiedContactStore)</span></span></p></td>
<td><p><span data-ttu-id="28fdf-179">Confirma que se puede acceder a los contactos de un usuario a través del almacén de contactos unificados.</span><span class="sxs-lookup"><span data-stu-id="28fdf-179">Confirms that a user's contacts can be accessed through the unified contact store.</span></span> <span data-ttu-id="28fdf-180">El almacén de contactos unificado permite a los usuarios mantener un único conjunto de contactos a los que se puede tener acceso mediante Lync 2013, Outlook o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="28fdf-180">The unified contact store provides a way for users to maintain a single set of contacts that can be accessed by using Lync 2013, Outlook, and/or Outlook Web Access.</span></span></p></td>
<td><p><span data-ttu-id="28fdf-181">No predeterminado</span><span class="sxs-lookup"><span data-stu-id="28fdf-181">Non-default</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28fdf-182">Test-CsXmppIM (XmppIM)</span><span class="sxs-lookup"><span data-stu-id="28fdf-182">Test-CsXmppIM (XmppIM)</span></span></p></td>
<td><p><span data-ttu-id="28fdf-183">Confirma que se pueden enviar mensajes instantáneos por la puerta de enlace XMPP (protocolo extensible de mensajería y presencia).</span><span class="sxs-lookup"><span data-stu-id="28fdf-183">Confirms that an instant message can be sent across the XMPP (Extensible Messaging and Presence Protocol) gateway.</span></span></p></td>
<td><p><span data-ttu-id="28fdf-184">No predeterminado</span><span class="sxs-lookup"><span data-stu-id="28fdf-184">Non-default</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="28fdf-185">No es necesario instalar los nodos de monitor para poder usar System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="28fdf-185">You do not need to install watcher nodes in order to use System Center Operations Manager.</span></span> <span data-ttu-id="28fdf-186">Si no instala estos nodos, podrá seguir consigo alertas en tiempo real de los componentes de Lync Server 2013 cuando se produzca un problema.</span><span class="sxs-lookup"><span data-stu-id="28fdf-186">If you do not install these nodes, you can still get real-time alerts from Lync Server 2013 components when an issue occurs.</span></span> <span data-ttu-id="28fdf-187">(El módulo de administración de componentes y usuarios no usa nodos de monitor). Sin embargo, los nodos de monitor son necesarios si desea supervisar los escenarios de un extremo a otro mediante el módulo de administración de supervisión activa.</span><span class="sxs-lookup"><span data-stu-id="28fdf-187">(The Component and User Management Pack does not use watcher nodes.) However, watcher nodes are required if you want to monitor end-to-end scenarios by using the Active Monitoring Management pack.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="28fdf-188">Los administradores también pueden ejecutar las transacciones sintéticas manualmente, sin tener que usar o instalar Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="28fdf-188">Administrators can also run synthetic transactions manually, without needing to use, or install, Operations Manager.</span></span> <span data-ttu-id="28fdf-189">Para obtener más información sobre los distintos cmdlets test-CS, vea el <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Índice de cmdlets de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="28fdf-189">For details about the various Test-Cs cmdlets, see the <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlets index</A>.</span></span>



</div>

<span data-ttu-id="28fdf-190">Las transacciones sintéticas pueden consumir una gran cantidad de memoria y tiempo de procesador del equipo, según cuál sea la envergadura de su implementación.</span><span class="sxs-lookup"><span data-stu-id="28fdf-190">Depending on the size of your deployment, synthetic transactions may use a large amount of computer memory and processor time.</span></span> <span data-ttu-id="28fdf-191">Por ello, se recomienda tener un equipo dedicado como nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="28fdf-191">For this reason, we recommend that you use a dedicated computer as a watcher node.</span></span> <span data-ttu-id="28fdf-192">Por ejemplo, no debe configurar un servidor front-end para que actúe como un nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="28fdf-192">For example, you should not configure a Front End Server to act as a watcher node.</span></span> <span data-ttu-id="28fdf-193">Los nodos de monitor deben cumplir las siguientes especificaciones de hardware:</span><span class="sxs-lookup"><span data-stu-id="28fdf-193">Watcher nodes should meet the following hardware specifications:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="28fdf-194">Un nodo de monitor de Microsoft Lync Server 2010 heredado no se puede combinar en el mismo equipo con un nodo de monitor de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="28fdf-194">A legacy Microsoft Lync Server 2010 watcher node cannot be collocated on the same machine with a Lync Server 2013 watcher node.</span></span> <span data-ttu-id="28fdf-195">Esto se debe a que los archivos del sistema principales para Lync Server 2010 y Lync Server 2013 no se pueden instalar en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="28fdf-195">This is because the core system files for Lync Server 2010 and Lync Server 2013 cannot be installed on the same computer.</span></span><BR><span data-ttu-id="28fdf-196">Sin embargo, los nodos de monitor de 2013 de Lync Server pueden supervisar simultáneamente Lync Server 2013 y Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="28fdf-196">However, Lync Server 2013 watcher nodes can simultaneously monitor both Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="28fdf-197">Las transacciones sintéticas predeterminadas se admiten en ambas versiones de producto.</span><span class="sxs-lookup"><span data-stu-id="28fdf-197">The Default synthetic transactions are supported on both product versions.</span></span>



</div>

<span data-ttu-id="28fdf-198">Los nodos de monitor de 2013 de Lync Server se pueden implementar dentro o fuera de una empresa para ayudar a comprobar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="28fdf-198">Lync Server 2013 watcher nodes may be deployed inside or outside of an enterprise to help verify:</span></span>

  - <span></span>  
    <span data-ttu-id="28fdf-199">La conectividad con los grupos de servidores de usuarios de la empresa.</span><span class="sxs-lookup"><span data-stu-id="28fdf-199">Connectivity to pools for users inside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="28fdf-200">La conectividad a través de redes perimetrales de los usuarios remotos que trabajan fuera de la empresa.</span><span class="sxs-lookup"><span data-stu-id="28fdf-200">Connectivity through perimeter networks for remote users who work outside the enterprise.</span></span>

  - <span></span>  
    <span data-ttu-id="28fdf-201">La conectividad con aplicaciones de sucursal.</span><span class="sxs-lookup"><span data-stu-id="28fdf-201">Connectivity to branch office appliances.</span></span>

  - <span></span>  
    <span data-ttu-id="28fdf-202">Conectividad con Lync Server 2010 dentro de la empresa y a través de redes perimetrales.</span><span class="sxs-lookup"><span data-stu-id="28fdf-202">Connectivity to Lync Server 2010 inside the enterprise and through perimeter networks.</span></span>

<span data-ttu-id="28fdf-203">Existen distintas opciones de autenticación desde dentro y fuera de la empresa que ayudan a simplificar las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="28fdf-203">Different authentication options are available for inside and outside of the enterprise to help simplify administration.</span></span> <span data-ttu-id="28fdf-204">Para obtener más información, consulte [configuración de un nodo de monitor para ejecutar transacciones sintéticas en Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="28fdf-204">For details, see [Configuring a watcher node to run synthetic transactions in Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).</span></span>

<span data-ttu-id="28fdf-205">Para configurar un equipo para que actúe como un nodo de monitor, debe completar los siguientes pasos después de haber instalado System Center Operations Manager e importado los paquetes de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="28fdf-205">To configure a computer to act as a watcher node, you must complete the following steps after you have installed System Center Operations Manager and imported the Lync Server 2013 management packs.</span></span>

<span data-ttu-id="28fdf-206">Antes de instalar los archivos principales de Lync Server 2013 y los archivos del agente de System Center, también debe asegurarse de que el equipo del nodo de monitor cumpla todos los requisitos previos para instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="28fdf-206">Before you install the Lync Server 2013 core files and the System Center agent files, you should also make sure that the watcher node computer meets all the prerequisites for installing Lync Server 2013.</span></span> <span data-ttu-id="28fdf-207">Además, dicho equipo debe tener instalados los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="28fdf-207">In addition, the watcher node computer should also have the following items installed:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="28fdf-208">Componente de hardware</span><span class="sxs-lookup"><span data-stu-id="28fdf-208">Hardware component</span></span></th>
<th><span data-ttu-id="28fdf-209">Requisito mínimo</span><span class="sxs-lookup"><span data-stu-id="28fdf-209">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28fdf-210">CPU</span><span class="sxs-lookup"><span data-stu-id="28fdf-210">CPU</span></span></p></td>
<td><p><span data-ttu-id="28fdf-211">Uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="28fdf-211">One of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="28fdf-212">procesador de 64 bits, Quad-Core, 2,33 GHz o superior</span><span class="sxs-lookup"><span data-stu-id="28fdf-212">64-bit processor, quad-core, 2.33 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="28fdf-213">procesador de 2 vías de 64 bits, doble núcleo, 2,33 GHz o superior</span><span class="sxs-lookup"><span data-stu-id="28fdf-213">64-bit 2-way processor, dual-core, 2.33 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28fdf-214">Memoria</span><span class="sxs-lookup"><span data-stu-id="28fdf-214">Memory</span></span></p></td>
<td><p><span data-ttu-id="28fdf-215">8 GB</span><span class="sxs-lookup"><span data-stu-id="28fdf-215">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28fdf-216">Sistema operativo de red</span><span class="sxs-lookup"><span data-stu-id="28fdf-216">Network operating system</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="28fdf-217">1 adaptador de red de 1 Gbps</span><span class="sxs-lookup"><span data-stu-id="28fdf-217">1 network adapter 1 Gbps</span></span></p></li>
<li><p><span data-ttu-id="28fdf-218">Windows Server 2008 R2, Windows Server 2012 o</span><span class="sxs-lookup"><span data-stu-id="28fdf-218">Windows Server 2008 R2, Windows Server 2012, or</span></span></p>
<p><span data-ttu-id="28fdf-219">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="28fdf-219">Windows Server 2012 R2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


  - <span data-ttu-id="28fdf-220">La versión completa de .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="28fdf-220">The full version of .NET Framework 4.5.</span></span>

  - <span data-ttu-id="28fdf-221">Windows Identity Foundation.</span><span class="sxs-lookup"><span data-stu-id="28fdf-221">Windows Identity Foundation.</span></span>

  - <span data-ttu-id="28fdf-222">Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="28fdf-222">Windows PowerShell 3.0.</span></span>

<span data-ttu-id="28fdf-223">Cuando se cumplan todos estos requisitos previos, podrá configurar el nodo de monitor del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="28fdf-223">As soon as all these prerequisites have been met, you can configure the watcher node by:</span></span>

  - <span data-ttu-id="28fdf-224">Instalar los archivos principales de Lync Server 2013 en el equipo del nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="28fdf-224">Installing the Lync Server 2013 core files on the watcher node computer.</span></span>

  - <span data-ttu-id="28fdf-225">Instalar el agente de System Center Operations Manager en el equipo del nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="28fdf-225">Installing System Center Operations Manager agent on the watcher node computer.</span></span>

  - <span data-ttu-id="28fdf-226">Ejecute el archivo ejecutable Watchernode.msi.</span><span class="sxs-lookup"><span data-stu-id="28fdf-226">Running the Watchernode.msi executable file.</span></span>

  - <span data-ttu-id="28fdf-227">Use los cmdlets de **CsWatcherNodeConfiguration** para configurar usuarios de prueba para que los utilice el nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="28fdf-227">Using the **CsWatcherNodeConfiguration** cmdlets to configure test users to be employed by the watcher node.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

