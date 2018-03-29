---
title: Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 'Para poder implementar la creación de reflejo de SQL, los servidores deben ejecutar como mínimo SQL Server 2008 R2. Esta versión debe ejecutarse en todos los servidores implicados: principal, reflejo y testigo. Para obtener información detallada, vea acumulado 9 de paquete de actualización para el Service Pack 1 de SQL Server 2008.'
ms.openlocfilehash: 8de94fc0e15b1d851b43b386b476abfa776fad2d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Skype Empresarial Server 2015
 

Para poder implementar la creación de reflejo de SQL, los servidores deben ejecutar como mínimo SQL Server 2008 R2. Esta versión debe ejecutarse en todos los servidores implicados: principal, reflejo y testigo. Para obtener información detallada, vea [9 para SQL Server 2008 Service Pack 1 del paquete de actualización acumulativa ](http://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).
  
En general, la configuración de creación de reflejo de SQL entre los dos servidores back-end con un testigo requiere lo siguiente:
  
- Versión del servidor principal de SQL Server debe ser compatible con la creación de reflejos de SQL.
    
- El servidor principal, el reflejo y el testigo (si se implementan) necesitan tener la misma versión de SQL Server. 
    
- El servidor principal y el reflejo necesitan tener la misma edición de SQL Server. El testigo puede tener una edición diferente.
    
Para recomendaciones SQL en términos de qué versiones SQL son compatibles para un rol de testigo, vea [Testigo de reflejo de base de datos](https://go.microsoft.com/fwlink/p/?LinkId=247345).
  
Utilice el generador de topología para implementar la creación de reflejos de SQL. Seleccione una opción en el generador de topología para reflejar las bases de datos y generador de topología configura el reflejo (incluyendo la configuración de un testigo, si se desea) al publicar la topología. Tenga en cuenta que configurar o quitar al testigo al mismo tiempo, configurar o quitar el espejo. No hay ningún comando independiente para implementar o quitar a sólo un testigo.
  
Para configurar la creación de reflejo de servidor, es necesario que primero configure los permisos de base de datos SQL correctamente. Para obtener más información, consulte [Set Up Accounts inicio de sesión para la creación de reflejo de base de datos o grupos de disponibilidad AlwaysOn (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).
  
Con el reflejo de SQL, el modo de recuperación de bases de datos siempre está configurado como **Completa**. Esto significa que es preciso controlar atentamente el tamaño del registro de transacciones y crear copias de seguridad de los registros de transacciones periódicamente para evitar que los servidores back-end se queden sin espacio en disco. La frecuencia con que se necesita crear copias de seguridad de los registros de transacciones depende de la tasa de crecimiento del registro, que, a su vez, depende de las transacciones de la base de datos producidas por las actividades del usuario en el grupo de servidores front-end. Recomendamos que determine el crecimiento estimado del registro de transacciones para la carga de trabajo de la implementación, de modo que pueda realizar la planeación en consonancia. En los artículos siguientes encontrará información adicional sobre la administración del registro y la copia de seguridad de SQL:
  
- [Modelos de recuperación de base de datos](https://go.microsoft.com/fwlink/p/?LinkId=268446)
    
- [Visión general de backup](https://go.microsoft.com/fwlink/p/?LinkId=268449)
    
- [Registro de copia de seguridad de transacciones](https://go.microsoft.com/fwlink/p/?LinkId=268452)
    
Con el reflejo de SQL, puede configurar la topología de creación de reflejos al crear los grupos o después de que ya se hayan creado los grupos.
  
> [!IMPORTANT]
> Mediante el generador de topología o cmdlets para configurar y quitar SQL reflejo sólo se admite cuando el principal, réplica y servidores testigo (si lo desea) pertenecen al mismo dominio. Si desea configurar la creación del reflejo de SQL entre servidores de dominios diferentes, consulte la documentación de SQL Server. 
  
> [!IMPORTANT]
> Siempre que haga algún cambio en las conexiones entre reflejos de la base de datos back-end, deberá reiniciar todos los servidores front-end del grupo de servidores.  > Para un cambio en el reflejo, (como cambiar la ubicación de un espejo), debe utilizar el generador de topología para realizar estos tres pasos: 
  
1. Quite reflejos del servidor reflejado antiguo.
    
2. Agregue reflejos al servidor reflejado nuevo.
    
3. Publique la topología.
    
> [!NOTE]
> Hay que crear un recurso compartido de archivos en el que puedan escribirse los archivos reflejados, y el servicio en el que se ejecutan SQL Server y SQL Agent necesita acceso de lectura y escritura. Si el servicio SQL Server se ejecuta bajo el contexto de servicio de red, puede agregar \<dominio\>\\< SQLSERVERNAME\>$ de los servidores SQL de espejo y Principal a los permisos de recurso compartido. El $ es importante para identificar si se trata de una cuenta de equipo. 
  
## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>Para configurar la creación de reflejos de SQL al crear un grupo en el generador de topología

1. En la página **Definir el almacén de SQL**, haga clic en **Nuevo** junto al cuadro **Almacén de SQL**. 
    
2. En la página **Definir nuevo almacén de SQL**, especifique el almacén principal, seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto de creación de reflejo de SQL (el valor predeterminado es 5022) y, a continuación, haga clic en **Aceptar**.
    
3. De vuelta en la página **Definir el almacén de SQL**, seleccione **Activar la creación de reflejo del almacén de SQL**.  
    
4. En la página **Definir nuevo almacén de SQL**, especifique el almacén de SQL que se utilizará como reflejo, seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto (el valor predeterminado es 5022) y, después, haga clic en **Aceptar**.
    
5. Si desea un testigo para este reflejo, realice lo siguiente:  
    
    a. Seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática**.  
    
    b. En la página **Definir el almacén de SQL**, seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y especifique el almacén de SQL que se utilizará como testigo.  
    
    c. Especifique el número de puerto (el valor predeterminado es 7022) y haga clic en **Aceptar**.  
    
6. Cuando termine de definir el grupo de servidores Front-End y todas las demás funciones en la topología, utilice el generador de topología para publicar la topología. Cuando se publica la topología, si el grupo de Front-End que aloja el almacén de Administración Central tiene la creación de reflejos de SQL habilitado, verá una opción para crear ambos principal y realiza espejado de bases de datos SQL.
    
    Haga clic en **Configuración** y escriba la ruta de acceso que se utilizará como recurso compartido de archivos para la copia de seguridad del reflejo.
    
    Haga clic en **Aceptar** y luego en **Siguiente** para crear las bases de datos y publicar la topología. Se implementarán los servidores de reflejo y de testigo (si se especificó).
    
Puede utilizar el generador de topología para editar las propiedades de un grupo ya existente para permitir la creación de reflejos de SQL. 
  
## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>Para agregar la creación de reflejos de SQL a un grupo existente de Front-End en el generador de topología

1. En el generador de topología (ratón) en el grupo y, a continuación, haga clic en **Editar propiedades**.
    
2. Seleccione **Habilitar creación de reflejos del almacén de SQL** y, después, haga clic en **Nuevo**, junto a **Creación de reflejos del almacén de SQL**.  
    
3. Especifique el almacén de SQL que desea utilizar como reflejo.  
    
4. Seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto de creación de reflejos de SQL (el puerto predeterminado es 5022) y, a continuación, haga clic en **Aceptar**.
    
5. Si desea configurar un testigo, seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y haga clic en **Nuevo**.  
    
6. Especifique el almacén de SQL que desea utilizar como testigo.  
    
7. Seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto de creación de reflejos de SQL (el puerto predeterminado es 7022) y, a continuación, haga clic en **Aceptar**.
    
8. Haga clic en **Aceptar**.
    
9. Publique la topología. Al hacerlo, se le va a solicitar instalar la base de datos.  
    
    Durante el proceso de publicación de la topología, se le pedirá que defina una ruta del recurso compartido de archivos. Los servidores SQL Server que participan en el reflejo deben tener acceso de lectura y escritura a este recurso compartido de archivos para que se establezca el reflejo.
    
A continuación, debe instalar la base de datos antes de continuar con el procedimiento siguiente.
  
Debe tener en cuenta lo siguiente al configurar la creación de reflejos de SQL:
  
- Si ya existe un extremo de creación de reflejos, se volverá a utilizar junto con los puertos definidos allí y pasará por alto los que especifique en la topología.
    
- Cualquier puerto que ya haya sido asignado a otras aplicaciones en el mismo servidor, incluidos aquellos para otras instancias de SQL, no deben utilizarse para las instancias de SQL instaladas a mano. Esto implica que si tiene más de una instancia de SQL instalada en el mismo servidor, no deben usar el mismo puerto para la creación de reflejos. Para obtener más información, consulte los artículos siguientes:
    
  - [Especificar una dirección de red de servidor (creación de reflejo de base de datos)](https://go.microsoft.com/fwlink/p/?LinkId=247346)
    
  - [La base de datos reflejada extremo (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=247347)
    
## <a name="using-skype-for-business-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Utiliza Skype para los Cmdlets del Shell de administración de Business Server para configurar el reflejo de SQL

La forma más sencilla de establecer la creación de reflejos es mediante el generador de topología, pero también puede hacerlo mediante cmdlets.
  
1. Abra un Skype para la ventana de Shell de administración de servidor empresarial y ejecute el siguiente cmdlet:
    
   ```
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 

   ```

    Por ejemplo:
    
   ```
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 

   ```

    Aparecerá lo siguiente:
    
  ```
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

  ```

2. Compruebe lo siguiente:
    
    - El puerto 5022 es accesible a través del firewall si el Firewall de Windows está habilitado en el servidor SQL Server primario e04-ocs.los_a.lsipt.local\rtc.  
    
    - El puerto 5022 es accesible a través del firewall si el Firewall de Windows está habilitado en el servidor SQL Server de reflejo K16-ocs.los_a.lsipt.local\rtc.  
    
    - El puerto 7022 es accesible a través del firewall si el Firewall de Windows está habilitado en el servidor SQL Server testigo AB14-lct.los_a.lsipt.local\rtc.  
    
   - Las cuentas de los servidores de SQL en todos los principales y los servidores SQL de espejo tienen permiso de lectura y escritura al recurso compartido de archivo \\E04 OCS\csdatabackup 
    
   - Asegúrese de que el proveedor de Instrumental de administración de Windows (WMI) se está ejecutando en todos estos servidores. El cmdlet utiliza dicho proveedor para encontrar la información de cuenta de los servicios de SQL Server que se ejecutan en el servidor principal, el reflejado y el testigo.  
    
   - Asegúrese de que la cuenta que ejecuta este cmdlet tiene permiso para crear las carpetas que contendrán los archivos de registro y los datos de todos los servidores reflejados.  
    
   - Es necesario que la cuenta de usuario en que se ejecuta la instancia de SQL tenga permisos de lectura y escritura en el recurso compartido de archivos. Si este recurso se encuentra en un servidor distinto y la instancia de SQL se ejecuta en una cuenta del sistema local, asegúrese de conceder los permisos del recurso compartido de archivos al servidor en que se hospeda la instancia de SQL.
    
3. Escriba A y presione ENTRAR.
    
    Se configurará la creación de reflejos.
    
    **CsMirrorDatabase de instalación** instala el espejo y configura espejado para todas las bases de datos están presentes en el almacén principal de SQL. Si desea configurar el reflejo de bases de datos específicas, puede utilizar la opción - tipodebasededatos, o si desea configurar el reflejo de todas las bases de datos excepto algunos, puede utilizar la opción - ExcludeDatabaseList, junto con una lista separada por comas de base de datos Para excluir los nombres.
  
    Por ejemplo, si agrega la opción siguiente para **Instalar CsMirrorDatabase**, se reflejará todas las bases de datos excepto rtcab y rtcxds.
  
    `-ExcludeDatabaseList rtcab,rtcxds`
  
   Por ejemplo, si agrega la opción siguiente para **Instalar CsMirrorDatabase**, se reflejará sólo las bases de datos rtcab, rtcshared y rtcxds.
  
    `-DatabaseType User`
  
## <a name="removing-or-changing-sql-mirroring"></a>Supresión o cambio de un reflejo de SQL

Para quitar un reflejo de SQL de un grupo de servidores en el Generador de topologías, primero se debe quitar el reflejo en SQL Server utilizando un cmdlet. Después, podrá usar el Generador de topologías para quitar el reflejo de la topología. Para quitar el reflejo de SQL Server, use este cmdlet:
  
```
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

```

Por ejemplo, para quitar reflejos y anular las bases de datos de las bases de datos del usuario, escriba lo siguiente:
  
```
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

```

La `-DropExistingDatabasesOnMirror` opción hace que las bases de datos afectadas se eliminarán del espejo retrovisor.
  
Luego, para quitar el reflejo de la topología, haga lo siguiente:
  
1. En Generador de topologías, haga clic con el botón derecho en el grupo y haga clic en **Modificar propiedades**.
    
2. Desactive **Habilitar creación de reflejos del almacén de SQL** y haga clic en **Aceptar**.
    
3. Publique la topología.
    
## <a name="removing-a-mirroring-witness"></a>Supresión de un testigo de creación de reflejo

Utilice este procedimiento si necesita quitar al testigo de un nuevo servidor configuración de creación de reflejo.
  
1. En Generador de topologías, haga clic con el botón derecho en el grupo y haga clic en **Modificar propiedades**. 
    
2. Desactive **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y haga clic en **Aceptar**.
    
3. Publique la topología.
    
    Después de publicar la topología, el generador de topología se verá un mensaje que incluye la siguiente
    
   ```
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    Sin embargo, no siga este paso y no escriba `Uninstall-CsMirrorDatabase` como que sería desinstalar toda la configuración de creación de reflejos.
    
4. Para quitar a sólo el testigo de la configuración de SQL Server, siga las instrucciones para [quitar al testigo de una sesión de creación de reflejo de base de datos (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).
    

