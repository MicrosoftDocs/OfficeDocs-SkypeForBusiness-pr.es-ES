---
title: 'Lync Server 2013: publicación de la topología actualizada para agregar bases de datos de archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f39e5f35dbd088543456f09ddd49f6aa2f9325c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a>Publicar la topología actualizada para agregar bases de datos de archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-01_

Después de actualizar su topología en el generador de topología, debe publicarla en el almacén de administración central antes de poder configurar y usar el archivado. Las copias de solo lectura de los datos se replican en todos los servidores de la topología para mantener todos los servidores sincronizados con los cambios en la topología y en otras opciones de configuración.

<div>

## <a name="to-publish-your-updated-topology"></a>Para publicar su topología actualizada

1.  En un equipo que ejecute Lync Server 2013 o en el que estén instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo usuarios locales (o una cuenta con derechos de usuario equivalentes).
    
    <div>
    

    > [!NOTE]  
    > Puede definir una topología con una cuenta que sea miembro del grupo usuarios locales, pero para publicar una topología, que es necesaria para agregar un servidor a la topología, debe usar una cuenta que sea miembro del grupo de <STRONG>administradores de dominio</STRONG> y la de <STRONG>RTCUniversalServer Grupo administradores</STRONG> , que tiene permisos de control total (es decir, lectura, escritura y modificación) en el recurso compartido de archivos que está usando para el almacén de archivos de Lync Server 2013 (es decir, el generador de topología puede configurar la lista de control de acceso discrecional (DACL) requerida. o una cuenta con derechos equivalentes.

    
    </div>

2.  Abra la topología que creó en la sección anterior con el generador de topologías.

3.  En el árbol de consola, haga clic con el botón secundario en **Lync Server 2013**y, a continuación, haga clic en **publicar topología**.

4.  En la página **Publicar la topología**, haga clic en **Siguiente**.

5.  En la página **Crear bases de datos**, compruebe que la base de datos está seleccionada y, luego, haga clic en **Siguiente**.
    
    <div>
    

    > [!NOTE]  
    > Si no tiene los permisos adecuados para crear bases de datos, puede cancelar la selección de la base de datos y alguien con permisos adecuados podrá crear la base de datos. Para obtener detalles sobre los permisos y derechos de administrador necesarios, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permisos de implementación para SQL Server en Lync server 2013</A> en la documentación de implementación.<BR>Con el generador de topologías solo se pueden instalar bases de datos en servidores SQL Server dedicados. Las bases de datos de los servidores SQL Server que se colocan con otros componentes del servidor se deben instalar ejecutando la configuración local en ese equipo.

    
    </div>

6.  En la página **Asistente para publicación completado**, compruebe que se ha publicado correctamente la topología y, luego, haga clic en **Finalizar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Una vez publicada la topología, necesita configurar las opciones y las directivas para el archivado antes de que se pueda archivar cualquier contenido. Para obtener más información, vea configuración de la <A href="lync-server-2013-configuring-support-for-archiving.md">compatibilidad de archivado en Lync Server 2013</A> en la documentación de implementación.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

