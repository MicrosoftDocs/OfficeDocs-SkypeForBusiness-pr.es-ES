---
title: Quitar los servidores de archivado y supervisión heredados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: befa586b-615c-496e-996e-395a6e36a826
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205221(v=OCS.15)
ms:contentKeyID: 48185278
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0447305ce1ed5486c6b8d83ae99d905ea1e74362
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="2fd06-102">Quitar los servidores de archivado y supervisión heredados</span><span class="sxs-lookup"><span data-stu-id="2fd06-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fd06-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="2fd06-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="2fd06-104">Si la implementación heredada contenía un servidor de archivado o un servidor de supervisión, después de migrar a Lync Server 2013, estos servidores pueden quitarse del entorno heredado siempre que todos los usuarios se hayan quitado de los grupos de servidores heredados restantes.</span><span class="sxs-lookup"><span data-stu-id="2fd06-104">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="2fd06-105">Puede quitar el servidor de archivado o de supervisión en cualquier secuencia.</span><span class="sxs-lookup"><span data-stu-id="2fd06-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="2fd06-106">El requisito clave es quitar a todos los usuarios de todos los grupos de servidores heredados restantes.</span><span class="sxs-lookup"><span data-stu-id="2fd06-106">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>

<span data-ttu-id="2fd06-107">Puede mover usuarios de Lync Server 2010 a Lync Server 2013 siguiendo los procedimientos descritos en la [fase 4: mover usuarios de prueba al grupo piloto](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="2fd06-107">You can move users from Lync Server 2010 to Lync Server 2013 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="2fd06-108">Una vez que haya confirmado que todos los usuarios se han quitado de los grupos restantes, siga el procedimiento descrito en "desinstalar Microsoft Lync Server 2010 y quitar roles de servidor", que [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)se pueden descargar en.</span><span class="sxs-lookup"><span data-stu-id="2fd06-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

