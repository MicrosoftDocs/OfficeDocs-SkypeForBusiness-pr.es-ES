---
title: Configurar la agrupación en clústeres de SQL Server en Lync Server 2013
TOCTitle: Configurar la agrupación en clústeres de SQL Server en Lync Server 2013
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56559137
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la agrupación en clústeres de SQL Server en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Microsoft Lync Server 2013 es compatible con la agrupación en clústeres de SQL Server 2012 y SQL Server 2008 R2. Para más información sobre compatibilidad, vea [Compatibilidad con software de base de datos en Lync Server 2013](lync-server-2013-database-software-support.md).

Se recomienda instalar y configurar el clúster de SQL Server antes de instalar e implementar la base de datos back-end y el servidor front-end Enterprise Edition. Para más información sobre procedimientos recomendados e instrucciones de configuración de los clústeres de conmutación por error en SQL Server 2012, vea <http://technet.microsoft.com/es-es/library/hh231721.aspx>. Para más información sobre los clústeres de conmutación por error en SQL Server 2008, vea <http://technet.microsoft.com/es-es/library/ms189134(v=sql.105).aspx>.

Al instalar SQL Server, debe instalarse también SQL Server Management Studio para administrar las ubicaciones de la base de datos y de los archivos de registro. La instalación de SQL Server Management Studio es opcional al instalar SQL Server.

> [!IMPORTANT]  
> Para poder instalar e implementar las bases de datos en el servidor basado en SQL Server, debe ser miembro del grupo de administrador del sistema de SQL Server en el servidor basado en SQL Server en el que se están instalando los archivos de base de datos. Si no es miembro de este grupo, solicite que se le incorpore hasta que se implementen los archivos de base de datos. Si no puede convertirse en miembro del grupo, proporcione al administrador de bases de datos de SQL Server el script para configurar e implementar las bases de datos. Para más información sobre los permisos y derechos de usuario que necesita para llevar a cabo estos procedimientos, vea <a href="lync-server-2013-deployment-permissions-for-sql-server.md">Permisos de implementación para SQL Server en Lync Server 2013</a>.



## Para configurar la agrupación en clústeres de SQL Server:

1.  Tras completar la instalación y la configuración de la agrupación en clústeres de SQL Server, defina SQL Server Store en el Generador de topologías con el nombre del clúster virtual de instancias de SQL Server (conforme a la configuración definida durante el proceso de instalación de la agrupación en clústeres de SQL Server) y el nombre de la instancia de la base de datos de SQL Server. Con un servidor basado en SQL Server en clúster, deberá usar el nombre de dominio completo (FQDN) del nodo virtual (cosa que no haría si se tratara de un servidor independiente basado en SQL Server).
    

    > [!NOTE]
    > No es necesario configurar los distintos nodos en clúster de Windows Server para el Generador de topologías. Únicamente deberá usar el nombre del clúster virtual de SQL Server.



2.  Para implementar las bases de datos con el Generador de topologías, debe ser miembro del grupo de administrador del sistema de SQL Server. Si ya es miembro de este grupo pero carece de privilegios en el dominio (por ejemplo, si no tiene el rol de administrador de bases de datos de SQL Server), dispondrá de los derechos necesarios para crear las bases de datos, pero no para leer la información necesaria en Lync Server. Para más información sobre los permisos y los derechos de usuario necesarios para implementar Lync Server, vea [Permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

3.  Compruebe que los valores predeterminados de las carpetas de los archivos de registro y la base de datos se han asignado correctamente a los discos compartidos en el clúster de SQL Server con SQL Server Management Studio. Este procedimiento es obligatorio para crear bases de datos con el Generador de topologías.
    

    > [!NOTE]
    > Si no ha instalado SQL Server Management Studio y desea hacerlo, ejecute de nuevo la instalación de SQL Server y seleccione la herramienta de administración como característica agregada para la implementación de SQL Server existente.



4.  Puede instalar las bases de datos para el servidor basado en SQL Server tanto con los cmdlets de Windows PowerShell como con el Generador de topologías. Si desea hacerlo con este último, realice el procedimiento siguiente. Si prefiere usar los cmdlets de Windows PowerShell, vea [Instalación de la base de datos con el Shell de administración de Lync Server en Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).

## Para crear bases de datos con el Generador de topologías:

1.  Inicie el Generador de topologías: haga clic en **Inicio** , **Todos los programas** , **Microsoft Lync Server 2013** y **Generador de topologías de Lync Server** .
    
    > [!WARNING]  
    > En el procedimiento siguiente se asume que la topología se ha definido y configurado con el Generador de topologías. Para más información sobre cómo definir una topología, vea <a href="lync-server-2013-defining-and-configuring-the-topology.md">Definición y configuración de la topología en Lync Server 2013</a>. Para publicar la topología y configurar la base de datos con el Generador de topologías, inicie sesión como usuario con las pertenencias a grupos y los derechos de usuario correctos. Para más información sobre estos derechos y pertenencias, vea <a href="lync-server-2013-deployment-permissions-for-sql-server.md">Permisos de implementación para SQL Server en Lync Server 2013</a>.
    


2.  Cuando publique la topología, vaya a la página **Crear bases de datos** del Generador de topologías y haga clic en **Avanzadas**.

3.  La página **Seleccionar la ubicación de los archivos de base de datos** ofrece dos opciones para determinar cómo se deben implementar los archivos de base de datos en el clúster de SQL Server. Seleccione una de estas opciones:
    
      - **Determinar automáticamente la ubicación del archivo de base de datos.** Esta selección usa un algoritmo para determinar las ubicaciones de los archivos de datos y registro de base de datos, en función de la configuración de la unidad del servidor basado en SQL Server. Los archivos se distribuirán para intentar ofrecer un rendimiento óptimo.
    
      - Usar los valores predeterminados de instancia de SQL Server. Seleccione esta opción para instalar los archivos de datos y registro conforme a la configuración de la instancia de SQL Server. Tras implementar los archivos de base de datos en el servidor de SQL Server, es posible que el administrador de bases de datos de SQL Server desee cambiar la ubicación de los archivos para optimizar el rendimiento de sus requisitos de configuración específicos para SQL Server.

4.  Complete la publicación de la topología y confirme que no se han producido errores durante esta operación.

