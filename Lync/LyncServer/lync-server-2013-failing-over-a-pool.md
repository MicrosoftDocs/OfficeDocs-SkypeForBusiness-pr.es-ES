---
title: 'Lync Server 2013: Conmutación por error de un grupo'
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
ms.openlocfilehash: ea66ae4a224d78e40a9fdb9de867d4738a5e3714
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a>Conmutación por error de un grupo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-10-10_

Si un único grupo de servidores front-end ha fallado y debe realizarse la conmutación por error, use el procedimiento siguiente. En este procedimiento, Datacenter1 contiene Pool1 y Pool1 ha fallado. Está conmutando por error a Pool2 que se encuentra en Datacenter2.

La mayor parte del trabajo para la conmutación por error del grupo incluye la conmutación por error del almacén de administración central, si es necesario. Esto es importante porque el almacén central de administración debe funcionar cuando se conmuta por error los usuarios del grupo.

Además, si se produce un error en un grupo de servidores front-end pero el grupo Edge de ese sitio aún se está ejecutando, debe saber si el grupo Edge usa el grupo erróneo como grupo de saltos próximos. Si es así, debe cambiar el grupo de límites para usar un grupo de servidores front end diferente antes de la conmutación por error del grupo de servidores front-end. La forma de cambiar la configuración del próximo salto depende de si el borde usará un grupo en el mismo sitio que el grupo de bordes o un sitio diferente.

**Para establecer que un grupo de servidores Perimetrals use un grupo de próximos saltos en el mismo sitio**

1.  Abra el generador de topologías, haga clic con el botón secundario en el grupo perimetral que necesita cambiar y haga clic en **Editar propiedades**.

2.  Haga clic en **próximo salto**. En la lista **grupo de próximos saltos:** , seleccione el grupo que servirá ahora como el grupo de próximos saltos.

3.  Haga clic en **Aceptar**y, a continuación, publique los cambios.

**Para establecer que un grupo de servidores Perimetrals use un grupo de próximos saltos en otro sitio**

1.  Abra una ventana del shell de administración de Lync Server y escriba el siguiente cmdlet:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Para conmutar por error un grupo en un desastre**

1.  Busque el grupo que es el host para el servidor de administración central escribiendo el siguiente cmdlet en un servidor front-end en Pool2:
    
        Invoke-CsManagementServerFailover -Whatif
    
    El resultado de este cmdlet muestra el grupo que hospeda actualmente el servidor de administración central. En el resto de este procedimiento, este grupo se conoce como grupo\_CMS.

2.  Use el generador de topologías para buscar la versión de Lync Server que se\_ejecuta en el grupo de CMS. Si está ejecutando Lync Server 2013, use el siguiente cmdlet para buscar el grupo de copias de seguridad del grupo 1.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Permitir que\_el grupo de copia de seguridad sea el grupo de copia de seguridad.

3.  Compruebe el estado del almacén de administración central con el siguiente cmdlet:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Este cmdlet debe mostrar que tanto ActiveMasterFQDN como ActiveFileTransferAgents apuntan al FQDN del grupo de\_servidores CMS. Si están vacíos, el servidor de administración central no está disponible y debe conmutarlo por error.

4.  Si el almacén central de administración no está disponible o si el almacén de administración central se estaba ejecutando en Pool1 (es decir, el grupo que falló), debe realizar la conmutación por error del servidor de administración central antes de realizar la conmutación por error. Si necesita conmutar por error el servidor de administración central alojado en un grupo que ejecuta Lync Server 2013, use el cmdlet en el paso 5 de este procedimiento. Si necesita migrar por error el servidor de administración central alojado en un grupo que ejecuta Lync Server 2010, use el cmdlet en el paso 6 de este procedimiento. Si no necesita realizar la conmutación por error del servidor de administración central, vaya al paso 7 de este procedimiento.

5.  Para conmutar por error el almacén de administración central en un grupo que ejecute Lync Server 2013, haga lo siguiente:
    
      - En primer lugar, compruebe qué servidor back-\_end del grupo de copia de seguridad ejecuta la instancia principal del almacén central de administración; para ello, escriba lo siguiente:
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Si el servidor back-end principal del\_grupo de copias de seguridad es el principal, escriba:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Si el servidor de back-end de\_duplicación de la copia de seguridad es el principal, escriba:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Valide que la conmutación por error del servidor de administración central se haya completado. Escriba lo siguiente:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Compruebe que tanto ActiveMasterFQDN como ActiveFileTransferAgents apunten al FQDN del grupo de\_copia de seguridad.
    
      - Por último, compruebe el estado de la réplica de todos los servidores front-end escribiendo lo siguiente:
        
            Get-CsManagementStoreReplicationStatus 
        
        Compruebe que todas las réplicas tengan el valor true.
        
        Vaya al paso 7 de este procedimiento.

6.  Instale el almacén central de administración en el servidor back-end\_del grupo de copia de seguridad.
    
      - En primer lugar, ejecute el siguiente comando:
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Ejecute el comando siguiente en uno de los servidores front-end del\_grupo de copia de seguridad para forzar el movimiento del almacén de administración central:
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - Valide que el movimiento se haya completado:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Compruebe que tanto ActiveMasterFQDN como ActiveFileTransferAgents apunten al FQDN del grupo de\_copia de seguridad.
    
      - Para comprobar el estado de la réplica de todos los servidores front-end, escriba lo siguiente:
        
            Get-CsManagementStoreReplicationStatus 
        
        Compruebe que todas las réplicas tengan el valor true.
    
      - Instale el servicio de servidor de administración central en el resto de los servidores Front-\_end del grupo de copias de seguridad. Para ello, ejecute el siguiente comando en todos los servidores front-end, excepto el que usó para forzar el movimiento del almacén de administración central anteriormente en este procedimiento:
        
            Bootstrapper /Setup 

7.  Conmutar por error los usuarios de Pool1 a Pool2 ejecutando el cmdlet siguiente en una ventana del shell de administración de Lync Server:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Puesto que los pasos que se han realizado en las partes anteriores de este procedimiento para comprobar el estado de la tienda de administración central no son universales, todavía existe la posibilidad de que este cmdlet falle porque el almacén de administración central aún no se ha realizado correctamente. En este caso, debe corregir el almacén de administración central en función de los mensajes de error que ve y, a continuación, volver a ejecutar este cmdlet.
    
    Si ve el siguiente mensaje de error, debe cambiar el grupo de bordes de este sitio para que use una agrupación diferente como el próximo salto antes de que se produzca un error en el grupo. Para obtener más información, consulte los procedimientos que se describen al principio de este tema.
    
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

