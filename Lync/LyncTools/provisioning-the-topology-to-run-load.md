---
title: Aprovisionamiento de la topología para ejecutar la carga
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf4c296068e2bd0deea9470dd84d8fd0c0c9d451
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a>Aprovisionamiento de la topología para ejecutar la carga

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-04_

<div>

## <a name="provisioning-the-topology-to-run-load"></a>Aprovisionamiento de la topología para ejecutar la carga

Según la configuración actual y la configuración de Lync Server 2013, es posible que tenga que realizar los siguientes cambios en su entorno:

1.  Establezca la Directiva de ejecución de Windows PowerShell en no restringido. Para comprobar la configuración de la Directiva de ejecución, abra el shell de administración de Lync Server y ejecute el siguiente comando:

    ``` powershell
        Get-ExecutionPolicy
    ```        

    Si este comando no devuelve el valor Unrestricted, ejecute este comando:

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  Para configurar eficazmente Lync Server 2013, tendrá que:
    
      - Familiarícese con la topología de Lync Server 2013 (por ejemplo, nombres de equipos, instancias de servicios, nombres de sitio y directivas).
    
      - Asigne algunos de los usuarios que se han creado a grupos, por ejemplo, grupos de captura de grupo de respuesta (por ejemplo, URI de SIP).

3.  Para ejecutar el script desde la línea de comandos, puede usar:

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  Normalmente, después de que se ejecute una de las secuencias de comandos de este paquete, los rastros generados desde el script se almacenarán en un archivo en la misma ruta desde la \<que\>se invocó la secuencia de comandos, denominada scriptName $h $ m $ s. txt. Por ejemplo, ejecutar ArchivingPolicy. PS1 a las 12:15 P.M. generará un archivo de registro como ArchivingPolicy121500. txt.

5.  Por último, tenga en cuenta que, aunque hemos proporcionado ejemplos para configurar el servidor, usted es responsable de modificar o eliminar la configuración una vez que haya terminado de ejecutar la carga.

</div>

</div>

<span> </span>

</div>

</div>

</div>

