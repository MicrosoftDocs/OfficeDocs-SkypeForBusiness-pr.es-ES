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
ms.openlocfilehash: 30dd3345545ae8c77c4ebfcece7154e91059f9aa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a>Procedimientos recomendados para copias de seguridad y restauración para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Esta sección incluye dos tipos de procedimientos recomendados:

  - Prácticas recomendadas para la copia de seguridad y restauración.

  - Procedimientos recomendados para minimizar el impacto de un desastre.

<div>

## <a name="best-practices-for-backup-and-restoration"></a>Procedimientos recomendados de copia de seguridad y restauración

Para facilitar el proceso de copia de seguridad y restauración, aplique los siguientes procedimientos recomendados al realizar una copia de seguridad de los datos o restaurarlos:

  - Realice copias de seguridad regularmente y a intervalos apropiados. La rutina más sencilla y habitual a la hora de programar copias de seguridad es hacer cada noche copias completas de toda la base de datos de SQL Server. A continuación, si la restauración es necesaria, el proceso de restauración solo requiere una copia de seguridad y no se deben perder más datos de un día.

  - Si usa cmdlets o el panel de control de Lync Server para realizar cambios en la configuración, use el cmdlet **Export-CsConfiguration** para realizar una copia de seguridad de instantáneas del archivo de configuración de la topología (XDS. MDF) después de realizar los cambios, de modo que no pierda los cambios si necesita restaurar las bases de datos. Tenga en cuenta que se realiza una copia de seguridad de esta configuración en formato XML y se comprime como un archivo ZIP.

  - Asegúrese de que la carpeta compartida que va a usar para hacer copias de seguridad de Lync Server tiene suficiente espacio en disco para contener todos los datos de los que ha realizado una copia de seguridad.

  - Programe las copias de seguridad cuando el uso de Lync Server sea normalmente bajo, para mejorar el rendimiento del servidor y la experiencia del usuario.

  - Asegúrese de que la ubicación donde se realiza la copia de seguridad de los datos es segura (se recomienda una ubicación remota).

  - Conserve los archivos de copia de seguridad donde estarán disponibles, en caso de que necesite restaurar los datos.

  - Planear y programar pruebas periódicas de los procesos de restauración compatibles con la organización.

  - Valide los procesos de copia de seguridad y restauración de antemano para asegurarse de que funcionan como se esperaba.

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a>Procedimientos recomendados para minimizar el impacto de un desastre

La mejor estrategia para tratar con interrupciones de servicio desastrosas (causadas por eventos no administrables, como cortes en la alimentación o errores repentinos de hardware) es suponer que se producirán y planear en consecuencia.

Si los servicios de Lync, con un mínimo de interrupción y interrupción, son fundamentales para el negocio en su organización, debe considerar la posibilidad de implementar grupos emparejados de servidores front-end, como se describe en [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). A continuación, si uno de estos grupos de servidores tiene un desastre, un administrador puede cambiar a los usuarios de ese grupo para que los atienda el otro grupo, con un mínimo de tiempo de inactividad.

Los planes de administración ante desastres que desarrolle como parte de su estrategia de copia de seguridad y restauración deben incluir lo siguiente:

  - Mantener los medios de software y las actualizaciones de software y firmware, disponibles fácilmente.

  - Mantenga registros de hardware y software.

  - Realizar copias de seguridad de los datos con regularidad y supervisar la integridad de las copias de seguridad.

  - Forme a su personal en recuperación de desastres, documente todos los procedimientos y lleve a cabo simulacros de recuperación de desastres.

  - Mantener disponible el hardware de reserva o, si tiene un contrato de nivel de servicio (SLA), contratando a los proveedores de hardware y proveedores los reemplazos de solicitudes.

  - Separe la ubicación de sus archivos de registro de transacciones (archivos .ldf) y los archivos de bases de datos (archivos .mdf).

</div>

</div>

<span> </span>

</div>

</div>

</div>

