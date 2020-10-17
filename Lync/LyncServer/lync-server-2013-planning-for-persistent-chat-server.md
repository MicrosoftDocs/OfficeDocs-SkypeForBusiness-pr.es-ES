---
title: 'Lync Server 2013: Planeación del servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Persistent Chat Server
ms:assetid: 57b2f574-234e-4a5a-bb78-8823369ba79e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398381(v=OCS.15)
ms:contentKeyID: 48184190
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37208a366ae1cac70733113d6b15605886f34e97
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521967"
---
# <a name="planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="f8960-102">Planeación del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8960-102">Planning for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8960-103">_**Última modificación del tema:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="f8960-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="f8960-104">Puede usar Lync Server 2013, el servidor de chat persistente para permitir que varios usuarios participen en conversaciones en las que publican y tienen acceso al contenido sobre temas específicos, incluidos texto, vínculos y archivos.</span><span class="sxs-lookup"><span data-stu-id="f8960-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="f8960-105">Aunque todos los usuarios se pueden comunicar en tiempo real durante una sesión, el contenido de cada sesión puede ser persistente, lo que significa que sigue disponible después de que finalice una sesión.</span><span class="sxs-lookup"><span data-stu-id="f8960-105">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>

<span data-ttu-id="f8960-106">En esta sección se describen las consideraciones de planeación en una implementación de Lync Server 2013, servidor de chat persistente, lo que incluye la definición de requisitos, la identificación de componentes y las topologías admitidas, y las recomendaciones de implementación.</span><span class="sxs-lookup"><span data-stu-id="f8960-106">This section describes planning considerations in a Lync Server 2013, Persistent Chat Server deployment, including defining requirements, identifying components and supported topologies, and deployment recommendations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f8960-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f8960-107">In This Section</span></span>

  - [<span data-ttu-id="f8960-108">Información general sobre el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8960-108">Overview of Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-overview-of-persistent-chat-server.md)

  - [<span data-ttu-id="f8960-109">Cómo funciona el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8960-109">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="f8960-110">Definición de los requisitos de la organización para el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8960-110">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="f8960-111">Componentes y topologías para el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8960-111">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-persistent-chat-server.md)

  - [<span data-ttu-id="f8960-112">Requisitos técnicos para el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8960-112">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="f8960-113">Configurar los sistemas y la infraestructura para el servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8960-113">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="f8960-114">Lista de comprobación para la implementación del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8960-114">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

