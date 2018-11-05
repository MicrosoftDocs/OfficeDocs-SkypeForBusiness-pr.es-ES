---
title: 'Lync Server 2013: Conmutación por error de un grupo'
TOCTitle: Conmutación por error de un grupo
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48274464
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conmutación por error de un grupo en Lync Server 2013

 

_**Última modificación del tema:** 2014-10-10_

Si ha fallado un grupo de servidores front-end y se deben conmutar los errores, utilice el procedimiento siguiente. En este procedimiento, Datacenter1 contiene el Grupo1, y el Grupo1 ha fallado. Está conmutando los errores en el Grupo2 situado en Datacenter2.

La mayoría del trabajo para el grupo de conmutación por error implica la conmutación de errores del Almacén de administración central, si es necesario. Esto es importante porque el Almacén de administración central debe ser funcional cuando los usuarios del grupo se conmutan.

Además, si se produce un error en un grupo de servidores front-end pero el servidor perimetral en dicho sitio todavía se está ejecutando, debe saber si el grupo de servidores perimetrales usa el grupo de servidores con error como el grupo de servidores de próximo salto. Si lo hace, debe cambiar el grupo de servidores perimetrales para que use un grupo de servidores de front-end diferente antes de conmutar por error el grupo de servidores front-end con error. La manera en que cambie la configuración del próximo salto depende de si el servidor perimetral usará un grupo de servidores en el mismo sitio que el grupo de servidores perimetrales, o un sitio diferente.

**Para establecer un grupo de servidores perimetrales para que usen un grupo de servidores de próximo salto en el mismo sitio**

1.  Abra Generador de topologías, haga clic con el botón secundario en el grupo de servidores perimetrales que se tiene que cambiar y haga clic en **Editar propiedades**.

2.  Haga clic en **Próximo salto**. En la lista **Grupo de servidores del próximo salto:**, seleccione el grupo de servidores que servirá ahora como el grupo de servidores de próximo salto.

3.  Haga clic en **Aceptar** y, a continuación, publique los cambios.

**Para establecer un grupo de servidores perimetrales para que usen un grupo de servidores de próximo salto en un sitio diferente**

1.  Abra una ventana de Shell de administración de Lync Server y escriba el siguiente cmdlet:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Para conmutar por error un grupo de servidores en un desastre**

1.  Busque qué grupo es el host para el Servidor de administración central, introduciendo el siguiente cmdlet en un servidor front-end en el Grupo2:
    
        Invoke-CsManagementServerFailover -Whatif
    
    Los resultados de este cmdlet muestran qué grupo de servidores hospeda actualmente el Servidor de administración central. En el resto de este procedimiento, este grupo de servidores se conoce como CMS\_Pool.

2.  Utilice el generador de topología para encontrar la versión de Lync Server que se ejecuta en el CMS\_Pool. Si se está ejecutando el Lync Server 2013, utilice el siguiente cmdlet para encontrar el grupo de reserva del grupo 1.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Supongamos que Backup\_Pool es el grupo de reserva.

3.  Compruebe el estado del Almacén de administración central con el siguiente cmdlet:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Este cmdlet debe mostrar que ActiveMasterFQDN y ActiveFileTransferAgents apuntan al FQDN de CMS\_Pool. Si están vacíos, el Servidor de administración central no está disponible y deberá conmutarlo.

4.  Si el Almacén de administración central no está disponible o si el Almacén de administración central se estaba ejecutando en el Grupo1 (es decir, el grupo que ha fallado), debe realizar la conmutación a través del Servidor de administración central antes de conmutar el grupo. Si necesita conmutar por error el Servidor de administración central que se alojó en un grupo de servidores que ejecutan el Lync Server 2013, use el cmdlet en el paso 5 de este procedimiento. Si necesita conmutar por error el Servidor de administración central que se alojó en un grupo de servidores que ejecutan Lync Server 2010, use el cmdlet en el paso 6 de este procedimiento. Si no es necesario conmutar por error el Servidor de administración central, vaya al paso 7 de este procedimiento.

5.  Para conmutar por error el Almacén de administración central en un grupo que ejecute el Lync Server 2013, realice lo siguiente:
    
      - En primer lugar, compruebe qué servidor back-end en Backup\_Pool ejecuta la instancia principal del Almacén de administración central introduciendo lo siguiente:
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Si el servidor back-end principal en Backup\_Pool es el principal, escriba:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Si el servidor back-end reflejado en Backup\_Pool es el principal, escriba:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Valide que la conmutación por error del Servidor de administración central está completa. Escriba lo siguiente:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Compruebe que ActiveMasterFQDN y ActiveFileTransferAgents apunten al FQDN de Backup\_Pool.
    
      - Por último, compruebe el estado de réplica para todos los Servidores front-end escribiendo lo siguiente:
        
            Get-CsManagementStoreReplicationStatus 
        
        Compruebe que todas las réplicas tengan un valor de True.
        
        Vaya al paso 7 de este procedimiento.

6.  Instale el Almacén de administración central en el servidor back-end de Backup\_Pool:
    
      - En primer lugar, ejecute el siguiente comando:
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Ejecute el comando siguiente en uno de los servidores front-end de Backup\_Pool para forzar el desplazamiento de Almacén de administración central:
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - La validación del movimiento se ha completado:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Compruebe que ActiveMasterFQDN y ActiveFileTransferAgents apunten al FQDN de Backup\_Pool.
    
      - Compruebe el estado de réplica para todos los servidores front-end escribiendo lo siguiente:
        
            Get-CsManagementStoreReplicationStatus 
        
        Compruebe que todas las réplicas tengan un valor de True.
    
      - Instale el servicio Servidor de administración central en el resto de servidores front-end en Backup\_Pool. Para ello, ejecute el siguiente comando en todos los servidores front-end, excepto en el utilizado al forzar el movimiento Almacén de administración central anteriormente en este procedimiento:
        
            Bootstrapper /Setup 

7.  Conmute por error los usuarios del Grupo1 al Grupo2 ejecutando el siguiente cmdlet en una ventana Shell de administración de Lync Server:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Debido a que las medidas adoptadas en la parte anterior de este procedimiento para comprobar el estado del Almacén de administración central no son universales, todavía hay una oportunidad de que se produzca un error en este cmdlet porque el Almacén de administración central no está completamente conmutado por error. En este caso, debe corregir el Almacén de administración central en función de los mensajes de error que vea y, a continuación, ejecutar de nuevo este cmdlet.
    
    Si ve el siguiente mensaje de error, tiene que cambiar el grupo de servidores perimetrales en este sitio para que use un grupo de servidores diferente al del próximo salto antes de conmutar por error el grupo de servidores. Para obtener detalles, vea los procedimientos al comienzo de este tema.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

