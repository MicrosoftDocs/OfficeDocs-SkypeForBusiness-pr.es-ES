---
title: 'Lync Server 2013: recursos necesarios para el servidor de chat persistente'
description: 'Lync Server 2013: recursos necesarios para el servidor de chat persistente.'
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
ms.openlocfilehash: 18c81f0017428e4305e46fbcf5580a83af38accf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542556"
---
# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a>Recursos necesarios para el servidor de chat persistente en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-02-05_

La alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente requieren recursos adicionales aparte de lo que normalmente se necesita para la operación completa. Antes de configurar el servidor de chat persistente para la alta disponibilidad y la recuperación ante desastres, asegúrese de que dispone de los siguientes recursos además de los necesarios para el funcionamiento del servidor de chat persistente estándar. Para obtener información adicional sobre la configuración, consulte [Configuring persistent chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).

  - Una instancia de base de datos dedicada ubicada en el mismo centro de datos físico en el que se encuentra el front-end principal del servicio del servidor de chat persistente. Esta base de datos servirá como reflejo de SQL Server para la base de datos de chat persistente principal. Opcionalmente, designe un servidor SQL Server adicional para que sirva como testigo de creación de reflejos si desea una conmutación por error automatizada para la base de datos reflejada.

  - Una instancia de base de datos dedicada ubicada en el otro centro de datos físico. Esta base de datos servirá como base de datos secundaria de trasvase de registros de SQL Server para la base de datos en el centro de datos principal.

  - Una instancia de base de datos dedicada que sirva como reflejo de SQL Server para la base de datos secundaria. Si lo desea, puede designar un servidor SQL Server a servidor adicional como testigo de creación de reflejos. Ambos deben estar ubicados en el mismo centro de datos físico que la base de datos secundaria.

  - Si el cumplimiento del servidor de chat persistente está habilitado, se necesitan tres instancias de base de datos dedicadas adicionales. Su distribución es la misma que la que se ha descrito anteriormente para la base de datos de chat persistente. Aunque es posible que la base de datos de cumplimiento comparta la misma instancia de SQL Server que la base de datos de chat persistente, recomendamos instancias independientes para la alta disponibilidad y la recuperación ante desastres.

  - Es necesario crear y designar un recurso compartido de archivos para los registros de transacciones de trasvase de registros de SQL Server. Todos los servidores SQL de ambos centros de datos que ejecutan bases de datos de chat persistente deben tener acceso de lectura y escritura a este recurso compartido de archivos. Este recurso compartido no está designado como parte del rol FileStore.

  - Un recurso compartido de archivos en el servidor de base de datos secundario que sirva como carpeta de destino para los registros de transacciones de SQL Server que se copian del recurso compartido de archivos del servidor principal.

<div>


> [!NOTE]  
> Los servidores de chat persistente activos en un grupo de servidores de chat persistente deben residir en la misma zona horaria que el grupo de Lync del próximo salto definido en la topología.



</div>

Las figuras siguientes proporcionan ejemplos sobre cómo se puede configurar todo el grupo de servidores de chat persistente en las dos topologías de grupo de servidores extendidos siguientes:

  - Grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda alto/latencia baja

  - Grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda bajo/latencia alta

La siguiente figura muestra una topología de grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda alto/baja latencia.

**Grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda alto/latencia baja**

![Examen de configuración del grupo de servidores de chat persistente HBW](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Examen de configuración del grupo de servidores de chat persistente HBW")

La siguiente figura muestra una topología de grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda bajo/latencia alta.

**Grupo de servidores de chat persistente estirados donde los centros de datos se ubican geográficamente con ancho de banda bajo/latencia alta**

![Examen de configuración del grupo de servidores de chat persistente LBW](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Examen de configuración del grupo de servidores de chat persistente LBW")

</div>

<span> </span>

</div>

</div>

</div>

