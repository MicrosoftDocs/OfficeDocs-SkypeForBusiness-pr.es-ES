---
title: Administración del servidor de chat persistente de Lync Server 2013
description: Administración de Lync Server 2013, servidor de chat persistente.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server 2013, Persistent Chat Server
ms:assetid: 82befdc6-5d32-45f1-bfd7-aaedffed1ab8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398657(v=OCS.15)
ms:contentKeyID: 48184672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe5306c79c738d61b70c3dd079fb55650e6fdae9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544586"
---
# <a name="managing-lync-server-2013-persistent-chat-server"></a><span data-ttu-id="942a8-103">Administración del servidor de chat persistente de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="942a8-103">Managing Lync Server 2013, Persistent Chat Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="942a8-104">_**Última modificación del tema:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="942a8-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="942a8-105">Puede usar Lync Server 2013, el servidor de chat persistente para permitir que varios usuarios participen en conversaciones en las que publican y tienen acceso al contenido sobre temas específicos, incluidos texto, vínculos y archivos.</span><span class="sxs-lookup"><span data-stu-id="942a8-105">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="942a8-106">Aunque todos los usuarios se pueden comunicar en tiempo real durante una sesión, el contenido de cada sesión perdura, lo que significa que sigue disponible después de que finalice una sesión.</span><span class="sxs-lookup"><span data-stu-id="942a8-106">Although users can communicate in real time during a session, the content of each session is persistent, which means that it continues to be available after a session ends.</span></span>

<span data-ttu-id="942a8-107">El contenido de los salones de chat persistente consta principalmente de mensajes de texto breves, aunque puede incluir mensajes más largos, a los que se hace referencia como *historias*, además de hipervínculos, emoticones y documentos cargados.</span><span class="sxs-lookup"><span data-stu-id="942a8-107">The content of Persistent Chat rooms consists primarily of short text messages, although it can include longer messages, referred to as *stories*, and also hyperlinks, emoticons, and uploaded documents.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="942a8-108">El cliente de Lync 2013 no admite la carga y descarga de archivos; sin embargo, sigue siendo compatible con Lync Server 2013, el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="942a8-108">File upload and download is not supported by the Lync 2013 client; however, it is still supported by Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="942a8-109">El cliente de chat de grupo heredado puede enviar y ver archivos, pero si se obtiene acceso al mismo salón de chat a través del cliente de Lync 2013, no podrá obtener acceso a los archivos.</span><span class="sxs-lookup"><span data-stu-id="942a8-109">The legacy Group Chat client can post and view files, but if the same chat room is accessed via the Lync 2013 client, it will not be able to access the files.</span></span>



</div>

<span data-ttu-id="942a8-110">El acceso a estos salones de chat se controla a través de una lista de pertenencia.</span><span class="sxs-lookup"><span data-stu-id="942a8-110">Access to a chat room is controlled by a membership list.</span></span> <span data-ttu-id="942a8-111">Cualquier miembro de esta lista puede obtener acceso al historial completo del salón de chat para repasarlo cronológicamente o realizar búsquedas de texto completo.</span><span class="sxs-lookup"><span data-stu-id="942a8-111">The entire chat room history is available to any member for chronological review or full-text search.</span></span> <span data-ttu-id="942a8-112">Para obtener información detallada sobre cómo usar el cliente de chat persistente, vea [Planning for clients in Lync server 2013](lync-server-2013-planning-for-clients.md) en la documentación referente a la planeación y [Deploying clients and Devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="942a8-112">For details about using the Persistent Chat client, see [Planning for clients in Lync Server 2013](lync-server-2013-planning-for-clients.md) in the Planning documentation, and [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

<span data-ttu-id="942a8-113">Cuando se configura el servidor de chat persistente para la organización, se especifica la configuración inicial durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="942a8-113">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="942a8-114">Sin embargo, puede que en ocasiones desee cambiar la forma en que se implementa la compatibilidad con el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="942a8-114">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="942a8-115">Por ejemplo, es posible que tenga que configurar la compatibilidad del servidor de chat persistente y los controles de manera diferente para un equipo o grupo específico dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="942a8-115">For example, you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="942a8-116">En esta sección se proporciona información y procedimientos para ayudarle a personalizar la implementación del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="942a8-116">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="942a8-117">Para obtener más información sobre las características y funciones que se pueden configurar para el servidor de chat persistente, vea [definir los requisitos de la organización para el servidor de chat persistente en Lync server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) en la documentación referente a la planeación y [Cómo funciona el servidor de chat persistente en Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) en la documentación de planeación, la documentación de implementación o las operaciones.</span><span class="sxs-lookup"><span data-stu-id="942a8-117">For details about the features and functionality that you can configure for Persistent Chat Server, see [Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in the Planning documentation, and [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="942a8-118">Para más detalles sobre la implementación del servidor de chat persistente para Lync Server 2013, consulte [Deploying persistent chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="942a8-118">For details about deploying Persistent Chat Server for Lync Server 2013, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="942a8-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="942a8-119">In This Section</span></span>

  - [<span data-ttu-id="942a8-120">Cómo funciona el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="942a8-120">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="942a8-121">Uso de categorías para administrar el servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="942a8-121">Using categories to administer Persistent Chat Server</span></span>](using-categories-to-administer-persistent-chat-server.md)

  - [<span data-ttu-id="942a8-122">Descripción de la pertenencia al chat persistente</span><span class="sxs-lookup"><span data-stu-id="942a8-122">Understanding Persistent Chat membership</span></span>](understanding-persistent-chat-membership.md)

  - [<span data-ttu-id="942a8-123">Procedimientos recomendados del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="942a8-123">Persistent Chat Server best practices</span></span>](persistent-chat-server-best-practices.md)

  - [<span data-ttu-id="942a8-124">Administrar categorías, salones y complementos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="942a8-124">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [<span data-ttu-id="942a8-125">Administración del acceso de usuarios de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="942a8-125">Managing Persistent Chat user access in Lync Server 2013</span></span>](lync-server-2013-managing-persistent-chat-user-access.md)

  - [<span data-ttu-id="942a8-126">Funcionamiento y mantenimiento del sistema de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="942a8-126">Operating and maintaining the Persistent Chat system in Lync Server 2013</span></span>](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

