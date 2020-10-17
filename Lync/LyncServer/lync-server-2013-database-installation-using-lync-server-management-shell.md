---
title: 'Lync Server 2013: instalación de bases de datos mediante el shell de administración de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b602e29e0f90a49a031c25d6bb919337bef87b8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516547"
---
# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a>Instalación de bases de datos mediante el shell de administración de Lync Server en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-06-16_

La separación de roles y responsabilidades entre los administradores de servidor y los administradores SQL Server puede ocasionar retrasos en la implementación. Lync Server 2013 usa el control de acceso basado en roles (RBAC) para mitigar estas dificultades. En algunos casos, el administrador de SQL Server tiene que administrar la instalación de bases de datos en el servidor de SQL Server fuera de RBAC. El shell de administración de Lync Server 2013 proporciona un método para que el administrador de SQL Server ejecute cmdlets de Windows PowerShell diseñados para configurar las bases de datos con los archivos de registro y datos correctos. Para obtener información detallada, consulte [permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

<div class=" ">


> [!IMPORTANT]  
> En el siguiente procedimiento se supone que, como mínimo, se instalan los objetos de administración de Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) de Microsoft SQL Server 2012, los tipos CLR para Microsoft SQL Server 2012 y Microsoft SQL Server 2012 ADOMD.NET. El archivo OCSCore.msi está ubicado en el medio de instalación en el directorio \Setup\AMD64\Setup. Los componentes restantes se encuentran en \Setup\amd64. Además, la preparación de Active Directory para Lync Server 2013 se ha completado correctamente.



</div>

**Install-CsDatabase** es el cmdlet de Windows PowerShell que se usa para instalar las bases de datos. El cmdlet **Install-CsDatabase** tiene una gran cantidad de parámetros, aquí solo se tratan algunos. Para obtener más información sobre los parámetros posibles, consulte la documentación del shell de administración de Lync Server 2013.

<div class=" ">


> [!WARNING]  
> Para evitar problemas de rendimiento y de posibles tiempos de espera, debe usar siempre nombres de dominio completos (FQDN) cuando hace referencia a servidores de SQL Server. Evite usar referencias de solo nombre de host. Por ejemplo, use sqlbe01.contoso.net, pero evite usar SQLBE01.



</div>

Para instalar bases de datos, **install-CsDatabase** usa tres métodos principales para colocar las bases de datos en el servidor preparado de SQL Server:

  - Ejecute **Install-CsDatabase** sin DatabasePaths o UseDefaultSqlPath. El cmdlet usa un algoritmo integrado para determinar la mejor posición para los archivos de datos y registros. El algoritmo solo funciona para implementaciones de SQL Server independientes.

  - Ejecute **Install-CsDatabase** con los parámetros DatabasePaths. El algoritmo integrado para optimizar las ubicaciones de archivos de datos y registros no se usa si el parámetro DatabasePaths está definido. El uso de este parámetro permite definir las ubicaciones donde se implementarán archivos de datos y registros.

  - Ejecute **Install-CsDatabase** con UseDefaultSqlPaths. Esta opción no usa el algoritmo integrado para optimizar las ubicaciones de archivos de datos y registros. Los archivos de datos y registros se implementan según los valores predeterminados establecidos por el administrador de SQL Server. Estas rutas de acceso se suelen establecer para la administración automática de archivos de registro y de datos en SQL Server por anticipado y no están asociadas con la configuración de Lync Server 2013.

  - El parámetro DatabasePathMap también se puede usar para especificar explícitamente una ubicación para cada base de datos y su archivo de registro respectivo.

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a>Para usar los cmdlets de Windows PowerShell para configurar el almacén de administración central de SQL Server

1.  Inicie sesión en cualquier equipo con credenciales administrativas para la creación de bases de datos en el servidor de SQL Server. Para obtener información detallada, consulte [permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

2.  Abra el shell de administración de Lync Server 2013. Si no ha ajustado la Directiva de ejecución de Windows PowerShell, debe ajustar la Directiva para permitir que se ejecuten los scripts de Windows PowerShell. Para obtener más información, consulte "examen de la Directiva de ejecución" en [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093) .

3.  Use el cmdlet **install-CsDatabase** para instalar el almacén de administración central.
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > El parámetro Report es opcional pero útil si está documentando el proceso de instalación.

    
    </div>

4.  **Install-CsDatabase – DatabasePaths** puede usar hasta seis parámetros PATH, cada uno de los cuales define las rutas de acceso de las unidades como se define en datos de SQL Server y ubicación del archivo de registro. Mediante las reglas lógicas de la configuración de la base de datos en Lync Server 2013, las unidades se redistribuyen en cubos de dos, cuatro o seis. En función de la configuración de SQL Server y del número de cubos, deberá proporcionar dos rutas, cuatro rutas o seis rutas.
    
    Si tiene tres unidades, se da prioridad al registro y los archivos de datos se distribuyen después. Un ejemplo de un servidor basado en SQL Server configurado con seis unidades:
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  Una vez finalizada la instalación de la base de datos, puede cerrar el shell de administración de Lync Server 2013 o continuar con la instalación de las bases de datos configuradas de Lync Server 2013 en el generador de topologías.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a>Para usar los cmdlets de Windows PowerShell con el fin de configurar las bases de datos configuradas de la topología de SQL Server

1.  Para instalar las bases de datos configuradas del generador de topologías para Lync Server 2013, el administrador de Lync Server 2013 debe publicar la topología. Para obtener más información, consulte [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md) en la documentación sobre implementación.

2.  Inicie sesión en cualquier equipo con credenciales administrativas para la creación de bases de datos en el servidor de SQL Server. Vea el tema [sobre los permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Para poder configurar las bases de datos basadas en SQL Server, asegúrese de que la cuenta de administrador de SQL Server que se usa para ejecutar los pasos descritos aquí también es miembro del grupo sysadmins (o equivalente) en el servidor que ejecuta SQL Server y que mantiene el rol de servidor de administración central. Esto es especialmente importante para comprobar si hay otros grupos de servidores de Lync Server 2013 que requieran la instalación o configuración de la base de datos de SQL Server. Por ejemplo, si va a implementar un segundo grupo de servidores (pool02), pero el rol de servidor de administración central se mantiene mediante grupo01. El grupo sysadmin de SQL Server (o equivalente) debe tener permisos en ambas bases de datos basadas en SQL Server.

    
    </div>

3.  Abra el shell de administración de Lync Server 2013, si aún no está abierto.

4.  Use el cmdlet **install-CsDatabase** para instalar las bases de datos configuradas del generador de topologías.
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > El parámetro Report es opcional pero útil si está documentando el proceso de instalación.

    
    </div>

5.  Cuando finalice la instalación de la base de datos, cierre Shell de administración de Lync Server 2013.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a>Para usar los cmdlets de Windows PowerShell para configurar la topología de SQL Server con el parámetro DatabasePathMap

1.  Para instalar bases de datos para Lync Server 2013, el administrador de Lync Server debe crear las rutas de acceso e implementar los archivos de base de datos y de registro de acuerdo con un conjunto de reglas predefinidas.

2.  Inicie sesión en cualquier equipo con credenciales administrativas para la creación de bases de datos en el servidor de SQL Server. Vea el tema [sobre los permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Para poder configurar las bases de datos basadas en SQL Server, asegúrese de que la cuenta de administrador de SQL Server que se usa para ejecutar los pasos descritos aquí también es miembro del grupo sysadmins (o equivalente) en el servidor que ejecuta SQL Server y que mantiene el rol de servidor de administración central. Esto es especialmente importante para comprobar si hay otros grupos de servidores de Lync Server que requieran la instalación o configuración de la base de datos de SQL Server. Por ejemplo, si va a implementar un segundo grupo de servidores (pool02), pero el rol de servidor de administración central se mantiene mediante grupo01. El grupo sysadmin de SQL Server (o equivalente) debe tener permisos en ambas bases de datos basadas en SQL Server.

    
    </div>

3.  Abra el shell de administración de Lync Server, si aún no está abierto.

4.  Use el cmdlet **install-CsDatabase** con el parámetro DatabasePathMap y una tabla hash de PowerShell para instalar las bases de datos configuradas del generador de topologías.

5.  En el código de ejemplo, las rutas de acceso definidas para las bases de datos pueden determinarse de una manera granular mediante el parámetro – DatabasePathMap y una tabla hash definida de la siguiente manera (en el ejemplo, se usa "C: \\ CSData" para todos los archivos de base de datos (. MDF) y "c: \\ CSLogFiles" para todos los archivos de registro (. ldf). La carpeta se creará según sea necesario mediante install-CsDatabase):
    ```powershell
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
    Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
6.  Dado que la base de datos y los archivos de registro se denominan explícitamente con su ubicación en el servidor de la base de datos de destino, puede definir ubicaciones específicas para la ubicación de registro y base de datos real de cada tipo de servicio. En el siguiente ejemplo se colocan bases de datos para cada tipo de servicio específico en discos independientes y archivos de registro asociados en otro. Por ejemplo:
    
      - Todas las bases de datos RTC a "D: \\ RTCDatabase"
    
      - Todos los archivos de registro RTC a "E: \\ RTCLogs"
    
      - Todas las bases de datos del almacén de aplicaciones en "F: \\ CPSDatabases"
    
      - Todos los registros del almacén de aplicaciones en "G: \\ CPSLogs"
    
      - Todas las bases de datos del almacén de grupos de respuesta a "H: \\ RGSDatabases"
    
      - Todos los registros del almacén de grupos de respuesta en "I: \\ RGSLogs"
    
      - Todas las bases de datos del almacén de la libreta de direcciones en "J: \\ ABSDatabases"
    
      - Todos los archivos de registro del almacén de la libreta de direcciones en "K: \\ ABSLogs"
    
      - Todas las bases de datos de almacenamiento de archivado en "L: \\ ArchivingDatabases"
    
      - Todos los registros del almacén de archivado en "M: \\ ArchivingLogs"
    
      - Todas las bases de datos del almacén de supervisión a "N: \\ MonitoringDatabases"
    
      - Todos los archivos de registro del almacén de supervisión a "O: \\ MonitoringLogfiles"
    
    <!-- end list -->
    
    ```powershell    
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
    
    Mediante el parámetro – DatabasePathMap, puede definir cualquier combinación de asignación de letra de unidad lógica que ofrezca la mejor solución para los requisitos de rendimiento y ubicación de SQL Server.

Si configura los archivos de datos y los archivos de registro de la base de datos mediante el método **DatabasePathMap** , tendrá que realizar un leve cambio en el proceso normal cuando use el generador de topologías. Normalmente, puede definir las opciones de topología, publicar la topología y elegir implementar las selecciones de la base de datos.

Si ha usado **DatabasePathMap** , ya ha realizado la tercera parte del proceso del generador de topologías. En el caso de tener un servidor de base de datos completamente configurado antes de ejecutar el generador de topologías, seguirá definiendo todos los roles de servidor y las opciones, pero anule la selección de la opción para crear las bases de datos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

