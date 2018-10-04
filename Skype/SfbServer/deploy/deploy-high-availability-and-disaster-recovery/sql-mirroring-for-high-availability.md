---
title: Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: 'Para poder implementar la creación de reflejo de SQL, los servidores deben ejecutar como mínimo SQL Server 2008 R2. Esta versión debe ejecutarse en todos los servidores implicados: principal, reflejo y testigo. Para obtener información detallada, vea acumulativa 9 de paquete de actualización para SQL Server 2008 Service Pack 1.'
ms.openlocfilehash: 9ea6e8a48fbcc3f5938c33e9d06db3c882f28de2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373803"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>Implementar la creación de reflejos de SQL para el servidor Back-End una alta disponibilidad en Skype para Business server 2015


Para poder implementar la creación de reflejo de SQL, los servidores deben ejecutar como mínimo SQL Server 2008 R2. Esta versión debe ejecutarse en todos los servidores implicados: principal, reflejo y testigo. Para obtener información detallada, vea [9 para SQL Server 2008 Service Pack 1 del paquete de actualización acumulativa ](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).

En general, la configuración de creación de reflejo de SQL entre los dos servidores back-end con un testigo requiere lo siguiente:

- Versión del servidor principal de SQL Server debe admitir la creación de reflejos de SQL.

- El servidor principal, el reflejo y el testigo (si se implementan) necesitan tener la misma versión de SQL Server.

- El servidor principal y el reflejo necesitan tener la misma edición de SQL Server. El testigo puede tener una edición diferente.

Procedimientos recomendados de SQL en términos de qué versiones SQL son compatibles para un rol de testigo, vea [El testigo de la creación de reflejo de base de datos](https://go.microsoft.com/fwlink/p/?LinkId=247345).

Use el generador de topología para implementar la creación de reflejos de SQL. Seleccione una opción en el generador de topología para reflejar las bases de datos y el generador de topología configura la creación de reflejos (incluyendo la configuración de un testigo, si lo desea) cuando publique la topología. Tenga en cuenta que configurar o quitar al testigo al mismo tiempo, puede configurar o quitar el reflejo. No hay ningún comando independiente para implementar o quitar a sólo un testigo.

Para configurar la creación de reflejo de servidor, es necesario que primero configure los permisos de base de datos SQL correctamente. Para obtener información detallada, vea [Establecer seguridad de cuentas de inicio de sesión para la creación de reflejo de base de datos o grupos de disponibilidad AlwaysOn (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).

Con el reflejo de SQL, el modo de recuperación de bases de datos siempre está configurado como **Completa**. Esto significa que es preciso controlar atentamente el tamaño del registro de transacciones y crear copias de seguridad de los registros de transacciones periódicamente para evitar que los servidores back-end se queden sin espacio en disco. La frecuencia con que se necesita crear copias de seguridad de los registros de transacciones depende de la tasa de crecimiento del registro, que, a su vez, depende de las transacciones de la base de datos producidas por las actividades del usuario en el grupo de servidores front-end. Recomendamos que determine el crecimiento estimado del registro de transacciones para la carga de trabajo de la implementación, de modo que pueda realizar la planeación en consonancia. En los artículos siguientes encontrará información adicional sobre la administración del registro y la copia de seguridad de SQL:

- [Modelos de recuperación de base de datos](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [Introducción a la copia de seguridad](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [Registro de transacciones de copia de seguridad](https://go.microsoft.com/fwlink/p/?LinkId=268452)

Con el reflejo de SQL, puede configurar la topología de creación de reflejos al crear los grupos o después de que ya se hayan creado los grupos.

> [!IMPORTANT]
> La creación de reflejos se admite el uso de Topology Builder o cmdlets para configurar y quitar SQL sólo cuando la principal, reflejado y servidores testigo (si así lo desea) pertenecen al mismo dominio. Si desea configurar la creación del reflejo de SQL entre servidores de dominios diferentes, consulte la documentación de SQL Server.

> [!IMPORTANT]
> Siempre que haga algún cambio en las conexiones entre reflejos de la base de datos back-end, deberá reiniciar todos los servidores front-end del grupo de servidores.  > Para un cambio en la creación de reflejos, (por ejemplo, para cambiar la ubicación de un reflejo), debe usar el generador de topología para llevar a cabo estos tres pasos:

1. Quite reflejos del servidor reflejado antiguo.

2. Agregue reflejos al servidor reflejado nuevo.

3. Publique la topología.

> [!NOTE]
> Hay que crear un recurso compartido de archivos en el que puedan escribirse los archivos reflejados, y el servicio en el que se ejecutan SQL Server y SQL Agent necesita acceso de lectura y escritura. Si el servicio SQL Server se está ejecutando en el contexto de servicio de red, puede agregar \<dominio\>\\< NOMBREDESERVIDORSQL\>$ de los servidores de SQL de reflejo y de entidad de seguridad a los permisos de recurso compartido. El $ es importante para identificar si se trata de una cuenta de equipo.

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>Para configurar la creación de reflejos de SQL al crear un grupo de servidores en el generador de topología

1. En la página **Definir el almacén de SQL**, haga clic en **Nuevo** junto al cuadro **Almacén de SQL**. 

2. En la página **Definir nuevo almacén de SQL**, especifique el almacén principal, seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto de creación de reflejo de SQL (el valor predeterminado es 5022) y, a continuación, haga clic en **Aceptar**.

3. De vuelta en la página **Definir el almacén de SQL**, seleccione **Activar la creación de reflejo del almacén de SQL**. 

4. En la página **Definir nuevo almacén de SQL**, especifique el almacén de SQL que se utilizará como reflejo, seleccione **Esta instancia de SQL está en relación de reflejo**, especifique el número de puerto (el valor predeterminado es 5022) y, después, haga clic en **Aceptar**.

5. Si desea un testigo para este reflejo, realice lo siguiente: 

    a. Seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática**. 

    b. En la página **Definir el almacén de SQL**, seleccione **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y especifique el almacén de SQL que se utilizará como testigo. 

    c. Especifique el número de puerto (el valor predeterminado es 7022) y haga clic en **Aceptar**. 

6. Una vez haya terminado de definir el grupo de servidores Front-End y todas las demás funciones en la topología, use el generador de topología para publicar la topología. Cuando se publica la topología, si el grupo de servidores Front-End que hospeda el almacén de Administración Central tiene habilitado el reflejo de SQL, verá una opción para crear ambos principal y reflejada bases de datos de almacén SQL.

    Haga clic en **Configuración** y escriba la ruta de acceso que se utilizará como recurso compartido de archivos para la copia de seguridad del reflejo.

    Haga clic en **Aceptar** y luego en **Siguiente** para crear las bases de datos y publicar la topología. Se implementarán los servidores de reflejo y de testigo (si se especificó).

Puede usar el generador de topología para editar las propiedades de un grupo de servidores ya existente para habilitar la creación de reflejos de SQL.

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>Para agregar la creación de reflejos de SQL a un grupo de servidores Front-End existente en el generador de topología

1. En el generador, haga clic en el grupo de servidores y, a continuación, haga clic en **Editar propiedades**.

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

  - [Especificar una dirección de red de servidor (creación de reflejos de base de datos)](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [La base de datos de la creación de reflejos extremo (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a>Uso de Skype para Cmdlets de Shell de administración de servidor 2015 empresarial al conjunto de la creación de reflejos de SQL

La forma más sencilla de configurar la creación de reflejos es mediante el generador de topología, pero también puede hacerlo mediante los cmdlets.

1. Abra un Skype para la ventana de Shell de administración de Business Server 2015 y ejecute el siguiente cmdlet:

   ```
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    Por ejemplo:

   ```
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    Aparecerá lo siguiente:

   <pre>
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
   </pre>

2. Compruebe lo siguiente:

    - El puerto 5022 es accesible a través del firewall si el Firewall de Windows está habilitado en el servidor SQL Server primario e04-ocs.los_a.lsipt.local\rtc. 

    - El puerto 5022 es accesible a través del firewall si el Firewall de Windows está habilitado en el servidor SQL Server de reflejo K16-ocs.los_a.lsipt.local\rtc. 

    - El puerto 7022 es accesible a través del firewall si el Firewall de Windows está habilitado en el servidor SQL Server testigo AB14-lct.los_a.lsipt.local\rtc. 

   - Las cuentas que se ejecutan los servidores de SQL en todos los principales y los servidores SQL Server de reflejo tienen permiso de lectura y escritura para el recurso compartido de archivos \\E04 OCS\csdatabackup

   - Asegúrese de que el proveedor de Instrumental de administración de Windows (WMI) se está ejecutando en todos estos servidores. El cmdlet utiliza dicho proveedor para encontrar la información de cuenta de los servicios de SQL Server que se ejecutan en el servidor principal, el reflejado y el testigo. 

   - Asegúrese de que la cuenta que ejecuta este cmdlet tiene permiso para crear las carpetas que contendrán los archivos de registro y los datos de todos los servidores reflejados. 

   - Es necesario que la cuenta de usuario en que se ejecuta la instancia de SQL tenga permisos de lectura y escritura en el recurso compartido de archivos. Si este recurso se encuentra en un servidor distinto y la instancia de SQL se ejecuta en una cuenta del sistema local, asegúrese de conceder los permisos del recurso compartido de archivos al servidor en que se hospeda la instancia de SQL.

3. Escriba A y presione ENTRAR.

    Se configurará la creación de reflejos.

    **Install-CsMirrorDatabase** el reflejo se instala y configura la creación de reflejos para todas las bases de datos que están presentes en el almacén de SQL principal. Si desea configurar la creación de reflejos de bases de datos sólo específicas, puede usar la opción - tipodebasededatos o, si desea configurar la creación de reflejos para todas las bases de datos, excepto algunos, puede usar la opción - ExcludeDatabaseList, junto con una lista separada por comas de base de datos nombres que se deben excluir.

    Por ejemplo, si agrega la opción siguiente a **Install-CsMirrorDatabase**, se reflejará todas las bases de datos, excepto rtcab y rtcxds.

    `-ExcludeDatabaseList rtcab,rtcxds`

   Por ejemplo, si agrega la opción siguiente a **Install-CsMirrorDatabase**, se reflejará sólo las bases de datos rtcab, rtcshared y rtcxds.

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

La `-DropExistingDatabasesOnMirror` opción hace que las bases de datos afectados que se eliminará de la réplica.

Luego, para quitar el reflejo de la topología, haga lo siguiente:

1. En Generador de topologías, haga clic con el botón derecho en el grupo y haga clic en **Modificar propiedades**.

2. Desactive **Habilitar creación de reflejos del almacén de SQL** y haga clic en **Aceptar**.

3. Publique la topología.

## <a name="removing-a-mirroring-witness"></a>Supresión de un testigo de creación de reflejo

Use este procedimiento si necesita quitar al testigo de un servidor Back-End la configuración de creación de reflejo.

1. En Generador de topologías, haga clic con el botón derecho en el grupo y haga clic en **Modificar propiedades**.

2. Desactive **Uso de testigo de creación de reflejos de SQL para permitir la conmutación por error automática** y haga clic en **Aceptar**.

3. Publique la topología.

    Después de publicar la topología, Topology Builder verá un mensaje que incluye las siguientes

   ```
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    Sin embargo, no siga este paso y no escriba `Uninstall-CsMirrorDatabase` como que sería desinstalar toda la configuración de la creación de reflejo.

4. Para quitar a solo el testigo de la configuración de SQL Server, siga las instrucciones de [quitar al testigo de una sesión de la creación de reflejo de base de datos (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).


