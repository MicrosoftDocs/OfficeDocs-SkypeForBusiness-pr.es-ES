---
title: 'Lync Server 2013: información general sobre el archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Archiving
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204729(v=OCS.15)
ms:contentKeyID: 48183570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe615b0bf434b0c87a452a35528aa565c85fe5d0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-archiving-in-lync-server-2013"></a><span data-ttu-id="c900b-102">Información general sobre el archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c900b-102">Overview of Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c900b-103">_**Última modificación del tema:** 2013-09-30_</span><span class="sxs-lookup"><span data-stu-id="c900b-103">_**Topic Last Modified:** 2013-09-30_</span></span>

<span data-ttu-id="c900b-104">El archivado en Lync Server 2013 proporciona una forma de archivar las comunicaciones que se envían a través de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c900b-104">Archiving in Lync Server 2013 provides a way for you to archive communications that are sent through Lync Server 2013.</span></span>

<span data-ttu-id="c900b-105">Puede implementar el archivado como parte de la implementación inicial de Lync Server 2013 o puede agregarlo a una implementación existente.</span><span class="sxs-lookup"><span data-stu-id="c900b-105">You can implement Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="c900b-106">Para usar las bases de datos de archivado de Lync Server 2013 (bases de datos de SQL Server) para el almacenamiento de datos de archivado, use el generador de topologías para agregar las bases de datos a la topología y, a continuación, vuelva a publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="c900b-106">To use Lync Server 2013 Archiving databases (SQL Server databases) for storage of archiving data, you use Topology Builder to add the databases to your topology, and then publish the topology again.</span></span> <span data-ttu-id="c900b-107">Si todos los usuarios están hospedados en Exchange 2013 y tienen sus buzones en conservación local, no es necesario actualizar la topología, pero solo es necesario habilitar la integración de Microsoft Exchange para almacenar datos archivados en Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="c900b-107">If all your users are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, you do not have to update your topology, but only need to enable Microsoft Exchange integration to store archived data in Exchange 2013.</span></span>

<span data-ttu-id="c900b-108">Al implementar el archivado, debe configurarlo para especificar qué se debe archivar.</span><span class="sxs-lookup"><span data-stu-id="c900b-108">When you implement Archiving, you configure it to specify what is archived.</span></span> <span data-ttu-id="c900b-109">De manera predeterminada, nada se archiva.</span><span class="sxs-lookup"><span data-stu-id="c900b-109">By default, nothing is archived.</span></span> <span data-ttu-id="c900b-110">Puede configurar y administrar el archivado mediante el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c900b-110">You configure and manage Archiving by using Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="c900b-111">Puede implementar el archivado para las comunicaciones internas, las comunicaciones externas o ambas.</span><span class="sxs-lookup"><span data-stu-id="c900b-111">You can implement Archiving for internal communications, external communications, or both.</span></span> <span data-ttu-id="c900b-112">Puede configurar las opciones de archivado para la organización completa y, de manera opcional, para sitios específicos, grupos de servidores específicos y usuarios y grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="c900b-112">You can configure archiving settings your entire organization and, optionally, for specific sites, specific pools, and specific users and user groups.</span></span> <span data-ttu-id="c900b-113">Para obtener información detallada sobre cómo determinar las opciones adecuadas para su organización, consulte definición de los [requisitos para el archivado en Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="c900b-113">For details about determining the appropriate options for your organization, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="c900b-114">Para obtener más información sobre cómo se implementan las directivas de archivado y las configuraciones, y sobre qué información se puede archivar o no, vea [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre Planeación, la documentación sobre la implementación o las operaciones.</span><span class="sxs-lookup"><span data-stu-id="c900b-114">For details about how Archiving policies and configurations are implemented, and details about what information can or cannot be archived, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

