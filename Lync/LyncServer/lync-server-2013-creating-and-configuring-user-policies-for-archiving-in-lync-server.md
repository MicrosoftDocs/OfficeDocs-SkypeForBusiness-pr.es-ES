---
title: Crear y configurar directivas de usuario para archivar en Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb4385d219173ca33ae7120dcf3e9d75d4c65f14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a>Crear y configurar directivas de usuario para archivar en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-09_

Para habilitar o deshabilitar el archivado de usuarios específicos alojados en Lync Server, primero debe crear una directiva de usuario y, a continuación, aplicar la Directiva a uno o más usuarios o grupos de usuarios. Para obtener detalles sobre cómo aplicar directivas de usuario a usuarios específicos y grupos de usuarios, vea [aplicar una directiva de archivado de Lync Server a un usuario en Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) en la documentación de implementación.

Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía para las directivas globales, de sitio y de usuario, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, en la documentación de implementación o en la documentación de operaciones.

<div>


> [!NOTE]
> Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de retención local de Exchange controlan si el archivado está habilitado para los usuarios alojados en Exchange 2013 y si sus buzones se colocan en conservación local. Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurar directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación de implementación.<BR>Debe especificar todas las opciones apropiadas en las configuraciones de archivado antes de habilitar el archivado. Para obtener información detallada, vea <A href="lync-server-2013-configuring-archiving-options.md">configuración de las opciones de archivado en Lync Server 2013</A> en la documentación de implementación.



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a>Para configurar una directiva de archivado para usuarios alojados en Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server 2013. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server 2013, consulte [abrir las herramientas administrativas de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.

4.  Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.

5.  En **Directiva de archivado nueva**, haga lo siguiente:
    
      - En **Nombre**, escriba el nombre de la directiva de usuario.
    
      - En **Descripción**, proporcione información sobre la directiva de usuario (por ejemplo, directiva de usuario para el departamento legal).
    
      - Para controlar el archivado de las comunicaciones internas para la directiva de usuario, active o desactive la casilla **Archivar comunicaciones internas**.
    
      - Para controlar el archivado de las comunicaciones externas para la directiva de usuario, active o desactive la casilla **Archivar comunicaciones externas**.

6.  Haga clic en **Confirmar**.

Una directiva de usuario solo se aplica a los usuarios a los que asigne la directiva. Para obtener más información sobre cómo aplicar una directiva de usuario a usuarios específicos, consulte [aplicar una directiva de archivado de Lync Server a un usuario en Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) en la documentación de implementación.

</div>

</div>

<span> </span>

</div>

</div>

</div>

