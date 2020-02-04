---
title: 'Lync Server 2013: Nuevas características de archivado'
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
ms.openlocfilehash: 1509a0857b54673ab20783f69b34b59c6d2afde8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="e31b9-102">Nuevas características de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e31b9-102">New Archiving features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e31b9-103">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="e31b9-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="e31b9-104">El archivado en Lync Server 2013 puede archivar los siguientes tipos de contenido:</span><span class="sxs-lookup"><span data-stu-id="e31b9-104">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="e31b9-105">Mensajes instantáneos de punto a punto</span><span class="sxs-lookup"><span data-stu-id="e31b9-105">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="e31b9-106">Conferencias (reuniones) que son mensajes instantáneos de varios participantes</span><span class="sxs-lookup"><span data-stu-id="e31b9-106">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="e31b9-107">Contenido de conferencias, como contenido que se carga (por ejemplo, documentos de la reunión) y contenido relacionado con el evento (por ejemplo, los usuarios que se unen o abandonan el evento, la carga de recursos compartidos y los cambios en la visibilidad)</span><span class="sxs-lookup"><span data-stu-id="e31b9-107">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="e31b9-108">Además, el archivado en Lync Server 2013 ofrece nuevas características que mejoran la implementación y la eficacia de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="e31b9-108">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="e31b9-109">Estas nuevas características constan de:</span><span class="sxs-lookup"><span data-stu-id="e31b9-109">These new features consist of:</span></span>

  - <span data-ttu-id="e31b9-110">**Collocation de archivo en los servidores frontales.**    Lync Server 2013 no tiene un rol de servidor de archivado independiente.</span><span class="sxs-lookup"><span data-stu-id="e31b9-110">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="e31b9-111">El archivado es una característica opcional disponible en todos los servidores front-end de una implementación de Enterprise Edition, y en servidores Standard Edition, que se puede implementar en un grupo o sitio.</span><span class="sxs-lookup"><span data-stu-id="e31b9-111">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="e31b9-112">**Integración con Microsoft Exchange.**    Al implementar el archivado, puede integrar el almacenamiento de datos para archivar con el almacenamiento existente de Exchange 2013 para todos los usuarios alojados en Exchange 2013 y para que sus buzones se coloquen en la retención local, por lo que no es necesario implementar bases de datos de SQL Server independientes para archivar datos de Lync.</span><span class="sxs-lookup"><span data-stu-id="e31b9-112">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="e31b9-113">Si no tiene una implementación de Exchange 2013, o si prefiere no integrarlo, o si tiene algún usuario de Lync 2013 que no está alojado en Exchange 2013 y sus buzones se colocan en conservación local, puede implementar bases de datos de archivado independientes con SQL Server a Stor e datos archivados de Lync Communications.</span><span class="sxs-lookup"><span data-stu-id="e31b9-113">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="e31b9-114">Puede usar las bases de datos de integración de Microsoft Exchange y de archivo de Lync Server 2013 si desea usar la integración de Microsoft Exchange para algunos, pero no todos los usuarios de su implementación.</span><span class="sxs-lookup"><span data-stu-id="e31b9-114">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="e31b9-115">Para obtener más información sobre la conservación local, vea "conservación local" en [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).</span><span class="sxs-lookup"><span data-stu-id="e31b9-115">For details about In-Place Hold, see “In-Place Hold” at [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="e31b9-116">**Reflejo de la tienda SQL.**    Al implementar el archivado, puede habilitar la creación de reflejo de la base de datos de SQL Server para la base de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="e31b9-116">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="e31b9-117">**Archivo de pizarras y sondeos.**    El contenido de conferencia archivado ahora incluye pizarras y sondeos compartidos durante la reunión.</span><span class="sxs-lookup"><span data-stu-id="e31b9-117">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="e31b9-118">Los siguientes tipos de contenido no se archivan:</span><span class="sxs-lookup"><span data-stu-id="e31b9-118">The following types of content are not archived:</span></span>

  - <span data-ttu-id="e31b9-119">Transferencias de archivos de punto a punto</span><span class="sxs-lookup"><span data-stu-id="e31b9-119">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="e31b9-120">Audio o vídeo para conferencias y mensajes instantáneos de punto a punto</span><span class="sxs-lookup"><span data-stu-id="e31b9-120">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="e31b9-121">Uso compartido de aplicaciones para conferencias y mensajes instantáneos de punto a punto</span><span class="sxs-lookup"><span data-stu-id="e31b9-121">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e31b9-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e31b9-122">See Also</span></span>


[<span data-ttu-id="e31b9-123">Planificar el archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e31b9-123">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

