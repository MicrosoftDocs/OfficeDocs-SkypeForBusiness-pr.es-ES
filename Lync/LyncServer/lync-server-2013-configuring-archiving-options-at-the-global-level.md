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
ms.openlocfilehash: 59ab58cbee3479bff424e7d69d475e1d83fdd3bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a>Configurar las opciones de archivado en el nivel global de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-10_

Al agregar el archivado a la topología y publicar la topología, Lync Server crea una configuración global para el archivado. De forma predeterminada, no se habilitan opciones de archivado en la configuración global. La configuración global controla qué opciones se habilitan para toda la implementación, a menos que realice configuraciones de sitio o de grupo, que omiten la configuración global.

Para obtener detalles sobre cómo funcionan las configuraciones de archivado, incluida la jerarquía para las configuraciones globales, de sitio y de grupo, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, la documentación de implementación o la documentación de operaciones.

<div>


> [!NOTE]  
> Debe especificar todas las opciones apropiadas en las configuraciones de archivado antes de habilitar el archivado.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a>Para configurar las opciones de archivado en el nivel global

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server 2013, consulte [abrir las herramientas administrativas de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.

4.  En la página **Configuración de archivado**, haga clic en **Global**, en **Editar** y, luego, en **Mostrar detalles**.

5.  En **Editar configuración de archivado: global**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones de archivado:
    
      - **Deshabilitar archivado**
    
      - **Archivar sesiones de mensajería instantánea (MI)**
    
      - **Archivar sesiones de mensajería instantánea (MI) y conferencias web**

6.  Además, en la página **Editar configuración de archivado: global**, haga lo siguiente:
    
      - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.
    
      - Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación **integración con Microsoft Exchange** .
    
      - Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:
        
          - Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.
        
          - Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.

7.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

