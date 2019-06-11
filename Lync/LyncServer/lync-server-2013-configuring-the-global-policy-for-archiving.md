---
title: 'Lync Server 2013: configuración de la directiva global para archivar'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ccb5ba267c3dc94e14f00cf96f240fa2f0e91b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a>Configuración de la directiva global para archivar en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

Al implementar los servidores front-end, Lync Server crea una directiva global para el archivado. De forma predeterminada, el archivado está deshabilitado en la directiva global. La directiva global controla si el archivado está habilitado para las comunicaciones internas y externas para toda la implementación, a no ser que Configure directivas de usuario o de sitio, que invaliden la directiva global, o si usa la integración de Microsoft Exchange para algunas o todas los usuarios. Si usa la integración de Microsoft Exchange, la directiva global no se aplica a los usuarios alojados en Exchange 2013 y tienen los buzones en conservación local.

Para obtener detalles sobre cómo funcionan las directivas de archivado, incluida la jerarquía para las directivas globales, de sitio y de usuario, consulte Cómo funciona el archivado en la documentación de planeamiento, la documentación de implementación o la documentación de operaciones [de Lync Server 2013](lync-server-2013-how-archiving-works.md) .

<div>


> [!NOTE]  
> Si habilita la integración de Microsoft Exchange para su implementación, las directivas de retención local de Exchange controlan si el archivado está habilitado para los usuarios alojados en Exchange 2013 y si sus buzones se colocan en conservación local. Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurar directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación de implementación.<BR>Debe especificar todas las opciones apropiadas en las configuraciones de archivado antes de habilitar el archivado. Para obtener información detallada, vea <A href="lync-server-2013-configuring-archiving-options.md">configuración de las opciones de archivado en Lync Server 2013</A> en la documentación de implementación.



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a>Para configurar la directiva global para archivar al usar las bases de datos de archivado de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server 2013, consulte [abrir las herramientas administrativas de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.

4.  En la página **Directiva de archivado**, haga clic en **Global**, **Editar** y, luego, en **Mostrar detalles**.

5.  En **Editar directiva de archivado: global**, haga lo siguiente:
    
      - En **Nombre**, si no desea usar el nombre predeterminado "global", especifique un nombre nuevo para la directiva global.
    
      - En **Descripción**, proporcione información sobre la directiva (por ejemplo, directiva global para *divisionName*).
    
      - Para controlar el archivado de las comunicaciones internas de todos los usuarios y sitios que no se controlan específicamente por medio de una directiva de sitio o de usuario, active o desactive la casilla **Archivar comunicaciones internas**.
    
      - Para controlar el archivado de las comunicaciones externas de todos los usuarios y sitios que no se controlan específicamente por medio de una directiva de sitio o de usuario, active o desactive la casilla **Archivar comunicaciones externas**.

6.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

