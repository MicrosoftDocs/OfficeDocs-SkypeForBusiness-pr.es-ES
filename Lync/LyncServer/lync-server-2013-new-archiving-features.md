---
title: 'Lync Server 2013: nuevas características de archivado'
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
ms.openlocfilehash: 3e09284d78ead2e8cd4249c2dc54159284ddad43
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42127653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="21a53-102">Nuevas características de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21a53-102">New Archiving features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21a53-103">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="21a53-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="21a53-104">El archivado en Lync Server 2013 puede archivar los siguientes tipos de contenido:</span><span class="sxs-lookup"><span data-stu-id="21a53-104">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="21a53-105">Mensajes instantáneos de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="21a53-105">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="21a53-106">Conferencias (reuniones) que incluyen mensajes instantáneos de varios participantes.</span><span class="sxs-lookup"><span data-stu-id="21a53-106">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="21a53-107">Contenido de conferencias, incluido el contenido que se ha cargado (por ejemplo, documentos) y el contenido relacionado con los eventos (por ejemplo, usuarios que se unen o abandonan la conferencia, la carga de recursos compartidos y los cambios de visibilidad).</span><span class="sxs-lookup"><span data-stu-id="21a53-107">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="21a53-108">Además, el archivado en Lync Server 2013 proporciona nuevas características que mejoran la eficacia de la implementación y las operaciones.</span><span class="sxs-lookup"><span data-stu-id="21a53-108">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="21a53-109">Estas nuevas características son:</span><span class="sxs-lookup"><span data-stu-id="21a53-109">These new features consist of:</span></span>

  - <span data-ttu-id="21a53-110">**Combinación de archivado en los servidores front-end.**    Lync Server 2013 no tiene un rol de servidor de archivado independiente.</span><span class="sxs-lookup"><span data-stu-id="21a53-110">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="21a53-111">El archivado es una característica opcional disponible en todos los servidores front-end de una implementación Enterprise Edition y en servidores Standard Edition, que pueden implementarse configurados para un grupo o un sitio.</span><span class="sxs-lookup"><span data-stu-id="21a53-111">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="21a53-112">**Integración de Microsoft Exchange.**    Al implementar el archivado, puede integrar el almacenamiento de datos para archivado con el almacenamiento de Exchange 2013 existente para todos los usuarios hospedados en Exchange 2013 y cuyos buzones se colocan en conservación local, por lo que no es necesario implementar bases de datos de SQL Server independientes para archivar datos de Lync.</span><span class="sxs-lookup"><span data-stu-id="21a53-112">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="21a53-113">Si no dispone de una implementación de Exchange 2013, o si prefiere no integrarlo, o si tiene algún usuario de Lync 2013 que no esté hospedado en Exchange 2013 con sus buzones en conservación local, puede implementar bases de datos de archivado independientes mediante SQL Server para Stor e datos archivados desde comunicaciones de Lync.</span><span class="sxs-lookup"><span data-stu-id="21a53-113">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="21a53-114">Puede usar las bases de datos de archivado de Microsoft Exchange Integration y Lync Server 2013 si desea usar la integración de Microsoft Exchange para algunos, pero no para todos los usuarios de la implementación.</span><span class="sxs-lookup"><span data-stu-id="21a53-114">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="21a53-115">Para obtener más información sobre la conservación local, vea "conservación local" en [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500).</span><span class="sxs-lookup"><span data-stu-id="21a53-115">For details about In-Place Hold, see “In-Place Hold” at [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="21a53-116">**Creación de reflejo del almacén de SQL.**    Al implementar el archivado, puede habilitar la creación de reflejo de la base de datos de SQL Server para la base de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="21a53-116">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="21a53-117">**Archivado de pizarras y sondeos.**    El contenido de conferencia archivado ahora incluye pizarras y sondeos compartidos durante la reunión.</span><span class="sxs-lookup"><span data-stu-id="21a53-117">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="21a53-118">No se archivan los tipos de contenido siguientes:</span><span class="sxs-lookup"><span data-stu-id="21a53-118">The following types of content are not archived:</span></span>

  - <span data-ttu-id="21a53-119">Transferencias de archivos de punto a punto</span><span class="sxs-lookup"><span data-stu-id="21a53-119">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="21a53-120">Audio y vídeo para conferencias y mensajes instantáneos de punto a punto</span><span class="sxs-lookup"><span data-stu-id="21a53-120">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="21a53-121">Uso compartido de aplicaciones para conferencias y mensajes instantáneos de punto a punto</span><span class="sxs-lookup"><span data-stu-id="21a53-121">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="21a53-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="21a53-122">See Also</span></span>


[<span data-ttu-id="21a53-123">Planeación del archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21a53-123">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

