---
title: 'Lync Server 2013: configuración de las opciones de archivado en el nivel global'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options at the global level
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48185303
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 939928b99c4372f3dafe9536365481fb737478a6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517547"
---
# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a>Configurar las opciones de archivado en el nivel global en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-10_

Cuando se agrega el archivado a la topología y se publica la topología, Lync Server crea una configuración global para el archivado. De forma predeterminada, no se habilita ninguna opción de archivado en la configuración global. La configuración global controla qué opciones se habilitan para su completa implementación, a menos que realice configuraciones de sitio o grupo de servidores, que omiten la configuración global.

Para obtener más información sobre cómo funcionan las configuraciones de archivado, incluida la jerarquía para las configuraciones globales, de sitio y de grupo, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, implementación o operaciones.

<div>


> [!NOTE]  
> Debe especificar todas las opciones adecuadas en las configuraciones de archivado antes de habilitar el archivado.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a>Procedimiento para configurar las opciones de archivado en el nivel global

1.  Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013. Para obtener más información acerca de los diferentes métodos que puede usar para iniciar el panel de control de Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.

4.  En la página **Configuración de archivado**, haga clic en **Global**, **Editar** y **Mostrar detalles**.

5.  En **Editar configuración de archivado: global**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones de archivado:
    
      - **Deshabilitar archivado**
    
      - **Archivar sesiones de mensajería instantánea**
    
      - **Archivar mensajería instantánea y sesiones de conferencias web**

6.  Además, en la página **Editar configuración de archivado: global**, haga lo siguiente:
    
      - Para bloquear la actividad si el archivado no está disponible, seleccione la casilla **Bloquear las sesiones de mensajería instantánea (MI) o conferencias web si se produce algún error en el archivado**.
    
      - Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación **integración de Microsoft Exchange** .
    
      - Para habilitar la purga de datos, active la casilla **Habilitar purga de los datos de archivado** y realice una de las siguientes acciones:
        
          - Para especificar la purga al transcurrir un número de días determinado, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique los días.
        
          - Para limitar la purga de los datos archivados que se han exportado, haga clic en **Purgar solo datos archivados exportados**.

7.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

