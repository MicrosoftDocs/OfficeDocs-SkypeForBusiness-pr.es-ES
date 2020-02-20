---
title: 'Lync Server 2013: cambiar las opciones de base de datos de archivado'
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
ms.openlocfilehash: a8961b33a7b576559115c3afaa36e07b795d69ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a>Cambiar las opciones de base de datos de archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Si implementa el archivado con el almacenamiento de SQL Server para el almacenamiento de archivado para cualquiera de sus usuarios, puede realizar los siguientes cambios en el almacenamiento de la base de datos:

  - Use una base de datos de SQL Server diferente para el almacenamiento de archivado. Esto incluye la base de datos de archivado principal y cualquier base de datos que use para la creación de reflejo de SQL Server.

  - Cambie a la integración de Microsoft Exchange para almacenar los datos y archivos de archivado en servidores de Exchange 2013. Si todos los usuarios están hospedados en los servidores de Exchange 2013 y desea usar el almacenamiento de Microsoft Exchange para todos los usuarios de la implementación, debe quitar las bases de datos de almacén de SQL Server de la topología.

Para realizar cualquiera de estos cambios, debe ejecutar el generador de topologías, realizar los cambios y, a continuación, volver a publicar la topología. Puede usar el generador de topologías para hacerlo. No especifique el **almacén de SQL Server de archivado** ni habilite la información de **reflejo del almacén de SQL Server** , a menos que tenga usuarios de Lync que no estén hospedados en servidores de Exchange 2013.

<div>

## <a name="to-change-your-archiving-database-option"></a>Cambiar la opción de la base de datos de archivado

1.  En un equipo que ejecuta Lync Server 2013 o en el que están instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo de usuarios locales (o una cuenta con derechos de usuario equivalentes).
    
    <div>
    

    > [!NOTE]  
    > Puede definir una topología con una cuenta que sea miembro del grupo de usuarios locales, pero para publicar una topología, que es necesaria para agregar un componente a la topología. debe usar una cuenta que sea miembro del grupo <STRONG>administradores de dominio</STRONG> y del grupo <STRONG>RTCUniversalServerAdmins</STRONG> , y que tenga permisos de control total (es decir, lectura, escritura y modificación) en el recurso compartido de archivos que usa para el almacén de archivos de Lync Server 2013 (es decir, el generador de topologías puede configurar las listas de control de acceso discrecional necesarias ( DACL) o una cuenta con derechos equivalentes.

    
    </div>

2.  Inicie el Generador de topologías.

3.  En el árbol de consola, explore el grupo de servidores front-end en los que ha implementado el servidor de archivado y, a continuación, haga clic en el nombre del grupo de servidores front-end al que quiere modificar las opciones de la base de datos.

4.  En el menú **Acción**, haga clic en **Editar propiedades**.

5.  En el cuadro de diálogo **Editar propiedades**, haga clic en **General**.

6.  Desplácese hacia abajo hasta **Servidor de archivado**.

7.  En **Servidor de archivado**, haga lo siguiente:
    
      - Para cambiar a un almacén de SQL Server existente diferente, en  **Almacén SQL Server de archivado**, en el cuadro de desplegable, haga lo siguiente:
        
          - Para usar un almacén de  SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar.
        
          - Para especificar un nuevo almacén de SQL Server, haga clic en **Nuevo** y en el cuadro de diálogo **Definir un nuevo almacén de SQL Server** lleve a cabo lo siguiente:
            
              - Para usar un almacén de  SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar.
            
              - Para especificar un nuevo almacén de SQL Server, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , haga lo siguiente:
                
                  - En **FQDN de SQL Server**, especifique el nombre de dominio completo (FQDN) del servidor en el que desea crear el nuevo almacén de SQL Server.
                
                  - Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en  **Instancia con nombre ** y especifique la instancia que desee usar.
                
                  - Si la instancia de SQL Server especificada está en una relación de creación de reflejo, active la casilla **esta instancia de SQL está en relación de reflejo** y, a continuación, en **número de puerto de reflejo**, especifique el número de puerto.
    
      - Para agregar un almacén de SQL Server para la creación de reflejos o para cambiar a un almacén de SQL Server existente diferente para la creación de reflejos del almacén de SQL Server, seleccione **Permitir creación de reflejos del almacén de SQL Server** y, a continuación, haga lo siguiente:
        
          - Para usar un almacén de SQL Server existente para la creación de reflejos, en el cuadro de lista desplegable **archivado de reflejo de almacén de SQL Server** , haga clic en el nombre del almacén de SQL Server que desee usar para la creación de reflejo.
        
          - Para especificar un nuevo almacén de SQL Server para la creación de reflejos, haga clic en **nuevo**y, a continuación, en el cuadro de diálogo **definir nuevo almacén de SQL Server** , realice una de las siguientes acciones:
            
            1.  En **FQDN de SQL Server**, especifique el nombre de dominio completo (FQDN) del SQL Server en el que desea crear el nuevo almacén de SQL Server.
            
            2.  Haga clic en **Instancia predeterminada** para utilizar la instancia predeterminada o, para especificar una instancia diferente, haga clic en **Instancia denominada** y, a continuación, haga clic en la instancia que desee utilizar.
            
            3.  Si la instancia de SQL Server especificada está en una relación de creación de reflejo, active la casilla **esta instancia de SQL está en relación de reflejo** y, a continuación, en **número de puerto de reflejo**, especifique el número de puerto.
        
          - Si habilita la creación de reflejos de SQL Server y desea agregar o cambiar un testigo de creación de reflejos de SQL Server (una tercera y distinta instancia de SQL Server que pueda detectar el estado del servidor SQL Server principal y de las instancias reflejadas), active la casilla **usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación automática por error**
            
            1.  En **FQDN de SQL Server**, especifique el FQDN del servidor en el que desea crear el nuevo testigo de creación de reflejos de SQL Server.
            
            2.  Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en  **Instancia con nombre ** y especifique la instancia que desee usar para el testigo de reflejo.
            
            3.  Si la instancia de SQL Server especificada está en una relación de creación de reflejo, active la casilla **esta instancia de SQL está en relación de reflejo** y, a continuación, en **número de puerto de reflejo**, especifique el número de puerto.
    
      - Para cambiar a la integración de Microsoft Exchange para almacenar los datos y los archivos de archivado en servidores de Exchange 2013 (si todos los usuarios de la implementación están alojados en los servidores de Exchange 2013), elimine toda la información de las bases de datos de archivado.
    
    <div>
    

    > [!IMPORTANT]  
    > Si tiene usuarios de Lync que no están hospedados en servidores de Exchange 2013, no elimine la información del almacén de SQL Server.

    
    </div>

8.  Para guardar la configuración, haga clic en **Aceptar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Los cambios que realice en el generador de topologías no surtirán efecto hasta que publique la nueva topología. Para obtener más información, consulte <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">publicación de la topología actualizada para agregar bases de datos de archivado en Lync Server 2013</A> en la documentación sobre implementación.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

