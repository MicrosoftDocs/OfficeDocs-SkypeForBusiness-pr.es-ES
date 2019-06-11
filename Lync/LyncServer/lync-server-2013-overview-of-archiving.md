---
title: 'Lync Server 2013: Información general del archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Archiving
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204729(v=OCS.15)
ms:contentKeyID: 48183570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba4aa88f94f0e32b35ab3fc5f71359e5a1c00d99
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-archiving-in-lync-server-2013"></a><span data-ttu-id="a5a30-102">Información general del archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5a30-102">Overview of Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5a30-103">_**Última modificación del tema:** 2013-09-30_</span><span class="sxs-lookup"><span data-stu-id="a5a30-103">_**Topic Last Modified:** 2013-09-30_</span></span>

<span data-ttu-id="a5a30-104">El archivado en Lync Server 2013 le proporciona una forma de archivar las comunicaciones que se envían a través de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a5a30-104">Archiving in Lync Server 2013 provides a way for you to archive communications that are sent through Lync Server 2013.</span></span>

<span data-ttu-id="a5a30-105">Puede implementar el archivado como parte de la implementación inicial de Lync Server 2013, o bien puede agregarlo a una implementación existente.</span><span class="sxs-lookup"><span data-stu-id="a5a30-105">You can implement Archiving as part of your initial Lync Server 2013 deployment, or you can add it to an existing deployment.</span></span> <span data-ttu-id="a5a30-106">Para usar las bases de datos de archivado de Lync Server 2013 (bases de datos de SQL Server) para el almacenamiento de datos de archivado, use el generador de topología para agregar las bases de datos a la topología y, a continuación, vuelva a publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="a5a30-106">To use Lync Server 2013 Archiving databases (SQL Server databases) for storage of archiving data, you use Topology Builder to add the databases to your topology, and then publish the topology again.</span></span> <span data-ttu-id="a5a30-107">Si todos los usuarios están alojados en Exchange 2013 y sus buzones se colocan en conservación local, no tiene que actualizar su topología, pero solo necesita habilitar la integración de Microsoft Exchange para almacenar datos archivados en Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="a5a30-107">If all your users are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, you do not have to update your topology, but only need to enable Microsoft Exchange integration to store archived data in Exchange 2013.</span></span>

<span data-ttu-id="a5a30-108">Al implementar el archivado, se configura para especificar qué es el archivo.</span><span class="sxs-lookup"><span data-stu-id="a5a30-108">When you implement Archiving, you configure it to specify what is archived.</span></span> <span data-ttu-id="a5a30-109">De forma predeterminada, no se archiva nada.</span><span class="sxs-lookup"><span data-stu-id="a5a30-109">By default, nothing is archived.</span></span> <span data-ttu-id="a5a30-110">Configure y administre el archivado mediante el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a5a30-110">You configure and manage Archiving by using Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="a5a30-111">Puede implementar el archivado para comunicaciones internas, comunicaciones externas o ambas.</span><span class="sxs-lookup"><span data-stu-id="a5a30-111">You can implement Archiving for internal communications, external communications, or both.</span></span> <span data-ttu-id="a5a30-112">Puede configurar las opciones de archivado para toda la organización y, opcionalmente, para sitios específicos, agrupaciones específicas, y usuarios y grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="a5a30-112">You can configure archiving settings your entire organization and, optionally, for specific sites, specific pools, and specific users and user groups.</span></span> <span data-ttu-id="a5a30-113">Para obtener más información sobre cómo determinar las opciones adecuadas para su organización, vea [definir los requisitos para el archivado en Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="a5a30-113">For details about determining the appropriate options for your organization, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md) in the Planning documentation.</span></span> <span data-ttu-id="a5a30-114">Para obtener detalles sobre cómo se implementan las directivas y configuraciones de archivado, y detalles sobre qué información se puede archivar o no, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, la documentación de implementación o Documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="a5a30-114">For details about how Archiving policies and configurations are implemented, and details about what information can or cannot be archived, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

