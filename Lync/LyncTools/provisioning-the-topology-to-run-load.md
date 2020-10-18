---
title: Aprovisionamiento de la topología para ejecutar la carga
description: Aprovisionamiento de la topología para ejecutar la carga.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da482fde949675acc1722305433b95b7a6a6b523
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578416"
---
# <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="5dd34-103">Aprovisionamiento de la topología para ejecutar la carga</span><span class="sxs-lookup"><span data-stu-id="5dd34-103">Provisioning the Topology to Run Load</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5dd34-104">_**Última modificación del tema:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="5dd34-104">_**Topic Last Modified:** 2013-02-04_</span></span>

<div>

<span data-ttu-id="5dd34-105">Según la configuración existente y la configuración de Lync Server 2013, es posible que deba realizar los siguientes cambios en su entorno:</span><span class="sxs-lookup"><span data-stu-id="5dd34-105">Depending on your existing settings and configuration of Lync Server 2013, you may need to make the following changes in your environment:</span></span>

1.  <span data-ttu-id="5dd34-106">Establezca la Directiva de ejecución de Windows PowerShell en irrestricto.</span><span class="sxs-lookup"><span data-stu-id="5dd34-106">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="5dd34-107">Para comprobar la configuración de la Directiva de ejecución, abra el shell de administración de Lync Server y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="5dd34-107">To check your execution policy settings, open the Lync Server Management Shell and run the following command:</span></span>

    ``` powershell
        Get-ExecutionPolicy
    ```        

    <span data-ttu-id="5dd34-108">Si este comando no devuelve el valor Unrestricted, ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="5dd34-108">If this command does not return the value Unrestricted, run this command:</span></span>

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  <span data-ttu-id="5dd34-109">Para configurar eficazmente Lync Server 2013, necesitará:</span><span class="sxs-lookup"><span data-stu-id="5dd34-109">To effectively configure Lync Server 2013, you will need to:</span></span>
    
      - <span data-ttu-id="5dd34-110">Familiarícese con la topología de Lync Server 2013 (por ejemplo, nombres de equipo, instancias de servicio, nombres de sitio y directivas).</span><span class="sxs-lookup"><span data-stu-id="5dd34-110">Be familiar with Lync Server 2013 topology (for example, computer names, service instances, site names, and policies).</span></span>
    
      - <span data-ttu-id="5dd34-111">Asigne algunos de los usuarios que se crearon a grupos, como grupos de respuesta de grupo de respuesta (por ejemplo, URI de SIP).</span><span class="sxs-lookup"><span data-stu-id="5dd34-111">Assign some of the users that were created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>

3.  <span data-ttu-id="5dd34-112">Para ejecutar el script desde la línea de comandos, puede usar:</span><span class="sxs-lookup"><span data-stu-id="5dd34-112">To run the script from the command line, you may use:</span></span>

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  <span data-ttu-id="5dd34-113">Normalmente, una vez que se ejecuta uno de los scripts de este paquete, los rastros resultantes del script se almacenarán en un archivo en la misma ruta de acceso desde la que se invocó el script, denominado \<scriptname\> $h $ m $s.txt.</span><span class="sxs-lookup"><span data-stu-id="5dd34-113">Typically, after one of the scripts in this package runs, the resulting traces from the script will be stored in a file in the same path from which the script was invoked, named \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="5dd34-114">Por ejemplo, la ejecución de ArchivingPolicy.ps1 a las 12:15 P.M.</span><span class="sxs-lookup"><span data-stu-id="5dd34-114">For example, running ArchivingPolicy.ps1 at 12:15 P.M.</span></span> <span data-ttu-id="5dd34-115">se generará un archivo de registro como ArchivingPolicy121500.txt.</span><span class="sxs-lookup"><span data-stu-id="5dd34-115">will generate a log file such as ArchivingPolicy121500.txt.</span></span>

5.  <span data-ttu-id="5dd34-116">Por último, tenga en cuenta que, aunque se han proporcionado ejemplos para configurar el servidor, usted es responsable de modificar o eliminar la configuración una vez que haya terminado de ejecutar la carga.</span><span class="sxs-lookup"><span data-stu-id="5dd34-116">Finally, note that although we have provided examples to configure the server, you are responsible for modifying or deleting the configuration after you have finished running the load.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

