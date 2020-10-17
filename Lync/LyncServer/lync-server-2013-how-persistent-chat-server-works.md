---
title: 'Lync Server 2013: funcionamiento del servidor de chat persistente'
description: 'Lync Server 2013: Cómo funciona el servidor de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c65df6a13305f75a8a25b85a39688fadf64e476c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562966"
---
# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a><span data-ttu-id="3f444-103">Cómo funciona el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f444-103">How Persistent Chat Server works in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f444-104">_**Última modificación del tema:** 2012-11-21_</span><span class="sxs-lookup"><span data-stu-id="3f444-104">_**Topic Last Modified:** 2012-11-21_</span></span>

<span data-ttu-id="3f444-105">Lync Server 2013, el servidor de chat persistente permite participar en conversaciones basadas en temas con varios participantes que persisten a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="3f444-105">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="3f444-106">El servidor de chat persistente puede ayudar a su organización a hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3f444-106">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="3f444-107">Mejorar la comunicación entre equipos geográficamente dispersos y multifuncionales</span><span class="sxs-lookup"><span data-stu-id="3f444-107">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="3f444-108">Ampliar el uso de la información y la participación</span><span class="sxs-lookup"><span data-stu-id="3f444-108">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="3f444-109">Mejorar la comunicación con la organización extendida</span><span class="sxs-lookup"><span data-stu-id="3f444-109">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="3f444-110">Reducir la sobrecarga de la información</span><span class="sxs-lookup"><span data-stu-id="3f444-110">Reduce information overload</span></span>

  - <span data-ttu-id="3f444-111">Mejorar el uso de la información</span><span class="sxs-lookup"><span data-stu-id="3f444-111">Improve information awareness</span></span>

  - <span data-ttu-id="3f444-112">Aumentar la divulgación de información y conocimientos importantes</span><span class="sxs-lookup"><span data-stu-id="3f444-112">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="3f444-113">Puede implementar el servidor de chat persistente como un rol opcional con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f444-113">You can deploy Persistent Chat Server as an optional role with Lync Server 2013.</span></span> <span data-ttu-id="3f444-114">Los servicios de chat persistente se ejecutan en un grupo dedicado y un grupo de servidores de chat persistente depende de un grupo de Lync Server para enrutar mensajes a él.</span><span class="sxs-lookup"><span data-stu-id="3f444-114">Persistent Chat services run on a dedicated pool, and a Persistent Chat Server pool depends on a Lync Server pool to route messages to it.</span></span> <span data-ttu-id="3f444-115">Los clientes utilizan eXtensible Chat Communication Over SIP (XCCOS).</span><span class="sxs-lookup"><span data-stu-id="3f444-115">Clients use eXtensible Chat Communication Over SIP (XCCOS).</span></span> <span data-ttu-id="3f444-116">Los servidores front-end de Lync Server están configurados para enrutar el tráfico a un grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3f444-116">The Lync Server Front End Servers are configured to route the traffic to a Persistent Chat Server pool.</span></span>

<div>

## <a name="high-level-architecture"></a><span data-ttu-id="3f444-117">Arquitectura de alto nivel</span><span class="sxs-lookup"><span data-stu-id="3f444-117">High-Level Architecture</span></span>

<span data-ttu-id="3f444-118">En los siguientes diagramas se proporcionan perspectivas de alto nivel de los servicios y la arquitectura del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3f444-118">The following diagrams provide high-level perspectives of the Persistent Chat Server architecture and services.</span></span>

<span data-ttu-id="3f444-119">**Arquitectura de alto nivel del servidor de chat persistente**</span><span class="sxs-lookup"><span data-stu-id="3f444-119">**Persistent Chat Server High-Level Architecture**</span></span>

<span data-ttu-id="3f444-120">![Arquitectura del servidor de chat persistente.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Arquitectura del servidor de chat persistente.")</span><span class="sxs-lookup"><span data-stu-id="3f444-120">![Persistent Chat Server architecture.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server architecture.")</span></span>

<span data-ttu-id="3f444-121">**Servicios de alto nivel del servidor de chat persistente**</span><span class="sxs-lookup"><span data-stu-id="3f444-121">**Persistent Chat Server High-Level Services**</span></span>

<span data-ttu-id="3f444-122">![Componentes del servidor de chat persistente.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Componentes del servidor de chat persistente.")</span><span class="sxs-lookup"><span data-stu-id="3f444-122">![Persistent Chat Server components.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server components.")</span></span>

<span data-ttu-id="3f444-123">Se ejecutan dos servicios en los servidores front-end del servidor de chat persistente:</span><span class="sxs-lookup"><span data-stu-id="3f444-123">Two services run on the Persistent Chat Server Front End Servers:</span></span>

  - <span data-ttu-id="3f444-124">Chat persistente (Canal)</span><span class="sxs-lookup"><span data-stu-id="3f444-124">Persistent Chat (Channel)</span></span>

  - <span data-ttu-id="3f444-125">Cumplimiento</span><span class="sxs-lookup"><span data-stu-id="3f444-125">Compliance</span></span>

<div>

## <a name="persistent-chat-channel-service"></a><span data-ttu-id="3f444-126">Servicio de chat persistente (Canal)</span><span class="sxs-lookup"><span data-stu-id="3f444-126">Persistent Chat (Channel) Service</span></span>

<span data-ttu-id="3f444-127">El servicio de chat persistente (canal) es el servicio principal responsable del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3f444-127">The Persistent Chat (Channel) service is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="3f444-128">Este servicio proporciona las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="3f444-128">This service provides the following functions:</span></span>

  - <span data-ttu-id="3f444-129">Acepta mensajes entrantes</span><span class="sxs-lookup"><span data-stu-id="3f444-129">Accepts incoming messages</span></span>

  - <span data-ttu-id="3f444-130">Registra y enumera los participantes en línea dentro de un salón de chat persistente</span><span class="sxs-lookup"><span data-stu-id="3f444-130">Registers and lists online participants within a Persistent Chat room</span></span>

  - <span data-ttu-id="3f444-131">Retransmite mensajes a los suscriptores de otros canales</span><span class="sxs-lookup"><span data-stu-id="3f444-131">Retransmits messages to other channel subscribers</span></span>

  - <span data-ttu-id="3f444-132">Implementa la lógica para la administración del canal, la invitación a una sala de chat, las búsquedas y las notificaciones de nuevo contenido</span><span class="sxs-lookup"><span data-stu-id="3f444-132">Implements logic for channel management, chat room invitation, search, and new content notifications</span></span>

<span data-ttu-id="3f444-133">El servicio de chat persistente (canal) almacena y accede al contenido del salón de chat y otros metadatos del sistema (reglas de autorización, etc.) mediante el almacén de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3f444-133">The Persistent Chat (Channel) service stores and accesses chat room content and other system metadata (authorization rules, and so on) by using the Persistent Chat Store.</span></span> <span data-ttu-id="3f444-134">Este servicio almacena los archivos que se cargan en salones de chat en el almacén de archivos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3f444-134">This service stores files that are uploaded into chat rooms in the Persistent Chat File Store.</span></span>

</div>

<div>

## <a name="compliance-service"></a><span data-ttu-id="3f444-135">Servicio de Cumplimiento</span><span class="sxs-lookup"><span data-stu-id="3f444-135">Compliance Service</span></span>

<span data-ttu-id="3f444-136">El servicio de cumplimiento es un componente opcional del servidor de chat persistente y es responsable de archivar el contenido y los eventos de chat en el almacén de cumplimiento de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3f444-136">The Compliance service is an optional component of Persistent Chat Server and is responsible for archiving chat content and events to the Persistent Chat Compliance Store.</span></span> <span data-ttu-id="3f444-137">Si su organización tiene regulaciones que requieran que se Archive la actividad de chat persistente, puede implementar el servicio opcional de cumplimiento de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3f444-137">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="3f444-138">El servicio de cumplimiento se instala en cada servidor de chat persistente en un grupo de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3f444-138">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> <span data-ttu-id="3f444-139">Cuando se configura, el cumplimiento del servidor de chat persistente registra la actividad de los usuarios, como unirse y abandonar salas, y publicar y leer los mensajes.</span><span class="sxs-lookup"><span data-stu-id="3f444-139">When configured, Persistent Chat Server compliance records user activity such as joining and leaving rooms, and posting and reading of messages.</span></span> <span data-ttu-id="3f444-140">El servicio de cumplimiento almacena los archivos que se deben archivar en el almacén de archivos de cumplimiento de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3f444-140">The Compliance service stores files that need to be archived in the Persistent Chat Compliance File Store.</span></span>

</div>

<div>

## <a name="persistent-chat-web-services"></a><span data-ttu-id="3f444-141">Servicios Web de chat persistente</span><span class="sxs-lookup"><span data-stu-id="3f444-141">Persistent Chat Web Services</span></span>

<span data-ttu-id="3f444-142">En los servidores front-end de Lync Server, se ejecutan dos servicios que dependen de Internet Information Services (IIS) y se implementan como componentes Web:</span><span class="sxs-lookup"><span data-stu-id="3f444-142">On the Lync Server Front End Servers, two services run that depend on Internet Information Services (IIS), and are implemented as web components:</span></span>

  - <span data-ttu-id="3f444-143">**Servicios Web de chat persistente para la carga y descarga de archivos** Responsable de publicar y recuperar archivos de salones de chat.</span><span class="sxs-lookup"><span data-stu-id="3f444-143">**Persistent Chat Web Services for File Upload/Download** Responsible for posting and retrieving files from chat rooms.</span></span>

  - <span data-ttu-id="3f444-144">**Servicios Web de chat persistente para la administración de salones de chat** Responsable de ofrecer a los usuarios la capacidad de administrar sus salones de chat y crear nuevos salones de chat.</span><span class="sxs-lookup"><span data-stu-id="3f444-144">**Persistent Chat Web Services for Chat Room Management** Responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a><span data-ttu-id="3f444-145">¿Cómo puedo empezar a usar el servidor de chat persistente?</span><span class="sxs-lookup"><span data-stu-id="3f444-145">How Do I Start Using Persistent Chat Server?</span></span>

<span data-ttu-id="3f444-146">El servidor de chat persistente es un rol de servidor opcional dentro de la infraestructura de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f444-146">Persistent Chat Server is an optional server role within the Lync Server 2013 infrastructure.</span></span> <span data-ttu-id="3f444-147">Si instala el rol de servidor de chat persistente, todos los usuarios que hayan sido habilitados mediante la Directiva por un administrador pueden usar chat persistente con el cliente de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3f444-147">If you install the Persistent Chat Server role, any users who have been enabled through policy by an administrator can use Persistent Chat with the Lync 2013 client.</span></span>

<span data-ttu-id="3f444-148">Para obtener más información sobre cómo implementar el servidor de chat persistente y permitir a los usuarios aprovechar las funciones por directiva, consulte [Deploying persistent chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="3f444-148">For details about how to deploy Persistent Chat Server and enable users to leverage the capabilities by policy, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>

<span data-ttu-id="3f444-149">Para obtener más información sobre cómo configurar las opciones en la implementación del servidor de chat persistente, consulte [Deploying persistent chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) y [Managing Lync Server 2013, persistent chat Server](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="3f444-149">For details about how to configure settings on your Persistent Chat Server deployment, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="3f444-150">Para obtener información detallada sobre cómo habilitar a los usuarios mediante directivas de modo que puedan aprovechar la funcionalidad de chat persistente en el cliente de Lync 2013, consulte [Deploying persistent chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) y [Managing Lync Server 2013, persistent chat Server](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="3f444-150">For details about how to enable users by policy such that they can leverage Persistent Chat functionality in Lync 2013 client, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="3f444-151">Si ha implementado el cumplimiento de chat persistente, consulte [Managing Lync server 2013, persistent chat Server](managing-lync-server-2013-persistent-chat-server.md) para obtener más información sobre cómo configurar las opciones para el cumplimiento normativo.</span><span class="sxs-lookup"><span data-stu-id="3f444-151">If you deployed Persistent Chat compliance, see [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) for details about how to configure settings for compliance.</span></span>

</div>

<div>

## <a name="persistent-chat-call-flows"></a><span data-ttu-id="3f444-152">Flujos de llamadas de chat persistente</span><span class="sxs-lookup"><span data-stu-id="3f444-152">Persistent Chat Call Flows</span></span>

<span data-ttu-id="3f444-153">El cliente de chat persistente se comunica con el servicio de chat persistente mediante XCCOS.</span><span class="sxs-lookup"><span data-stu-id="3f444-153">The Persistent Chat client communicates with the Persistent Chat service by using XCCOS.</span></span> <span data-ttu-id="3f444-154">Las siguientes secuencias describen el proceso de inicio de sesión y un escenario típico de suscripción a la sala y de publicación de mensaje.</span><span class="sxs-lookup"><span data-stu-id="3f444-154">The following sequences describe the sign-in process and a typical room subscription and message post scenario.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="3f444-155">Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="3f444-155">Sign-in</span></span>

<span data-ttu-id="3f444-156">El siguiente diagrama de flujo de llamadas y los pasos describen el proceso de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="3f444-156">The following call flow diagram and steps describe the sign-in process.</span></span>

<span data-ttu-id="3f444-157">**Flujo de llamadas de inicio de sesión de cliente de chat persistente**</span><span class="sxs-lookup"><span data-stu-id="3f444-157">**Persistent Chat Client Sign-in Call Flow**</span></span>

<span data-ttu-id="3f444-158">![Diagrama de flujo de llamadas del servidor de chat persistente.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Diagrama de flujo de llamadas del servidor de chat persistente.")</span><span class="sxs-lookup"><span data-stu-id="3f444-158">![Persistent Chat Server call flow diagram.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server call flow diagram.")</span></span>

1.  <span data-ttu-id="3f444-159">El cliente de chat persistente envía primero un SIP SUBSCRIBE para recuperar el documento de aprovisionamiento en banda del servidor.</span><span class="sxs-lookup"><span data-stu-id="3f444-159">The Persistent Chat client first sends a SIP SUBSCRIBE to retrieve the in-band provisioning document from the server.</span></span> <span data-ttu-id="3f444-160">Este documento indica si el chat persistente está habilitado o deshabilitado para el usuario y la lista de URI de SIP para el grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3f444-160">This document indicates if Persistent Chat is enabled or disabled for the user and the list of SIP URIs for the Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="3f444-161">El cliente de chat persistente envía un mensaje SIP INVITE al URI del SIP del servidor de chat persistente que obtuvo en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="3f444-161">The Persistent Chat client sends a SIP INVITE message to the SIP URI of the Persistent Chat Server that it obtained in the previous step.</span></span> <span data-ttu-id="3f444-162">La secuencia de invitación va seguida de 200 aceptar y ACK, y el cliente de chat persistente ahora ha abierto una sesión SIP con un extremo del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3f444-162">The INVITE sequence is followed by 200 OK and ACK, and the Persistent Chat client has now opened a SIP session with a Persistent Chat Server endpoint.</span></span> <span data-ttu-id="3f444-163">Por lo tanto, el cliente de chat persistente se comunica con el servidor de chat persistente mediante el envío de mensajes de información SIP que contienen mensajes de chat o comandos que solicitan al servidor que realice una acción.</span><span class="sxs-lookup"><span data-stu-id="3f444-163">Consequently, the Persistent Chat client communicates with Persistent Chat Server by sending SIP INFO messages that contain either chat messages or commands requesting the server to take an action.</span></span> <span data-ttu-id="3f444-164">Todos estos mensajes son reconocidos con 200 OK o 503 Service Unavailable (es decir, en caso de fuertes carga de servidor).</span><span class="sxs-lookup"><span data-stu-id="3f444-164">All of these messages are acknowledged with either 200 OK or 503 Service Unavailable (that is, in the event of heavy server load).</span></span> <span data-ttu-id="3f444-165">Si el cliente recibe una respuesta 503, volverá a intentar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="3f444-165">If the client receives a 503 response, it will retry the message.</span></span> <span data-ttu-id="3f444-166">(En este ejemplo no se incluye una respuesta 503). Si el servidor acepta el mensaje o el comando y envía 200 aceptar, proporciona una respuesta al cliente en forma de un mensaje SIP independiente.</span><span class="sxs-lookup"><span data-stu-id="3f444-166">(This example does not include a 503 response.) If the server accepts the message or command and sends 200 OK, it provides a response to the client in the form of a separate SIP INFO message.</span></span> <span data-ttu-id="3f444-167">Esta respuesta incluye una referencia al comando original.</span><span class="sxs-lookup"><span data-stu-id="3f444-167">This response includes a reference to the originating command.</span></span>

3.  <span data-ttu-id="3f444-168">El cliente de chat persistente envía un mensaje de información SIP que contiene el comando XCCOS **getServerInfo** .</span><span class="sxs-lookup"><span data-stu-id="3f444-168">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getserverinfo** command.</span></span> <span data-ttu-id="3f444-169">El servidor de chat persistente responde con un nuevo mensaje de información SIP que contiene información sobre la configuración del servicio de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3f444-169">Persistent Chat Server replies with a new SIP INFO message that contains information about the Persistent Chat service configuration.</span></span>

4.  <span data-ttu-id="3f444-170">El cliente de chat persistente envía un mensaje de información SIP que contiene el comando XCCOS **getassociations** .</span><span class="sxs-lookup"><span data-stu-id="3f444-170">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getassociations** command.</span></span> <span data-ttu-id="3f444-171">El servidor de chat persistente responde con un nuevo mensaje de información SIP que contiene la lista de salas de las que el usuario es miembro.</span><span class="sxs-lookup"><span data-stu-id="3f444-171">Persistent Chat Server replies with a new SIP INFO message that contains the list of rooms of which the user is a member.</span></span> <span data-ttu-id="3f444-172">El cliente de chat persistente repite el comando para recuperar la lista de salas de las que el usuario es administrador.</span><span class="sxs-lookup"><span data-stu-id="3f444-172">The Persistent Chat client repeats the command to retrieve the list of rooms of which the user is a manager.</span></span>

5.  <span data-ttu-id="3f444-173">El cliente de chat persistente obtiene la lista de salones seguidos del documento "Presence", donde cada salón seguido está representado por una categoría "roomSetting".</span><span class="sxs-lookup"><span data-stu-id="3f444-173">The Persistent Chat client gets the list of followed rooms from the "presence" document, where each followed room is represented by a "roomSetting" category.</span></span> <span data-ttu-id="3f444-174">Todas las salas seguidas están unidas por un único mensaje SIP INFO que contiene el comando **bjoin** de XCCOS que contiene la lista de URI de las salas.</span><span class="sxs-lookup"><span data-stu-id="3f444-174">All followed rooms are joined by a single SIP INFO message that contains the XCCOS **bjoin** command that contains the list of room URIs.</span></span> <span data-ttu-id="3f444-175">Puesto que la lista de salas seguidas se guarda en el servidor, cualquier cliente desde cualquier equipo tiene la misma lista de salas seguidas para el URI de usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="3f444-175">Because the list of followed rooms is kept on the server, any client on any computer has the same list of followed rooms for the specified user URI.</span></span> <span data-ttu-id="3f444-176">El cliente de chat persistente también mantiene la lista de salones abiertos (si el usuario ha habilitado esta opción) en el registro del equipo local y combina cada uno de estos salones en el inicio de sesión mediante el envío de un mensaje de información SIP que contiene el comando XCCOS **join** para cada salón abierto.</span><span class="sxs-lookup"><span data-stu-id="3f444-176">The Persistent Chat client also keeps the list of opened rooms (if this option is enabled by the user) in the local computer registry, and joins each of these rooms at sign-in by sending a SIP INFO message that contains the XCCOS **join** command for each opened room.</span></span> <span data-ttu-id="3f444-177">Como esta lista se guarda en el registro, puede ser diferente en dos clientes de chat persistente que se ejecutan en equipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="3f444-177">Because this list is kept in the registry, it can be different on two Persistent Chat clients running on different computers.</span></span>

6.  <span data-ttu-id="3f444-178">Para cada habitación que se une, el cliente de chat persistente envía un mensaje de información SIP que contiene el comando XCCOS **bccontext** .</span><span class="sxs-lookup"><span data-stu-id="3f444-178">For each room joined, the Persistent Chat client sends a SIP INFO message that contains the XCCOS **bccontext** command.</span></span> <span data-ttu-id="3f444-179">El servidor de chat persistente responde con un nuevo mensaje de información SIP que contiene el mensaje de chat más reciente en el salón.</span><span class="sxs-lookup"><span data-stu-id="3f444-179">Persistent Chat Server replies with a new SIP INFO message that contains the most recent chat message in the room.</span></span>

7.  <span data-ttu-id="3f444-180">El cliente de chat persistente envía un mensaje de información SIP que contiene un comando XCCOS **getinv** (es decir, obtener invitación) para solicitar nuevas invitaciones Room que el cliente todavía no ha visto.</span><span class="sxs-lookup"><span data-stu-id="3f444-180">The Persistent Chat client sends a SIP INFO message that contains a XCCOS **getinv** (that is, get invitation) command to request any new room invitations that the client has not yet seen.</span></span> <span data-ttu-id="3f444-181">En un mensaje de información SIP independiente, el servidor de chat persistente devuelve una lista de estas salas.</span><span class="sxs-lookup"><span data-stu-id="3f444-181">In a separate SIP INFO message, Persistent Chat Server returns a list of those rooms.</span></span>

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a><span data-ttu-id="3f444-182">Suscribirse a una sala y publicar un mensaje</span><span class="sxs-lookup"><span data-stu-id="3f444-182">Subscribe to a Room and Post a Message</span></span>

<span data-ttu-id="3f444-183">El siguiente diagrama de flujo de llamadas y los pasos describen una suscripción de salón típica y un escenario de exposición de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3f444-183">The following call flow diagram and steps describe a typical room subscription and message post scenario.</span></span>

<span data-ttu-id="3f444-184">**Suscripción de salón de cliente de chat persistente y flujo de llamada de registro de mensajes**</span><span class="sxs-lookup"><span data-stu-id="3f444-184">**Persistent Chat Client Room Subscription and Message Posting Call Flow**</span></span>

<span data-ttu-id="3f444-185">![Suscripción a salas y escenario de exposición de mensajes.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Suscripción a salas y escenario de exposición de mensajes.")</span><span class="sxs-lookup"><span data-stu-id="3f444-185">![Room subscription and message post scenario.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Room subscription and message post scenario.")</span></span>

1.  <span data-ttu-id="3f444-186">Desde el cliente de chat persistente, user1 hace clic en **unirse a un salón de chat**, hace clic en **Buscar**y, a continuación, escribe algunos criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3f444-186">From the Persistent Chat client, User1 clicks **Join a Chat Room**, clicks **Search**, and then enters some search criteria.</span></span> <span data-ttu-id="3f444-187">El cliente de chat persistente envía un mensaje SIP INFO que contiene el comando XCCOS **chansrch** (Search Room), junto con los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3f444-187">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **chansrch** (room search) command, along with the search criteria.</span></span> <span data-ttu-id="3f444-188">El servidor de chat persistente consulta la base de datos back-end y responde en un nuevo mensaje de información SIP que contiene una lista de salones disponibles que cumplen con los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3f444-188">Persistent Chat Server queries the back-end database and replies in a new SIP INFO message that contains a list of available rooms that meet the search criteria.</span></span>

2.  <span data-ttu-id="3f444-189">Usuario1 selecciona la sala de chat a la que desea conectarse y luego hace clic en **Seguir esta sala**.</span><span class="sxs-lookup"><span data-stu-id="3f444-189">User1 selects the chat room that he or she wants to join, and then clicks **Follow this room**.</span></span> <span data-ttu-id="3f444-190">El cliente de chat persistente envía un mensaje SIP información del servidor de chat persistente que contiene el comando XCCOS **join** y el identificador de sala del salón de chat que seleccionó el usuario.</span><span class="sxs-lookup"><span data-stu-id="3f444-190">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **join** command and the room ID of the chat room that the user selected.</span></span> <span data-ttu-id="3f444-191">El servidor de chat persistente responde con un mensaje de información SIP que contiene los datos de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="3f444-191">Persistent Chat Server replies with a SIP INFO message that contains the provisioning data.</span></span>

3.  <span data-ttu-id="3f444-192">El cliente de chat persistente envía un mensaje SIP información del servidor de chat persistente que contiene el comando XCCOS **bccontext** (contexto de mi chat).</span><span class="sxs-lookup"><span data-stu-id="3f444-192">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **bccontext** (backchat context) command.</span></span> <span data-ttu-id="3f444-193">El servidor de chat persistente recupera el historial de chats y lo devuelve al cliente de chat persistente en un mensaje SIP independiente.</span><span class="sxs-lookup"><span data-stu-id="3f444-193">Persistent Chat Server retrieves the chat history, and returns it to the Persistent Chat client in a separate SIP INFO message.</span></span> <span data-ttu-id="3f444-194">En este momento, el usuario ingresa a la sala de chat y está listo para participar.</span><span class="sxs-lookup"><span data-stu-id="3f444-194">At this point, the user enters the chat room and is ready to participate.</span></span>

4.  <span data-ttu-id="3f444-195">Usuario1 introduce un nuevo mensaje y luego hace clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="3f444-195">User1 enters a new message, and then clicks **Send**.</span></span> <span data-ttu-id="3f444-196">El cliente de chat persistente publica el mensaje en el salón de chat en un comando SIP información XCCOS **grpchat** .</span><span class="sxs-lookup"><span data-stu-id="3f444-196">The Persistent Chat client posts the message to the chat room in a SIP INFO XCCOS **grpchat** command.</span></span> <span data-ttu-id="3f444-197">El servidor de chat persistente almacena una copia de este nuevo mensaje en la base de datos back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="3f444-197">Persistent Chat Server stores a copy of this new message in the Persistent Chat back-end database.</span></span>

5.  <span data-ttu-id="3f444-198">El servidor de chat persistente envía una copia independiente del mensaje SIP información XCCOS **grpchat** a user2, que ya ha entrado en el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="3f444-198">Persistent Chat Server sends a separate copy of the SIP INFO XCCOS **grpchat** message to User2, who has already entered the chat room.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a><span data-ttu-id="3f444-199">Flujos de llamadas de cumplimiento de chat persistente</span><span class="sxs-lookup"><span data-stu-id="3f444-199">Persistent Chat Compliance Call Flows</span></span>

<span data-ttu-id="3f444-200">El servidor de chat persistente usa Message Queue Server (también conocido como MSMQ) y una base de datos de cumplimiento adicional (mgccomp) para procesar los datos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="3f444-200">Persistent Chat Server uses Message Queuing (also known as MSMQ) and an additional compliance database (mgccomp) to process compliance data.</span></span> <span data-ttu-id="3f444-201">Como ejemplo de cómo se procesan los eventos de cumplimiento, la siguiente secuencia de eventos describe cómo se procesa un evento de publicación de mensaje.</span><span class="sxs-lookup"><span data-stu-id="3f444-201">As an example of how compliance events are processed, the following sequence of events describes how a message post event is processed.</span></span>

1.  <span data-ttu-id="3f444-202">Un usuario publica un mensaje en una sala.</span><span class="sxs-lookup"><span data-stu-id="3f444-202">A user posts a message to a room.</span></span>

2.  <span data-ttu-id="3f444-203">El servidor de chat persistente coloca información relativa al evento en una cola privada de Message Queue Server.</span><span class="sxs-lookup"><span data-stu-id="3f444-203">Persistent Chat Server places information pertaining to the event in a private Message Queuing queue.</span></span>

3.  <span data-ttu-id="3f444-204">El servidor de cumplimiento de chat persistente Lee este evento de la cola y lo coloca en la base de datos de mgccomp para su procesamiento posterior.</span><span class="sxs-lookup"><span data-stu-id="3f444-204">Persistent Chat Compliance server reads this event from the queue, and places it into the mgccomp database for processing later.</span></span>

4.  <span data-ttu-id="3f444-205">Periódicamente, el servidor de cumplimiento de chat persistente procesa un conjunto de eventos en la base de datos y los envía al adaptador de cumplimiento de chat persistente para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="3f444-205">Periodically, the Persistent Chat Compliance server processes a set of events in the database, and sends them to the Persistent Chat Compliance adapter for processing.</span></span>

5.  <span data-ttu-id="3f444-206">Si el adaptador procesa los datos correctamente, el servidor de cumplimiento de chat persistente elimina los eventos de la base de datos de mgccomp.</span><span class="sxs-lookup"><span data-stu-id="3f444-206">If the adapter successfully processes the data, Persistent Chat Compliance server deletes the events from the mgccomp database.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

