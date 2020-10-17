---
title: 'Lync Server 2013: configurar opciones de archivado para un sitio'
description: 'Lync Server 2013: configurar las opciones de archivado de un sitio.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2db164d7c4c1cdda158387be62c0eb535fac662f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562566"
---
# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a>Configurar las opciones de archivado para un sitio en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

Puede especificar las opciones de archivado que se aplicarán a sitios específicos creando y configurando opciones en una configuración de archivado para cada uno de esos sitios. Una configuración de sitio invalida la configuración global, pero solo para el sitio especificado en la configuración del sitio. Las configuraciones de grupo invalidan las configuraciones de sitio

Para obtener más información sobre cómo funcionan las configuraciones de archivado, incluida la jerarquía para las configuraciones globales, de sitio y de grupo, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, implementación o operaciones.

<div>


> [!NOTE]  
> Antes de habilitar el archivado, debe especificar todas las opciones adecuadas en las configuraciones de archivado.



</div>

<div>


> [!IMPORTANT]  
> Para habilitar el archivado, debe especificar las directivas de archivado para controlar el archivado de las comunicaciones internas y externas a nivel global y, si procede, en los niveles de sitio y usuario. Si configura directivas de nivel de usuario, también debe asignar las directivas de usuario a usuarios específicos. Para obtener más información sobre cómo crear y configurar las directivas de archivado, consulte <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing The external and external Communications in Lync Server 2013</A> en la documentación de operaciones.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a>Para configurar las opciones de archivado en el nivel de sitio

1.  Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.

4.  En la página **configuración de archivado** , haga clic en **nuevo**y, a continuación, haga clic en **configuración del sitio**.

5.  En **Seleccionar un sitio**, seleccione el sitio que debe configurarse para el archivado.

6.  En **Nueva configuración de archivado**, vaya al cuadro de lista desplegable **Configuración de archivado** y siga uno de estos procedimientos:
    
      - Para habilitar el archivado solo para las sesiones de mensajería instantánea, haga clic en **Archivar sesiones de mensajería instantánea**.
    
      - Para habilitar el archivado de sesiones de mensajería instantánea y conferencias, haga clic en **archivar sesiones de mensajería instantánea y conferencias web**.
    
      - Para deshabilitar el archivado para la directiva, haga clic en **Deshabilitar archivado**.

7.  Además, en **Nueva configuración de archivado**, haga lo siguiente:
    
      - Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear las sesiones de mensajería instantánea (MI) o conferencias web si se produce algún error en el archivado**.
    
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

