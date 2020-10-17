---
title: 'Lync Server 2013: administración de la configuración'
description: 'Lync Server 2013: administración de la configuración.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5999708811cc4a34cf846a1ddd481ba38e07c62
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552156"
---
# <a name="configuration-management-in-lync-server-2013"></a>Administración de la configuración en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-05-15_

La administración de la configuración es el proceso de registrar y realizar un seguimiento de los activos de hardware y software y la información de configuración del sistema. Por lo general, se usa para realizar un seguimiento de las licencias de software, mantener una compilación estándar de hardware y software para los equipos cliente y los servidores, y definir los estándares de nomenclatura para nuevos equipos. La administración de la configuración generalmente abarca las siguientes categorías:

  - **Hardware**     Esta categoría realiza un seguimiento de las piezas de equipamiento que posee la organización de ti, Dónde está ubicado el equipo y quién usa el equipo. Esta información permite a una organización planear y presupuestar las actualizaciones, mantener compilaciones de hardware estándar, informar sobre el valor de los activos de TI con fines de contabilidad y ayudar a evitar el robo.

  - **Software**     de Esta categoría realiza un seguimiento del software instalado en cada equipo, los números de versión y el lugar donde se encuentran las licencias. Esta información ayuda a planear actualizaciones, garantizar que el software tiene una licencia y detectar la presencia de software no autorizado (y sin licencia).

  - **Compilaciones estándar**     Esta categoría realiza un seguimiento de la compilación estándar actual para los equipos cliente y los servidores, y si los equipos cliente y los servidores cumplen este estándar. Definir e imponer compilaciones estándar ayuda al personal de soporte técnico, ya que el personal debe mantener un número limitado de versiones de cada elemento de software.

  - **Actualizaciones acumulativas y revisiones**     Esta categoría realiza un seguimiento de los Service Pack que se han probado y aprobado para su uso y los equipos que están actualizados. Esta información es importante para reducir el riesgo de que los equipos se pongan en peligro y para detectar los usuarios que han instalado actualizaciones no aprobadas.

  - Información de configuración **del sistema**     Esta categoría realiza un seguimiento de la función de un sistema, la interacción entre los elementos del sistema y los procesos que dependen de un sistema que se ejecuta sin problemas. Por ejemplo, se puede configurar un servidor proxy de terceros en un único servidor. Se debe comprender la dependencia del servidor proxy en este servidor y es posible que se necesiten planes de contingencia si se produce un error. Si el servidor proxy se puede configurar para que también se comunique con otro servidor front-end, es probable que cambien las dependencias y los planes de contingencia.

<div>

## <a name="implementing-configuration-management"></a>Implementación de la administración de la configuración

Después de determinar qué elementos necesitan administrar, implemente la administración de la configuración mediante la recopilación de datos y datos de informes. El método más sencillo para las organizaciones pequeñas es recopilar datos manualmente (número y modelo de equipos cliente, sistema operativo, software instalado) y guardarlos en un documento de Office Word u Office Excel. Para sistemas de mayor tamaño, más complejo y constante cambio, se debe automatizar el descubrimiento de activos y la recopilación de información detallada. Decida qué información es relevante para su organización y guárdela en una base de datos.

La base de datos de administración de la configuración es una herramienta útil para el personal de soporte técnico y la administración en las siguientes áreas:

  - **Auditorías**     de seguridad La base de datos le permite identificar los servidores que ejecutan Lync Server y los sistemas informáticos que deben tener revisiones aplicadas o que no han podido instalar un Service Pack o las actualizaciones más recientes de antivirus.

  - **Instalación**     de software Identificar las versiones de software de cliente y realizar un seguimiento de ellas ayudará a los administradores a planear actualizaciones de la versión y nuevas instalaciones, además de ayudarle con la documentación de licencias y el cumplimiento normativo.

  - **Información**     de configuración Si mantiene una lista actualizada de todas las opciones de configuración que se cambiaron de forma predeterminada, podrá solucionar problemas de forma rápida y eficaz.

  - **Planeación de actualizaciones**     Si una revisión de capacidad revela que es necesario disponer de espacio de almacenamiento adicional en los servidores de base de datos de Lync, es importante saber si cada servidor tiene un controlador RAID interno. Si es así, ¿son el mismo modelo? ¿Tienen el mismo número de discos instalados? La base de datos de administración de la configuración indicará el tipo de disco que se puede instalar, el número y la ruta de actualización en cada caso.

</div>

<div>

## <a name="tools-used-for-configuration-management"></a>Herramientas usadas para la administración de la configuración

Hay muchas herramientas para descubrir, auditar y reportar activos. Algunas de estas herramientas se describen en esta sección.

  - **Scripts**     automatizados Puede escribir scripts sencillos para notificar elementos como el sistema operativo, el nivel de Service Pack y si hay software en un conjunto específico de equipos. Puede escribir estos scripts para los requisitos exactos de una organización. Sin embargo, el número necesario de scripts y su complejidad puede hacer que los scripts sean caros de crear y mantener.

  - **Herramientas**     automatizadas Según el tamaño de su empresa y las necesidades de su organización, es posible que quiera considerar el uso de herramientas automatizadas. Herramientas como Microsoft Endpoint Configuration Manager incorporan plantillas de informes estándar (como el nivel de Service Pack) y también permiten crear informes personalizados, por ejemplo, para una aplicación personalizada. Microsoft Endpoint Configuration Manager también se puede usar para informar sobre las configuraciones de hardware y software.

</div>

<div>

## <a name="relationship-with-change-management"></a>Relación con la administración de cambios

La administración de la configuración está estrechamente relacionada con la administración de cambios. La administración de la configuración identifica la necesidad de cambiar e identifica y registra que se ha producido un cambio. Por ejemplo, la base de datos de administración de la configuración se puede usar para identificar los servidores que requieren una revisión. A continuación, la administración de cambios define el proceso para aplicar la revisión.

Por el contrario, si se implementa una nueva actualización acumulativa, el proceso de administración de cambios debe proporcionar esta información al sistema de administración de la configuración. Es probable que las herramientas de administración de la configuración tengan que configurarse para identificar el nuevo software a fin de que puedan descubrir y realizar un seguimiento del lugar y el momento en que se implemente el software.

</div>

</div>

<span> </span>

</div>

</div>

</div>

