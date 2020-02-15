---
title: 'Lync Server 2013: Windows Update para Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows Update for Lync Server 2013
ms:assetid: fe26ab32-b1a9-421d-9227-506703d4b834
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518337(v=OCS.15)
ms:contentKeyID: 62625495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e70ac17e27508a7922d8353e6142b3b5f05b34e9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-update-for-lync-server-2013"></a><span data-ttu-id="75b10-102">Windows Update para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75b10-102">Windows Update for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75b10-103">_**Última modificación del tema:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="75b10-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="75b10-104">Utilice el servicio Windows Update para comprobar con frecuencia si hay actualizaciones y actualizaciones de seguridad y aplicarlas.</span><span class="sxs-lookup"><span data-stu-id="75b10-104">Frequently check for and apply updates and security updates using Windows Update Services.</span></span> <span data-ttu-id="75b10-105">De este modo, se evitan las vulnerabilidades de otros componentes del sistema que puedan provocar que los atacantes puedan obtener acceso a los servidores que ejecutan Microsoft Lync Server 2013 con derechos de administrador y, por lo tanto, poner en peligro Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75b10-105">Doing so helps prevents vulnerabilities in other system components that might lead to attackers being able to gain access to servers running Microsoft Lync Server 2013 with administrator rights and thereby compromise Lync Server 2013.</span></span>

<span data-ttu-id="75b10-106">Las actualizaciones de Microsoft SQL Server 2008 Express (edición de 64 bits) se ejecutan en cada servidor de Lync Server 2013 Standard Edition (para la base de datos back-end) y en todos los demás roles de servidor de Lync Server 2013 (para el almacén de configuración local), a menos que haya actualizado estos bases de datos a SQL Server 2008 R2 Express.</span><span class="sxs-lookup"><span data-stu-id="75b10-106">Updates for Microsoft SQL Server 2008 Express (64-bit edition) runs on each Lync Server 2013 Standard Edition server (for the back-end database) and on all other Lync Server 2013 server roles (for the Local Configuration Store), unless you have upgraded these databases to SQL Server 2008 R2 Express.</span></span> <span data-ttu-id="75b10-107">Debe considerar estas bases de datos como parte del mantenimiento rutinario de las actualizaciones de seguridad, al igual que SQL Server en la base de datos back-end de un grupo de servidores front-end, la base de datos de supervisión y la base de datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="75b10-107">You should consider these databases as part of routine security update maintenance, as should SQL Server on the back-end database of a Front End pool, the Monitoring database, and the Archiving database.</span></span>

<div>

## <a name="best-practice"></a><span data-ttu-id="75b10-108">Procedimiento recomendado</span><span class="sxs-lookup"><span data-stu-id="75b10-108">Best Practice</span></span>

  - <span data-ttu-id="75b10-109">Mantenga el equipo actualizado a través del servicio Windows Update.</span><span class="sxs-lookup"><span data-stu-id="75b10-109">Keep current with Windows Update.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

