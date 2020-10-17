---
title: 'Lync Server 2013: restaurar un almacén de archivos'
description: 'Lync Server 2013: restaurar un almacén de archivos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 201c4b20f224fa3a25e931689e564410c60143e6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543836"
---
# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="7d987-103">Restaurar un almacén de archivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d987-103">Restoring a file store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d987-104">_**Última modificación del tema:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="7d987-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="7d987-105">Los almacenes de archivos para Standard Edition suelen estar ubicados en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7d987-105">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="7d987-106">Los almacenes de archivos para Enterprise Edition suelen estar ubicados en un clúster o un servidor de archivos.</span><span class="sxs-lookup"><span data-stu-id="7d987-106">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="7d987-107">El siguiente procedimiento describe cómo restaurar un almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="7d987-107">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="7d987-108">Para restaurar un almacén de archivos</span><span class="sxs-lookup"><span data-stu-id="7d987-108">To restore a File Store</span></span>

1.  <span data-ttu-id="7d987-109">Si se produce un error en un almacén de archivos, copie el almacén de archivos correspondiente de $Backup \\ a la ubicación del almacén de archivos en el servidor de archivos o Standard Edition y, a continuación, comparta la carpeta.</span><span class="sxs-lookup"><span data-stu-id="7d987-109">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7d987-110">La ruta de acceso y el nombre de archivo del almacén de archivos restaurados deben ser exactamente los mismos que los del almacén de archivos de copia de seguridad, para que los componentes que usan los archivos puedan tener acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="7d987-110">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="7d987-111">Si es necesario, establezca las listas de control de acceso (ACL) para el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="7d987-111">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="7d987-112">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7d987-112">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7d987-113">Debe realizar este paso solo si, de lo contrario, no ejecutó el generador de topologías durante el proceso de restauración.</span><span class="sxs-lookup"><span data-stu-id="7d987-113">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

