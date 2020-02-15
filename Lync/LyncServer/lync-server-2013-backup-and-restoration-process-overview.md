---
title: 'Lync Server 2013: información general del proceso de copia de seguridad y restauración'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9d5e2700065444691dee1041ff210768e9bade7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a>Información general sobre el proceso de copia de seguridad y restauración para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-26_

En esta sección se proporciona información general sobre cómo funciona el proceso de copia de seguridad y restauración para Lync Server 2013. Se usa el mismo proceso para todos los servidores Standard Edition y Enterprise, independientemente de su ubicación.

En general, el proceso de copia de seguridad funciona de la siguiente manera:

  - Se crea una ubicación para copias de seguridad como una carpeta compartida en un equipo independiente que no forma parte de ningún grupo de servidores. La ubicación de la copia de seguridad refiere a **$Backup**.

  - De forma periódica y programada, realice una copia de seguridad de todas las bases de datos de Lync Server y de todos los almacenes de archivos que se describen en [requisitos de copia de seguridad y restauración en Lync server 2013: los datos](lync-server-2013-backup-and-restoration-requirements-data.md) siguiendo los procedimientos descritos en copia de seguridad de [Lync Server 2013](lync-server-2013-backing-up-lync-server.md) el almacén de administración central incluye todas las configuraciones y configuraciones del servidor.

  - Cada vez que se ejecuta una copia de seguridad posterior, se crea una nueva carpeta compartida y cambia la ruta a la que hace referencia **$Backup**.

En general, el proceso de restauración funciona de la siguiente manera:

  - Cuando se produce un error o una interrupción, se restauran los datos en la ubicación a la que hacen referencia **$backup** a equipos nuevos o limpios.
    
    <div>
    

    > [!IMPORTANT]  
    > Este proceso de restauración no restaura datos en un estado de servidor existente. Es decir, este proceso requiere que el servidor esté limpio o sea nuevo.

    
    </div>

  - Para permitir que la información de usuarios y conferencias sea recuperable hasta el punto de error, puede implementar una topología de recuperación ante desastres con grupos de servidores front-end emparejados, tal como se describe en [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - Toda la configuración del Sistema de nombres de dominio (DNS), del Protocolo de la configuración dinámica de host (DHCP), los nombres de dominio, los nombres de dominio completos (FQDN), las rutas de almacenes de archivos, etc. deben ser los mismos al momento de la restauración que cuando se hizo la copia de seguridad.

Si se produce un error en un servidor que ejecuta Lync Server, la recuperación incluye los siguientes pasos:

  - Instalar el sistema operativo en un equipo nuevo o limpio con el mismo FQDN que había en el equipo donde se produjo el error.

  - Reinstalar certificados.

  - Si el servidor hospedaba una base de datos, instale Microsoft SQL Server 2012 o Microsoft SQL Server 2008 R2.

  - En general, si el servidor hospedaba una base de datos, ejecute el generador de topologías para crear e instalar la base de datos y configurar las listas de control de acceso (ACL).

  - En general, si el servidor hospedaba una función de servidor, ejecute el paso 1 hasta el paso 4 del Asistente para la implementación de Lync Server para instalar los archivos de configuración locales, instalar los componentes del rol de servidor, asignar certificados e iniciar los servicios.
    
    <div>
    

    > [!NOTE]  
    > Si el servidor hospedaba una base de datos combinada con la función de servidor, al ejecutar el paso 2 del Asistente para la implementación de Lync Server se vuelve a crear la base de datos.

    
    </div>

  - Si el servidor hospedaba una base de datos, restaure los datos de la copia de seguridad.

</div>

<span> </span>

</div>

</div>

</div>

