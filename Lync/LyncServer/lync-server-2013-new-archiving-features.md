---
title: 'Lync Server 2013: nuevas características de archivado'
description: 'Lync Server 2013: nuevas características de archivado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5b69c90e62914284f178ae328375c6e350f5b3e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561356"
---
# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="b67f6-103">Nuevas características de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b67f6-103">New Archiving features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b67f6-104">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="b67f6-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="b67f6-105">El archivado en Lync Server 2013 puede archivar los siguientes tipos de contenido:</span><span class="sxs-lookup"><span data-stu-id="b67f6-105">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="b67f6-106">Mensajes instantáneos de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="b67f6-106">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="b67f6-107">Conferencias (reuniones) que incluyen mensajes instantáneos de varios participantes.</span><span class="sxs-lookup"><span data-stu-id="b67f6-107">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="b67f6-108">Contenido de conferencias, incluido el contenido que se ha cargado (por ejemplo, documentos) y el contenido relacionado con los eventos (por ejemplo, usuarios que se unen o abandonan la conferencia, la carga de recursos compartidos y los cambios de visibilidad).</span><span class="sxs-lookup"><span data-stu-id="b67f6-108">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="b67f6-109">Además, el archivado en Lync Server 2013 proporciona nuevas características que mejoran la eficacia de la implementación y las operaciones.</span><span class="sxs-lookup"><span data-stu-id="b67f6-109">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="b67f6-110">Estas nuevas características son:</span><span class="sxs-lookup"><span data-stu-id="b67f6-110">These new features consist of:</span></span>

  - <span data-ttu-id="b67f6-111">**Combinación de archivado en los servidores front-end.**     Lync Server 2013 no tiene un rol de servidor de archivado independiente.</span><span class="sxs-lookup"><span data-stu-id="b67f6-111">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="b67f6-112">El archivado es una característica opcional disponible en todos los servidores front-end de una implementación Enterprise Edition y en servidores Standard Edition, que pueden implementarse configurados para un grupo o un sitio.</span><span class="sxs-lookup"><span data-stu-id="b67f6-112">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="b67f6-113">**Integración de Microsoft Exchange.**     Al implementar el archivado, puede integrar el almacenamiento de datos para archivado con el almacenamiento de Exchange 2013 existente para todos los usuarios hospedados en Exchange 2013 y que sus buzones se colocan en In-Place, por lo que no es necesario que implemente bases de datos de SQL Server independientes para archivar datos de Lync.</span><span class="sxs-lookup"><span data-stu-id="b67f6-113">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="b67f6-114">Si no dispone de una implementación de Exchange 2013, o si prefiere no integrarlo, o si tiene algún usuario de Lync 2013 que no esté hospedado en Exchange 2013 con sus buzones de correo que se encuentran en retención de In-Place, puede implementar bases de datos de archivado independientes mediante SQL Server para almacenar datos archivados desde comunicaciones de Lync.</span><span class="sxs-lookup"><span data-stu-id="b67f6-114">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="b67f6-115">Puede usar las bases de datos de archivado de Microsoft Exchange Integration y Lync Server 2013 si desea usar la integración de Microsoft Exchange para algunos, pero no para todos los usuarios de la implementación.</span><span class="sxs-lookup"><span data-stu-id="b67f6-115">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="b67f6-116">Para obtener más información sobre la retención de In-Place, consulte "conservación local" en [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500) .</span><span class="sxs-lookup"><span data-stu-id="b67f6-116">For details about In-Place Hold, see “In-Place Hold” at [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="b67f6-117">**Creación de reflejo del almacén de SQL.**     Al implementar el archivado, puede habilitar la creación de reflejo de la base de datos de SQL Server para la base de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="b67f6-117">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="b67f6-118">**Archivado de pizarras y sondeos.**     El contenido de conferencia archivado ahora incluye pizarras y sondeos compartidos durante la reunión.</span><span class="sxs-lookup"><span data-stu-id="b67f6-118">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="b67f6-119">No se archivan los tipos de contenido siguientes:</span><span class="sxs-lookup"><span data-stu-id="b67f6-119">The following types of content are not archived:</span></span>

  - <span data-ttu-id="b67f6-120">Transferencias de archivos de punto a punto</span><span class="sxs-lookup"><span data-stu-id="b67f6-120">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="b67f6-121">Audio y vídeo para conferencias y mensajes instantáneos de punto a punto</span><span class="sxs-lookup"><span data-stu-id="b67f6-121">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="b67f6-122">Uso compartido de aplicaciones para conferencias y mensajes instantáneos de punto a punto</span><span class="sxs-lookup"><span data-stu-id="b67f6-122">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b67f6-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b67f6-123">See Also</span></span>


[<span data-ttu-id="b67f6-124">Planeación del archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b67f6-124">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

