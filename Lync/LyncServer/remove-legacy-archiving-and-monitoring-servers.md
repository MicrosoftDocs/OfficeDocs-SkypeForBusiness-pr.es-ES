---
title: Quitar los servidores de archivado y supervisión heredados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: befa586b-615c-496e-996e-395a6e36a826
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205221(v=OCS.15)
ms:contentKeyID: 48185278
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31f9d3419d9fc46cc4b547c645fa9f938f4a2a23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="67105-102">Quitar los servidores de archivado y supervisión heredados</span><span class="sxs-lookup"><span data-stu-id="67105-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67105-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="67105-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="67105-104">Si la implementación heredada contenía un servidor de archivado o un servidor de supervisión, después de migrar a Lync Server 2013, esos servidores se pueden quitar del entorno heredado siempre que todos los usuarios hayan sido eliminados de cualquier grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="67105-104">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="67105-105">Puede quitar el servidor de archivado o el servidor de supervisión en cualquier secuencia.</span><span class="sxs-lookup"><span data-stu-id="67105-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="67105-106">El requisito clave es que se han quitado todos los usuarios de cualquier grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="67105-106">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>

<span data-ttu-id="67105-107">Puede mover usuarios de Lync Server 2010 a Lync Server 2013 siguiendo los procedimientos descritos en la [fase 4: mover usuarios de prueba a la agrupación piloto](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="67105-107">You can move users from Lync Server 2010 to Lync Server 2013 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="67105-108">Una vez que haya confirmado que todos los usuarios se han quitado del grupo restante, siga el procedimiento de "desinstalar Microsoft Lync Server 2010 y quitar roles de servidor", que se puede [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)descargar en.</span><span class="sxs-lookup"><span data-stu-id="67105-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

