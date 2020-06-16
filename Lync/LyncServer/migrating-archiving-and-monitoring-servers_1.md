---
title: Migrar servidores de archivado y supervisión
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43b7c7509dcf678967db651900c67cdfb3d26685
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>Migrar servidores de archivado y supervisión

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Si ha implementado el servidor de archivado y el servidor de supervisión en Office Communications Server 2007 R2, puede implementar estos servidores en su entorno de Lync Server 2013 después de migrar los grupos de servidores front-end. No obstante, si las funciones de archivado y supervisión son esenciales para su organización, debe agregar el archivado y la supervisión a su grupo piloto antes de migrar para que dichas funciones estén disponibles durante el proceso de migración.

Si desea contar con la funcionalidad de archivado y de supervisión durante la fase de migración y coexistencia, tenga en cuenta lo siguiente:

  - Los datos de archivado y supervisión no se mueven a la implementación de Lync Server 2013. Los datos de los que ha realizado una copia de seguridad antes de retirar el entorno heredado serán el historial de actividad en Office Communications Server 2007 R2.

  - La versión de Office Communications Server 2007 R2 del servidor de archivado y el servidor de supervisión solo se pueden asociar a un grupo de servidores front-end de Office Communications Server 2007 R2. En Lync Server 2013, el archivado y la supervisión ya no tienen roles de servidor, sino que están integrados en el grupo de servidores front-end de Lync Server 2013.

  - Durante el tiempo que coexisten las implementaciones heredadas de Lync Server 2013, la versión de Office Communications Server 2007 R2 del servidor de archivado y el servidor de supervisión recopilan datos para los usuarios alojados en los grupos de servidores de Office Communications Server 2007 R2. La versión de Lync Server 2013 del servidor de archivado y el servidor de supervisión recopilan datos para los usuarios hospedados en los grupos de servidores de Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Durante la fase de migración, cuando sigue usando el servidor perimetral heredado con el nuevo grupo piloto de Lync Server 2013, la versión de Office Communications Server 2007 R2 del servidor de archivado continúa recopilando datos para los usuarios alojados en los grupos de servidores de Office Communications Server 2007 R2 y la versión de Lync Server 2013 del servidor de archivado recopila datos para los usuarios hospedados 2013 en grupos de

    
    </div>

  - Si usa una solución de archivado y supervisión de terceros junto con el servidor de archivado y el servidor de supervisión, hable con su proveedor sobre cuándo y cómo necesita integrar la solución de terceros con Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

