---
title: 'Lync Server 2013: Recursos requeridos para el servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31683641e50a3e3bc898841b0cf4b0911e046262
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a>Recursos requeridos para el servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-02-05_

La alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente requieren recursos adicionales más allá de lo que normalmente se necesita para una completa operación. Antes de configurar el servidor de chat persistente para una alta disponibilidad y recuperación ante desastres, asegúrese de disponer de los recursos siguientes, además de lo que se requiere para el funcionamiento del servidor de chat persistente estándar. Para obtener información de configuración adicional, consulte [configuración de un servidor de chat persistente en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).

  - Una instancia de base de datos dedicada ubicada en el mismo centro de datos físico en el que se encuentra el front-end del servicio del servidor de chat persistente. Esta base de datos servirá de SQL Server Mirror para la base de datos de chat persistente principal. De manera opcional, designe un servidor SQL Server adicional para que sirva como testigo de creación de reflejos si desea una conmutación automática para la base de datos reflejada.

  - Una instancia de base de datos dedicada ubicada en el otro centro de datos físico. Esta base de datos servirá como la base de datos secundaria de trasvase de registros de SQL Server para la base de datos en el centro de datos principal.

  - Una instancia de base de datos dedicada que servirá como reflejo de SQL Server para la base de datos secundaria. De manera opcional, designe un servidor SQL Server adicional como testigo de creación de reflejos. Es preciso que ambos estén ubicados en el mismo centro de datos físico que la base de datos secundaria.

  - Si el cumplimiento del servidor de chat persistente está habilitado, se necesitan tres instancias de base de datos dedicadas adicionales. Su distribución es la misma que la de la base de datos de chat persistente anterior. Aunque es posible que la base de datos de cumplimiento comparta la misma instancia de SQL Server que la base de datos de chat persistente, recomendamos instancias independientes para la alta disponibilidad y la recuperación ante desastres.

  - Es necesario crear y designar un recurso compartido de archivos para los registros de transacciones de trasvase de registros de SQL Server. Todos los servidores SQL de ambos centros de datos que ejecutan bases de datos de chat persistentes deben tener acceso de lectura y escritura a este recurso compartido de archivos. Este recurso compartido no está designado como parte del rol FileStore.

  - Un recurso compartido de archivos en el servidor de la base de datos secundaria para que sirva como carpeta de destino para los registros de transacciones de SQL Server que se copian desde el recurso compartido de archivos del servidor principal.

<div>


> [!NOTE]  
> Los servidores de chat persistente activos en un grupo de servidores de chat persistente deben residir en la misma zona horaria que el grupo de Lync del próximo salto definido en la topología.



</div>

Las figuras siguientes proporcionan ejemplos acerca de cómo se puede configurar todo el grupo de servidores de chat persistente en las dos topologías de grupo extendidas diferentes:

  - Grupo de servidores de chat persistente estirado cuando los centros de datos se encuentran en un gran ancho de banda y baja latencia.

  - Grupo de servidores de chat persistente estirado cuando los centros de datos se encuentran en una ubicación geográfica con un ancho de banda bajo y una latencia alta.

La siguiente ilustración muestra una topología de grupo de servidores de chat persistente superpuesto en la que los centros de datos se encuentran en una ubicación geográfica con un alto ancho de banda y baja latencia.

**Grupo de servidores de chat persistente estirado cuando los centros de datos se encuentran en un gran ancho de banda y baja latencia.**

![Examen de configuración HBW del grupo de servidores de chat persistente](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Examen de configuración HBW del grupo de servidores de chat persistente")

La siguiente ilustración muestra una topología de grupo de servidores de chat persistente superpuesto en la que los centros de datos se encuentran en una ubicación geográfica con un ancho de banda bajo y una latencia elevada.

**Grupo de servidores de chat persistente estirado cuando los centros de datos se encuentran en una ubicación geográfica con un ancho de banda bajo y una latencia alta.**

![Examen de configuración LBW del grupo de servidores de chat persistente](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Examen de configuración LBW del grupo de servidores de chat persistente")

</div>

<span> </span>

</div>

</div>

</div>

