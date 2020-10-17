---
title: 'Lync Server 2013: configuración de la directiva global para el archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 589c249f772b130eeed80abb97e272b8053dfdc4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532387"
---
# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a>Configuración de la directiva global para el archivado en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

Cuando se implementan los servidores front-end, Lync Server crea una directiva global para el archivado. De forma predeterminada, el archivado está deshabilitado en la directiva global. La directiva global controla si el archivado está habilitado para las comunicaciones internas y externas para toda la implementación, a menos que Configure directivas de sitio o de usuario, que invalidan la directiva global o si usa la integración de Microsoft Exchange para algunos o todos los usuarios. Si usa la integración de Microsoft Exchange, la directiva global no se aplica a los usuarios hospedados en Exchange 2013 y tienen los buzones que se colocan en In-Place en espera.

Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, de sitio y de usuario, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning Documentation, Deployment Documentation o Operations Documentation.

<div>


> [!NOTE]  
> Si habilita la integración de Microsoft Exchange para su implementación, las directivas de Exchange In-Place retenciones controlan si el archivado está habilitado para los usuarios que están hospedados en Exchange 2013 y que sus buzones se colocan en In-Place suspensión. Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuración de directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación sobre implementación.<BR>Antes de habilitar el archivado, debe especificar todas las opciones adecuadas en las configuraciones de archivado. Para obtener más información, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring archiving Options in Lync Server 2013</A> en la documentación sobre implementación.



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a>Para configurar la directiva global para el archivado al usar las bases de datos de archivado de Lync Server

1.  Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.

4.  En la página **Directiva de archivado** , haga clic en **global**, en **Editar**y, a continuación, en **Mostrar detalles**.

5.  En **Editar directiva de archivado - Global**, haga lo siguiente:
    
      - En **nombre**, si no desea usar el nombre predeterminado global, especifique un nuevo nombre para la directiva global.
    
      - En **Descripción**, proporcione información sobre la Directiva (por ejemplo, directiva global para *divisionName*).
    
      - Para controlar el archivado de las comunicaciones internas de todos los usuarios y sitios que no se controlan específicamente mediante una directiva de sitio o de usuario, active o desactive la casilla **Archivar comunicaciones internas**.
    
      - Para controlar el archivado de comunicaciones externas para todos los sitios y usuarios que no se controlan específicamente mediante una directiva de sitio o de usuario, Active o desactive la casilla **archivar comunicaciones externas** .

6.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

