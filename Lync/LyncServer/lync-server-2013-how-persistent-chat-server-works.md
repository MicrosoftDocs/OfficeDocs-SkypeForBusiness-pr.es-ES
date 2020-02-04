---
title: 'Lync Server 2013: Cómo funciona el servidor de chat persistente'
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
ms.openlocfilehash: 692f9a40bc2c0fd885fc251a4a792d480a69c57d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a><span data-ttu-id="8dfb0-102">Cómo funciona el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dfb0-102">How Persistent Chat Server works in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dfb0-103">_**Última modificación del tema:** 2012-11-21_</span><span class="sxs-lookup"><span data-stu-id="8dfb0-103">_**Topic Last Modified:** 2012-11-21_</span></span>

<span data-ttu-id="8dfb0-104">Lync Server 2013, el servidor de chat persistente le permite participar en conversaciones con varias partes y basadas en temas que se conservan a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="8dfb0-105">El servidor de chat persistente puede ayudar a su organización a hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8dfb0-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="8dfb0-106">Mejorar la comunicación entre equipos geográficamente dispersos y con varias funciones</span><span class="sxs-lookup"><span data-stu-id="8dfb0-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="8dfb0-107">Ampliar el conocimiento y la participación de la información</span><span class="sxs-lookup"><span data-stu-id="8dfb0-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="8dfb0-108">Mejorar la comunicación con su organización extendida</span><span class="sxs-lookup"><span data-stu-id="8dfb0-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="8dfb0-109">Reducir sobrecarga de información</span><span class="sxs-lookup"><span data-stu-id="8dfb0-109">Reduce information overload</span></span>

  - <span data-ttu-id="8dfb0-110">Mejorar el conocimiento de la información</span><span class="sxs-lookup"><span data-stu-id="8dfb0-110">Improve information awareness</span></span>

  - <span data-ttu-id="8dfb0-111">Aumentar la dispersión de información y conocimientos importantes</span><span class="sxs-lookup"><span data-stu-id="8dfb0-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="8dfb0-112">Puede implementar el servidor de chat persistente como un rol opcional con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-112">You can deploy Persistent Chat Server as an optional role with Lync Server 2013.</span></span> <span data-ttu-id="8dfb0-113">Los servicios de chat persistente se ejecutan en un grupo dedicado y un grupo de servidores de chat persistente depende de un grupo de Lync Server para enrutar mensajes a él.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-113">Persistent Chat services run on a dedicated pool, and a Persistent Chat Server pool depends on a Lync Server pool to route messages to it.</span></span> <span data-ttu-id="8dfb0-114">Los clientes usan la comunicación de chats extensibles a través de SIP (XCCOS).</span><span class="sxs-lookup"><span data-stu-id="8dfb0-114">Clients use eXtensible Chat Communication Over SIP (XCCOS).</span></span> <span data-ttu-id="8dfb0-115">Los servidores front-end de Lync Server están configurados para enrutar el tráfico a un grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-115">The Lync Server Front End Servers are configured to route the traffic to a Persistent Chat Server pool.</span></span>

<div>

## <a name="high-level-architecture"></a><span data-ttu-id="8dfb0-116">Arquitectura de alto nivel</span><span class="sxs-lookup"><span data-stu-id="8dfb0-116">High-Level Architecture</span></span>

<span data-ttu-id="8dfb0-117">Los siguientes diagramas proporcionan perspectivas de alto nivel de los servicios y la arquitectura del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-117">The following diagrams provide high-level perspectives of the Persistent Chat Server architecture and services.</span></span>

<span data-ttu-id="8dfb0-118">**Arquitectura de alto nivel del servidor de chat persistente**</span><span class="sxs-lookup"><span data-stu-id="8dfb0-118">**Persistent Chat Server High-Level Architecture**</span></span>

<span data-ttu-id="8dfb0-119">![Arquitectura del servidor de chat persistente.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Arquitectura del servidor de chat persistente.")</span><span class="sxs-lookup"><span data-stu-id="8dfb0-119">![Persistent Chat Server architecture.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server architecture.")</span></span>

<span data-ttu-id="8dfb0-120">**Servicios de alto nivel del servidor de chat persistente**</span><span class="sxs-lookup"><span data-stu-id="8dfb0-120">**Persistent Chat Server High-Level Services**</span></span>

<span data-ttu-id="8dfb0-121">![Componentes del servidor de chat persistente.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Componentes del servidor de chat persistente.")</span><span class="sxs-lookup"><span data-stu-id="8dfb0-121">![Persistent Chat Server components.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server components.")</span></span>

<span data-ttu-id="8dfb0-122">Se ejecutan dos servicios en los servidores front-end del servidor de chat persistente:</span><span class="sxs-lookup"><span data-stu-id="8dfb0-122">Two services run on the Persistent Chat Server Front End Servers:</span></span>

  - <span data-ttu-id="8dfb0-123">Chat persistente (canal)</span><span class="sxs-lookup"><span data-stu-id="8dfb0-123">Persistent Chat (Channel)</span></span>

  - <span data-ttu-id="8dfb0-124">Respeto</span><span class="sxs-lookup"><span data-stu-id="8dfb0-124">Compliance</span></span>

<div>

## <a name="persistent-chat-channel-service"></a><span data-ttu-id="8dfb0-125">Servicio de chat persistente (canal)</span><span class="sxs-lookup"><span data-stu-id="8dfb0-125">Persistent Chat (Channel) Service</span></span>

<span data-ttu-id="8dfb0-126">El servicio de chat persistente (canal) es el servicio principal responsable del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-126">The Persistent Chat (Channel) service is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="8dfb0-127">Este servicio ofrece las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="8dfb0-127">This service provides the following functions:</span></span>

  - <span data-ttu-id="8dfb0-128">Acepta mensajes entrantes</span><span class="sxs-lookup"><span data-stu-id="8dfb0-128">Accepts incoming messages</span></span>

  - <span data-ttu-id="8dfb0-129">Registra y enumera los participantes en línea dentro de un salón de chat persistente</span><span class="sxs-lookup"><span data-stu-id="8dfb0-129">Registers and lists online participants within a Persistent Chat room</span></span>

  - <span data-ttu-id="8dfb0-130">Retransmite mensajes a los suscriptores de otros canales</span><span class="sxs-lookup"><span data-stu-id="8dfb0-130">Retransmits messages to other channel subscribers</span></span>

  - <span data-ttu-id="8dfb0-131">Implementa lógica para la administración de canales, la invitación a un salón de chat, una búsqueda y nuevas notificaciones de contenido</span><span class="sxs-lookup"><span data-stu-id="8dfb0-131">Implements logic for channel management, chat room invitation, search, and new content notifications</span></span>

<span data-ttu-id="8dfb0-132">El servicio de chat persistente (canal) almacena y accede al contenido del salón de chat y otros metadatos del sistema (reglas de autorización, etc.) mediante el almacén de chats persistentes.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-132">The Persistent Chat (Channel) service stores and accesses chat room content and other system metadata (authorization rules, and so on) by using the Persistent Chat Store.</span></span> <span data-ttu-id="8dfb0-133">Este servicio almacena los archivos cargados en salones de chat en el almacén de archivos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-133">This service stores files that are uploaded into chat rooms in the Persistent Chat File Store.</span></span>

</div>

<div>

## <a name="compliance-service"></a><span data-ttu-id="8dfb0-134">Servicio de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="8dfb0-134">Compliance Service</span></span>

<span data-ttu-id="8dfb0-135">El servicio de cumplimiento normativo es un componente opcional de un servidor de chat persistente y es el responsable de archivar el contenido y los eventos de chat en el almacén de cumplimiento persistente de la conversación.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-135">The Compliance service is an optional component of Persistent Chat Server and is responsible for archiving chat content and events to the Persistent Chat Compliance Store.</span></span> <span data-ttu-id="8dfb0-136">Si la organización cuenta con normas que precisan que se archive la actividad del chat persistente, puede implementar el servicio de cumplimiento opcional del chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-136">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="8dfb0-137">El servicio de cumplimiento está instalado en cada servidor de chat persistente en un grupo de chats persistentes.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-137">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> <span data-ttu-id="8dfb0-138">Una vez configurado, el cumplimiento del servidor de chat persistente registra la actividad de los usuarios, como unirse a salas y abandonarlos, y publicar y leer los mensajes.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-138">When configured, Persistent Chat Server compliance records user activity such as joining and leaving rooms, and posting and reading of messages.</span></span> <span data-ttu-id="8dfb0-139">El servicio de cumplimiento almacena los archivos que necesitan archivarse en el almacén de archivos de cumplimiento de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-139">The Compliance service stores files that need to be archived in the Persistent Chat Compliance File Store.</span></span>

</div>

<div>

## <a name="persistent-chat-web-services"></a><span data-ttu-id="8dfb0-140">Servicios Web de chat persistente</span><span class="sxs-lookup"><span data-stu-id="8dfb0-140">Persistent Chat Web Services</span></span>

<span data-ttu-id="8dfb0-141">En los servidores front-end de Lync Server, se ejecutan dos servicios que dependen de Internet Information Services (IIS) y se implementan como componentes Web:</span><span class="sxs-lookup"><span data-stu-id="8dfb0-141">On the Lync Server Front End Servers, two services run that depend on Internet Information Services (IIS), and are implemented as web components:</span></span>

  - <span data-ttu-id="8dfb0-142">**Servicios Web de chat persistente para carga y descarga de archivos** Responsable de publicar y recuperar archivos de salones de chat.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-142">**Persistent Chat Web Services for File Upload/Download** Responsible for posting and retrieving files from chat rooms.</span></span>

  - <span data-ttu-id="8dfb0-143">**Servicios Web de chat persistente para la administración de salones de chat** Responsable de proporcionar a los usuarios la capacidad de administrar sus salones de chat y de crear nuevos salones de chat.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-143">**Persistent Chat Web Services for Chat Room Management** Responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a><span data-ttu-id="8dfb0-144">¿Cómo empiezo a usar el servidor de chat persistente?</span><span class="sxs-lookup"><span data-stu-id="8dfb0-144">How Do I Start Using Persistent Chat Server?</span></span>

<span data-ttu-id="8dfb0-145">El servidor de chat persistente es un rol de servidor opcional dentro de la infraestructura de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-145">Persistent Chat Server is an optional server role within the Lync Server 2013 infrastructure.</span></span> <span data-ttu-id="8dfb0-146">Si instala el rol de servidor de chat persistente, los usuarios que hayan habilitado la Directiva mediante un administrador pueden usar la conversación persistente con el cliente de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-146">If you install the Persistent Chat Server role, any users who have been enabled through policy by an administrator can use Persistent Chat with the Lync 2013 client.</span></span>

<span data-ttu-id="8dfb0-147">Para obtener más información sobre cómo implementar el servidor de chat persistente y permitir que los usuarios aprovechen las funciones por directiva, consulte [implementar un servidor de chat persistente en Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="8dfb0-147">For details about how to deploy Persistent Chat Server and enable users to leverage the capabilities by policy, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>

<span data-ttu-id="8dfb0-148">Para obtener más información sobre cómo configurar las opciones de la implementación del servidor de chat persistente, consulte [implementar un servidor de chat persistente en Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) y [administrar Lync Server 2013, servidor de chat persistente](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="8dfb0-148">For details about how to configure settings on your Persistent Chat Server deployment, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="8dfb0-149">Para obtener detalles sobre cómo habilitar a los usuarios mediante directivas de modo que puedan aprovechar la funcionalidad de chat persistente en el cliente de Lync 2013, consulte [implementar el servidor de chat persistente en Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) y [administrar Lync Server 2013, servidor de chat persistente](managing-lync-server-2013-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="8dfb0-149">For details about how to enable users by policy such that they can leverage Persistent Chat functionality in Lync 2013 client, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="8dfb0-150">Si ha implementado el cumplimiento persistente de la conversación, consulte [administrar Lync server 2013, servidor de chat persistente](managing-lync-server-2013-persistent-chat-server.md) para obtener información sobre cómo configurar las opciones de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-150">If you deployed Persistent Chat compliance, see [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) for details about how to configure settings for compliance.</span></span>

</div>

<div>

## <a name="persistent-chat-call-flows"></a><span data-ttu-id="8dfb0-151">Flujos de llamadas de chat persistentes</span><span class="sxs-lookup"><span data-stu-id="8dfb0-151">Persistent Chat Call Flows</span></span>

<span data-ttu-id="8dfb0-152">El cliente de chat persistente se comunica con el servicio de chat persistente usando XCCOS.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-152">The Persistent Chat client communicates with the Persistent Chat service by using XCCOS.</span></span> <span data-ttu-id="8dfb0-153">Las siguientes secuencias describen el proceso de inicio de sesión y un escenario típico de suscripción a salas y mensajes.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-153">The following sequences describe the sign-in process and a typical room subscription and message post scenario.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="8dfb0-154">Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="8dfb0-154">Sign-in</span></span>

<span data-ttu-id="8dfb0-155">El siguiente diagrama de flujo de llamadas y los pasos describen el proceso de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-155">The following call flow diagram and steps describe the sign-in process.</span></span>

<span data-ttu-id="8dfb0-156">**Flujo de llamadas de inicio de sesión de clientes de chat persistente**</span><span class="sxs-lookup"><span data-stu-id="8dfb0-156">**Persistent Chat Client Sign-in Call Flow**</span></span>

<span data-ttu-id="8dfb0-157">![Diagrama de flujo de llamadas del servidor de chat persistente.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Diagrama de flujo de llamadas del servidor de chat persistente.")</span><span class="sxs-lookup"><span data-stu-id="8dfb0-157">![Persistent Chat Server call flow diagram.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server call flow diagram.")</span></span>

1.  <span data-ttu-id="8dfb0-158">El cliente de chat persistente envía primero un SIP SUBSCRIBE para recuperar el documento de aprovisionamiento en banda del servidor.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-158">The Persistent Chat client first sends a SIP SUBSCRIBE to retrieve the in-band provisioning document from the server.</span></span> <span data-ttu-id="8dfb0-159">Este documento indica si el chat persistente está habilitado o deshabilitado para el usuario y la lista de URI de SIP para el grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-159">This document indicates if Persistent Chat is enabled or disabled for the user and the list of SIP URIs for the Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="8dfb0-160">El cliente de chat persistente envía un mensaje SIP INVITE al URI SIP del servidor de chat persistente que obtuvo en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-160">The Persistent Chat client sends a SIP INVITE message to the SIP URI of the Persistent Chat Server that it obtained in the previous step.</span></span> <span data-ttu-id="8dfb0-161">La secuencia de invitación viene seguida de 200 aceptar y ACK, y el cliente de chat persistente ha abierto una sesión SIP con un extremo del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-161">The INVITE sequence is followed by 200 OK and ACK, and the Persistent Chat client has now opened a SIP session with a Persistent Chat Server endpoint.</span></span> <span data-ttu-id="8dfb0-162">Por lo tanto, el cliente de chat persistente se comunica con el servidor de chat persistente enviando mensajes de información SIP que contienen mensajes de chat o comandos que solicitan que el servidor realice una acción.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-162">Consequently, the Persistent Chat client communicates with Persistent Chat Server by sending SIP INFO messages that contain either chat messages or commands requesting the server to take an action.</span></span> <span data-ttu-id="8dfb0-163">Todos estos mensajes se confirman con el servicio 200 aceptar o 503, ya sea no disponible (es decir, en el caso de una carga pesada del servidor).</span><span class="sxs-lookup"><span data-stu-id="8dfb0-163">All of these messages are acknowledged with either 200 OK or 503 Service Unavailable (that is, in the event of heavy server load).</span></span> <span data-ttu-id="8dfb0-164">Si el cliente recibe una respuesta de 503, se volverá a intentar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-164">If the client receives a 503 response, it will retry the message.</span></span> <span data-ttu-id="8dfb0-165">(Este ejemplo no incluye una respuesta 503). Si el servidor acepta el mensaje o el comando y envía 200 aceptar, proporciona una respuesta al cliente en forma de mensaje de información SIP independiente.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-165">(This example does not include a 503 response.) If the server accepts the message or command and sends 200 OK, it provides a response to the client in the form of a separate SIP INFO message.</span></span> <span data-ttu-id="8dfb0-166">Esta respuesta incluye una referencia al comando de origen.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-166">This response includes a reference to the originating command.</span></span>

3.  <span data-ttu-id="8dfb0-167">El cliente de chat persistente envía un mensaje de información SIP que contiene el comando XCCOS **getServerInfo** .</span><span class="sxs-lookup"><span data-stu-id="8dfb0-167">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getserverinfo** command.</span></span> <span data-ttu-id="8dfb0-168">El servidor de chat persistente responde con un nuevo mensaje de información SIP que contiene información sobre la configuración del servicio de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-168">Persistent Chat Server replies with a new SIP INFO message that contains information about the Persistent Chat service configuration.</span></span>

4.  <span data-ttu-id="8dfb0-169">El cliente de chat persistente envía un mensaje de información SIP que contiene el comando XCCOS **getassociations** .</span><span class="sxs-lookup"><span data-stu-id="8dfb0-169">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getassociations** command.</span></span> <span data-ttu-id="8dfb0-170">El servidor de chat persistente responde con un nuevo mensaje de información SIP que contiene la lista de salas de las que es miembro el usuario.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-170">Persistent Chat Server replies with a new SIP INFO message that contains the list of rooms of which the user is a member.</span></span> <span data-ttu-id="8dfb0-171">El cliente de chat persistente repite el comando para recuperar la lista de salas de las que el usuario es administrador.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-171">The Persistent Chat client repeats the command to retrieve the list of rooms of which the user is a manager.</span></span>

5.  <span data-ttu-id="8dfb0-172">El cliente de chat persistente obtiene la lista de salones seguidos del documento "de presencia", en el que cada sala seguida está representada por una categoría "roomSetting".</span><span class="sxs-lookup"><span data-stu-id="8dfb0-172">The Persistent Chat client gets the list of followed rooms from the "presence" document, where each followed room is represented by a "roomSetting" category.</span></span> <span data-ttu-id="8dfb0-173">Todas las salas seguidas se unen mediante un solo mensaje SIP que contiene el XCCOS **búnete** que contiene la lista de URI de la sala.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-173">All followed rooms are joined by a single SIP INFO message that contains the XCCOS **bjoin** command that contains the list of room URIs.</span></span> <span data-ttu-id="8dfb0-174">Dado que la lista de salas seguidas se guarda en el servidor, cualquier cliente en cualquier equipo tiene la misma lista de salones seguidos para el URI de usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-174">Because the list of followed rooms is kept on the server, any client on any computer has the same list of followed rooms for the specified user URI.</span></span> <span data-ttu-id="8dfb0-175">El cliente de chat persistente también mantiene la lista de salas abiertas (si el usuario ha habilitado esta opción) en el registro del equipo local y se une a cada una de estas salas al enviar un mensaje de información SIP que contiene el comando XCCOS **join** para cada sala abierta.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-175">The Persistent Chat client also keeps the list of opened rooms (if this option is enabled by the user) in the local computer registry, and joins each of these rooms at sign-in by sending a SIP INFO message that contains the XCCOS **join** command for each opened room.</span></span> <span data-ttu-id="8dfb0-176">Como esta lista se guarda en el registro, puede ser diferente en dos clientes de chat persistentes que se ejecutan en equipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-176">Because this list is kept in the registry, it can be different on two Persistent Chat clients running on different computers.</span></span>

6.  <span data-ttu-id="8dfb0-177">Para cada habitación Unido, el cliente de chat persistente envía un mensaje SIP INFO que contiene el comando XCCOS **bccontext** .</span><span class="sxs-lookup"><span data-stu-id="8dfb0-177">For each room joined, the Persistent Chat client sends a SIP INFO message that contains the XCCOS **bccontext** command.</span></span> <span data-ttu-id="8dfb0-178">El servidor de chat persistente responde con un nuevo mensaje de información SIP que contiene el mensaje de chat más reciente en el salón.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-178">Persistent Chat Server replies with a new SIP INFO message that contains the most recent chat message in the room.</span></span>

7.  <span data-ttu-id="8dfb0-179">El cliente de la conversación persistente envía un mensaje de información SIP que contiene un XCCOS **getinv** (es decir, obtener invitación) para solicitar nuevas invitaciones Room que el cliente aún no ha visto.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-179">The Persistent Chat client sends a SIP INFO message that contains a XCCOS **getinv** (that is, get invitation) command to request any new room invitations that the client has not yet seen.</span></span> <span data-ttu-id="8dfb0-180">En un mensaje de información SIP independiente, el servidor de chat persistente devuelve una lista de esas salas.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-180">In a separate SIP INFO message, Persistent Chat Server returns a list of those rooms.</span></span>

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a><span data-ttu-id="8dfb0-181">Suscribirse a una sala y publicar un mensaje</span><span class="sxs-lookup"><span data-stu-id="8dfb0-181">Subscribe to a Room and Post a Message</span></span>

<span data-ttu-id="8dfb0-182">El siguiente diagrama de flujo de llamadas y los pasos describen un escenario típico de suscripción a un salón y mensaje.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-182">The following call flow diagram and steps describe a typical room subscription and message post scenario.</span></span>

<span data-ttu-id="8dfb0-183">**Suscripción al salón del cliente de chat persistente y flujo de llamadas de publicación de mensajes**</span><span class="sxs-lookup"><span data-stu-id="8dfb0-183">**Persistent Chat Client Room Subscription and Message Posting Call Flow**</span></span>

<span data-ttu-id="8dfb0-184">![Suscripción al salón y mensaje postescenario.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Suscripción al salón y mensaje postescenario.")</span><span class="sxs-lookup"><span data-stu-id="8dfb0-184">![Room subscription and message post scenario.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Room subscription and message post scenario.")</span></span>

1.  <span data-ttu-id="8dfb0-185">Desde el cliente de chat persistente, usuario1 hace clic en **unirse a un salón de chat**, hace clic en **Buscar**y, a continuación, escribe algunos criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-185">From the Persistent Chat client, User1 clicks **Join a Chat Room**, clicks **Search**, and then enters some search criteria.</span></span> <span data-ttu-id="8dfb0-186">El cliente de chat persistente envía un mensaje SIP INFO que contiene el comando XCCOS **chansrch** (búsqueda de la sala) junto con los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-186">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **chansrch** (room search) command, along with the search criteria.</span></span> <span data-ttu-id="8dfb0-187">El servidor de chat persistente consulta la base de datos back-end y responde en un mensaje de información SIP nueva que contiene una lista de las salas disponibles que cumplen los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-187">Persistent Chat Server queries the back-end database and replies in a new SIP INFO message that contains a list of available rooms that meet the search criteria.</span></span>

2.  <span data-ttu-id="8dfb0-188">Usuario1 selecciona el salón de chat al que desea unirse y, a continuación, hace clic en **seguir este salón**.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-188">User1 selects the chat room that he or she wants to join, and then clicks **Follow this room**.</span></span> <span data-ttu-id="8dfb0-189">El cliente de la conversación persistente envía un mensaje SIP INFO que contiene el comando XCCOS **join** y el identificador Room del salón de chat que seleccionó el usuario.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-189">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **join** command and the room ID of the chat room that the user selected.</span></span> <span data-ttu-id="8dfb0-190">El servidor de chat persistente responde con un mensaje de información SIP que contiene los datos de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-190">Persistent Chat Server replies with a SIP INFO message that contains the provisioning data.</span></span>

3.  <span data-ttu-id="8dfb0-191">El cliente de la conversación persistente envía un mensaje de información SIP que contiene el XCCOS **bccontext** (contexto de chat).</span><span class="sxs-lookup"><span data-stu-id="8dfb0-191">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **bccontext** (backchat context) command.</span></span> <span data-ttu-id="8dfb0-192">El servidor de chat persistente recupera el historial de chats y lo devuelve al cliente de chat persistente en un mensaje SIP independiente.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-192">Persistent Chat Server retrieves the chat history, and returns it to the Persistent Chat client in a separate SIP INFO message.</span></span> <span data-ttu-id="8dfb0-193">En este punto, el usuario entra en el salón de chat y está listo para participar.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-193">At this point, the user enters the chat room and is ready to participate.</span></span>

4.  <span data-ttu-id="8dfb0-194">Usuario1 escribe un nuevo mensaje y, a continuación, hace clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-194">User1 enters a new message, and then clicks **Send**.</span></span> <span data-ttu-id="8dfb0-195">El cliente de chat persistente publica el mensaje en el salón de chat en un comando SIP INFO XCCOS **grpchat** .</span><span class="sxs-lookup"><span data-stu-id="8dfb0-195">The Persistent Chat client posts the message to the chat room in a SIP INFO XCCOS **grpchat** command.</span></span> <span data-ttu-id="8dfb0-196">El servidor de chat persistente almacena una copia de este mensaje nuevo en la base de datos back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-196">Persistent Chat Server stores a copy of this new message in the Persistent Chat back-end database.</span></span>

5.  <span data-ttu-id="8dfb0-197">El servidor de chat persistente envía una copia separada del mensaje SIP INFO XCCOS **grpchat** a user2, que ya ha entrado en el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-197">Persistent Chat Server sends a separate copy of the SIP INFO XCCOS **grpchat** message to User2, who has already entered the chat room.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a><span data-ttu-id="8dfb0-198">Flujos de llamada de cumplimiento de chat persistente</span><span class="sxs-lookup"><span data-stu-id="8dfb0-198">Persistent Chat Compliance Call Flows</span></span>

<span data-ttu-id="8dfb0-199">El servidor de chat persistente usa Message Queue Server (también conocido como MSMQ) y una base de datos de cumplimiento adicional (mgccomp) para procesar los datos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-199">Persistent Chat Server uses Message Queuing (also known as MSMQ) and an additional compliance database (mgccomp) to process compliance data.</span></span> <span data-ttu-id="8dfb0-200">Como ejemplo de cómo se procesan los eventos de conformidad, la siguiente secuencia de eventos describe cómo se procesa un evento de exposición de mensajes.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-200">As an example of how compliance events are processed, the following sequence of events describes how a message post event is processed.</span></span>

1.  <span data-ttu-id="8dfb0-201">Un usuario publica un mensaje en un salón.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-201">A user posts a message to a room.</span></span>

2.  <span data-ttu-id="8dfb0-202">El servidor de chat persistente coloca información relacionada con el evento en una cola privada de Message Queue Server.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-202">Persistent Chat Server places information pertaining to the event in a private Message Queuing queue.</span></span>

3.  <span data-ttu-id="8dfb0-203">El servidor de cumplimiento de chat persistente Lee este evento en la cola y lo coloca en la base de datos mgccomp para su procesamiento posterior.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-203">Persistent Chat Compliance server reads this event from the queue, and places it into the mgccomp database for processing later.</span></span>

4.  <span data-ttu-id="8dfb0-204">Periódicamente, el servidor de cumplimiento de chat persistente procesa un conjunto de eventos en la base de datos y los envía al adaptador de cumplimiento de chat persistente para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-204">Periodically, the Persistent Chat Compliance server processes a set of events in the database, and sends them to the Persistent Chat Compliance adapter for processing.</span></span>

5.  <span data-ttu-id="8dfb0-205">Si el adaptador procesa correctamente los datos, el servidor de cumplimiento de chat persistente elimina los eventos de la base de datos de mgccomp.</span><span class="sxs-lookup"><span data-stu-id="8dfb0-205">If the adapter successfully processes the data, Persistent Chat Compliance server deletes the events from the mgccomp database.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

