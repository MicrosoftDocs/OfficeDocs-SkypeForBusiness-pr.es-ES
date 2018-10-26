---
title: "Lync Server 2013 : Ajout d’un serv. de conv. permanente à la topologie"
TOCTitle: Agregar un servidor de chat persistente a la topología
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48275877
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Agregar un servidor de chat persistente a la topología en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-06_

Debe incorporar la compatibilidad de Lync Server 2013, Servidor de chat persistente en su topología antes de configurar su implementación para que sea compatible con Servidor de chat persistente. La información sobre ese tema describe cómo utilizar el Generador de topologías para agregar la compatibilidad con Servidor de chat persistente a su topología existente.

## Adición de un Servidor de chat persistente a una topología

Realice los pasos siguientes para la instalación de un único Grupo de servidores de chat persistente sin la configuración para la recuperación de desastres. Para configurar un Grupo de servidores de chat persistente ampliado de alta disponibilidad y recuperación de desastres, consulte [Configurar servidores de chat persistente para la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) en la documentación de implementación.

Para implementar varios grupos de Grupos de servidores de chat persistente, repita el mismo proceso para cada grupo.

1.  En un equipo que se ejecuta en Lync Server 2013 o en el que están instaladas las herramientas administrativas de Lync Server, inicie sesión utilizando una cuenta que sea miembro del grupo de usuarios locales (o una cuenta con derechos de autor equivalentes).
    

    > [!NOTE]
    > Puede definir una topología utilizando una cuenta que sea miembro de un grupo de usuarios locales, pero para publicar una topología, que se requiere para instalar un servidor Lync Server 2013, debe utilizar una cuenta que sea miembro del grupo de <STRONG>Administradores de dominio</STRONG> y del grupo <STRONG>RTCUniversalServerAdmins</STRONG>, y que tenga todos los permisos de control (es decir, de lectura, de escritura y de modificación) sobre el almacén de archivos que va a utilizar para el almacén de archivos de Servidor de chat persistente (es decir, de modo que Generador de topologías pueda configurar los DACL necesarios), o una cuenta con derechos equivalentes.



2.  Inicie Generador de topologías.

3.  En el árbol de la consola, vaya al nodo **GrupoChat persistente** y amplíelo para seleccionar un Grupo de servidores de chat persistente o haga clic con el botón derecho en el nodo y seleccione **Nuevo grupo Chat persistente**. Deberá definir el nombre de dominio completo (FQDN) del grupo, e indicar si el grupo será la implementación de un grupo de un único servidor o de un grupo de varios servidores.
    
    Puede elegir un **Grupo de varios PC** o **Grupo de un PC** . Elija el último si está planeando tener más de un Servidor de chat persistenteServidor front-end en su Grupo de servidores de chat persistente. Realice esta elección ahora, o luego, debido a que después de crear un solo grupo de PC no podrá agregar servidores adicionales más adelante. Si elige un grupo de varios PC, escriba los nombres de los Servidor de chat persistenteServidores front-end individuales que componen el grupo.
    
    > [!IMPORTANT]  
    > Si el rol Servidor de chat persistente está instalado en un Lync Server 2013Servidor Standard Edition, el FQDN debe coincidir con el FQDN del Servidor Standard Edition.
    


4.  Defina un solo **Nombre para mostrar** para el Grupo de servidores de chat persistente. El nombre de visualización puede utilizarse para clientes personalizados, especialmente cuando hay varios Grupos de servidores de chat persistente, para diferenciar las salas.

5.  Defina el puerto usado por el Servidor de chat persistente para comunicarse con Lync ServerServidores front-end. El puerto predeterminado es 5041.

6.  Si su organización requiere compatibilidad con el cumplimiento, seleccione la casilla **Habilitar cumplimiento** . Si está seleccionada, el servicio de cumplimiento Servidor de chat persistente se instala en el mismo equipo que el Servidor de chat persistenteServidor front-end. Luego se le solicitará que seleccione un SQL ServerServidor back-end para el cumplimiento de Servidor de chat persistente

7.  Asigne la afinidad del sitio para el Grupo de servidores de chat persistente. Seleccione la casilla **Usar este grupo como predeterminado para el sitio \<NombredeSitio\>** o **Usar este grupo como predeterminado para todos los sitios** para designar este Grupo de servidores de chat persistente como el grupo predeterminado para el sitio actual o para todos los sitios. Cuando el cliente Lync 2013 se utiliza para crear y administrar salas, el grupo predeterminado asociado con el sitio del usuario es utilizado por la creación de salas y la experiencia de administración para que pueda enrutar para la creación de salas y las operaciones de administración de ese grupo. Esto solo aplica cuando tiene varios Grupos de servidores de chat persistente implementados y desea usar la creación de salas y características de administración de Servidor de chat persistente.
    
    > [!IMPORTANT]  
    > Puede personalizar la creación de salas y características de administración mediante el Servidor de chat persistente Kit de desarrollo de software (SDK).<br />
    > Para obtener detalles acerca de cómo configurar las bases de datos de respaldo de SQL Server para la recuperación de desastres, vea <a href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configurar servidores de chat persistente para la alta disponibilidad y la recuperación ante desastres en Lync Server 2013</a> en la documentación de implementación.


8.  Defina el **almacén SQL para el servidor back-end de Servidor de chat persistente (donde se almacena el contenido de la sala de chat)** realizando una de las acciones siguientes:
    
      - Para utilizar una base de datos SQL Server, en la lista desplegable, haga clic en el nombre de la base de datos SQL Server que desea utilizar.
    
      - Para especificar una nueva base de datos de SQL Server, haga clic en **Nuevo** y en **Definir nuevo almacén SQL** y haga lo siguiente:
    
    <!-- end list -->
    
      - En el **FQDN del SQL Server** , especifique el FQDN del SQL Server en el que desea crear la nueva base de datos SQL Server.
    
      - Puede seleccionar **Instancia predeterminada** para utilizar la instancia predeterminada, o bien, para especificar una instancia diferente, seleccione **Instancia con nombre** y, a continuación, especifique la instancia que desee utilizar.

9.  Defina la base de datos de cumplimiento de SQL Server si habilitó Cumplimiento.
    
    > [!IMPORTANT]  
    > Para obtener detalles acerca de cómo configurar los espejos SQL Server para alta disponibilidad para la base de datos Servidor de chat persistente y la base de datos de cumplimiento de Servidor de chat persistente, vea <a href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configurar servidores de chat persistente para la alta disponibilidad y la recuperación ante desastres en Lync Server 2013</a> en la documentación de implementación.
    


10. Defina el almacén de archivos. Un almacén de archivos es una carpeta en la que se almacena una copia de cualquier archivo cargado al repositorio de archivos, por ejemplo, el almacenamiento de datos adjuntos de archivos publicados en una de chat. En el caso de una topología Servidor de chat persistente de varios servidores, debe ser una ruta de acceso de convención de nomenclatura universal (UNC); y para una topología de un solo servidor Servidor de chat persistente, puede ser una ruta de archivo local.
    
    Para utilizar un almacén de archivos existente, realice los siguientes pasos:
    
      - En el **FQDN del servidor de archivos** , especifique el FQDN del almacén de archivos en el que desee crear el nuevo almacén de archivos.
    
      - En **Recurso compartido de archivos** , especifique el almacén de archivos que desee utilizar.
    
    > [!IMPORTANT]  
    > Puede definir un almacén de archivos en Generador de topologías antes de crear el almacén de archivos, pero debe crearlo en la ubicación que ha definido antes de publicar la topología.
    


11. Seleccione el grupo Servidor front-end que se utilizará como el próximo paso para este Grupo de servidores de chat persistente. Este es el grupo Servidor front-end que podrá enrutar solicitudes Servidor de chat persistente a este grupo.

12. Para guardar la configuración, haga clic en **Finalizar** . Grupo de servidores de chat persistente aparece en Generador de topologías acompañados por sus configuraciones de grupo específicas.
    
    Para publicar ahora su topología actualizada a la que ha agregado el Servidor de chat persistente, consulte [Publicar la topología actualizada en Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) en la documentación de implementación.
    

    > [!NOTE]
    > Con el Generador de topologías ya abierto, puede continuar con el paso 3 en <A href="lync-server-2013-publish-the-updated-topology.md">Publicar la topología actualizada en Lync Server 2013</A> para empezar a publicar su topología actualizada.


