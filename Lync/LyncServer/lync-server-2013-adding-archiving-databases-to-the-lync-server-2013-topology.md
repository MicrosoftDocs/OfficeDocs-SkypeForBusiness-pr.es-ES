---
title: 'Lync Server 2013: agregar bases de datos de archivado a la topología de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7476107b064b45dbef74b03ff9d54e02fc9eee52
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a>Agregar bases de datos de archivado a la topología de 2013 de Lync Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-10_

Es preciso incorporar el archivado a la topología para poder configurar la implementación a fin de admitir el archivado. La información de este tema explica cómo usar el generador de topología para agregar el archivado a la topología existente.

<div>


> [!NOTE]  
> Si desea usar la integración de Microsoft Exchange para almacenar datos y archivos en servidores de Exchange 2013 para todos los usuarios de su implementación, no especifique el <STRONG>almacenamiento de SQL Server</STRONG> en el almacén o use la información de reflejo de la <STRONG>tienda SQL Server</STRONG> .



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a>Para agregar compatibilidad con la base de datos de archivado a su topología

1.  En un equipo que ejecute Lync Server 2013 o en el que estén instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo usuarios locales (o una cuenta con derechos de usuario equivalentes).
    
    <div>
    

    > [!NOTE]  
    > Puede definir una topología con una cuenta que sea miembro del grupo usuarios locales, pero para publicar una topología, que es necesaria para agregar un servidor a la topología. debe usar una cuenta que sea miembro del grupo <STRONG>administradores de dominio</STRONG> y el grupo <STRONG>RTCUniversalServerAdmins</STRONG> , y que tenga permisos de control total (es decir, leer, escribir y modificar) en el recurso compartido de archivos de Lync Server 2013 (es decir, para que el generador de topología pueda configurar la lista de control de acceso discrecional (DACL) requerida. o una cuenta con derechos equivalentes.

    
    </div>

2.  Iniciar el generador de topología.

3.  En el árbol de consola, vaya al grupo de servidores front-end en el que desea implementar el archivado y, a continuación, haga clic en el nombre del grupo de servidores front-end en el que desea implementar el archivado.

4.  En el menú **Acción**, haga clic en **Editar propiedades**.

5.  En el cuadro de diálogo **Editar propiedades**, haga clic en **General**.

6.  Desplácese hacia abajo hasta **Archivado**.

7.  Marque la casilla **Archivado**.

8.  En **archivar almacén de SQL Server,** realice una de las siguientes acciones:
    
      - Para usar un almacén de SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar. Si todos los usuarios están alojados en Microsoft Exchange Server 2013 o una versión posterior, puede archivar las comunicaciones de Lync para todos los usuarios de Exchange. En este caso, no es necesario configurar el almacén de archivado de SQL Server.
    
      - Para especificar un nuevo almacén de SQL Server, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , haga lo siguiente:
        
          - En **FQDN de SQL Server**, especifique el nombre completo del servidor en el que desea crear el nuevo almacén de SQL Server.
        
          - Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.
        
          - Si la instancia de SQL Server especificada tiene una relación de creación de reflejos, seleccione la casilla **de verificación esta instancia de SQL está en relación de creación de reflejo** y, a continuación, en número de puerto de **réplica**, especifique el número de puerto.

9.  Si desea usar el reflejo de la tienda SQL Server, seleccione **Habilitar reflejo de la tienda SQL Server**y, a continuación, haga lo siguiente:
    
      - Para usar un almacén de SQL Server existente para la creación de reflejo, en el cuadro de lista desplegable **archivado reflejado de SQL Server** , haga clic en el nombre del almacén de SQL Server que desea usar para el reflejo.
    
      - Para especificar un nuevo almacén de SQL Server para la creación de reflejo, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , realice una de las siguientes acciones:
        
        1.  En **FQDN de SQL Server**, especifique el nombre completo del servidor SQL Server en el que desea crear el nuevo almacén de SQL Server.
        
        2.  Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.
        
        3.  Si la instancia de SQL Server especificada tiene una relación de creación de reflejos, seleccione la casilla **de verificación esta instancia de SQL está en relación de creación de reflejo** y, a continuación, en número de puerto de **réplica**, especifique el número de puerto.
    
      - Si habilita el reflejo de SQL Server y desea incluir un testigo de reflejo de SQL Server (una tercera, instancia independiente de SQL Server que puede detectar el estado del servidor SQL Server principal y de las instancias reflejadas), seleccione la casilla **usar el testigo de reflejo de SQL Server para habilitar la conmutación por error automática** y, a continuación, siga uno de estos procedimientos:
        
        1.  En **FQDN de SQL Server**, especifique el nombre completo del servidor en el que desea crear el nuevo testigo de reflejo de SQL Server.
        
        2.  Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar para el testigo de reflejo.
        
        3.  Si la instancia de SQL Server especificada tiene una relación de creación de reflejos, seleccione la casilla **de verificación esta instancia de SQL está en relación de creación de reflejo** y, a continuación, en número de puerto de **réplica**, especifique el número de puerto.

10. Para guardar la configuración, haga clic en **Aceptar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

