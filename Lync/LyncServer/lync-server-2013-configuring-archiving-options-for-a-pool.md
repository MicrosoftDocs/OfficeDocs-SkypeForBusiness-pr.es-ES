---
title: 'Lync Server 2013: configuración de las opciones de archivado de un grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options for a pool
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205200(v=OCS.15)
ms:contentKeyID: 48185230
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae5547320a9af0f11870ad0dc92ba03e40d8af4f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-pool-in-lync-server-2013"></a>Configuración de las opciones de archivado de un grupo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-10_

Puede especificar las opciones de archivado que se aplicarán a agrupaciones específicas mediante la creación y la configuración de las opciones de una configuración de archivado para cada uno de esos grupos. Una configuración de grupo reemplaza la configuración global y de sitio, pero solo para el grupo especificado en la configuración de grupo.

Para obtener más información sobre cómo funcionan las configuraciones de archivado, incluida la jerarquía para las configuraciones globales, de sitio y de grupo, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, documentación de implementación o en la documentación de operaciones. .

<div>


> [!NOTE]  
> Debe especificar todas las opciones apropiadas en las configuraciones de archivado antes de habilitar el archivado. Para obtener información detallada, vea <A href="lync-server-2013-configuring-archiving-options.md">configuración de las opciones de archivado en Lync Server 2013</A> en la documentación de implementación.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-pool-level"></a>Para configurar las opciones de archivado en el nivel de grupo

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server 2013, consulte [abrir las herramientas administrativas de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.

4.  En la página **Configuración de archivado**, haga clic en **Nuevo** y, luego, haga clic en **Configuración de grupo**.

5.  En **Seleccionar un servicio**, seleccione el grupo que desea configurar para el archivado.

6.  En **Nueva configuración de archivado**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones:
    
      - **Deshabilitar archivado**
    
      - **Archivar sesiones de mensajería instantánea (MI)**
    
      - **Archivar sesiones de mensajería instantánea (MI) y conferencias web**

7.  Además, en la página **Nueva configuración de archivado**, haga lo siguiente:
    
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

