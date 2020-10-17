---
title: 'Lync Server 2013: comprobación del uso de disco'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6379d110fc25ba31062d211d3893567ad92fda1f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526207"
---
# <a name="checking-disk-usage-in-lync-server-2013"></a>Comprobar el uso de disco en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-04-30_

Las unidades de disco duro son un componente importante de la implementación de Lync Server 2013. Sin un volumen de disco libre suficiente, ni el sistema operativo ni las bases de datos de Lync Server 2013 pueden funcionar correctamente. Debe supervisar diariamente las estadísticas de la base de datos back-end de Lync Server 2013 para garantizar que los servidores no se queden sin espacio en disco y para prepararse para agregar recursos de almacenamiento según sea necesario.

Además de la comprobación del espacio en discos que hospedan el sistema operativo, archivos de programa, bases de datos y registros de transacciones (back-end 2013 de Lync Server), también debe supervisar el uso del sistema de archivos que incluya espacio en disco para recursos compartidos de archivos que contengan los siguientes datos importantes:

  - Contenido de reuniones

  - Metadatos de contenido de reunión

  - Registros de cumplimiento de reuniones

  - Archivos de datos de aplicación (lo utiliza internamente el componente del servidor de aplicaciones)

  - Servicio Web del servidor de chat en grupo y carpetas de cumplimiento (para almacenar los archivos cargados en el servicio Web de chat en grupo)

  - Archivos XML de cumplimiento de chat en grupo (que contienen registros de cumplimiento de chat de grupo)

  - Archivos de actualización (para el servicio de actualización de dispositivos)

  - Archivos de la libreta de direcciones

Lync Server 2013 necesita espacio en el disco duro para almacenar sus bases de datos y registros de transacciones, además de los archivos en los recursos compartidos de archivos enumerados anteriormente.

Debe supervisar el espacio en disco de forma regular para asegurarse de que la implementación de Lync Server 2013 no se ve afectada negativamente debido a recursos de almacenamiento insuficientes.

Compare y mantenga la información estadística sobre el espacio disponible en disco en cada volumen de Lync Server 2013 y el crecimiento esperado de las bases de datos y los archivos de registro de transacciones. Esto le ayuda a planear la capacidad y a agregar almacenamiento cuando se necesitan los recursos de almacenamiento.

Para dar cabida a situaciones de solución de problemas y recuperación ante desastres, se recomienda que el espacio de volumen disponible sea igual o mayor que el 110 por ciento del tamaño de la base de datos.

Puede comprobar el espacio libre en disco con los métodos siguientes:

1.  **System Center Operations Manager**     System Center Operations Manager se puede usar para advertir a los administradores cuando se restringe el espacio en el volumen.

2.  **Ejecutar un script**     Supervise el espacio en disco ejecutando un script que le envía un mensaje si el espacio disponible en el disco duro cae por debajo del 20 por ciento. Puede encontrar un script de ejemplo en el centro de scripts de Microsoft en TechNet, examine: [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)

3.  **Explorador**     de Windows Use el explorador de Windows para comprobar el espacio en disco de los volúmenes que almacenan las bases de datos y los registros de Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

