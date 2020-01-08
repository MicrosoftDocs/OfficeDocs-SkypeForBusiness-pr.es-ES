---
title: 'Lync Server 2013: Instalación de la base de datos con el Shell de administración de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: deac68fb5f20066632bc48a9e9b6244a9bd34fe9
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a>Instalación de la base de datos con el Shell de administración de Lync Server en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-06-16_

La separación de roles y responsabilidades entre los administradores del servidor y los administradores de SQL Server puede dar lugar a retrasos en la implementación. Lync Server 2013 usa control de acceso basado en roles (RBAC) para mitigar estas dificultades. En algunos casos, el administrador de SQL Server debe administrar la instalación de bases de datos en el servidor basado en SQL Server fuera de RBAC. El shell de administración de Lync Server 2013 proporciona una forma para que el administrador de SQL Server ejecute cmdlets de Windows PowerShell diseñados para configurar las bases de datos con los archivos de datos y de registro correctos. Para obtener más información, consulte [permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

<div class=" ">


> [!IMPORTANT]  
> En el procedimiento siguiente se supone que al menos Lync Server 2013 OCSCore. msi, SQL Server Native Client (SQLNCLI. msi) objetos de administración de Microsoft SQL Server 2012, tipos de CLR para Microsoft SQL Server 2012 y Microsoft SQL Server 2012 ADOMD.NET están instalados. El OCSCore. msi se encuentra en el medio de instalación en el directorio \Setup\AMD64\Setup Los componentes restantes se encuentran en \Setup\amd64. Además, la preparación de Active Directory para Lync Server 2013 se ha completado correctamente.



</div>

**Install-CsDatabase** es el cmdlet de Windows PowerShell que usas para instalar las bases de datos. El cmdlet **install-CsDatabase** tiene un gran número de parámetros, solo algunos de los cuales se tratan aquí. Para obtener más información sobre los parámetros posibles, consulte la documentación del shell de administración de Lync Server 2013.

<div class=" ">


> [!WARNING]  
> Para evitar problemas de rendimiento y posibles problemas de tiempo de espera, use siempre nombres de dominio completos (FQDN) al hacer referencia a servidores basados en SQL Server. Evite usar referencias de solo nombres de host. Por ejemplo, use sqlbe01.contoso.net, pero evite usar SQLBE01.



</div>

Para instalar bases de datos, **install-CsDatabase** usa tres métodos principales para ubicar las bases de datos en el servidor basado en SQL preparado:

  - Ejecute **install-CsDatabase** sin DatabasePaths o UseDefaultSqlPath. El cmdlet usa un algoritmo integrado para determinar la mejor ubicación de los archivos de registro y de datos. El algoritmo solo funciona para implementaciones independientes de SQL Server.

  - Ejecute **install-CsDatabase** con el parámetro DatabasePaths. El algoritmo integrado para optimizar las ubicaciones de los archivos de registro y datos no se usa si el parámetro DatabasePaths está definido. El uso de este parámetro le permite definir las ubicaciones en las que se implementarán los archivos de registro y de datos.

  - Ejecute **install-CsDatabase** con UseDefaultSqlPaths. Esta opción no usa el algoritmo integrado para optimizar el registro y las ubicaciones de los archivos de datos. El registro y el archivo de datos se implementan de acuerdo con los valores predeterminados establecidos por el administrador de SQL Server. Normalmente, estas rutas se establecen para la administración automática de archivos de registro y datos en SQL Server por adelantado y no están asociadas a la configuración de Lync Server 2013.

  - El parámetro DatabasePathMap también se puede usar para especificar de forma explícita una ubicación para cada base de datos y el archivo de registro correspondiente.

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a>Para usar los cmdlets de Windows PowerShell para configurar el almacén de administración central de SQL Server

1.  En cualquier equipo, inicie sesión con credenciales administrativas para crear las bases de datos en el servidor basado en SQL Server. Para obtener más información, consulte [permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

2.  Abra el shell de administración de Lync Server 2013. Si no ha ajustado la Directiva de ejecución de Windows PowerShell, debe ajustar la Directiva para permitir la ejecución de los scripts de Windows PowerShell. Para obtener más información, consulte "examen de la Directiva de [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)ejecución" en.

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
    > El parámetro de informe es opcional pero es útil si está documentando el proceso de instalación.

    
    </div>

4.  **Install-CsDatabase – DatabasePaths** puede usar hasta seis parámetros PATH, cada uno de los cuales define las rutas de las unidades según se definen en los datos y la ubicación del archivo de registro de SQL Server. Según las reglas lógicas de la configuración de la base de datos en Lync Server 2013, las unidades se redistribuyen en cubos de dos, cuatro o seis. Según la configuración de SQL Server y el número de cubos, deberá proporcionar dos rutas, cuatro rutas o seis rutas.
    
    Si tiene tres unidades, el registro obtiene prioridad y los archivos de datos se distribuyen después de. Un ejemplo de un servidor basado en SQL Server configurado con seis unidades:
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  Una vez completada la instalación de la base de datos, puede cerrar el shell de administración de Lync Server 2013 o ir a la instalación de las bases de datos de Lync Server 2013 configuradas en el generador de topología.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a>Para usar los cmdlets de Windows PowerShell para configurar la topología de SQL Server configurada bases de datos

1.  Para instalar las bases de datos configuradas en el generador de topologías para Lync Server 2013, el administrador de Lync Server 2013 debe publicar la topología. Para obtener más información, vea [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md) en la documentación de implementación.

2.  En cualquier equipo, inicie sesión con credenciales administrativas para crear las bases de datos en el servidor basado en SQL Server. Vea el tema [sobre los permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Para poder configurar las bases de datos basadas en SQL Server, asegúrese de que la cuenta de administrador de SQL Server que se usa para ejecutar los pasos descritos aquí también es miembro del grupo sysadmins (o equivalente) en el servidor que ejecuta SQL Server y que mantiene la administración central. Rol de servidor. Esto es especialmente importante para comprobar si hay otros grupos de 2013 de Lync Server que requieran la instalación o configuración de la base de datos de SQL Server. Por ejemplo, si está implementando un segundo grupo (pool02) pero el rol de servidor de administración central es de pool01. El grupo sysadmin de SQL Server (o equivalente) debe tener permisos en ambas bases de datos basadas en SQL Server.

    
    </div>

3.  Abra el shell de administración de Lync Server 2013, si aún no está abierto.

4.  Use el cmdlet **install-CsDatabase** para instalar las bases de datos configuradas en el generador de topología.
    
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
    > El parámetro de informe es opcional pero es útil si está documentando el proceso de instalación.

    
    </div>

5.  Cuando se complete la instalación de la base de datos, cierre el shell de administración de Lync Server 2013.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a>Para usar los cmdlets de Windows PowerShell para configurar la topología de SQL Server con el parámetro DatabasePathMap

1.  Para instalar las bases de datos de Lync Server 2013, el administrador de Lync Server debe crear las rutas e implementar los archivos de base de datos y los archivos de registro según un conjunto predefinido de reglas.

2.  En cualquier equipo, inicie sesión con credenciales administrativas para crear las bases de datos en el servidor basado en SQL Server. Vea el tema [sobre los permisos de implementación para SQL Server en Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Para poder configurar las bases de datos basadas en SQL Server, asegúrese de que la cuenta de administrador de SQL Server que se usa para ejecutar los pasos descritos aquí también es miembro del grupo sysadmins (o equivalente) en el servidor que ejecuta SQL Server y que mantiene la administración central. Rol de servidor. Esto es especialmente importante para comprobar si hay otros grupos de servidores de Lync que requieran la instalación o configuración de la base de datos de SQL Server. Por ejemplo, si está implementando un segundo grupo (pool02) pero el rol de servidor de administración central es de pool01. El grupo sysadmin de SQL Server (o equivalente) debe tener permisos en ambas bases de datos basadas en SQL Server.

    
    </div>

3.  Abra el shell de administración de Lync Server, si aún no está abierto.

4.  Use el cmdlet **install-CsDatabase** con el parámetro DatabasePathMap y una tabla hash de PowerShell para instalar las bases de datos configuradas en el generador de topología.

5.  En el código de ejemplo, las rutas de las bases de datos se pueden determinar de forma granular con el parámetro – DatabasePathMap y una tabla hash definida de la siguiente manera (el ejemplo usa "C:\\CSData" para todos los archivos de base de datos (. MDF) y\\"c: CSLogFiles" para todos los archivos de registro (. ldf). Se creará una carpeta según sea necesario por install-CsDatabase):
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
6.  Puesto que la base de datos y los archivos de registro se denominan explícitamente con su ubicación en el servidor de la base de datos de destino, puede definir ubicaciones específicas para cada tipo de servicio y la ubicación de registro y de la base de datos. En el siguiente ejemplo se colocan bases de datos para cada tipo de servicio específico en discos independientes y archivos de registro relacionados en otro. Por ejemplo:
    
      - Todas las bases de datos de RTC a "\\D: RTCDatabase"
    
      - Todos los archivos de registro de RTC a\\"E: RTCLogs"
    
      - Todas las bases de datos del almacén de aplicaciones a\\"F: CPSDatabases"
    
      - Todos los registros del almacén de aplicaciones a\\"G: CPSLogs"
    
      - Todas las bases de datos de la tienda de grupos de\\respuesta a "H: RGSDatabases"
    
      - Todos los registros del almacén de grupos de respuesta\\en "I: RGSLogs"
    
      - Todas las bases de datos del almacén de la libreta de\\direcciones en "J: ABSDatabases"
    
      - Todos los archivos de registro del almacén de la libreta\\de direcciones a "K: ABSLogs"
    
      - Todas las bases de datos del almacén de archivado a\\"L: ArchivingDatabases"
    
      - Todos los registros del almacén de archivado a\\"M: ArchivingLogs"
    
      - Todas las bases de datos del almacén de supervisión a\\"N: MonitoringDatabases"
    
      - Todos los archivos de registro del almacén de supervisión\\a "O: MonitoringLogfiles"
    
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
    
    Con el parámetro – DatabasePathMap, puede definir cualquier combinación de asignación de letra de unidad lógica que proporcione la mejor solución para sus requisitos de rendimiento y ubicación de SQL Server.

Si configura los archivos de datos y los archivos de registro de la base de datos con el método **DatabasePathMap** , tendrá que hacer un leve cambio en el proceso normal cuando use el generador de topologías. Normalmente, debe definir las opciones de topología, publicar la topología y elegir implementar las selecciones de la base de datos.

Si ha usado **DatabasePathMap** ya ha realizado la tercera parte del proceso de creación de topología. En el caso de que haya un servidor de base de datos completamente configurado antes de ejecutar el generador de topología, aún definirá todos los roles y las opciones del servidor, pero desactivando la opción para crear las bases de datos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

