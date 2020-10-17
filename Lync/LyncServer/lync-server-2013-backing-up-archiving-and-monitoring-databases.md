---
title: 'Lync Server 2013: copia de seguridad de las bases de datos de archivado y supervisión'
description: 'Lync Server 2013: copia de seguridad de las bases de datos de archivado y supervisión.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Archiving and Monitoring databases
ms:assetid: c120db81-b02c-4a4c-90cd-8aca6cff64f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202188(v=OCS.15)
ms:contentKeyID: 51541515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49b4fa194bffa27a52f32d61a729eeaa31cc0ad3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543766"
---
# <a name="backing-up-archiving-and-monitoring-databases-in-lync-server-2013"></a><span data-ttu-id="15b7a-103">Copia de seguridad de las bases de datos de archivado y supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15b7a-103">Backing up Archiving and Monitoring databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15b7a-104">_**Última modificación del tema:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="15b7a-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="15b7a-105">Si implementó el archivado o la supervisión, debe crear una copia de seguridad de estas bases de datos según la política de copias de seguridad de SQL Server de la organización.</span><span class="sxs-lookup"><span data-stu-id="15b7a-105">If you deployed Archiving or Monitoring, you need to back up these databases according to your organization's SQL Server backup policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="15b7a-106">Se realiza una copia de seguridad de la configuración de archivado y supervisión cuando se realiza una copia de seguridad del almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="15b7a-106">The settings for Archiving and Monitoring are backed up when you back up the Central Management store.</span></span> <span data-ttu-id="15b7a-107">Para obtener más información, consulte <A href="lync-server-2013-backing-up-core-data-and-settings.md">realizar copias de seguridad de datos y configuraciones principales en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="15b7a-107">For details, see <A href="lync-server-2013-backing-up-core-data-and-settings.md">Backing up core data and settings in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="15b7a-108">Para el archivado y la supervisión, puede usar una herramienta de SQL Server como SQL Server Management Studio para realizar una copia de seguridad manual, o bien puede usar las herramientas de administración de SQL Server para programar copias de seguridad regulares y automáticas.</span><span class="sxs-lookup"><span data-stu-id="15b7a-108">For Archiving and Monitoring, you can use a SQL Server tool such as SQL Server Management Studio to perform a manual backup, or you can use SQL Server management tools to schedule regular, automatic backups.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

