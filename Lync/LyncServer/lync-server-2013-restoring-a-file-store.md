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
ms.openlocfilehash: 60c4a3e1563890d64394f3a99141523cb95add38
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a>Restaurar un almacén de archivos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-18_

Los almacenes de archivos para Standard Edition suelen estar ubicados en el servidor Standard Edition. Los almacenes de archivos para Enterprise Edition suelen estar ubicados en un clúster o un servidor de archivos. El siguiente procedimiento describe cómo restaurar un almacén de archivos.

<div>

## <a name="to-restore-a-file-store"></a>Para restaurar un almacén de archivos

1.  Si se produce un error en un almacén de archivos, copie el\\ almacén de archivos correspondiente de $backup a la ubicación del almacén de archivos en el servidor de archivos o Standard Edition y, a continuación, comparta la carpeta.
    
    <div>
    

    > [!IMPORTANT]  
    > La ruta de acceso y el nombre de archivo del almacén de archivos restaurados deben ser exactamente los mismos que los del almacén de archivos de copia de seguridad, para que los componentes que usan los archivos puedan tener acceso a ellos.

    
    </div>

2.  Si es necesario, establezca las listas de control de acceso (ACL) para el almacén de archivos. En la línea de comandos, escriba lo siguiente:
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Debe realizar este paso solo si, de lo contrario, no ejecutó el generador de topologías durante el proceso de restauración.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

