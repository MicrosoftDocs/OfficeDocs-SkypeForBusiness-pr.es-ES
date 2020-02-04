---
title: 'Lync Server 2013: procedimientos recomendados para copias de seguridad y restauración'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e51f846d92f5d8cfecbbface31df6543c5c9ac23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a>Procedimientos recomendados para copias de seguridad y restauración de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Esta sección incluye dos tipos de procedimientos recomendados:

  - Procedimientos recomendados para la copia de seguridad y la restauración.

  - Procedimientos recomendados para minimizar el impacto de un desastre.

<div>

## <a name="best-practices-for-backup-and-restoration"></a>Procedimientos recomendados para copias de seguridad y restauración

Para facilitar el proceso de copia de seguridad y restauración, al hacer una copia de seguridad o restaurar los datos, siga estos procedimientos recomendados:

  - Realice copias de seguridad periódicas en intervalos apropiados. La programación de rotación y el tipo de copia de seguridad más simple y frecuente es una copia de seguridad nocturna completa de toda la base de datos de SQL Server. Después, si es necesario restaurar, el proceso de restauración solo requiere una copia de seguridad, y no se deben perder más de un día.

  - Si usa cmdlets o el panel de control de Lync Server para realizar cambios de configuración, use el cmdlet **Export-CsConfiguration** para tomar una copia de seguridad de instantáneas del archivo de configuración de topología (XDS. MDF) después de realizar los cambios, de modo que no pierda los cambios si necesita restaurar las bases de datos. Tenga en cuenta que se realiza una copia de seguridad de esta configuración en formato XML y se comprime como archivo ZIP.

  - Asegúrese de que la carpeta compartida que va a usar para realizar copias de seguridad de Lync Server tenga suficiente espacio en disco para almacenar todos los datos de la copia de seguridad.

  - Programe copias de seguridad cuando el uso de Lync Server sea generalmente bajo, para mejorar el rendimiento del servidor y la experiencia del usuario.

  - Asegúrese de que la ubicación donde se realiza la copia de seguridad de los datos es segura (recomendamos una ubicación remota).

  - Mantenga los archivos de copia de seguridad donde estarán disponibles, en caso de que necesite restaurar los datos.

  - Planear y programar pruebas periódicas de los procesos de restauración admitidos por su organización.

  - Valide los procesos de copia de seguridad y restauración por adelantado para asegurarse de que funcionan de la forma esperada.

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a>Procedimientos recomendados para minimizar el impacto de un desastre

La mejor estrategia para resolver interrupciones de servicio desastrosas (causadas por eventos no manejables, como cortes de energía o errores de hardware repentinos) es asumir que ocurrirán y planificar según corresponda.

Si los servicios de Lync, con un mínimo de interrupción y interrupción, son importantes para la empresa, debe considerar la posibilidad de implementar grupos de servidores de solicitudes de cliente emparejados, como se describe en [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Después, si uno de estos grupos de servidores tiene un desastre, un administrador puede cambiar los usuarios de ese grupo para que el otro grupo lo atienda, con un mínimo de tiempo de inactividad.

Los planes de administración ante desastres que desarrolla como parte de su estrategia de copia de seguridad y restauración deben incluir lo siguiente:

  - Cómo mantener los medios de software y las actualizaciones de software y firmware disponibles.

  - Mantener registros de hardware y software.

  - Realizar copias de seguridad de los datos de forma periódica y supervisar la integridad de las copias de seguridad.

  - Formación de su personal en la recuperación de desastres, documentación de procedimientos e implementación de simulacros de recuperación ante desastres.

  - Mantener disponible el hardware de repuesto o, si tiene un contrato de nivel de servicio (SLA), contratar a proveedores de hardware y proveedores para el reemplazo de solicitudes.

  - Separar la ubicación de los archivos de registro de transacciones (archivos. ldf) y los archivos de base de datos (archivos. MDF).

</div>

</div>

<span> </span>

</div>

</div>

</div>

