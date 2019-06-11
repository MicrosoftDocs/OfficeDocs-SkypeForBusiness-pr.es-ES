---
title: 'Lync Server 2013: Información general del servidor de chat en grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Persistent Chat Server
ms:assetid: 23f7c886-304d-495a-ae70-3cbb44241acd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425717(v=OCS.15)
ms:contentKeyID: 48183622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a744f4eb251bbbacc8b1b5f4c2a5978a9689f225
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="75a42-102">Información general del servidor de chat en grupo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75a42-102">Overview of Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75a42-103">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="75a42-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="75a42-104">Lync Server 2013, el servidor de chat persistente permite a los usuarios participar en conversaciones de varias partes y basadas en temas que persisten a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="75a42-104">Lync Server 2013, Persistent Chat Server enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="75a42-105">El servidor de chat persistente puede ayudar a su organización a hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="75a42-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="75a42-106">Mejorar la comunicación entre equipos geográficamente dispersos y con varias funciones.</span><span class="sxs-lookup"><span data-stu-id="75a42-106">Improve communication between geographically dispersed and cross-functional teams.</span></span> <span data-ttu-id="75a42-107">Al usar el chat persistente, los equipos pueden compartir de forma eficaz información, ideas y decisiones entre sí.</span><span class="sxs-lookup"><span data-stu-id="75a42-107">By using Persistent Chat, teams can efficiently share information, ideas, and decisions with one another.</span></span> <span data-ttu-id="75a42-108">Los mensajes publicados en los salones de chat (foros de discusión) pueden persistir (es decir, pueden estar disponibles a lo largo del tiempo), de modo que puedan participar las personas de diferentes ubicaciones y departamentos, incluso cuando no estén conectados de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="75a42-108">The messages posted to chat rooms (discussion forums) can persist (that is, can be available over time), so that people from different locations and departments can participate, even when they are not simultaneously online.</span></span> <span data-ttu-id="75a42-109">Cuando un usuario se conecta a un salón de chat, el chat de postales (un número configurable de mensajes del historial de conversaciones) se carga automáticamente en el salón de chat para darle al usuario un contexto para la conversación.</span><span class="sxs-lookup"><span data-stu-id="75a42-109">When a user connects to a chat room, backchat (a configurable number of chat-history messages) is automatically loaded in the chat room to give the user a context for the conversation.</span></span>

  - <span data-ttu-id="75a42-110">Mejorar el conocimiento de la información.</span><span class="sxs-lookup"><span data-stu-id="75a42-110">Improve information awareness.</span></span> <span data-ttu-id="75a42-111">Al usar filtros de cliente, los usuarios pueden definir condiciones, como palabras clave en el contenido del mensaje o el valor del campo "de" en un mensaje, para recibir una notificación cuando estas condiciones se cumplan en mensajes instantáneos de chat persistente o en mensajes de salones de chat.</span><span class="sxs-lookup"><span data-stu-id="75a42-111">By using client-side filters, users can define conditions—such as keywords in message content, or the value of the "from" field in a message—to receive notification when those conditions are met in Persistent Chat instant messages or chat room messages.</span></span> <span data-ttu-id="75a42-112">De esta manera, los usuarios pueden mantenerse al día con el contenido que más les interesa.</span><span class="sxs-lookup"><span data-stu-id="75a42-112">This way, users can stay up-to-date with the content that interests them most.</span></span>

  - <span data-ttu-id="75a42-113">Mejorar la comunicación con su organización extendida.</span><span class="sxs-lookup"><span data-stu-id="75a42-113">Improve communication with their extended organization.</span></span> <span data-ttu-id="75a42-114">Al facilitar la colaboración en temas de larga ejecución con otras personas de la organización y proporcionando un lugar persistente para compartir información, el chat persistente ayuda a mejorar la comunicación.</span><span class="sxs-lookup"><span data-stu-id="75a42-114">By making it easy to collaborate over long-running topics with others in the organization, and by providing a persistent place to share information, Persistent Chat helps improve communication.</span></span>

  - <span data-ttu-id="75a42-115">Reduzca la sobrecarga de información.</span><span class="sxs-lookup"><span data-stu-id="75a42-115">Reduce information overload.</span></span> <span data-ttu-id="75a42-116">Los usuarios pueden seguir las salas de chats y los mensajes de mayor interés mediante filtros de cliente, y pueden agregar salones de chat que deseen seguir a su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="75a42-116">Users can follow chat rooms and messages of most interest by using client-side filters, and can add chat rooms they want to follow to their contact list.</span></span>

  - <span data-ttu-id="75a42-117">Aumente la dispersión de información importante y conocimientos.</span><span class="sxs-lookup"><span data-stu-id="75a42-117">Increase dispersion of important knowledge and information.</span></span> <span data-ttu-id="75a42-118">Los documentos y vínculos se pueden incluir en las conversaciones para que todo el equipo pueda acceder a ellos.</span><span class="sxs-lookup"><span data-stu-id="75a42-118">Documents and links can be included within conversations for access by all the team.</span></span> <span data-ttu-id="75a42-119">Al publicar preguntas en un equipo más amplio, los usuarios pueden beneficiarse de las respuestas de expertos en la materia.</span><span class="sxs-lookup"><span data-stu-id="75a42-119">By posting questions to a broader team, users can benefit from responses by subject matter experts.</span></span> <span data-ttu-id="75a42-120">La integración con otros sistemas de información permite comunicar fácilmente datos organizativos importantes a grupos grandes.</span><span class="sxs-lookup"><span data-stu-id="75a42-120">Integration with other information systems enables important organizational data to be easily communicated to large groups.</span></span>

<span data-ttu-id="75a42-121">Para habilitar los salones de chat en Lync Server 2013, implemente Lync Server 2013 chat persistente.</span><span class="sxs-lookup"><span data-stu-id="75a42-121">To enable chat rooms in Lync Server 2013, deploy Lync Server 2013 Persistent Chat.</span></span> <span data-ttu-id="75a42-122">Para obtener información sobre cómo habilitar salones de chat, consulte la ayuda <http://go.microsoft.com/fwlink/p/?linkid=270945>de chat persistente en.</span><span class="sxs-lookup"><span data-stu-id="75a42-122">For information about enabling chat rooms, see the Persistent Chat Help at <http://go.microsoft.com/fwlink/p/?linkid=270945>.</span></span> <span data-ttu-id="75a42-123">Si los usuarios están habilitados para Lync Server y la compatibilidad con Lync Server está implementada, los usuarios pueden instalar y usar Lync 2013 chat persistente para proporcionar compatibilidad con el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="75a42-123">If users are enabled for Lync Server, and Lync Server support is deployed, users can install and use Lync 2013 Persistent Chat to provide chat room support.</span></span>

<span data-ttu-id="75a42-124">Si es necesario que su organización siga las normas de cumplimiento, puede implementar el servicio de cumplimiento de chat persistente de manera opcional.</span><span class="sxs-lookup"><span data-stu-id="75a42-124">If your organization is required to follow compliance regulations, you can optionally deploy Persistent Chat Compliance service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

