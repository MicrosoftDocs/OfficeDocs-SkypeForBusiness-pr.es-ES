---
title: 'Lync Server 2013: cambiar las opciones de la base de datos de archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 198e2abff6118197167f0f017ace22fc2ad76381
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a>Cambiar las opciones de base de datos de archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Si implementa el archivado con almacenamiento de SQL Server para archivar el almacenamiento de cualquiera de los usuarios, puede realizar los siguientes cambios de almacenamiento en la base de datos:

  - Use una base de datos de SQL Server diferente para archivar almacenamiento. Esto incluye la base de datos de archivado principal y cualquier base de datos que use para el reflejo de SQL Server.

  - Cambie a la integración de Microsoft Exchange para almacenar datos y archivos en servidores de Exchange 2013. Si todos los usuarios están alojados en los servidores de Exchange 2013 y desea usar el almacenamiento de Microsoft Exchange para todos los usuarios de su implementación, debe quitar las bases de datos del almacén de SQL Server de su topología.

Para realizar alguno de estos cambios, debe ejecutar el generador de topología, realizar los cambios y, a continuación, volver a publicar la topología. Puede usar el generador de topología para hacerlo. No especifique el **archivado de SQL Server Store** ni habilitar la información de reflejo de la **tienda de SQL Server** , a menos que tenga usuarios de Lync que no estén alojados en servidores de Exchange 2013.

<div>

## <a name="to-change-your-archiving-database-option"></a>Cambiar la opción de base de datos de archivado

1.  En un equipo que ejecute Lync Server 2013 o en el que estén instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo usuarios locales (o una cuenta con derechos de usuario equivalentes).
    
    <div>
    

    > [!NOTE]  
    > Puede definir una topología con una cuenta que sea miembro del grupo usuarios locales, pero para publicar una topología, que es necesaria para agregar un componente a la topología. debe usar una cuenta que sea miembro del grupo <STRONG>administradores de dominio</STRONG> y el grupo <STRONG>RTCUniversalServerAdmins</STRONG> , y que tenga permisos de control total (es decir, leer, escribir y modificar) en el recurso compartido de archivos de Lync Server 2013 (es decir, para que el generador de topología pueda configurar las listas de control de acceso discrecional obligatorias ( DACL) o una cuenta con derechos equivalentes.

    
    </div>

2.  Iniciar el generador de topología.

3.  En el árbol de consola, explore el grupo de servidores front-end en los que ha implementado el servidor de archivado y, luego, haga clic en el nombre del grupo de servidores front-end al que quiere modificar las opciones de la base de datos.

4.  En el menú **Acción**, haga clic en **Editar propiedades**.

5.  En el cuadro de diálogo **Editar propiedades**, haga clic en **General**.

6.  Desplácese hacia abajo hasta **Archivado**.

7.  En **Archivado**, haga lo siguiente:
    
      - Para cambiar a otro almacén de SQL Server existente, en **Almacén SQL Server de archivado**, en el cuadro de desplegable, haga lo siguiente:
        
          - Para usar un almacén de SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar.
        
          - Para especificar un nuevo almacén de SQL Server, haga clic en **Nuevo** y, en el cuadro de diálogo **Definir un nuevo almacén de SQL Server**, haga lo siguiente:
            
              - Para usar un almacén de SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar.
            
              - Para especificar un nuevo almacén de SQL Server, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , haga lo siguiente:
                
                  - En **FQDN de SQL Server**, especifique el nombre completo del servidor en el que desea crear el nuevo almacén de SQL Server.
                
                  - Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.
                
                  - Si la instancia de SQL Server especificada tiene una relación de creación de reflejos, seleccione la casilla **de verificación esta instancia de SQL está en relación de creación de reflejo** y, a continuación, en número de puerto de **réplica**, especifique el número de puerto.
    
      - Para agregar un almacén de SQL Server para la creación de reflejos o para cambiar a un almacén de SQL Server existente diferente para la creación de reflejos del almacén de SQL Server, seleccione **Permitir creación de reflejos del almacén de SQL Server** y, luego, haga lo siguiente:
        
          - Para usar un almacén de SQL Server existente para la creación de reflejo, en el cuadro de lista desplegable **archivado reflejado de SQL Server** , haga clic en el nombre del almacén de SQL Server que desea usar para el reflejo.
        
          - Para especificar un nuevo almacén de SQL Server para la creación de reflejo, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , realice una de las siguientes acciones:
            
            1.  En **FQDN de SQL Server**, especifique el nombre completo del servidor SQL Server en el que desea crear el nuevo almacén de SQL Server.
            
            2.  Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.
            
            3.  Si la instancia de SQL Server especificada tiene una relación de creación de reflejos, seleccione la casilla **de verificación esta instancia de SQL está en relación de creación de reflejo** y, a continuación, en número de puerto de **réplica**, especifique el número de puerto.
        
          - Si habilita el reflejo de SQL Server y quiere agregar o cambiar un testigo de reflejo de SQL Server (una tercera, instancia independiente de SQL Server que puede detectar el estado del servidor SQL Server principal y las instancias reflejadas), seleccione la casilla de verificación **usar el testigo de reflejo de SQL Server para habilitar la conmutación por error automática** y, a continuación, siga uno de estos procedimientos:
            
            1.  En **FQDN de SQL Server**, especifique el nombre completo del servidor en el que desea crear el nuevo testigo de reflejo de SQL Server.
            
            2.  Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar para el testigo de reflejo.
            
            3.  Si la instancia de SQL Server especificada tiene una relación de creación de reflejos, seleccione la casilla **de verificación esta instancia de SQL está en relación de creación de reflejo** y, a continuación, en número de puerto de **réplica**, especifique el número de puerto.
    
      - Para cambiar a la integración de Microsoft Exchange para almacenar datos y archivos en servidores de Exchange 2013 (si todos los usuarios de su implementación están alojados en los servidores de Exchange 2013), elimine toda la información para archivar bases de datos.
    
    <div>
    

    > [!IMPORTANT]  
    > Si tiene usuarios de Lync que no estén alojados en servidores de Exchange 2013, no elimine la información de la tienda SQL Server.

    
    </div>

8.  Para guardar la configuración, haga clic en **Aceptar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Los cambios que haga en el generador de topología no se aplicarán hasta que publique la nueva topología. Para obtener más información, vea <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">publicación de la topología actualizada para agregar bases de datos de archivado en Lync Server 2013</A> en la documentación de implementación.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

