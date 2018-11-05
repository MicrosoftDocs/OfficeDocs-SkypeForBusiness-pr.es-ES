---
title: "Modif. des options de la base de données d’archivage dans Lync Server 2013"
TOCTitle: "Modif. des options de la base de données d’archivage dans Lync Server 2013"
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48274919
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Cambiar las opciones de base de datos de archivado en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Si implementa el servidor de archivado mediante el almacenamiento de SQL Server para el almacenamiento de archivos para cualquiera de sus usuarios, puede realizar los siguientes cambios en el almacenamiento de la base de datos:

  - Utilice una base de datos SQL Server diferente para el almacenamiento de archivos. Esto incluye la base de datos de archivado principal o cualquier base de datos utilizada para la creación de reflejos de SQL Server.

  - Cambie a la integración con Microsoft Exchange para almacenar los datos de archivado y los archivos en los servidores Exchange 2013. Si todos los usuarios se hospedan en sus servidores Exchange 2013 y desea utilizar el almacenamiento de Microsoft Exchange para todos los usuarios en su implementación, debería eliminar las bases de datos del almacén SQL Server de su topología.

Para realizar cualquiera de estos cambios, debe ejecutar Generador de topologías, realizar los cambios y, a continuación, publicar de nuevo la topología. Para ello, puede utilizar Generador de topologías. No especifique la información **Almacén SQL Server de archivado** o **Permitir la creación de reflejos del almacén SQL Server**, a no ser que tenga usuarios de Lync que no estén alojados en los servidores Exchange 2013.

## Cambiar la opción de la base de datos de archivado

1.  En un equipo que ejecute Lync Server 2013 o en el que estén instaladas las herramientas administrativas de Lync Server, inicie sesión utilizando una cuenta que sea miembro de un grupo de usuarios local (o una cuenta con derechos de usuario equivalentes).
    

    > [!NOTE]
    > Puede definir una topología utilizando una cuenta que sea miembro de un grupo de usuarios local, pero para publicar una topología, que se requiere para agregar un componente a la topología, tiene que utilizar una cuenta que sea miembro de los grupos <STRONG>Administradores de dominio</STRONG> y <STRONG>RTCUniversalServerAdmins</STRONG>, y que disponga de permisos de control total (es decir, de lectura, escritura y modificación) en el uso compartido de archivos que está utilizando para el almacén de archivos Lync Server 2013 (es decir, de modo que Generador de topologías pueda configurar las listas de control de acceso discrecionales [DACL] necesarias), o una cuenta con derechos equivalentes.



2.  Inicie el Generador de topologías.

3.  En el árbol de consola, explore el grupo de servidores front-end en los que ha implementado el servidor de archivado y, a continuación, haga clic en el nombre del grupo de servidores front-end al que quiere modificar las opciones de la base de datos.

4.  En el menú **Acción**, haga clic en **Editar propiedades**.

5.  En el cuadro de diálogo **Editar propiedades**, haga clic en **General**.

6.  Desplácese hacia abajo hasta **Servidor de archivado**.

7.  En **Servidor de archivado**, haga lo siguiente:
    
      - Para cambiar a un almacén de SQL Server existente diferente, en **Almacén SQL Server de archivado**, en el cuadro de desplegable, haga lo siguiente:
        
          - Para usar un almacén de SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar.
        
          - Para especificar un nuevo almacén de SQL Server, haga clic en **Nuevo** y en el cuadro de diálogo **Definir un nuevo almacén de SQL Server** lleve a cabo lo siguiente:
            
              - Para usar un almacén de SQL Server existente, en el cuadro de lista desplegable, haga clic en el nombre del almacén de SQL Server que desee usar.
            
              - Para especificar un nuevo almacén de SQL Server, haga clic en **Nuevo** y, a continuación, en el cuadro de diálogo **Definir nuevo almacén de SQL Server**, haga lo siguiente:
                
                  - En **FQDN de SQL Server** , especifique el FQDN del servidor SQL donde desee crear el nuevo almacén de SQL Server.
                
                  - Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar.
                
                  - Si la instancia especificada de SQL Server se encuentra en una relación de reflejo, active la casilla **Esta instancia de SQL tiene una relación de reflejo** y, a continuación, en **Número de puerto de reflejo**, especifique el número de puerto.
    
      - Para agregar un almacén de SQL Server para la creación de reflejos o para cambiar a un almacén de SQL Server existente diferente para la creación de reflejos del almacén de SQL Server, seleccione **Permitir creación de reflejos del almacén de SQL Server** y, a continuación, haga lo siguiente:
        
          - Para utilizar un almacén de SQL Server existente para la creación de reflejos, en el cuadro de lista desplegable **Archivado de reflejo de almacén de SQL Server**, haga clic en el nombre del almacén de SQL Server que desee utilizar para la creación de reflejo.
        
          - Para especificar un nuevo almacén de SQL Server para la creación de reflejos, haga clic en **Nuevo** y, a continuación, en el cuadro de diálogo **Definir nuevo almacén de SQL Server**, lleve a cabo una de las acciones siguientes:
            
            1.  En el **FQDN del servidor SQL**, especifique el FQDN del servidor SQL donde desee crear el nuevo almacén de SQL Server.
            
            2.  Haga clic en **Instancia predeterminada** para utilizar la instancia predeterminada o, para especificar una instancia diferente, haga clic en **Instancia denominada** y, a continuación, haga clic en la instancia que desee utilizar.
            
            3.  Si la instancia especificada de SQL Server se encuentra en una relación de reflejo, active la casilla **Esta instancia de SQL tiene una relación de reflejo** y, a continuación, en **Número de puerto de reflejo**, especifique el número de puerto.
        
          - Si habilita la creación de reflejos de SQL Server y desea agregar o cambiar un testigo de reflejo de SQL Server (tercera instancia separada de SQL Server capaz de detectar el estado del servidor de SQL Server principal y de las instancias de reflejo), active la casilla **Usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación tras fallo automática** y lleve a cabo una de las acciones siguientes:
            
            1.  En **FQDN de SQL Server** , especifique el FQDN del servidor SQL donde desee crear el nuevo testigo de reflejo de SQL Server.
            
            2.  Haga clic en **Instancia predeterminada** para usar la instancia predeterminada o, para especificar una instancia distinta, haga clic en **Instancia con nombre** y especifique la instancia que desee usar para el testigo de reflejo.
            
            3.  Si la instancia especificada de SQL Server se encuentra en una relación de reflejo, active la casilla **Esta instancia de SQL tiene una relación de reflejo** y, a continuación, en **Número de puerto de reflejo**, especifique el número de puerto.
    
      - Para cambiar a la integración de Microsoft Exchange para almacenar los datos de archivado y los archivos en los servidores Exchange 2013 (si todos los usuarios en su implementación están hospedados en sus servidores Exchange 2013), elimine toda la información en de archivado de bases de datos.
    
    > [!IMPORTANT]  
    > Si tiene algún usuario de Lync que no esté hospedado en los servidores Exchange 2013, no elimine la información del almacén de SQL Server.
    


8.  Para guardar la configuración, haga clic en **Aceptar**.
    
    > [!IMPORTANT]  
    > Los cambios que ha realizado en Generador de topologías no tendrán efecto hasta que publique la nueva topología. Para obtener información, consulte <a href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publicación de la topología actualizada para agregar bases de datos de archivado</a> en la documentación referente a la implementación.
    

