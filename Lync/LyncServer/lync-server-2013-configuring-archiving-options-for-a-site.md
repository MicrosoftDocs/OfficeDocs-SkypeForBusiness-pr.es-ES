---
title: 'Lync Server 2013: configuración de las opciones de archivado de un sitio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14b0e29a2796c23c13a16bfb3e8a202a0a535aaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a>Configuración de las opciones de archivado de un sitio en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

Puede especificar las opciones de archivado que se aplicarán a sitios específicos mediante la creación y la configuración de las opciones de una configuración de archivado para cada uno de esos sitios. Una configuración de sitio reemplaza la configuración global, pero solo para el sitio especificado en la configuración del sitio. Las configuraciones de grupo invalidan las configuraciones del sitio

Para obtener más información sobre cómo funcionan las configuraciones de archivado, incluida la jerarquía para las configuraciones globales, de sitio y de grupo, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, documentación de implementación o en la documentación de operaciones. .

<div>


> [!NOTE]  
> Debe especificar todas las opciones apropiadas en las configuraciones de archivado antes de habilitar el archivado.



</div>

<div>


> [!IMPORTANT]  
> Para habilitar el archivado, es necesario especificar directivas de archivado para controlar el archivado de comunicaciones internas y externas en el nivel global y, si es adecuado, en los niveles de sitio y usuario. Si configura directivas de nivel de usuario, también deberá asignar directivas a usuarios específicos. Para obtener más información sobre cómo crear y configurar directivas de archivado, vea <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">administrar el archivado de comunicaciones internas y externas en Lync Server 2013</A> en la documentación de operaciones.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a>Para configurar las opciones de archivado en el nivel de sitio

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server 2013, consulte [abrir las herramientas administrativas de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.

4.  En la página **Configuración de archivado**, haga clic en **Nuevo** y, luego, en **Configuración de sitio**.

5.  En **Seleccionar un sitio**, seleccione el sitio que necesita configurar para el archivado.

6.  En **Nueva configuración de archivado**, vaya al cuadro de lista desplegable **Configuración de archivado** y siga uno de estos procedimientos:
    
      - Para habilitar el archivado solo para las sesiones de mensajería instantánea (MI), haga clic en **Archivar sesiones de mensajería instantánea (MI)**.
    
      - Para habilitar el archivado tanto para las sesiones de mensajería instantánea (MI) y las conferencias, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.
    
      - A fin de deshabilitar el archivado de la directiva, haga clic en **Deshabilitar archivado**.

7.  Además, en **Nueva configuración de archivado**, haga lo siguiente:
    
      - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.
    
      - Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación **integración con Microsoft Exchange** .
    
      - Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:
        
          - Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.
        
          - Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.

8.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

