---
title: 'Lync Server 2013: conmutación por error de un grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7de00de8361ac8bc5827fd76ea2486ae790a66d4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a>Conmutación por error de un grupo de servidores en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-10-10_

Si ha fallado un grupo de servidores front-end y se deben conmutar los errores, utilice el procedimiento siguiente. En este procedimiento, Datacenter1 contiene el Grupo1, y el Grupo1 ha fallado. Está conmutando los errores en el Grupo2 situado en Datacenter2.

La mayor parte del trabajo de la conmutación por error del grupo de servidores implica la conmutación por error del almacén de administración central, si es necesario. Esto es importante porque el almacén de administración central debe ser funcional cuando los usuarios del grupo de servidores se conmutan por error.

Además, si se produce un error en un grupo de servidores front-end pero el servidor perimetral en dicho sitio todavía se está ejecutando, debe saber si el grupo de servidores perimetrales usa el grupo de servidores con error como el grupo de servidores de próximo salto. Si lo hace, debe cambiar el grupo de servidores perimetrales para que use un grupo de servidores de front-end diferente antes de conmutar por error el grupo de servidores front-end con error. La manera en que cambie la configuración del próximo salto depende de si el servidor perimetral usará un grupo de servidores en el mismo sitio que el grupo de servidores perimetrales, o un sitio diferente.

**Para establecer un grupo de servidores perimetrales para que usen un grupo de servidores de próximo salto en el mismo sitio**

1.  Abra el generador de topologías, haga clic con el botón secundario en el grupo de servidores perimetrales que se debe cambiar y haga clic en **Editar propiedades**.

2.  Haga clic en **Próximo salto**. En la lista **Grupo de servidores del próximo salto:**, seleccione el grupo de servidores que servirá ahora como el grupo de servidores de próximo salto.

3.  Haga clic en **Aceptar** y, a continuación, publique los cambios.

**Para establecer un grupo de servidores perimetrales para que usen un grupo de servidores de próximo salto en un sitio diferente**

1.  Abra una ventana del shell de administración de Lync Server y escriba el siguiente cmdlet:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Para conmutar por error un grupo de servidores en un desastre**

1.  Busque qué grupo de servidores es el host del servidor de administración central; para ello, escriba el siguiente cmdlet en un servidor front-end en Grupo2:
    
        Invoke-CsManagementServerFailover -Whatif
    
    Los resultados de este cmdlet muestran el grupo que hospeda actualmente el servidor de administración central. En el resto de este procedimiento, este grupo se conoce como grupo\_CMS.

2.  Use el generador de topologías para buscar la versión de Lync Server que se\_ejecuta en el grupo de servidores CMS. Si ejecuta Lync Server 2013, use el siguiente cmdlet para encontrar el grupo de copia de seguridad del grupo de servidores 1.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Permita que\_el grupo de copia de seguridad sea el grupo de copia de seguridad.

3.  Compruebe el estado del almacén de administración central con el siguiente cmdlet:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Este cmdlet debería mostrar que tanto ActiveMasterFQDN como ActiveFileTransferAgents apuntan al FQDN del grupo de\_CMS. Si están vacíos, el servidor de administración central no está disponible y se debe producir un error.

4.  Si el almacén de administración central no está disponible o si el almacén de administración central se estaba ejecutando en Grupo1 (es decir, el grupo de servidores que ha fallado), debe realizar una conmutación por error del servidor de administración central antes de realizar la conmutación por error del grupo. Si necesita realizar una conmutación por error del servidor de administración central que se hospeda en un grupo de servidores que ejecuta Lync Server 2013, use el cmdlet en el paso 5 de este procedimiento. Si necesita realizar una conmutación por error del servidor de administración central que se hospeda en un grupo de servidores que ejecuta Lync Server 2010, use el cmdlet en el paso 6 de este procedimiento. Si no necesita realizar la conmutación por error del servidor de administración central, vaya al paso 7 de este procedimiento.

5.  Para conmutar por error el almacén de administración central en un grupo de servidores que ejecute Lync Server 2013, haga lo siguiente:
    
      - En primer lugar, compruebe el servidor back-\_end del grupo de copia de seguridad que ejecuta la instancia principal del almacén de administración central; para ello, escriba lo siguiente:
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Si el servidor back-end principal del\_grupo de copia de seguridad es el principal, escriba:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Si el servidor back-end reflejado\_en el grupo de copia de seguridad es el principal, escriba:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Compruebe que se ha completado la conmutación por error del servidor de administración central. Escriba lo siguiente:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Compruebe que tanto ActiveMasterFQDN como ActiveFileTransferAgents estén señalando al FQDN del grupo\_de copia de seguridad.
    
      - Por último, compruebe el estado de la réplica para todos los servidores front-end; para ello, escriba lo siguiente:
        
            Get-CsManagementStoreReplicationStatus 
        
        Compruebe que todas las réplicas tengan un valor de True.
        
        Vaya al paso 7 de este procedimiento.

6.  Instale el almacén de administración central en el servidor back-end\_del grupo de copia de seguridad.
    
      - En primer lugar, ejecute el siguiente comando:
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Ejecute el comando siguiente en uno de los servidores front-end del\_grupo de copia de seguridad para forzar la transferencia del almacén de administración central:
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - La validación del movimiento se ha completado:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Compruebe que tanto ActiveMasterFQDN como ActiveFileTransferAgents estén señalando al FQDN del grupo\_de copia de seguridad.
    
      - Compruebe el estado de réplica para todos los servidores front-end escribiendo lo siguiente:
        
            Get-CsManagementStoreReplicationStatus 
        
        Compruebe que todas las réplicas tengan un valor de True.
    
      - Instale el servicio de servidor de administración central en el resto de los servidores Front-\_end del grupo de copia de seguridad. Para ello, ejecute el siguiente comando en todos los servidores front-end, excepto el que usó para forzar el movimiento del almacén de administración central anteriormente en este procedimiento:
        
            Bootstrapper /Setup 

7.  Conmute por error los usuarios de Grupo1 a grupo2 ejecutando el siguiente cmdlet en una ventana del shell de administración de Lync Server:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Debido a que los pasos realizados en las partes anteriores de este procedimiento para comprobar el estado del almacén de administración central no son universales, todavía existe la posibilidad de que se produzca un error en el cmdlet porque el almacén de administración central aún no ha conmutado por error. En este caso, debe corregir el almacén de administración central en función de los mensajes de error que aparecen y, a continuación, volver a ejecutar este cmdlet.
    
    Si ve el siguiente mensaje de error, tiene que cambiar el grupo de servidores perimetrales en este sitio para que use un grupo de servidores diferente al del próximo salto antes de conmutar por error el grupo de servidores. Para obtener detalles, vea los procedimientos al comienzo de este tema.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

</div>

<span> </span>

</div>

</div>

</div>

