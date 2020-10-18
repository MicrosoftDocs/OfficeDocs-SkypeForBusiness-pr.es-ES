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
# <a name="provisioning-the-topology-to-run-load"></a>Aprovisionamiento de la topología para ejecutar la carga

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-04_

<div>

Según la configuración existente y la configuración de Lync Server 2013, es posible que deba realizar los siguientes cambios en su entorno:

1.  Establezca la Directiva de ejecución de Windows PowerShell en irrestricto. Para comprobar la configuración de la Directiva de ejecución, abra el shell de administración de Lync Server y ejecute el siguiente comando:

    ``` powershell
        Get-ExecutionPolicy
    ```        

    Si este comando no devuelve el valor Unrestricted, ejecute este comando:

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  Para configurar eficazmente Lync Server 2013, necesitará:
    
      - Familiarícese con la topología de Lync Server 2013 (por ejemplo, nombres de equipo, instancias de servicio, nombres de sitio y directivas).
    
      - Asigne algunos de los usuarios que se crearon a grupos, como grupos de respuesta de grupo de respuesta (por ejemplo, URI de SIP).

3.  Para ejecutar el script desde la línea de comandos, puede usar:

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  Normalmente, una vez que se ejecuta uno de los scripts de este paquete, los rastros resultantes del script se almacenarán en un archivo en la misma ruta de acceso desde la que se invocó el script, denominado \<scriptname\> $h $ m $s.txt. Por ejemplo, la ejecución de ArchivingPolicy.ps1 a las 12:15 P.M. se generará un archivo de registro como ArchivingPolicy121500.txt.

5.  Por último, tenga en cuenta que, aunque se han proporcionado ejemplos para configurar el servidor, usted es responsable de modificar o eliminar la configuración una vez que haya terminado de ejecutar la carga.

</div>

</div>

<span> </span>

</div>

</div>

</div>

