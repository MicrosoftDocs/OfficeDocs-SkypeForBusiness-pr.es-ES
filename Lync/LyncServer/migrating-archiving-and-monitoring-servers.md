---
title: Migración de servidores de archivado y supervisión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4edd989985c4ed65027ed8d19725ec1f93c2bdc4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>Migración de servidores de archivado y supervisión

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Si ha implementado el servidor de archivado y el servidor de supervisión en su entorno de Lync Server 2010, puede implementar estos servidores en su entorno de Lync Server 2013 después de migrar los grupos de servidores front-end. Sin embargo, si la funcionalidad de archivado y supervisión es fundamental para su organización, debe agregar el archivado y la supervisión al grupo piloto de Lync Server 2013 antes de migrar para que la funcionalidad esté disponible durante el proceso de migración.

Si desea contar con la funcionalidad de archivado y de supervisión durante la el proceso de migración, tenga en cuenta lo siguiente:

  - Los datos de archivado y supervisión no se mueven a la implementación de Lync Server 2013. Los datos de los que realice una copia de seguridad antes de retirar el entorno heredado serán su historial de actividades en el entorno de Lync Server 2010.

  - La versión 2010 de Lync Server del servidor de archivado y el servidor de supervisión solo pueden asociarse con un grupo de servidores front-end de Lync Server 2010. En Lync Server 2013, el archivado y la supervisión ya no tienen roles de servidor, sino que están integrados en el grupo de servidores front-end de Lync Server 2013.

  - Durante el tiempo que coexisten las implementaciones heredadas de Lync Server 2013, la versión de Lync Server 2010 del servidor de archivado y el servidor de supervisión recopilan datos para los usuarios hospedados en los grupos de servidores de Lync Server 2010. Archivado y supervisión en Lync Server 2013 recopilar datos para los usuarios alojados en los grupos de servidores de Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Durante la fase de migración, cuando sigue usando el servidor perimetral heredado con el nuevo grupo piloto de Lync Server 2013, la versión de Lync Server 2010 del servidor de archivado continúa recopilando datos para los usuarios hospedados en los grupos de servidores de Lync Server 2010 y el archivado en Lync Server 2013 recopila datos para los usuarios hospedados en los grupos de servidores de Lync Server 2013.

    
    </div>

  - Si usa una solución de archivado y supervisión de terceros junto con el archivado y la supervisión en Lync Server 2013, consulte al proveedor Cuándo y cómo debe integrar la solución de terceros con Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

