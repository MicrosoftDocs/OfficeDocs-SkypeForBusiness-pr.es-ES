---
title: Quitar los servidores de archivado y supervisión heredados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: bca6b419-d5bc-4a46-af42-1dd51b99a26b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205215(v=OCS.15)
ms:contentKeyID: 48185261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 816855b2661b8834264a2ff4b573ecbfe403d9b4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="5a69e-102">Quitar los servidores de archivado y supervisión heredados</span><span class="sxs-lookup"><span data-stu-id="5a69e-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a69e-103">_**Última modificación del tema:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="5a69e-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="5a69e-104">Si su implementación de Office Communications Server 2007 R2 contenía un servidor de archivado o un servidor de supervisión, después de migrar a Lync Server 2013, esos servidores se pueden quitar del entorno heredado siempre que todos los usuarios hayan eliminado de cualquier Grupos de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="5a69e-104">If your Office Communications Server 2007 R2 deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="5a69e-105">Puede quitar el servidor de archivado o el servidor de supervisión en cualquier secuencia.</span><span class="sxs-lookup"><span data-stu-id="5a69e-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="5a69e-106">El requisito fundamental es que todos los usuarios han sido eliminados de cualquier grupo de Office Communications Server 2007 R2 restante.</span><span class="sxs-lookup"><span data-stu-id="5a69e-106">The key requirement is that all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span>

<span data-ttu-id="5a69e-107">Puede mover usuarios de Office Communications Server 2007 R2 a Lync Server 2013 siguiendo los procedimientos descritos en la [fase 6: mover usuarios a la agrupación piloto](phase-6-move-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="5a69e-107">You can move users from Office Communications Server 2007 R2 to Lync Server 2013 by following the procedures outlined in [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="5a69e-108">Una vez que haya confirmado que todos los usuarios se han quitado de las agrupaciones restantes, siga el procedimiento de "quitar servidores y [http://go.microsoft.com/fwlink/p/?linkId=205887](http://go.microsoft.com/fwlink/p/?linkid=205887)roles de servidor" en.</span><span class="sxs-lookup"><span data-stu-id="5a69e-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Removing Servers and Server Roles" at [http://go.microsoft.com/fwlink/p/?linkId=205887](http://go.microsoft.com/fwlink/p/?linkid=205887).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

