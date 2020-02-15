---
title: 'Lync Server 2013: configurar opciones de archivado para un grupo de servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a pool
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205200(v=OCS.15)
ms:contentKeyID: 48185230
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 388adb28a2b484afadb4a02b21d3ab0a57b3f567
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-pool-in-lync-server-2013"></a>Configuración de opciones de archivado para un grupo de servidores en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-10_

Puede especificar las opciones de archivado que se aplican a grupos de servidores específicos al crear y configurar las opciones en una configuración de archivado para cada uno de estos grupos de servidores. La configuración de un grupo de servidores anula la configuración global y de sitio, pero únicamente para el grupo de servidores especificad en la configuración del grupo de servidores.

Para obtener más información sobre cómo funcionan las configuraciones de archivado, incluida la jerarquía para las configuraciones globales, de sitio y de grupo, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, implementación o operaciones.

<div>


> [!NOTE]  
> Antes de habilitar el archivado, debe especificar todas las opciones adecuadas en las configuraciones de archivado. Para obtener más información, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring archiving Options in Lync Server 2013</A> en la documentación sobre implementación.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-pool-level"></a>Para configurar las opciones de archivado en el nivel de grupo

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013. Para obtener más información acerca de los diferentes métodos que puede usar para iniciar el panel de control de Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.

4.  En la página **Configuración de archivado**, haga clic en **Nuevo** y en **Directiva de grupo**.

5.  En **Seleccione un servicio**, seleccione el grupo de servidores que desea configurar para el archivado.

6.  En **Nueva configuración de archivado**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones:
    
      - **Deshabilitar archivado**
    
      - **Archivar sesiones de mensajería instantánea**
    
      - **Archivar sesiones de MI y conferencias**

7.  Además, en la página **Nueva configuración de archivado**, haga lo siguiente:
    
      - Para bloquear la actividad cuando el archivado no está disponible, active la casilla  **Bloquear las sesiones de mensajería instantánea (MI) o conferencias si se produce algún error en el archivado **.
    
      - Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación **integración de Microsoft Exchange** .
    
      - Para habilitar la purga de datos, active la casilla **Habilitar purga de los datos de archivado** y realice una de las siguientes acciones:
        
          - Para especificar la purga al transcurrir un número de días determinado, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique los días.
        
          - Para limitar la purga de los datos archivados que se han exportado, haga clic en **Purgar solo datos archivados exportados**.

8.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

