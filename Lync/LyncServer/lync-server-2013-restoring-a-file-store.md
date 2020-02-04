---
title: 'Lync Server 2013: restaurar un almacén de archivos'
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
ms.openlocfilehash: c013159de83d258273e381dd54556bcceec056f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="ffc16-102">Restaurar un almacén de archivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffc16-102">Restoring a file store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffc16-103">_**Última modificación del tema:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="ffc16-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="ffc16-104">Los almacenes de archivos para Standard Edition suelen estar ubicados en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ffc16-104">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="ffc16-105">Los almacenes de archivos para Enterprise Edition suelen estar situados en un clúster o servidor de archivos.</span><span class="sxs-lookup"><span data-stu-id="ffc16-105">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="ffc16-106">En el procedimiento siguiente se describe cómo restaurar un almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="ffc16-106">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="ffc16-107">Para restaurar un almacén de archivos</span><span class="sxs-lookup"><span data-stu-id="ffc16-107">To restore a File Store</span></span>

1.  <span data-ttu-id="ffc16-108">Si se produce un error en el almacén de archivos, copie el\\ almacén de archivos correspondiente de $backup a la ubicación del almacén de archivos en el servidor Standard Edition o el servidor de archivos y, a continuación, comparta la carpeta.</span><span class="sxs-lookup"><span data-stu-id="ffc16-108">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ffc16-109">La ruta de acceso y el nombre de archivo del almacén de archivos restaurado deberían ser exactamente iguales a los del almacén de archivos de la copia de seguridad, de modo que los componentes que los usen puedan tener acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="ffc16-109">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="ffc16-110">Si es necesario, establezca las listas de control de acceso (ACL) para el almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="ffc16-110">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="ffc16-111">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="ffc16-111">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ffc16-112">Solo debe realizar este paso si todavía no ha ejecutado la topología Builder durante el proceso de restauración.</span><span class="sxs-lookup"><span data-stu-id="ffc16-112">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

