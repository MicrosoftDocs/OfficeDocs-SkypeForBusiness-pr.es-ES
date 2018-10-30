---
title: "Implementar un reflejo de SQL para alta disponibilidad de servidores back-end"
TOCTitle: Implementar un reflejo de SQL para alta disponibilidad de servidores back-end
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48275612
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Para poder implementar la creación de reflejo de SQL, los servidores deben ejecutar un mínimo de SQL Server 2008 R2. Esta versión debe ejecutarse en todos los servidores implicados: principal, reflejo y testigo. Para más información, consulte [http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0xc0a).

En general, la configuración de creación de reflejo de SQL entre los dos servidores back-end con un testigo requiere lo siguiente:

  - La versión del servidor principal de SQL Server debe admitir la creación de reflejo de SQL.

  - El servidor principal, reflejo y testigo (si se implementan) deben tener la misma versión de SQL Server.

  - El servidor principal y el reflejo deben tener la misma edición de SQL Server. El testigo puede tener una edición diferente.

Para ver los procedimientos recomendados de SQL en relación con las versiones de SQL que son compatibles para un rol de testigo, consulte "Testigo de creación de reflejo de la base de datos" en MSDN Library, en [http://go.microsoft.com/fwlink/?linkid=247345\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=247345%26clcid=0xc0a)

Utiliza el Generador de topologías para implementar la creación de reflejo de SQL. Selecciona una opción en el Generador de topologías para crear un reflejo de las bases de datos y el Generador de topologías configura la creación de reflejo (y también la configuración de un testigo, si lo desea) cuando publica la topología. Tenga en cuenta que no existe ningún comando para implementar o eliminar solo un testigo, sino que este se instala o se elimina cuando se instala o se elimina el reflejo.

Para configurar la creación de reflejo de servidor, es necesario que primero configure los permisos de base de datos SQL correctamente. Para más información, vea "Configurar cuentas de inicio de sesión para la creación de reflejo de la base de datos o grupos de disponibilidad de AlwaysOn (SQL Server)" en [http://go.microsoft.com/fwlink/?linkid=268454\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268454%26clcid=0xc0a).

Con el reflejo de SQL, el modo de recuperación de bases de datos siempre está configurado como **Completa** . Esto significa que deberá controlar atentamente el tamaño del registro de transacciones y crear copias de seguridad de los registros de transacciones periódicamente para evitar que los servidores back-end se queden sin espacio en disco. La frecuencia con que se deben crear copias de seguridad de los registros de transacciones depende de la tasa de crecimiento del registro, que, a su vez, depende de las transacciones de la base de datos producidas por las actividades del usuario en el grupo de servidores front-end. Le recomendamos que determine el crecimiento estimado del registro de transacciones que se necesitará para la carga de trabajo de su implementación de Lync, de modo que pueda realizar la planeación en consonancia. En los artículos siguientes encontrará información adicional sobre la administración del registro y la copia de seguridad de SQL:

  - Modelos de recuperación de base de datos: "Modelos de recuperación (SQL Server)", en [http://go.microsoft.com/fwlink/?linkid=268446\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268446%26clcid=0xc0a)

  - Información general sobre la copia de seguridad: "Información general de copia de seguridad (SQL Server)", en [http://go.microsoft.com/fwlink/?linkid=268449\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268449%26clcid=0xc0a)

  - Creación de una copia de seguridad del registro de transacciones: "Realizar copia de seguridad de un registro de transacciones (SQL Server)", en [http://go.microsoft.com/fwlink/?linkid=268452\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268452%26clcid=0xc0a)

Con el reflejo de SQL, puede configurar la topología de creación de reflejos al crear los grupos o después de que ya se hayan creado los grupos.

> [!IMPORTANT]  
> El uso de Generador de topologías o de cmdlets para instalar y eliminar el reflejo de SQL se admite solo cuando el servidor principal, el reflejo y el testigo (si se desea) pertenecen al mismo dominio. Si desea configurar la creación del reflejo de SQL entre servidores de dominios diferentes, consulte la documentación sobre SQL Server.



> [!IMPORTANT]  
> Siempre que haga algún cambio en las conexiones entre reflejos de la base de datos back-end, deberá reiniciar todos los servidores front-end del grupo de servidores.<br />
> Para realizar cambios en relación con los reflejos (como cambiar la ubicación de un reflejo), use el Generador de topologías para realizar estas tres operaciones:
> <ol>
> <li><p>Quitar reflejos del servidor reflejado antiguo.</p></li>
> <li><p>Agregar reflejos al servidor reflejado nuevo.</p></li>
> <li><p>Publique la topología.</p></li>
> </ol>



> [!NOTE]
> Hay que crear un recurso compartido de archivos en el que puedan escribirse los archivos reflejados, y el servicio en el que se ejecutan SQL Server y SQL Agent necesita acceso de lectura y escritura. Si el servicio de SQL Server se ejecuta en el contexto de servicio de red, puede agregar &lt;Domain&gt;\\&lt;SQLSERVERNAME&gt;$ de los servidores SQL Server principal y reflejado a los permisos de recurso compartido. El $ es importante para identificar si se trata de una cuenta de equipo.



## Para configurar el reflejo de SQL al crear un grupo de servidores en Generador de topologías

1.  En la página **Definir el almacén de SQL** , haga clic en **Nuevo** junto al cuadro **Almacén de SQL** .

2.  En la página **Definir nuevo almacén de SQL** , especifique el almacén principal, seleccione **Esta instancia de SQL está en relación de reflejo** , especifique el número de puerto de creación de reflejo de SQL (el valor predeterminado es 5022) y, a continuación, haga clic en **Aceptar** .

3.  De vuelta en la página **Definir el almacén de SQL** , seleccione **Activar la creación de reflejo del almacén de SQL** .

4.  En la página **Definir nuevo almacén de SQL** , especifique el almacén de SQL que se utilizará como reflejo, seleccione **Esta instancia de SQL está en relación de reflejo** , especifique el número de puerto (el valor predeterminado es 5022) y, después, haga clic en **Aceptar** .

5.  Si desea un testigo para este reflejo, realice lo siguiente:
    
    1.  Seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** .
    
    2.  En la página **Definir el almacén de SQL** , seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y especifique el almacén de SQL que se utilizará como testigo.
    
    3.  Especifique el número de puerto (el valor predeterminado es 7022) y haga clic en **Aceptar** .

6.  Una vez que haya terminado de definir el grupo de servidores front-end y todos los demás roles de la topología, utilice el Generador de topologías para publicar la topología. Cuando se haya publicado la topología, si el grupo de servidores front-end que hospeda el Almacén de administración central tiene la creación de reflejo de SQL habilitada, verá una opción para crear bases de datos del almacén SQL tanto primarias como de reflejo de la manera siguiente:
    
    Haga clic en **Configuración** y escriba la ruta de acceso que se utilizará como recurso compartido de archivos para la copia de seguridad del reflejo.
    
    Haga clic en **Aceptar** y luego en **Siguiente** para crear las bases de datos y publicar la topología. Se implementarán los servidores de reflejo y de testigo (si se especificó).

Puede utilizar Generador de topologías para editar las propiedades de un grupo ya existente para habilitar la creación de reflejos de SQL.

## Para agregar la creación de reflejos de SQL a un grupo existente de servidores front-end en Generador de topologías

1.  En Generador de topologías, haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Modificar propiedades** .

2.  Seleccione **Habilitar creación de reflejos del almacén de SQL** y, después, haga clic en **Nuevo** , junto a **Creación de reflejos del almacén de SQL** .

3.  Especifique el almacén de SQL que desea utilizar como reflejo.

4.  Seleccione **Esta instancia de SQL está en relación de reflejo** , especifique el número de puerto de creación de reflejos de SQL (el puerto predeterminado es 5022) y, a continuación, haga clic en **Aceptar** .

5.  Si desea configurar un testigo, seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y haga clic en **Nuevo** .

6.  Especifique el almacén de SQL que desea utilizar como testigo.

7.  Seleccione **Esta instancia de SQL está en relación de reflejo** , especifique el número de puerto de creación de reflejos de SQL (el puerto predeterminado es 7022) y, a continuación, haga clic en **Aceptar** .

8.  Haga clic en **Aceptar** .

9.  Publique la topología. Al hacerlo, se le va a solicitar instalar la base de datos.
    
    Durante el proceso de publicación de la topologí, se le pedirá que defina una ruta del recurso compartido de archivos. Los servidores SQL Server que participan en el reflejo deben tener acceso de lectura y escritura a este recurso compartido de archivos para que se establezca el reflejo.

A continuación, debe instalar la base de datos antes de continuar con el procedimiento siguiente.

Debe tener en cuenta lo siguiente al configurar la creación de reflejos de SQL:

  - Si ya existe un extremo de creación de reflejos, se volverá a utilizar junto con los puertos definidos allí y pasará por alto los que especifique en la topología.

  - Cualquier puerto que ya haya sido asignado a otras aplicaciones en el mismo servidor, incluidos aquellos para otras instancias de SQL, no deben utilizarse para las instancias de SQL instaladas a mano. Esto implica que si tiene más de una instancia de SQL instalada en el mismo servidor, no deben usar el mismo puerto para la creación de reflejos. Para obtener más información, consulte los artículos siguientes:
    
      - "Especificar una dirección de red de servidor (creación de reflejo de la base de datos)", en MSDN Library, en [http://go.microsoft.com/fwlink/?linkid=247346\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=247346%26clcid=0xc0a)
    
      - "El extremo de creación de reflejo de la base de datos (SQL Server)", en [http://go.microsoft.com/fwlink/?linkid=247347\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=247347%26clcid=0xc0a)

## Uso de cmdlets de Shell de administración de Lync Server para configurar la creación de reflejos de SQL

La manera más sencilla de configurar la creación de reflejos es con el Generador de topologías, pero también puede utilizar cmdlets para hacerlo.

1.  Abra una ventana de Shell de administración de Lync Server y ejecute el siguiente cmdlet:
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    Por ejemplo:
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    Aparecerá lo siguiente:
    
        Database Name:rtcxds 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcshared 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcab 
                Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf 
                 Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsconfig 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:cpsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:xds 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:lis 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$
        [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): 

2.  Compruebe lo siguiente:
    
      - El puerto 5022 es accesible a través del firewall si el Firewall de Windows está habilitado en el servidor SQL Server primario e04-ocs.los\_a.lsipt.local\\rtc.
    
      - El puerto 5022 es accesible a través del firewall si el Firewall de Windows está habilitado en el servidor SQL Server de reflejo K16-ocs.los\_a.lsipt.local\\rtc.
    
      - El puerto 7022 es accesible a través del firewall si el Firewall de Windows está habilitado en el servidor SQL Server testigo AB14-lct.los\_a.lsipt.local\\rtc.
    
      - Las cuentas que ejecutan los servidores de Server SQL de todos los servidores SQL primarios y de reflejo tienen permiso de lectura y escritura en el recurso compartido de archivos \\\\E04-OCS\\csdatabackup
    
      - Asegúrese de que el proveedor de Instrumental de administración de Windows (WMI) se está ejecutando en todos estos servidores. El cmdlet utiliza dicho proveedor para encontrar la información de cuenta de los servicios de SQL Server que se ejecutan en el servidor principal, el reflejado y el testigo.
    
      - Asegúrese de que la cuenta que ejecuta este cmdlet tiene permiso para crear las carpetas que contendrán los archivos de registro y los datos de todos los servidores reflejados.
    
      - Es necesario que la cuenta de usuario en que se ejecuta la instancia de SQL tenga permisos de lectura y escritura en el recurso compartido de archivos. Si este recurso se encuentra en un servidor distinto y la instancia de SQL se ejecuta en una cuenta del sistema local, asegúrese de conceder los permisos del recurso compartido de archivos al servidor en que se hospeda la instancia de SQL.

3.  Escriba A y presione ENTRAR.
    
    Se configurará la creación de reflejos.

**Install-CsMirrorDatabase** instala el reflejo y configura la creación de reflejos para todas las bases de datos que están presentes en el almacén principal de SQL. Si desea configurar la creación de reflejos solo para bases de datos específicas, puede utilizar la opción de –DatabaseType; si desea configurar la creación de reflejos para todas las bases de datos excepto unas pocas, puede utilizar la opción –ExcludeDatabaseList, junto con una lista separada por comas que contengan los nombres de las bases de datos que se deban excluir.

Por ejemplo, si agrega la opción siguiente a **Install-CsMirrorDatabase**, se creará un reflejo de todas las bases de datos, excepto rtcab y rtcxds.

`-ExcludeDatabaseList rtcab,rtcxds`

Por ejemplo, si agrega la opción siguiente a **Install-CsMirrorDatabase**, solo se creará un reflejo de las bases de datos rtcab, rtcshared y rtcxds.

`-DatabaseType User`

## Supresión o cambio de un reflejo de SQL

Para quitar un reflejo de SQL de un grupo de servidores en el Generador de topologías, primero se debe quitar el reflejo en SQL Server utilizando un cmdlet. Después, podrá usar el Generador de topologías para quitar el reflejo de la topología. Para quitar el reflejo de SQL Server, use este cmdlet:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Por ejemplo, para quitar reflejos y anular las bases de datos de las bases de datos del usuario, escriba lo siguiente:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

La opción `-DropExistingDatabasesOnMirror` hace que las bases de datos afectadas se eliminen del reflejo.

Luego, para quitar el reflejo de la topología, haga lo siguiente:

1.  En Topology Builder, haga clic con el botón secundario en el grupo y haga clic en **Modificar propiedades** .

2.  Desactive **Habilitar creación de reflejos del almacén de SQL** y haga clic en **Aceptar** .

3.  Publique la topología.

## Supresión de un testigo de creación de reflejo

Realice este procedimiento si desea quitar un testigo de una configuración de creación de reflejo de un Servidor back-end.

1.  En el Generador de topologías, haga clic con el botón secundario en el grupo y luego haga clic en **Editar propiedades** .

2.  Desactive **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y haga clic en **Aceptar** .

3.  Publique la topología.
    
    Tras publicar la topología en el Generador de topologías, verá un mensaje que incluirá lo siguiente:
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    Sin embargo, no siga este paso ni escriba `Uninstall-CsMirrorDatabase`, ya que con ello se desinstalaría toda la configuración de la creación de reflejo.

4.  Para quitar solo el testigo de la configuración de SQL Server, siga las instrucciones descritas en "Quitar el testigo de una sesión de creación de reflejo de la base de datos (SQL Server)", disponible en [http://go.microsoft.com/fwlink/?linkid=268456\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=268456%26clcid=0xc0a).

