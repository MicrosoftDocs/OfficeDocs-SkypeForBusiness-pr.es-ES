---
title: 'Lync Server 2013: publicación de la topología actualizada para agregar bases de datos de archivado'
description: 'Lync Server 2013: publicación de la topología actualizada para agregar bases de datos de archivado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90d1c53fb2a2dde5dde079f09b13ff4f06a659b3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571456"
---
# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a>Publicación de la topología actualizada para agregar bases de datos de archivado en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Después de actualizar la topología en el generador de topologías, debe publicar la topología en el almacén de administración central para poder configurar y usar el archivado. Las copias de solo lectura de los datos se replican en todos los servidores de la topología para mantener todos los servidores sincronizados con los cambios de topología y de otro tipo.

<div>

## <a name="to-publish-your-updated-topology"></a>Para publicar su topología actualizada

1.  En un equipo que ejecuta Lync Server 2013 o en el que están instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo de usuarios locales (o una cuenta con derechos de usuario equivalentes).
    
    <div>
    

    > [!NOTE]  
    > Puede definir una topología con una cuenta que sea miembro del grupo de usuarios locales, pero para publicar una topología, que es necesaria para agregar un servidor a la topología, debe usar una cuenta que sea miembro del grupo administradores de dominio y del grupo <STRONG>RTCUniversalServerAdmins</STRONG> de <STRONG>dominio</STRONG> , y que tiene permisos de control total (es decir, de lectura, escritura y modificación) en el recurso compartido de archivos que usa para el almacén de archivos de Lync Server 2013 (es decir, el generador de topologías puede configurar la lista de control de acceso discrecional (DACL) necesaria o una cuenta con derechos equivalentes.

    
    </div>

2.  Abra la topología que creó en la sección anterior mediante el generador de topologías.

3.  En el árbol de la consola, haga clic con el botón secundario en **Lync Server 2013**y, a continuación, haga clic en **publicar topología**.

4.  En la página **Publicar la topología**, haga clic en **Siguiente**.

5.  En la página **Crear bases de datos**, compruebe que la base de datos está seleccionada y haga clic en **Siguiente**.
    
    <div>
    

    > [!NOTE]  
    > Si no tiene los permisos adecuados para crear bases de datos, puede cancelar la selección de la base de datos y alguien con permisos adecuados podrá crear la base de datos. Para obtener más información sobre los permisos y derechos de administrador necesarios, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permisos de implementación para SQL Server en Lync Server 2013</A> en la documentación sobre implementación.<BR>Solo se pueden instalar bases de datos en servidores SQL Server dedicados mediante el generador de topologías. Las bases de datos de los servidores de SQL Server que se colocan con otros componentes del servidor deben instalarse mediante la ejecución de la configuración local en ese equipo.

    
    </div>

6.  En la página **Asistente para publicación completado**, verifique que se ha publicado correctamente la topología y haga clic en **Finalizar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Una vez publicada la topología, debe configurar opciones y directivas para el archivado antes de que se pueda archivar cualquier contenido. Para obtener más información, consulte <A href="lync-server-2013-configuring-support-for-archiving.md">Configuring Support for archiving in Lync Server 2013</A> en la documentación sobre implementación.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

