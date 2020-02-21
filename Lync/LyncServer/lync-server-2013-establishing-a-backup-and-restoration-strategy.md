---
title: 'Lync Server 2013: establecer una estrategia de copia de seguridad y restauración'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a65dd081cacd9952ce1b9a7f0917209532a28cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a>Establecimiento de una estrategia de copia de seguridad y restauración para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-26_

Antes de poder desarrollar un plan de copia de seguridad y restauración para Lync Server, debe desarrollar una estrategia que se ajuste a los objetivos de la organización. Para desarrollar una estrategia eficaz de copia de seguridad y restauración, tendrá que:

  - Establecer prioridades empresariales.

  - Identificar los requisitos de copia de seguridad y restauración.

<div>

## <a name="establishing-business-priorities"></a>Establecer las prioridades profesionales

Evaluar las prioridades profesionales de la organización. Normalmente, las principales prioridades profesionales que afectan a la estrategia de copia de seguridad y restauración son las siguientes:

  - Requisitos de continuidad profesionales

  - Precisión de los datos

  - Importancia de los datos

  - Requisitos de portabilidad

  - Restricciones de costos

Necesidades empresariales como estas le ayudarán a determinar los contratos de nivel de servicio (SLA) que desarrolle con sus clientes. Los contratos de nivel de servicio tienen una gran influencia en la estrategia de copia de seguridad y restauración.

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a>Identificar los requisitos de copia de seguridad y restauración

Las prioridades empresariales y los contratos de nivel de servicio actúan en la determinación de los requisitos de la organización para realizar copias de seguridad y restaurar Lync Server. Identifique y documente los requisitos para lo siguiente:

  - **Frecuencia de las copias de seguridad**   para obtener más información sobre los procedimientos recomendados para la frecuencia de copia de seguridad, vea [procedimientos recomendados para copias de seguridad y restauración para Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).

  - **Las herramientas**   de copia de seguridad y restauración incluyen quién va a usar las herramientas y en qué equipos. Para obtener más información acerca de las herramientas descritas en este tema y los permisos necesarios, consulte [Backup and restore requirements in Lync Server 2013: Tools and Permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).

  - **Ubicación**   de la copia de seguridad identifique si las copias de seguridad se guardan de forma local o remota, teniendo en cuenta la seguridad y la accesibilidad. Especifique los medios que se utilizarán para las copias de seguridad.

  - **Los requisitos**   de hardware y software identifican y documentan los requisitos de hardware y software específicos, incluido el hardware para el almacenamiento y la restauración de copias de seguridad de componentes específicos y la conectividad de software y red necesaria para admitir la copia de seguridad y restauración. A medida que desarrolle sus requisitos de hardware y software, tenga en cuenta los distintos escenarios de restauración que se exponen a continuación.

  - **Escenarios de restauración**   a continuación se muestran los procesos de restauración para los siguientes escenarios:
    
      - Un grupo de Lync Server produce errores. Este escenario requiere volver a generar cada servidor del grupo.
    
      - Se produce un error en un servidor Standard Edition. Este escenario requiere volver a generar el servidor en un equipo nuevo o limpio y restaurar las bases de datos.
    
      - Pérdida del almacén de administración central. Como mínimo, este escenario requiere restaurar y publicar el almacén de administración central.
    
      - Pérdida de un servidor back-end cuando el almacén de administración central sigue funcionando con normalidad. Este escenario requiere volver a generar el servidor en un equipo nuevo o limpio y restaurar las bases de datos.
    
      - Se produce un error en un servidor que es miembro de un grupo de servidores de Lync. Este escenario requiere volver a generar el servidor en un equipo nuevo o limpio.
    
      - Se produce un error en el almacén de archivos. Este escenario requiere restaurar el servidor de archivos o el clúster de archivos.
    
      - Se produce un error en una base de datos de archivado, supervisión o chat persistente. Este escenario requiere volver a crear las bases de datos y, si los datos son esenciales para la organización, restaurar los datos. El archivado, la supervisión y los datos del chat persistente no son necesarios para que la copia de seguridad y la ejecución de Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

