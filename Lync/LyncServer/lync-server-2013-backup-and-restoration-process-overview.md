---
title: 'Lync Server 2013: información general del proceso de copia de seguridad y restauración'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b01230e84c9278d5540c21d41d9af1342479e6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a>Descripción general del proceso de copia de seguridad y restauración de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-26_

Esta sección proporciona información general sobre cómo funciona el proceso de copia de seguridad y restauración para Lync Server 2013. Use el mismo proceso para todos los servidores Standard Edition y los servidores Enterprise Edition, independientemente de su ubicación.

En general, el proceso de copia de seguridad funciona de la siguiente manera:

  - Cree una ubicación de copia de seguridad como una carpeta compartida en un equipo independiente que no forme parte de ningún grupo. En **$backup**se hace referencia a la ubicación de la copia de seguridad.

  - De forma periódica y programada, haga una copia de seguridad de todas las bases de datos de Lync Server y de todos los almacenes de archivos que se describen en [los requisitos de copia de seguridad y restauración de Lync server 2013: datos](lync-server-2013-backup-and-restoration-requirements-data.md) siguiendo los procedimientos descritos en [copia de seguridad de Lync Server 2013 ](lync-server-2013-backing-up-lync-server.md)El almacén central de administración incluye todas las configuraciones y la configuración del servidor.

  - Cada vez que ejecute una copia de seguridad posterior, cree una nueva carpeta compartida y cambie la ruta de acceso a la **$backup** referencias.

En general, el proceso de restauración funciona de la siguiente manera:

  - Cuando se produce un error o una interrupción, se restauran los datos en la ubicación a la que hacen referencia **$backup** a equipos nuevos o limpios.
    
    <div>
    

    > [!IMPORTANT]  
    > Este proceso de restauración no restaura datos en el estado de un servidor existente. Es decir, este proceso requiere que el servidor esté limpio o sea nuevo.

    
    </div>

  - Para permitir que se pueda recuperar la información de usuarios y conferencias hasta el momento en que se produjo el error, puede implementar una topología de recuperación ante desastres con grupos front-end emparejados, como se describe en [planear la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - Toda la configuración del sistema de nombres de dominio (DNS), la configuración del Protocolo de configuración dinámica de host (DHCP), los nombres de dominio, los nombres de dominio completos (FQDN), las rutas de almacenamiento de archivos, etc., deben ser los mismos en el momento de la restauración que estaban en el momento de la restauración Haga una copia de seguridad.

Si se produce un error en un servidor que ejecuta Lync Server, la recuperación incluye los siguientes pasos:

  - Instale el sistema operativo en un equipo nuevo o limpio con el mismo FQDN que el equipo que ha fallado.

  - Reinstale certificados.

  - Si el servidor ha hospedado una base de datos, instale Microsoft SQL Server 2012 o Microsoft SQL Server 2008 R2.

  - En general, si el servidor ha hospedado una base de datos, ejecute el generador de topología para crear e instalar la base de datos y configurar las listas de control de acceso (ACL).

  - En general, si el servidor ha hospedado un rol de servidor, ejecute el paso 1 hasta el paso 4 del Asistente para la implementación de Lync Server para instalar los archivos de configuración local, instalar los componentes del rol de servidor, asignar certificados e iniciar los servicios.
    
    <div>
    

    > [!NOTE]  
    > Si el servidor ha hospedado una base de datos colocada con el rol de servidor, al paso 2 del Asistente para la implementación de Lync Server se vuelve a crear la base de datos.

    
    </div>

  - Si el servidor ha hospedado una base de datos, restaure los datos de copia de seguridad.

</div>

<span> </span>

</div>

</div>

</div>

