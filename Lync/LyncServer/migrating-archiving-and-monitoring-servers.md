---
title: Migrar servidores de archivado y supervisión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901961ad7456dfd8b0340cba03ff44a9e77a147f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>Migrar servidores de archivado y supervisión

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Si ha implementado el servidor de archivado y el servidor de supervisión en el entorno de Lync Server 2010, puede implementar estos servidores en el entorno de Lync Server 2013 después de migrar los grupos de aplicaciones para el usuario. Sin embargo, si la funcionalidad de archivado y supervisión es crítica para su organización, debe agregar el archivado y la supervisión al grupo de pruebas piloto de Lync Server 2013 antes de la migración para que la funcionalidad esté disponible durante el proceso de migración.

Si desea mantener la funcionalidad de archivado y supervisión durante el proceso de migración, tenga en cuenta las siguientes consideraciones:

  - Los datos de archivado y supervisión no se mueven a la implementación de Lync Server 2013. Los datos de los que haya hecho una copia de seguridad antes de retirar el entorno heredado serán el historial de actividad en el entorno de Lync Server 2010.

  - La versión de Lync Server 2010 del servidor de archivado y del servidor de supervisión solo se puede asociar con un grupo front-end de Lync Server 2010. En Lync Server 2013, el archivado y la supervisión ya no tienen roles de servidor, pero los servicios integrados en el grupo front-end de Lync Server 2013.

  - Durante el tiempo que coexistan las implementaciones heredadas de Lync Server 2013, la versión de Lync Server 2010 del servidor de archivado y el servidor de supervisión recopilan datos para los usuarios alojados en los grupos de Lync Server 2010. Archivado y supervisión en Lync Server 2013 recopilar datos para los usuarios alojados en los grupos de servidores de Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Durante la fase de migración, cuando aún está usando su servidor perimetral heredado con el nuevo grupo piloto de Lync Server 2013, la versión de Lync Server 2010 del servidor de archivado continúa recopilando datos para los usuarios alojados en los grupos de Lync Server 2010 y archivados en Lync Server 2013 recopila datos para los usuarios alojados en los grupos de 2013 de Lync Server.

    
    </div>

  - Si usa una solución de archivado y supervisión de terceros junto con el archivado y la supervisión en Lync Server 2013, consulte con su proveedor sobre cuándo y cómo necesita integrar la solución de terceros con Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

