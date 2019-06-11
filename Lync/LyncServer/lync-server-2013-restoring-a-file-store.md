---
title: 'Lync Server 2013: restaurar un almacén de archivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc9f1bae4e1a9a84815e576267a15155bec227da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a>Restaurar un almacén de archivos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-18_

Los almacenes de archivos para Standard Edition suelen estar ubicados en el servidor Standard Edition. Los almacenes de archivos para Enterprise Edition suelen estar situados en un clúster o servidor de archivos. En el procedimiento siguiente se describe cómo restaurar un almacén de archivos.

<div>

## <a name="to-restore-a-file-store"></a>Para restaurar un almacén de archivos

1.  Si se produce un error en el almacén de archivos, copie el\\ almacén de archivos correspondiente de $backup a la ubicación del almacén de archivos en el servidor Standard Edition o el servidor de archivos y, a continuación, comparta la carpeta.
    
    <div>
    

    > [!IMPORTANT]  
    > La ruta de acceso y el nombre de archivo del almacén de archivos restaurado deberían ser exactamente iguales a los del almacén de archivos de la copia de seguridad, de modo que los componentes que los usen puedan tener acceso a ellos.

    
    </div>

2.  Si es necesario, establezca las listas de control de acceso (ACL) para el almacén de archivos. En la línea de comandos, escriba:
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Solo debe realizar este paso si todavía no ha ejecutado la topología Builder durante el proceso de restauración.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

