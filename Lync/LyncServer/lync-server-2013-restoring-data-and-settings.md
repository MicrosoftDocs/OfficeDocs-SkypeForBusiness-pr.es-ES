---
title: 'Lync Server 2013: restauración de datos y configuración'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring data and settings
ms:assetid: b07f5dd7-7bed-4819-8cb5-617f5acd478e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202185(v=OCS.15)
ms:contentKeyID: 51541503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5b8575ee1362b240df0bfc0a1a1a6b27afde268
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="6eb4e-102">Restauración de datos y configuración en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb4e-102">Restoring data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6eb4e-103">_**Última modificación del tema:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="6eb4e-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="6eb4e-104">Si ha implementado una topología de recuperación ante desastres con grupos emparejados y uno de estos grupos de servidores front-end ha dejado de funcionar y necesita restaurar rápidamente el servicio para los usuarios, consulte [Failing over a Pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="6eb4e-104">If you have implemented a disaster recovery topology with paired pools, and one of those Front End pools has gone down and you need to quickly restore service to your users, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="6eb4e-105">De lo contrario, use la información de los temas siguientes, junto con las hojas de [cálculo de copias de seguridad y restauración de Lync server 2013](lync-server-2013-backup-and-restoration-worksheets.md), para restaurar Lync Server después de un error o una interrupción.</span><span class="sxs-lookup"><span data-stu-id="6eb4e-105">Otherwise, use the information in the following topics, along with the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md), to restore Lync Server after a failure or outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6eb4e-106">Para reducir el tiempo de inactividad y la pérdida potencial de datos, realice los procedimientos de restauración descritos en este documento sólo si los procedimientos de solución de problemas no son eficaces para identificar y corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="6eb4e-106">To reduce downtime and potential data loss, perform the restoration procedures described in this document only if troubleshooting procedures are not effective in identifying and correcting the problem.</span></span> <span data-ttu-id="6eb4e-107">Durante la solución de problemas, intente minimizar el impacto en otros servidores y componentes mientras apaga y reinicia los servidores.</span><span class="sxs-lookup"><span data-stu-id="6eb4e-107">During troubleshooting, try to minimize the impact on other servers and components as you shut down and restart servers.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6eb4e-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6eb4e-108">In This Section</span></span>

  - [<span data-ttu-id="6eb4e-109">Preparación de la restauración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb4e-109">Preparing to restore Lync Server 2013</span></span>](lync-server-2013-preparing-to-restore-lync-server.md)

  - [<span data-ttu-id="6eb4e-110">Restaurar un servidor Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb4e-110">Restoring a Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-restoring-a-standard-edition-server.md)

  - [<span data-ttu-id="6eb4e-111">Restauración del servidor que hospeda el almacén de administración central en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb4e-111">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)

  - [<span data-ttu-id="6eb4e-112">Restauración de un servidor back-end de Enterprise Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb4e-112">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)

  - [<span data-ttu-id="6eb4e-113">Restauración de un servidor miembro de Enterprise Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb4e-113">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

  - [<span data-ttu-id="6eb4e-114">Restauración de un grupo de servidores de Lync Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb4e-114">Restoring a Lync Server pool in Lync Server 2013</span></span>](lync-server-2013-restoring-a-lync-server-pool.md)

  - [<span data-ttu-id="6eb4e-115">Realizar la conmutación por error de un grupo de servidores front-end ABC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb4e-115">Performing an ABC Front End pool failover in Lync Server 2013</span></span>](lync-server-2013-performing-an-abc-front-end-pool-failover.md)

  - [<span data-ttu-id="6eb4e-116">Restaurar un almacén de archivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb4e-116">Restoring a file store in Lync Server 2013</span></span>](lync-server-2013-restoring-a-file-store.md)

  - [<span data-ttu-id="6eb4e-117">Restauración de datos de supervisión o archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb4e-117">Restoring monitoring or archiving data in Lync Server 2013</span></span>](lync-server-2013-restoring-monitoring-or-archiving-data.md)

  - [<span data-ttu-id="6eb4e-118">Restauración de datos de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6eb4e-118">Restoring Persistent Chat data in Lync Server 2013</span></span>](lync-server-2013-restoring-persistent-chat-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

