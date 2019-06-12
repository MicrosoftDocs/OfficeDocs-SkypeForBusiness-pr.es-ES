---
title: Migrar servidores de archivado y supervisión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 902970548d4bd9e95e1bd4e7d6eba75e2fe405d3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849966"
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

Si ha implementado el servidor de archivado y el servidor de supervisión en Office Communications Server 2007 R2, puede implementar estos servidores en el entorno de Lync Server 2013 después de migrar los grupos de aplicaciones para el usuario. Sin embargo, si la funcionalidad de archivado y supervisión es crítica para su organización, debe agregar el archivado y la supervisión al grupo piloto antes de realizar la migración para que la funcionalidad esté disponible durante el proceso de migración.

Si quiere que la funcionalidad de archivado y supervisión durante la migración y la fase de coexistencia, tenga en cuenta las siguientes consideraciones:

  - Los datos de archivado y supervisión no se mueven a la implementación de Lync Server 2013. Los datos de los que haya hecho una copia de seguridad antes de retirar el entorno heredado serán el historial de actividad en el Office Communications Server 2007 R2.

  - La versión de Office Communications Server 2007 R2 del servidor de archivado y del servidor de supervisión solo se puede asociar con un grupo front-end de Office Communications Server 2007 R2. En Lync Server 2013, el archivado y la supervisión ya no tienen roles de servidor, pero los servicios integrados en el grupo front-end de Lync Server 2013.

  - Durante el tiempo que coexistan las implementaciones heredadas de Lync Server 2013, la versión de Office Communications Server 2007 R2 del servidor de archivado y el servidor de supervisión recopilan datos para los usuarios alojados en los grupos de Office Communications Server 2007 R2. La versión de Lync Server 2013 del servidor de archivado y el servidor de supervisión recopilan datos para los usuarios alojados en los grupos de servidores de Skype empresarial 2013.
    
    <div>
    

    > [!NOTE]  
    > Durante la fase de migración, cuando aún está usando su servidor perimetral heredado con el nuevo grupo piloto de Lync Server 2013, la versión R2 de Office Communications Server 2007 R2 recopila datos para usuarios alojados en Office Communications Server 2007 Los grupos R2 y la versión 2013 de Lync Server del servidor de archivado recopilan datos para los usuarios alojados en los grupos de servidores de Lync Server 2013.

    
    </div>

  - Si usa una solución de archivado y supervisión de terceros junto con el servidor de archivado y el servidor de supervisión, hable con su proveedor sobre cuándo y cómo necesita integrar la solución de terceros con Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

