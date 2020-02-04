---
title: 'Lync Server 2013: Agregar un servidor de chat persistente a la topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53f8c65f561a0f2c7b1937d60344c0177d221ba8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a>Agregar un servidor de chat persistente a la topología en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

Debe incorporar Lync Server 2013, la compatibilidad con el servidor de chat persistente en su topología antes de configurar su implementación para que admita el servidor de chat persistente. La información de este tema describe cómo usar el generador de topologías para agregar la compatibilidad con el servidor de chat persistente a su topología existente.

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a>Para agregar un servidor de chat persistente a una topología

Siga estos pasos para instalar un único grupo de servidores de chat persistente sin una configuración de recuperación ante desastres. Para configurar un grupo de servidores de chat persistente ampliado para una alta disponibilidad y recuperación ante desastres, vea [configurar el servidor de chat persistente para una alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) en la documentación de implementación.

Para implementar varios grupos de servidores de chat persistentes, repita el mismo proceso para cada grupo.

1.  En un equipo que ejecute Lync Server 2013 o en el que estén instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo usuarios locales (o una cuenta con derechos de usuario equivalentes).
    
    <div>
    

    > [!NOTE]  
    > Puede definir una topología con una cuenta que sea miembro del grupo usuarios locales, pero para publicar una topología, que es necesaria para instalar un servidor de Lync Server 2013, debe usar una cuenta que sea miembro del grupo de <STRONG>administradores del dominio</STRONG> y el grupo <STRONG>RTCUniversalServerAdmins</STRONG> , y que tenga permisos de control total (es decir, leer, escribir y modificar) en el almacén de archivos que va a usar para el almacén de archivos del servidor de chat persistente (es decir, para que el generador de topología pueda configurar las DACL obligatorias) o una cuenta con derechos equivalentes.

    
    </div>

2.  Iniciar el generador de topología.

3.  En el árbol de consola, vaya al nodo **grupos de chats persistentes** y expándalo para seleccionar un grupo de servidores de chat persistente, o haga clic con el botón derecho en el nodo y seleccione **nuevo grupo de chats persistentes**. You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.
    
    Puede elegir un **Grupo de varios equipos** o **Grupo de un solo equipo**. Elija el primero si está planeando tener más de un servidor de usuario de chat persistente en el grupo de servidores de chat persistente. Realice esta elección ahora, porque después de crear un grupo de un solo equipo no le podrá agregar servidores adicionales más adelante. Si elige un grupo de varios equipos, escriba los nombres de los servidores de cliente de la conversación persistente que forman el grupo.
    
    <div>
    

    > [!IMPORTANT]  
    > Si el rol de servidor de chat persistente se instala en un servidor de&nbsp;Lync Server 2013 Standard Edition, el FQDN debe coincidir con el FQDN del servidor Standard Edition.

    
    </div>

4.  Defina un **nombre para mostrar** simple para el grupo de servidores de chat persistente. El nombre para mostrar puede ser usado por clientes personalizados, especialmente cuando hay varios grupos de servidores de chat persistentes, para diferenciar las habitaciones.

5.  Defina el puerto que usa el servidor de chat persistente para comunicarse con los servidores front-end de Lync Server. El puerto predeterminado es 5041.

6.  Si su organización requiere compatibilidad con el cumplimiento, seleccione la casilla **Habilitar cumplimiento**. Si se elige, el servicio de cumplimiento de servidor de chat persistente se instala en el mismo equipo que el servidor de front-end del servidor de chat persistente. Se le pedirá que seleccione un servidor Back End SQL Server para el cumplimiento del servidor de chat persistente más adelante.

7.  Asigne afinidad de sitio para el grupo de servidores de chat persistente. Active la casilla de verificación **usar este grupo como \<predeterminado\> para el sitio siteName** o **use este grupo como predeterminado para que todos los sitios** designen este grupo de servidores de chat persistente como el grupo predeterminado para el sitio actual o todos los sitios. Cuando se usa el cliente de Lync 2013 para crear y administrar salas, la experiencia de creación y administración de la sala usa el grupo predeterminado asociado al sitio del usuario para que pueda dirigir las operaciones de administración y creación de salas a ese grupo. Esto solo se aplica cuando se han implementado varios grupos de servidores de chat persistentes y desea usar las características de creación y administración de la sala de un servidor de chat persistente.
    
    <div>
    

    > [!IMPORTANT]  
    > Puede personalizar las características de creación y administración de la sala con el kit de desarrollo de software (SDK) del servidor de chat persistente.<BR>Para obtener más información sobre cómo configurar las bases de datos de copia de seguridad de SQL Server para la recuperación ante desastres, vea <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">configurar el servidor de chat persistente para una alta disponibilidad y recuperación ante desastres en Lync Server 2013</A> en la documentación de implementación.

    
    </div>

8.  Defina el **almacén SQL para el back-end del servidor de chat persistente (donde se almacena el contenido del salón de chat)** mediante uno de los siguientes procedimientos:
    
      - Para usar una base de datos de SQL Server existente, en la lista desplegable, haga clic en el nombre de la base de datos de SQL Server que desea usar.
    
      - Para especificar una nueva base de datos de SQL Server, haga clic en **nuevo**y, en **definir nueva tienda SQL**, realice lo siguiente:
    
    <!-- end list -->
    
      - En **FQDN de SQL Server**, especifique el nombre completo del servidor SQL Server en el que desea crear la nueva base de datos de SQL Server.
    
      - Puede seleccionar **Instancia predeterminada** para utilizar la instancia predeterminada, o bien, para especificar una instancia diferente, seleccione **Instancia con nombre** y, luego, especifique la instancia que desee utilizar.

9.  Defina la base de datos de cumplimiento de SQL Server si ha habilitado la compatibilidad.
    
    <div>
    

    > [!IMPORTANT]  
    > Para obtener más información sobre cómo configurar espejos de SQL Server para una alta disponibilidad de la base de datos del servidor de chat persistente y la base de datos de cumplimiento del servidor de chat persistente, vea <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">configurar el servidor de chat persistente para una alta disponibilidad y recuperación ante desastres en Lync Server 2013</A> en la documentación de implementación.

    
    </div>

10. Defina el almacén de archivos. Un almacén de archivos es una carpeta en la que se almacena una copia de cualquier archivo cargado al repositorio de archivos (por ejemplo, el almacenamiento de datos adjuntos de archivos publicados en un salón de chat). En el caso de una topología de servidor de chat persistente de varios servidores, debe ser una ruta de acceso UNC (Convención de nomenclatura universal); para una topología de servidor de chat persistente de un solo servidor, puede ser una ruta de acceso de archivo local.
    
    Para utilizar un almacén de archivos existente, haga lo siguiente:
    
      - En **FQDN del servidor de archivos**, especifique el FQDN del almacén de archivos en el que desea crear el nuevo almacén de archivos.
    
      - En **Recurso compartido de archivos**, especifique el almacén de archivos que desee utilizar.
    
    <div>
    

    > [!IMPORTANT]  
    > Puede definir el almacén de archivos en el generador de topología antes de crear el almacén de archivos, pero debe crear el almacén de archivos en la ubicación definida que defina antes de publicar la topología.

    
    </div>

11. Seleccione el grupo de servidores front-end que se usará como próximo salto para este grupo de servidores de chat persistente. Este es el grupo de servidores front-end que podrá enrutar solicitudes de servidor de chat persistentes a este grupo.

12. Para guardar la configuración, haga clic en **Finalizar**. El grupo de servidores de chat persistente aparece en el generador de topología junto con la configuración específica de la agrupación.
    
    Para publicar su topología actualizada a la que tiene el servidor de chat persistente, vea [publicar la topología actualizada en Lync server 2013](lync-server-2013-publish-the-updated-topology.md) en la documentación de implementación.
    
    <div>
    

    > [!NOTE]  
    > Con el generador de topología ya abierto, puede continuar con el paso 3 en <A href="lync-server-2013-publish-the-updated-topology.md">publicar la topología actualizada en Lync Server 2013</A> para empezar a publicar su topología actualizada.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

