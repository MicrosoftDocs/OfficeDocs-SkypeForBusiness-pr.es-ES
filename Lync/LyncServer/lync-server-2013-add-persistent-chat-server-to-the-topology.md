---
title: 'Lync Server 2013: agregar un servidor de chat persistente a la topología'
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
ms.openlocfilehash: b857c63b08906ada2cee2611960717f97e7a3cc1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a>Agregar un servidor de chat persistente a la topología en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-06_

Debe incorporar Lync Server 2013, la compatibilidad con el servidor de chat persistente en su topología antes de configurar la implementación para que admita el servidor de chat persistente. La información de este tema describe cómo usar el generador de topologías para agregar compatibilidad con el servidor de chat persistente a la topología existente.

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a>Para agregar un servidor de chat persistente a una topología

Realice los siguientes pasos para instalar un único grupo de servidores de chat persistente sin una configuración de recuperación ante desastres. Para configurar un grupo de servidores de chat persistente estirado para alta disponibilidad y recuperación ante desastres, consulte [Configuring persistent chat Server for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) en la documentación sobre implementación.

Para implementar varios grupos de servidores de chat persistente, repita el mismo proceso para cada grupo.

1.  En un equipo que ejecuta Lync Server 2013 o en el que están instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo de usuarios locales (o una cuenta con derechos de usuario equivalentes).
    
    <div>
    

    > [!NOTE]  
    > Puede definir una topología con una cuenta que sea miembro del grupo de usuarios locales, pero para publicar una topología, necesaria para instalar un servidor de Lync Server 2013. debe usar una cuenta que sea miembro del grupo <STRONG>administradores de dominio</STRONG> y del grupo <STRONG>RTCUniversalServerAdmins</STRONG> , y que tenga permisos de control total (es decir, lectura, escritura y modificación) en el almacén de archivos que va a usar para el almacén de archivos del servidor de chat persistente (es decir, el generador de topologías puede configurar las DACL necesarias) o una cuenta con derechos equivalentes.

    
    </div>

2.  Inicie el Generador de topologías.

3.  En el árbol de la consola, vaya al nodo **grupos de chat persistentes** y expándalo para seleccionar un grupo de servidores de chat persistente, o haga clic con el botón secundario en el nodo y seleccione **nuevo grupo de chat persistente**. Deberá definir el nombre de dominio completo (FQDN) del grupo, e indicar si el grupo será la implementación de un grupo de un único servidor o de un grupo de varios servidores.
    
    Puede elegir un **Grupo de varios PC** o **Grupo de un PC**. Elija el primero si tiene previsto tener más de un servidor de servidor de chat persistente en su grupo de servidores de chat persistente. Realice esta elección ahora, o luego, debido a que después de crear un solo grupo de PC no podrá agregar servidores adicionales más adelante. Si elige un grupo de varios equipos, escriba los nombres de los servidores front-end de servidor de chat persistente individuales que componen el grupo.
    
    <div>
    

    > [!IMPORTANT]  
    > Si se está instalando el rol de servidor de chat persistente en un&nbsp;servidor de Lync Server 2013 Standard Edition, el FQDN debe coincidir con el FQDN del servidor Standard Edition.

    
    </div>

4.  Definir un **nombre para mostrar** sencillo para el grupo de servidores de chat persistente. Los clientes personalizados pueden usar el nombre para mostrar, especialmente cuando hay varios grupos de servidores de chat persistente, para diferenciar las salas.

5.  Definir el puerto usado por el servidor de chat persistente para comunicarse con los servidores front-end de Lync Server. El puerto predeterminado es 5041.

6.  Si su organización requiere compatibilidad con el cumplimiento, seleccione la casilla **Habilitar cumplimiento**. Si se elige, el servicio de cumplimiento del servidor de chat persistente se instala en el mismo equipo que el servidor front-end del servidor de chat persistente. Más adelante, se le pedirá que seleccione un servidor back-end de SQL Server para el cumplimiento del servidor de chat persistente.

7.  Asigne la afinidad de sitios para el grupo de servidores de chat persistente. Active la casilla de verificación **usar este grupo de \<servidores\> como predeterminado para el sitio siteName** o **use este grupo de servidores como predeterminado para todos los sitios** para designar este grupo de servidores de chat persistente como grupo predeterminado para el sitio actual o todos los sitios. Cuando se usa el cliente de Lync 2013 para crear y administrar salones, la experiencia de creación y administración de la sala usa el grupo de servidores predeterminado asociado al sitio del usuario, de modo que pueda redirigir las operaciones de creación y administración de salas a ese grupo. Esto solo se aplica cuando se implementan varios grupos de servidores de chat persistente y se desea usar las características de creación y administración de salas del servidor de chat persistente.
    
    <div>
    

    > [!IMPORTANT]  
    > Puede personalizar las características de creación y administración de salas con el kit de desarrollo de software (SDK) del servidor de chat persistente.<BR>Para obtener más información sobre cómo configurar las bases de datos de copia de seguridad de SQL Server para la recuperación ante desastres, consulte <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring persistent chat Server for High Availability and Disaster Recovery in Lync Server 2013</A> en la documentación sobre implementación.

    
    </div>

8.  Defina el **almacén de SQL para el back-end del servidor de chat persistente (donde se almacena el contenido del salón de chat)** mediante uno de los siguientes procedimientos:
    
      - Para usar una base de datos de SQL Server existente, en la lista desplegable, haga clic en el nombre de la base de datos de SQL Server que desee usar.
    
      - Para especificar una nueva base de datos de SQL Server, haga clic en **nuevo**y, en **definir nuevo almacén de SQL**, realice lo siguiente:
    
    <!-- end list -->
    
      - En **FQDN de SQL Server**, especifique el FQDN del servidor SQL Server en el que desea crear la nueva base de datos de SQL Server.
    
      - Puede seleccionar **Instancia predeterminada** para utilizar la instancia predeterminada, o bien, para especificar una instancia diferente, seleccione **Instancia con nombre** y, a continuación, especifique la instancia que desee utilizar.

9.  Defina la base de datos de cumplimiento de SQL Server si ha habilitado el cumplimiento.
    
    <div>
    

    > [!IMPORTANT]  
    > Para obtener más información sobre cómo configurar reflejos de SQL Server para alta disponibilidad de la base de datos del servidor de chat persistente y la base de datos de cumplimiento del servidor de chat persistente, vea <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring persistent chat Server for High Availability and Disaster Recovery in Lync Server 2013</A> en la documentación sobre implementación.

    
    </div>

10. Defina el almacén de archivos. Un almacén de archivos es una carpeta en la que se almacena una copia de cualquier archivo cargado al repositorio de archivos, por ejemplo, el almacenamiento de datos adjuntos de archivos publicados en una de chat. En el caso de una topología de servidor de chat persistente de varios servidores, debe ser una ruta de acceso de Convención de nomenclatura universal (UNC); para una topología de servidor de chat persistente de un solo servidor, puede ser una ruta de acceso de archivo local.
    
    Para utilizar un almacén de archivos existente, realice los siguientes pasos:
    
      - En el **FQDN del servidor de archivos**, especifique el FQDN del almacén de archivos en el que desee crear el nuevo almacén de archivos.
    
      - En **Recurso compartido de archivos**, especifique el almacén de archivos que desee utilizar.
    
    <div>
    

    > [!IMPORTANT]  
    > Puede definir el almacén de archivos en Topology Builder antes de crear el almacén de archivos, pero debe crear el almacén de archivos en la ubicación definida que defina antes de publicar la topología.

    
    </div>

11. Seleccione el grupo de servidores front-end que se usará como próximo salto para este grupo de servidores de chat persistente. Se trata del grupo de servidores front-end que podrá enrutar las solicitudes del servidor de chat persistente a este grupo.

12. Para guardar la configuración, haga clic en **Finalizar**. El grupo de servidores de chat persistente aparece en Topology Builder junto con la configuración específica del grupo de servidores.
    
    Para publicar ahora la topología actualizada a la que tiene el servidor de chat persistente, vea [Publish The Updated Topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) en la documentación sobre implementación.
    
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

