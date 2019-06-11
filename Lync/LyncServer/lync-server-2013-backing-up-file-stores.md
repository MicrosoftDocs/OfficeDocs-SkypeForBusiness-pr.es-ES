---
title: 'Lync Server 2013: copia de seguridad de los almacenes de archivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up file stores
ms:assetid: 1a7f4e93-aa3d-461e-878e-2c572baa1293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202167(v=OCS.15)
ms:contentKeyID: 51541449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6facef86481e247d1f51d3ec567c8a4ee4bfde8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-file-stores-in-lync-server-2013"></a><span data-ttu-id="9c847-102">Copia de seguridad de almacenes de archivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c847-102">Backing up file stores in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c847-103">_**Última modificación del tema:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="9c847-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="9c847-104">La copia de seguridad de los almacenes de archivos de Lync Server incluye todos los archivos y carpetas que usan los componentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9c847-104">Backing up the Lync Server File Stores includes all the files and folders used by Lync Server components.</span></span>

<div>

## <a name="to-back-up-file-stores"></a><span data-ttu-id="9c847-105">Para hacer una copia de seguridad de los almacenes de archivos</span><span class="sxs-lookup"><span data-stu-id="9c847-105">To back up File Stores</span></span>

1.  <span data-ttu-id="9c847-106">Para buscar las ubicaciones específicas de los almacenes de archivos de Lync Server, abra el generador de topologías y mire en el nodo **almacenes de archivos** .</span><span class="sxs-lookup"><span data-stu-id="9c847-106">To find the specific locations of your Lync Server File Stores, open Topology Builder and look in the **File stores** node.</span></span>

2.  <span data-ttu-id="9c847-107">Use Robocopy u otra herramienta de administración del sistema de archivos para copiar cada almacén\\de archivos en $backup almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="9c847-107">Use Robocopy or another file system management tool to copy each File Store to $Backup\\filestore.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

