---
title: 'Lync Server 2013: adición de bases de datos de archivado a la topología de Lync Server 2013'
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
ms.openlocfilehash: e73fe49aaf3a5b90a23bcfd6b99c9a5bb4476513
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a>Adición de bases de datos de archivado a la topología de 2013 de Lync Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-10_

Debe incorporar el archivado a la topología para poder configurar la implementación a fin de admitir el archivado. La información de este tema explica cómo usar el generador de topologías para agregar archivado a la topología existente.

<div>


> [!NOTE]  
> Si desea usar la integración de Microsoft Exchange para almacenar los datos y los archivos de archivado en servidores de Exchange 2013 para todos los usuarios de la implementación, no especifique el <STRONG>almacén de SQL Server de archivado</STRONG> ni use la información de <STRONG>reflejo de almacén de SQL Server</STRONG> .



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a>Para agregar la compatibilidad de base de datos de archivado a la topología

1.  En un equipo que ejecuta Lync Server 2013 o en el que están instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo de usuarios locales (o una cuenta con derechos de usuario equivalentes).
    
    <div>
    

    > [!NOTE]  
    > Puede definir una topología con una cuenta que sea miembro del grupo de usuarios locales, pero para publicar una topología, que es necesaria para agregar un servidor a la topología. debe usar una cuenta que sea miembro del grupo <STRONG>administradores de dominio</STRONG> y del grupo <STRONG>RTCUniversalServerAdmins</STRONG> , y que tenga permisos de control total (es decir, lectura, escritura y modificación) en el recurso compartido de archivos que está usando para el almacén de archivos de Lync Server 2013 (es decir, el generador de topología puede configurar la lista de control de acceso discrecional (DACL) requerida. o una cuenta con derechos equivalentes.

    
    </div>

2.  Inicie el Generador de topologías.

3.  En el árbol de consola, vaya al grupo de servidores front-end en el que desee implementar el archivado y haga clic en el nombre de dicho grupo.

4.  En el menú **Acción**, haga clic en **Editar propiedades**.

5.  En el cuadro de diálogo **Editar propiedades**, haga clic en **General**.

6.  Desplácese a  **Archivado**.

7.  Seleccione la casilla **Archivado**.

8.  En **almacén de SQL Server de archivado,** realice una de las siguientes acciones:
    
      - Para usar un almacén de  SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar. Si todos los usuarios están hospedados en Microsoft Exchange Server 2013 o posterior, puede archivar las comunicaciones de Lync para todos los usuarios de Exchange. En este caso, no es necesario configurar el almacén de archivado de SQL Server.
    
      - Para especificar un nuevo almacén de SQL Server, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , haga lo siguiente:
        
          - En **FQDN de SQL Server**, especifique el nombre de dominio completo (FQDN) del servidor en el que desea crear el nuevo almacén de SQL Server.
        
          - Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en  **Instancia con nombre ** y especifique la instancia que desee usar.
        
          - Si la instancia de SQL Server especificada está en una relación de creación de reflejo, active la casilla **esta instancia de SQL está en relación de reflejo** y, a continuación, en **número de puerto de reflejo**, especifique el número de puerto.

9.  Si desea usar la creación de reflejos del almacén de SQL Server, seleccione **Habilitar creación de reflejos del almacén de SQL Server**y, a continuación, haga lo siguiente:
    
      - Para usar un almacén de SQL Server existente para la creación de reflejos, en el cuadro de lista desplegable **archivado de reflejo de almacén de SQL Server** , haga clic en el nombre del almacén de SQL Server que desee usar para la creación de reflejo.
    
      - Para especificar un nuevo almacén de SQL Server para la creación de reflejos, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , realice una de las siguientes acciones:
        
        1.  En **FQDN de SQL Server**, especifique el nombre de dominio completo (FQDN) del SQL Server en el que desea crear el nuevo almacén de SQL Server.
        
        2.  Haga clic en **Instancia predeterminada** para utilizar la instancia predeterminada o, para especificar una instancia diferente, haga clic en **Instancia denominada** y, a continuación, haga clic en la instancia que desee utilizar.
        
        3.  Si la instancia de SQL Server especificada está en una relación de creación de reflejo, active la casilla **esta instancia de SQL está en relación de reflejo** y, a continuación, en **número de puerto de reflejo**, especifique el número de puerto.
    
      - Si habilita la creación de reflejos de SQL Server y desea incluir un testigo de creación de reflejos de SQL Server (una tercera y distinta instancia de SQL Server que pueda detectar el estado del servidor SQL Server principal y las instancias reflejadas), active la casilla **usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación por error automática** y, a continuación, siga uno de estos procedimientos
        
        1.  En **FQDN de SQL Server**, especifique el FQDN del servidor en el que desea crear el nuevo testigo de creación de reflejos de SQL Server.
        
        2.  Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en  **Instancia con nombre ** y especifique la instancia que desee usar para el testigo de reflejo.
        
        3.  Si la instancia de SQL Server especificada está en una relación de creación de reflejo, active la casilla **esta instancia de SQL está en relación de reflejo** y, a continuación, en **número de puerto de reflejo**, especifique el número de puerto.

10. Para guardar la configuración, haga clic en **Aceptar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

