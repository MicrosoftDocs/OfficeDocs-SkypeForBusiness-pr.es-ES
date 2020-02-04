---
title: Administrar el servidor de chat persistente de Lync Server 2013
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
ms.openlocfilehash: 067e24a7e1534e355e39f80b6a3fda90e059be14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-persistent-chat-server"></a><span data-ttu-id="cde1c-102">Administrar el servidor de chat persistente de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cde1c-102">Managing Lync Server 2013, Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cde1c-103">_**Última modificación del tema:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="cde1c-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="cde1c-104">Puede usar Lync Server 2013, servidor de chat persistente para permitir que varios usuarios participen en las conversaciones en las que publican y tienen acceso al contenido sobre temas específicos, como texto, vínculos y archivos.</span><span class="sxs-lookup"><span data-stu-id="cde1c-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="cde1c-105">Aunque los usuarios se pueden comunicar en tiempo real durante una sesión, el contenido de cada sesión es persistente, lo que significa que sigue estando disponible después de que finalice la sesión.</span><span class="sxs-lookup"><span data-stu-id="cde1c-105">Although users can communicate in real time during a session, the content of each session is persistent, which means that it continues to be available after a session ends.</span></span>

<span data-ttu-id="cde1c-106">El contenido de los salones de chat persistente consta principalmente de mensajes de texto breves, aunque puede incluir mensajes más largos, como *historias*, además de hipervínculos, emoticonos y documentos cargados.</span><span class="sxs-lookup"><span data-stu-id="cde1c-106">The content of Persistent Chat rooms consists primarily of short text messages, although it can include longer messages, referred to as *stories*, and also hyperlinks, emoticons, and uploaded documents.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cde1c-107">El cliente de Lync 2013 no admite la carga y descarga de archivos; sin embargo, sigue siendo compatible con Lync Server 2013, el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="cde1c-107">File upload and download is not supported by the Lync 2013 client; however, it is still supported by Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="cde1c-108">El cliente de conversación de grupo heredado puede publicar y ver archivos, pero si se obtiene acceso al mismo salón de chat a través del cliente de Lync 2013, no podrá acceder a los archivos.</span><span class="sxs-lookup"><span data-stu-id="cde1c-108">The legacy Group Chat client can post and view files, but if the same chat room is accessed via the Lync 2013 client, it will not be able to access the files.</span></span>



</div>

<span data-ttu-id="cde1c-109">El acceso a un salón de chat está controlado por una lista de miembros.</span><span class="sxs-lookup"><span data-stu-id="cde1c-109">Access to a chat room is controlled by a membership list.</span></span> <span data-ttu-id="cde1c-110">El historial completo de los salones de chat está disponible para todos los miembros de la revisión cronológica o la búsqueda de texto completo.</span><span class="sxs-lookup"><span data-stu-id="cde1c-110">The entire chat room history is available to any member for chronological review or full-text search.</span></span> <span data-ttu-id="cde1c-111">Para obtener más información sobre cómo usar el cliente de chat persistente, consulte [planificación de clientes en Lync server 2013](lync-server-2013-planning-for-clients.md) en la documentación de planeación e [implementación de clientes y dispositivos en Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="cde1c-111">For details about using the Persistent Chat client, see [Planning for clients in Lync Server 2013](lync-server-2013-planning-for-clients.md) in the Planning documentation, and [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

<span data-ttu-id="cde1c-112">Al configurar un servidor de chat persistente para su organización, debe especificar la configuración inicial durante la implementación.</span><span class="sxs-lookup"><span data-stu-id="cde1c-112">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="cde1c-113">Sin embargo, puede haber ocasiones en las que desee cambiar el modo en que se implementa la compatibilidad con el servidor de chat.</span><span class="sxs-lookup"><span data-stu-id="cde1c-113">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="cde1c-114">Por ejemplo, es posible que tenga que configurar la compatibilidad del servidor de chat persistente y los controles de forma diferente para un equipo o grupo específico de su organización.</span><span class="sxs-lookup"><span data-stu-id="cde1c-114">For example, you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="cde1c-115">Esta sección proporciona información y procedimientos para ayudarle a personalizar la implementación del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="cde1c-115">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="cde1c-116">Para obtener detalles sobre las características y funcionalidades que puede configurar para el servidor de chat persistente, vea [definir los requisitos de su organización para el servidor de chat persistente en Lync server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) en la documentación de planeación y [Cómo funciona el servidor de chat persistente en Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) en la documentación de planeación, la documentación de implementación o la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="cde1c-116">For details about the features and functionality that you can configure for Persistent Chat Server, see [Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in the Planning documentation, and [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="cde1c-117">Para obtener más información sobre cómo implementar el servidor de chat persistente para Lync Server 2013, vea [implementar un servidor de chat persistente en Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="cde1c-117">For details about deploying Persistent Chat Server for Lync Server 2013, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cde1c-118">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cde1c-118">In This Section</span></span>

  - [<span data-ttu-id="cde1c-119">Cómo funciona el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cde1c-119">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="cde1c-120">Usar categorías para administrar el servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="cde1c-120">Using categories to administer Persistent Chat Server</span></span>](using-categories-to-administer-persistent-chat-server.md)

  - [<span data-ttu-id="cde1c-121">Comprender la pertenencia a un chat persistente</span><span class="sxs-lookup"><span data-stu-id="cde1c-121">Understanding Persistent Chat membership</span></span>](understanding-persistent-chat-membership.md)

  - [<span data-ttu-id="cde1c-122">Procedimientos recomendados para el servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="cde1c-122">Persistent Chat Server best practices</span></span>](persistent-chat-server-best-practices.md)

  - [<span data-ttu-id="cde1c-123">Administrar categorías, salones de chat y complementos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cde1c-123">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [<span data-ttu-id="cde1c-124">Administración del acceso de usuarios de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cde1c-124">Managing Persistent Chat user access in Lync Server 2013</span></span>](lync-server-2013-managing-persistent-chat-user-access.md)

  - [<span data-ttu-id="cde1c-125">Usar y llevar el mantenimiento del sistema de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cde1c-125">Operating and maintaining the Persistent Chat system in Lync Server 2013</span></span>](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

