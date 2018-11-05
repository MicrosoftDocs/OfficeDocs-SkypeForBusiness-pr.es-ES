---
title: Adición de bases de datos de archivado a la topología de Lync Server 2013
TOCTitle: Adición de bases de datos de archivado a la topología de Lync Server 2013
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48274351
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Adición de bases de datos de archivado a la topología de Lync Server 2013

 

_**Última modificación del tema:** 2012-10-10_

Debe incorporar el archivado a la topología para poder configurar la implementación a fin de admitir el archivado. La información de este tema explica cómo usar Generador de topologías para agregar el archivado a su topología existente.


> [!NOTE]
> Si desea usar la integración de Microsoft Exchange para almacenar datos de archivado en servidores de Exchange 2013 para todos sus usuarios en su implementación, no especifique la información de <STRONG>Almacén SQL Server de archivado</STRONG> o <STRONG>Usar la creación de reflejos de almacén SQL Server</STRONG>.



## Para agregar la compatibilidad de base de datos de archivado a la topología

1.  En un equipo que ejecute Lync Server 2013 o en el que se instalen herramientas administrativas de Lync Server, inicie sesión usando una cuenta que sea miembro del grupo Usuarios locales (o una cuenta con derechos de usuario equivalente).
    

    > [!NOTE]
    > Puede definir una topología con una cuenta que sea miembro del grupo Usuarios locales, pero para publicar una topología, que es necesario para instalar un servidor a la topología, debe usar una cuenta que sea miembro del grupo <STRONG>Admins. del dominio</STRONG> y del grupo <STRONG>RTCUniversalServerAdmins</STRONG>, y que tenga permisos de control total (es decir, leer, escribir y modificar) en el recurso compartido de archivos que va a usar para el almacén de archivos de Lync Server 2013 (es decir, para que la Generador de topologías pueda configurar las listas de control de acceso discrecionales (DACL), o una cuenta con derechos similares.



2.  Inicie la Generador de topologías.

3.  En el árbol de consola, vaya al grupo de servidores front-end en el que desee implementar el archivado y haga clic en el nombre de dicho grupo.

4.  En el menú **Acción**, haga clic en **Editar propiedades**.

5.  En el cuadro de diálogo **Editar propiedades**, haga clic en **General**.

6.  Desplácese a **Archivado**.

7.  Seleccione la casilla **Archivado**.

8.  En **Almacén SQL Server de archivado**, siga uno de estos pasos:
    
      - Para usar un almacén de SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desea usar. Si todos los usuarios se hospedan en Microsoft Exchange Server 2013 o superior, puede archivar las comunicaciones de Lync para todos los usuarios en Exchange. En este caso, no tiene que configurar el almacén de archivado de SQL Server.
    
      - Para especificar un nuevo almacén SQL Server, haga clic en **Nuevo** y, a continuación, en el cuadro de diálogo **Definir nuevo almacén SQL Server**, siga uno de estos pasos:
        
          - En **FQDN de SQL Server**, especifique el FQDN del servidor donde desee crear el nuevo almacén SQL Server.
        
          - Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o bien, para especificar una instancia diferente, haga clic en **Instancia con nombre** y, a continuación, especifique la instancia que desea usar.
        
          - Si la instancia de SQL Server especificada está en una relación de creación de reflejo, active la casilla **Esta instancia de SQL se encuentra en una relación de creación de reflejo** y, a continuación, en **Número de puerto de reflejo**, especifique el número de puerto.

9.  Si desea usar la creación de reflejos de almacén SQL Server, seleccione **Habilitar la creación de reflejos de almacén SQL Server** y siga estos pasos:
    
      - Para usar un almacén SQL Server existente para creación de reflejos, haga clic en el nombre del almacén SQL Server que desee usar para creación de reflejos en el cuadro de lista desplegable **Archivado de creación de reflejos de SQL Server**.
    
      - Para especificar un nuevo almacén SQL Server para la creación de reflejos, haga clic en **Nuevo** y, a continuación, en el cuadro de diálogo **Definir nuevo almacén SQL Server**, siga uno de estos pasos:
        
        1.  En **SQL Server FQDN**, especifique el FQDN del SQL Server en el que desea crear el nuevo almacén de SQL Server.
        
        2.  Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y, a continuación, especifique la instancia que desee usar.
        
        3.  Si la instancia de SQL Server especificada está en una relación de creación de reflejo, active la casilla **Esta instancia de SQL se encuentra en una relación de creación de reflejo** y, a continuación, en **Número de puerto de reflejo**, especifique el número de puerto.
    
      - Si habilita la creación de reflejos de SQL Server y desea incluir un testigo de creación de reflejo de SQL Server (una tercera instancia de SQL Server independiente que puede detectar el estado del servidor principal de SQL Server y las instancias de reflejo), seleccione el testigo de creación de reflejo de la casilla **Usar testigo de creación de reflejo de SQL Server para habilitar la conmutación automática por error** y, a continuación, realice una de las siguientes acciones:
        
        1.  En **FQDN de SQL Server**, especifique el FQDN del servidor donde desee crear el nuevo testigo de creación de reflejo de SQL Server.
        
        2.  Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y, a continuación, especifique la instancia que desee usar para el testigo de creación de reflejo.
        
        3.  Si la instancia de SQL Server especificada está en una relación de creación de reflejo, active la casilla **Esta instancia de SQL se encuentra en una relación de creación de reflejo** y, a continuación, en **Número de puerto de reflejo**, especifique el número de puerto.

10. Para guardar la configuración, haga clic en **Aceptar**.

