---
title: "Instalación de la base de datos con el Shell de administración de Lync Server"
TOCTitle: Instalación de la base de datos con el Shell de administración de Lync Server
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48276654
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalación de la base de datos con el Shell de administración de Lync Server en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

La separación de roles y responsabilidades entre los administradores de servidor y los de SQL Server puede ocasionar retrasos en la implementación. Lync Server 2013 usa el control de acceso basado en roles (RBAC) para atenuar estas dificultades. En algunos casos, el administrador de SQL Server tiene que administrar la instalación de las bases de datos en el servidor de SQL Server independientemente de RBAC. Shell de administración de Lync Server 2013 permite al administrador de SQL Server ejecutar los cmdlets de Windows PowerShell diseñados para configurar bases de datos con los archivos de datos y de registro correctos. Para más información, consulte [Permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

> [!IMPORTANT]  
> El siguiente procedimiento presupone que, como mínimo, están instalados Microsoft SQL Server 2012 ADOMD.NET, CLR Types for Microsoft SQL Server 2012, CLR Types for Microsoft SQL Server 2012, SQL Server Native Client (sqlncli.msi) y OCSCore.msi de Lync Server 2013. OCSCore.msi está ubicado en el medio de instalación en el directorio \Setup\AMD64\Setup. El resto de los componentes se encuentran en \Setup\amd64. Además, la preparación de Active Directory para Lync Server 2013 se ha realizado correctamente.



**Install-CsDatabase** es el cmdlet de Windows PowerShell que debe usar para instalar las bases de datos. El cmdlet **Install-CsDatabase** tiene una gran cantidad de parámetros, aquí solo se analizan algunos. Para más información sobre los posibles parámetros, consulte la documentación de Shell de administración de Lync Server 2013.

> [!WARNING]  
> Para evitar problemas de rendimiento y posibles tiempos de espera, debe usar siempre nombres de dominio completos (FQDN) cuando hace referencia a servidores de SQL Server. Evite usar referencias de solo nombre de host. Por ejemplo, use sqlbe01.contoso.net, pero evite usar SQLBE01.



A la hora de instalar bases de datos, **Install-CsDatabase** usa tres métodos básicos para colocar las bases de datos en el servidor de SQL Server preparado:

  - Ejecutar **Install-CsDatabase** sin DatabasePaths o UseDefaultSqlPath. El cmdlet usa un algoritmo integrado para determinar la mejor posición para los archivos de datos y registros. El algoritmo solo funciona para implementaciones independientes de SQL Server.

  - Ejecutar **Install-CsDatabase** con el parámetro DatabasePaths. El algoritmo integrado para optimizar las ubicaciones de archivos de datos y registros no se usa si el parámetro DatabasePaths está definido. Este parámetro permite definir las ubicaciones donde se implementarán los archivos de datos y registros.

  - Ejecutar **Install-CsDatabase** con UseDefaultSqlPaths. Esta opción no usa el algoritmo integrado para optimizar las ubicaciones de archivos de datos y registros. Los archivos de datos y registros se implementan según los valores predeterminados que establece el administrador de SQL Server. Estas rutas de acceso se establecen normalmente con antelación, para la administración automática de archivos de datos y registros en SQL Server, y no están asociadas a la instalación de Lync Server 2013.

  - El parámetro DatabasePathMap también se puede usar para especificar explícitamente una ubicación para cada base de datos y su archivo de registro correspondiente.

## Para configurar Almacén de administración central de SQL Server con los cmdlets de Windows PowerShell:

1.  Inicie sesión en cualquier PC con credenciales administrativas para la creación de bases de datos en el servidor de SQL Server. Para más información, consulte [Permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

2.  Abra Shell de administración de Lync Server 2013. Si no ha ajustado la directiva de ejecución para Windows PowerShell, debe hacerlo para permitir que los scripts de Windows PowerShell se ejecuten. Para más información, consulte "Examinar la directiva de ejecución" en <http://go.microsoft.com/fwlink/?linkid=203093>.

3.  Use el cmdlet **Install-CsDatabase** para instalar Almacén de administración central.
    
    ```
    Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
    -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
    -Report <path to report file>
    ```
    ```
    Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
    ```
    
    > [!TIP]  
    > El parámetro Report es opcional pero útil si está documentando el proceso de instalación.
    


4.  **Install-CsDatabase –DatabasePaths** puede usar hasta seis parámetros de ruta de acceso de modo que cada uno defina las rutas de acceso para las unidades que se definen en la ubicación del archivo de registro y los datos de SQL Server. Mediante las reglas lógicas de la configuración de base de datos de Lync Server 2013, las unidades se analizan en cubos de dos, cuatro o seis. Dependiendo de la configuración de SQL Server y del número de cubos, se proporcionarán dos, cuatro o seis rutas de acceso.
    
    Si dispone de tres unidades, se da prioridad al registro y los archivos de datos se distribuyen más adelante. Un ejemplo de un servidor de SQL Server configurado con seis unidades:
    
    ```
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```

5.  Cuando la instalación de la base de datos finaliza, puede cerrar Shell de administración de Lync Server 2013 o continuar con la instalación de las bases de datos configuradas de Lync Server 2013 en Generador de topologías.

## Para configurar las bases de datos configuradas de la topología de SQL Server con los cmdlets de Windows PowerShell:

1.  Para instalar las bases de datos configuradas de Generador de topologías para Lync Server 2013, el administrador de Lync Server 2013 debe publicar la topología. Para más información, consulte [Publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md) en la documentación de implementación.

2.  Inicie sesión en cualquier PC con credenciales administrativas para la creación de bases de datos en el servidor de SQL Server. Consulte el tema [Permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    > [!IMPORTANT]  
    > Para poder configurar las bases de datos de SQL Server, asegúrese de que la cuenta de administrador de SQL Server con la que se han realizado los pasos descritos anteriormente también es miembro del grupo sysadmins (o equivalente) en el servidor que ejecuta SQL Server, y desempeña el rol de Servidor de administración central. Esto es especialmente importante para comprobar grupos de Lync Server 2013 adicionales que requieren la instalación o configuración de bases de datos de SQL Server. Por ejemplo, si implementa un segundo grupo (Grupo02), pero el rol de Servidor de administración central pertenece al Grupo01. El grupo sysadmin de SQL Server (o equivalente) debe tener permisos en las dos bases de datos de SQL Server.
    


3.  Abra Shell de administración de Lync Server 2013 si no está abierto.

4.  Use el cmdlet **Install-CsDatabase** para instalar las bases de datos configuradas de Generador de topologías.
    
    ```
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
      -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
    ```
    ```
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
      -Report "C:\Logs\InstallDatabases.html"
    ```
    
    > [!TIP]  
    > El parámetro Report es opcional pero útil si está documentando el proceso de instalación.
    


5.  Cuando la instalación de la base de datos finalice, cierre Shell de administración de Lync Server 2013.

## Para configurar la topología de SQL Server con el parámetro DatabasePathMap mediante los cmdlets de Windows PowerShell:

1.  Para instalar bases de datos para Lync Server 2013, el administrador de Lync Server debe crear las rutas de acceso e implementar los archivos de bases de datos y registro, según un conjunto de reglas predefinido.

2.  Inicie sesión en cualquier PC con credenciales administrativas para la creación de bases de datos en el servidor de SQL Server. Consulte el tema [Permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    > [!IMPORTANT]  
    > Para poder configurar las bases de datos de SQL Server, asegúrese de que la cuenta de administrador de SQL Server con la que se han realizado los pasos descritos anteriormente también es miembro del grupo sysadmins (o equivalente) en el servidor que ejecuta SQL Server, y desempeña el rol de Servidor de administración central. Esto es especialmente importante para comprobar grupos de Lync Server adicionales que requieren la instalación o configuración de bases de datos de SQL Server. Por ejemplo, si implementa un segundo grupo (Grupo02), pero el rol de Servidor de administración central pertenece al Grupo01. El grupo sysadmin de SQL Server (o equivalente) debe tener permisos en las dos bases de datos de SQL Server.
    


3.  Abra Shell de administración de Lync Server, si no está abierto.

4.  Use el cmdlet **Install-CsDatabase** con el parámetro DatabasePathMap y la tabla hash de PowerShell para instalar las bases de datos configuradas de Generador de topologías.

5.  En el código de ejemplo, las rutas de acceso definidas para las bases de datos pueden determinarse de forma pormenorizada con el parámetro –DatabasePathsMap y una tabla hash definida del modo siguiente (el ejemplo usa “C:\\CSData” para todos los archivos de base de datos (.mdf) y “C:\\CSLogFiles” para todos los archivos de registro (.ldf). Install-CsDatabase creará la carpeta según sea necesario):
    
        $pathmap = @{
        "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
        "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
        "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
        "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
        "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
        "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
        "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
        "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
        "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
        }
        Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathsMap $pathmap

6.  Dado que los archivos de base de datos y registro se denominan explícitamente con su ubicación en el servidor de base de datos de destino, puede definir ubicaciones específicas para cada ubicación de base de datos y registro real del tipo de servicio. Los ejemplos siguientes colocan las bases de datos de cada tipo de servicio específico en discos independientes, y los archivos de registro asociados en otro. Por ejemplo:
    
      - Todas las bases de datos de RTC en “D:\\RTCDatabase”
    
      - Todos los archivos de registro de RTC en “E:\\RTCLogs”
    
      - Todas las bases de datos del almacén de aplicaciones en “F:\\CPSDatabases”
    
      - Todos los registros del almacén de aplicaciones en “G:\\CPSLogs”
    
      - Todas las bases de datos del almacén del grupo de respuesta en “H:\\RGSDatabases”
    
      - Todos los registros del almacén del grupo de respuesta en “I:\\RGSLogs”
    
      - Todas las bases de datos del almacén de la libreta de direcciones en “J:\\ABSDatabases”
    
      - Todos los archivos de registro del almacén de la libreta de direcciones en “K:\\ABSLogs”
    
      - Todas las bases de datos del almacén de archivado en “L:\\ArchivingDatabases”
    
      - Todos los archivos de registro del almacén de archivado en “M:\\ArchivingLogs”
    
      - Todas las bases de datos del almacén de supervisión en “N:\\MonitoringDatabases”
    
      - Todas las bases de datos del almacén de supervisión en “O:\\MonitoringLogfiles”
    
    <!-- end list -->
    
    ``` 
    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    Con el parámetro –DatabasePathMap, puede definir la combinación de asignaciones de letras de unidad lógicas que proporcione la mejor solución para el rendimiento y los requisitos de ubicación de SQL Server.

Si configura los archivos de datos de base de datos y los archivos de registro con el método **DatabasePathMap**, tendrá que realizar un pequeño cambio en el proceso habitual cuando use Generador de topologías. Normalmente, definirá las opciones de topología, publicará la topología y optará por implementar las selecciones de la base de datos.

Si ha usado **DatabasePathMap**, ya habrá realizado la tercera parte del proceso de Generador de topologías. Si tiene un servidor de base de datos configurado completamente antes de ejecutar Generador de topologías, tendrá que definir todos los roles y las opciones del servidor, pero tendrá que desmarcar la opción de crear las bases de datos.

