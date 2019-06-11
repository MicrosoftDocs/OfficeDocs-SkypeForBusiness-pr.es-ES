---
title: Implementar un reflejo de SQL para alta disponibilidad de servidores back-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb8c9647c24f326b1a2a51c99e7fa4ee5eafa23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a>Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-01-08_

Para poder implementar la creación de reflejo de SQL, los servidores deben ejecutar como mínimo SQL Server 2008 R2. Esta versión debe ejecutarse en todos los servidores implicados: principal, reflejo y testigo. Para obtener más información [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921), consulte.

En general, la configuración de creación de reflejo de SQL entre los dos servidores back-end con un testigo requiere lo siguiente:

  - La versión del servidor principal de SQL Server necesita ser compatible con la creación de reflejo de SQL.

  - El servidor principal, el reflejo y el testigo (si se implementan) necesitan tener la misma versión de SQL Server.

  - El servidor principal y el reflejo necesitan tener la misma edición de SQL Server. El testigo puede tener una edición diferente.

Para conocer los procedimientos recomendados de SQL en cuanto a las versiones de SQL admitidas para un rol testigo, consulte "testigo de creación de reflejos [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345)de base de datos" en la biblioteca MSDN en.

El generador de topología se usa para implementar el reflejo de SQL. Seleccione una opción en el generador de topología para reflejar las bases de datos y el generador de topologías configura el reflejo (incluida la configuración de un testigo, si lo desea) al publicar la topología. Observe que debe configurar o quitar el testigo al mismo tiempo que configura o quita el reflejo. No hay un comando independiente para implementar o quitar solo un testigo.

Para configurar la creación de reflejo de servidor, es necesario que primero configure los permisos de base de datos SQL correctamente. Para obtener más información, consulte "configurar cuentas de inicio de sesión para el reflejo de bases de datos o grupos de disponibilidad [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454)AlwaysOn (SQL Server)" en.

Con el reflejo de SQL, el modo de recuperación de bases de datos siempre está configurado como **Completa**. Esto significa que es preciso controlar atentamente el tamaño del registro de transacciones y crear copias de seguridad de los registros de transacciones periódicamente para evitar que los servidores back-end se queden sin espacio en disco. La frecuencia con que se necesitan crear copias de seguridad de los registros de transacciones depende de la tasa de crecimiento del registro, que, a su vez, depende de las transacciones de la base de datos producidas por las actividades del usuario en el grupo de servidores front-end. Recomendamos que determine el crecimiento estimado del registro de transacciones para la carga de trabajo de la implementación de Skype Empresarial, de modo que pueda realizar la planeación en consonancia. En los artículos siguientes encontrará información adicional sobre la administración del registro y la copia de seguridad de SQL:

  - Modelos de recuperación de bases de datos: "modelos de recuperación (SQL Server)" en[http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)

  - Información general sobre copia de seguridad: "información general de copia de seguridad (SQL Server)" en[http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)

  - Registro de transacciones de copia de seguridad: "copia de seguridad de un registro de transacciones (SQL Server)" en[http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)

Con el reflejo de SQL, puede configurar la topología de creación de reflejos al crear los grupos o después de que ya se hayan creado los grupos.



> [!IMPORTANT]
> Usar el generador de topología o cmdlets para configurar y quitar la creación de reflejos de SQL solo se admite cuando los servidores principal, reflejado y testigo (si lo desea) pertenecen al mismo dominio. Si desea configurar la creación del reflejo de SQL entre servidores de dominios diferentes, consulte la documentación de SQL Server.





> [!IMPORTANT]
> Siempre que haga algún cambio en las conexiones entre reflejos de la base de datos back-end, deberá reiniciar todos los servidores front-end del grupo de servidores. <BR>Para realizar un cambio en la creación de reflejos, (por ejemplo, cambiar la ubicación de un reflejo), debe usar el generador de topologías para realizar estos tres pasos: 
> <OL>
> <LI>
> <P>Quite reflejos del servidor reflejado antiguo.</P>
> <LI>
> <P>Agregue reflejos al servidor reflejado nuevo.</P>
> <LI>
> <P>Publique la topología.</P></LI></OL>




> [!NOTE]
> Hay que crear un recurso compartido de archivos en el que puedan escribirse los archivos reflejados, y el servicio en el que se ejecutan SQL Server y SQL Agent necesita acceso de lectura y escritura. Si el servicio de SQL Server se ejecuta en el contexto de servicio de red, puede &lt;agregar&gt; el &lt;&#92;&gt;de dominio SQLSERVERNAME $ de los servidores SQL principal y de espejo a los permisos de uso compartido. El $ es importante para identificar si se trata de una cuenta de equipo.


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>Para configurar el reflejo de SQL durante la creación de un grupo en el generador de topologías

1.  En la página **Definir el almacén de SQL**, haga clic en **Nuevo** junto al cuadro **Almacén de SQL**. 

2.  En la página **Definir nuevo almacén de SQL**, especifique el almacén principal, seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto de creación de reflejo de SQL (el valor predeterminado es 5022) y, a continuación, haga clic en **Aceptar**.

3.  De vuelta en la página **Definir el almacén de SQL**, seleccione **Activar la creación de reflejo del almacén de SQL**. 

4.  En la página **Definir nuevo almacén de SQL**, especifique el almacén de SQL que se utilizará como reflejo, seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto (el valor predeterminado es 5022) y, después, haga clic en **Aceptar**.

5.  Si desea un testigo para este reflejo, realice lo siguiente: 
    
    1.  Seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática**. 
    
    2.  En la página **Definir el almacén de SQL**, seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y especifique el almacén de SQL que se utilizará como testigo. 
    
    3.  Especifique el número de puerto (el valor predeterminado es 7022) y haga clic en **Aceptar**. 

6.  Una vez que haya terminado de definir el grupo de servidores front-end y todos los demás roles de su topología, use el generador de topología para publicar la topología. Cuando se publique la topología, si el grupo de servidores front-end que hospeda el almacén de administración central tiene habilitado el reflejo de SQL, verá una opción para crear bases de datos de almacenamiento de SQL principales y reflejadas.
    
    Haga clic en **Configuración** y escriba la ruta de acceso que se utilizará como recurso compartido de archivos para la copia de seguridad del reflejo.
    
    Haga clic en **Aceptar** y luego en **Siguiente** para crear las bases de datos y publicar la topología. Se implementarán los servidores de reflejo y de testigo (si se especificó).

Puede usar el generador de topología para editar las propiedades de un grupo ya existente para habilitar el reflejo SQL.

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>Para agregar reflejo SQL a un grupo front end existente en el generador de topología

1.  En el generador de topología, haga clic con el botón secundario en el grupo y luego haga clic en **Editar propiedades**.

2.  Seleccione **Habilitar creación de reflejos del almacén de SQL** y, después, haga clic en **Nuevo**, junto a **Creación de reflejos del almacén de SQL**. 

3.  Especifique el almacén de SQL que desea utilizar como reflejo. 

4.  Seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto de creación de reflejos de SQL (el puerto predeterminado es 5022) y, a continuación, haga clic en **Aceptar**.

5.  Si desea configurar un testigo, seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y haga clic en **Nuevo**. 

6.  Especifique el almacén de SQL que desea utilizar como testigo. 

7.  Seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto de creación de reflejos de SQL (el puerto predeterminado es 7022) y, a continuación, haga clic en **Aceptar**.

8.  Haga clic en **Aceptar**.

9.  Publique la topología. Al hacerlo, se le va a solicitar instalar la base de datos. 
    
    Durante el proceso de publicación de la topología, se le pedirá que defina una ruta del recurso compartido de archivos. Los servidores SQL Server que participan en el reflejo deben tener acceso de lectura y escritura a este recurso compartido de archivos para que se establezca el reflejo.

A continuación, debe instalar la base de datos antes de continuar con el procedimiento siguiente.

Debe tener en cuenta lo siguiente al configurar la creación de reflejos de SQL:

  - Si ya existe un extremo de creación de reflejos, se volverá a utilizar junto con los puertos definidos allí y pasará por alto los que especifique en la topología.

  - Cualquier puerto que ya haya sido asignado a otras aplicaciones en el mismo servidor, incluidos aquellos para otras instancias de SQL, no deben utilizarse para las instancias de SQL instaladas a mano. Esto implica que si tiene más de una instancia de SQL instalada en el mismo servidor, no deben usar el mismo puerto para la creación de reflejos. Para obtener más información, consulte los artículos siguientes:
    
      - "Especifique una dirección de red del servidor (reflejo de base de datos)" en la biblioteca de MSDN en[http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)
    
      - "El punto de conexión de creación de reflejo de la base de datos (SQL Server)" en[http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Usar los cmdlets del shell de administración de Lync Server para configurar el reflejo SQL

La forma más sencilla de configurar el reflejo es mediante el generador de topologías, pero también puede hacerlo con los cmdlets.

1.  Abra una ventana del shell de administración de Lync Server y ejecute el siguiente cmdlet:
    
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
    
      - El puerto 5022 es accesible a través del firewall si el Firewall de Windows está habilitado en el servidor\_SQL Server E04-OCS. RTC\\local. lsipt.
    
      - Se puede acceder al puerto 5022 a través del firewall si el Firewall de Windows está habilitado en el\_servidor SQL Server de duplicación K16-OCS. RTC local\\.
    
      - El puerto 7022 es accesible a través del firewall si el Firewall de Windows está habilitado en el servidor\_SQL testigo AB14-LCT. RTC\\local. lsipt.
    
      - Las cuentas que ejecutan los servidores SQL en todos los servidores SQL principal y de espejo tienen permiso de lectura \\ \\y escritura para\\el archivo de recursos compartidos de E04-OCS csdatabackup
    
      - Asegúrese de que el proveedor de Instrumental de administración de Windows (WMI) se está ejecutando en todos estos servidores. El cmdlet utiliza dicho proveedor para encontrar la información de cuenta de los servicios de SQL Server que se ejecutan en el servidor principal, el reflejado y el testigo. 
    
      - Asegúrese de que la cuenta que ejecuta este cmdlet tiene permiso para crear las carpetas que contendrán los archivos de registro y los datos de todos los servidores reflejados. 
    
      - Es necesario que la cuenta de usuario en que se ejecuta la instancia de SQL tenga permisos de lectura y escritura en el recurso compartido de archivos. Si este recurso se encuentra en un servidor distinto y la instancia de SQL se ejecuta en una cuenta del sistema local, asegúrese de conceder los permisos del recurso compartido de archivos al servidor en que se hospeda la instancia de SQL.

3.  Escriba A y presione ENTRAR.
    
    Se configurará la creación de reflejos.

**Install-CsMirrorDatabase** instala el reflejo y configura la creación de reflejos para todas las bases de datos que están presentes en el almacén principal de SQL. Si desea configurar la creación de reflejos solo para bases de datos específicas, puede utilizar la opción –DatabaseType; si desea configurar la creación de reflejos para todas las bases de datos excepto unas pocas, puede utilizar la opción –ExcludeDatabaseList, junto con una lista separada por comas que contenga los nombres de las bases de datos que se deban excluir.

Por ejemplo, si agrega la opción siguiente a **Install-CsMirrorDatabase**, se creará un reflejo de todas las bases de datos, excepto rtcab y rtcxds.

`-ExcludeDatabaseList rtcab,rtcxds`

Por ejemplo, si agrega la opción siguiente a **Install-CsMirrorDatabase**, solo se creará un reflejo de las bases de datos rtcab, rtcshared y rtcxds.

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a>Supresión o cambio de un reflejo de SQL

Para quitar un reflejo de SQL de un grupo de servidores en el Generador de topologías, primero se debe quitar el reflejo en SQL Server utilizando un cmdlet. Después, podrá usar el Generador de topologías para quitar el reflejo de la topología. Para quitar el reflejo de SQL Server, use este cmdlet:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Por ejemplo, para quitar reflejos y anular las bases de datos de las bases de datos del usuario, escriba lo siguiente:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

Esta `-DropExistingDatabasesOnMirror` opción hace que las bases de datos afectadas se eliminen del reflejo.

Luego, para quitar el reflejo de la topología, haga lo siguiente:

1.  En Generador de topologías, haga clic con el botón derecho en el grupo y haga clic en **Modificar propiedades**.

2.  Desactive **Habilitar creación de reflejos del almacén de SQL** y haga clic en **Aceptar**.

3.  Publique la topología.

</div>

<div>

## <a name="removing-a-mirroring-witness"></a>Supresión de un testigo de creación de reflejo

Use este procedimiento si necesita quitar el testigo de una configuración de reflejo del servidor back-end.

1.  En Generador de topologías, haga clic con el botón derecho en el grupo y haga clic en **Modificar propiedades**.

2.  Desactive **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y haga clic en **Aceptar**.

3.  Publique la topología.
    
    Después de publicar la topología, el generador de topología verá un mensaje que incluye lo siguiente:
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    Sin embargo, no siga ese paso y no escriba `Uninstall-CsMirrorDatabase` de la forma que desinstalaría toda la configuración de la duplicación.

4.  Para quitar solo el testigo de la configuración de SQL Server, siga las instrucciones de "quitar el testigo de una sesión de creación de reflejo de la base de [http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456)datos (SQL Server)" en.

</div>

</div>

<span> </span>

</div>

</div>

</div>

