---
title: Conmutar por error y conmutar por recuperación un grupo
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: d5409441336ef2af8bbe9c6a39530584a167ec05
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818211"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Conmutación por error y reversión de un grupo en Skype empresarial Server 

Use los procedimientos siguientes si un único grupo de servidores front-end ha fallado y necesita conmutar por error, o el grupo que experimentó el desastre está de nuevo en línea y necesita restaurar la implementación a un estado de funcionamiento normal. También puede obtener información sobre la conmutación por error y la conmutación por error del grupo perimetral usado para la Federación de Skype empresarial o la Federación XMPP, o cambiar el grupo perimetral asociado a un grupo de servidores front-end.

- [Conmutación por error de un grupo de servidores front-end](#fail-over-a-front-end-pool)
- [Devolver un grupo por error](#fail-back-a-pool)
- [Conmutación por error del grupo perimetral usado para la Federación de Skype empresarial Server](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Conmutación por error del grupo perimetral usado para la Federación de XMPP en Skype empresarial Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Conmutación por error del grupo perimetral usado para la Federación de Skype empresarial Server o con la Federación de XMPP](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Cambiar el grupo perimetral asociado a un grupo de servidores front-end](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Conmutación por error de un grupo de servidores front-end

En este procedimiento, Datacenter1 contiene Pool1 y Pool1 ha fallado. Está conmutando por error a Pool2 que se encuentra en Datacenter2.

La mayor parte del trabajo para la conmutación por error del grupo incluye la conmutación por error del almacén de administración central, si es necesario. Esto es importante porque el almacén central de administración debe funcionar cuando se conmuta por error los usuarios del grupo.

Además, si se produce un error en un grupo de servidores front-end pero el grupo Edge de ese sitio aún se está ejecutando, debe saber si el grupo Edge usa el grupo erróneo como grupo de saltos próximos. Si es así, debe cambiar el grupo de límites para usar un grupo de servidores front end diferente antes de la conmutación por error del grupo de servidores front-end. La forma de cambiar la configuración del próximo salto depende de si el borde usará un grupo en el mismo sitio que el grupo de bordes o un sitio diferente.

**Para establecer que un grupo de servidores Perimetrals use un grupo de próximos saltos en el mismo sitio**

1.  Abra el generador de topologías, haga clic con el botón secundario en el grupo perimetral que necesita cambiar y haga clic en **Editar propiedades**.

2.  Haga clic en **próximo salto**. En la lista **grupo de próximos saltos:** , seleccione el grupo que servirá ahora como el grupo de próximos saltos.

3.  Haga clic en **Aceptar**y, a continuación, publique los cambios.

**Para establecer que un grupo de servidores Perimetrals use un grupo de próximos saltos en otro sitio**

1.  Abra una ventana del shell de administración de Skype empresarial Server y escriba el siguiente cmdlet:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Para conmutar por error un grupo en un desastre**

1.  Busque el grupo que es el host para el servidor de administración central escribiendo el siguiente cmdlet en un servidor front-end en Pool2:
    
        Invoke-CsManagementServerFailover -Whatif
    
    El resultado de este cmdlet muestra el grupo que hospeda actualmente el servidor de administración central. En el resto de este procedimiento, este grupo se conoce como grupo\_CMS.

2.  Use el generador de topologías para buscar la versión de Skype empresarial Server que se ejecuta\_en el grupo de CMS. Si está ejecutando Skype empresarial Server, use el siguiente cmdlet para buscar el grupo de copias de seguridad del grupo 1.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Permitir que\_el grupo de copia de seguridad sea el grupo de copia de seguridad.

3.  Compruebe el estado del almacén de administración central con el siguiente cmdlet:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Este cmdlet debe mostrar que tanto ActiveMasterFQDN como ActiveFileTransferAgents apuntan al FQDN del grupo de\_servidores CMS. Si están vacíos, el servidor de administración central no está disponible y debe conmutarlo por error.

4.  Si el almacén central de administración no está disponible o si el almacén de administración central se estaba ejecutando en Pool1 (es decir, el grupo que falló), debe realizar la conmutación por error del servidor de administración central antes de realizar la conmutación por error. Si necesita migrar por error el servidor de administración central que se ha hospedado en un grupo de servidores que ejecutan Skype empresarial Server, use el cmdlet del paso 5 de este procedimiento. Si no necesita realizar la conmutación por error del servidor de administración central, vaya al paso 7 de este procedimiento.

5.  Para conmutar por error el almacén de administración central en un grupo que ejecute Skype empresarial Server, haga lo siguiente:
    
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

7.  Realice la conmutación por error a los usuarios de Pool1 a Pool2 ejecutando el cmdlet siguiente en una ventana del shell de administración de Skype empresarial Server:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Puesto que los pasos que se han realizado en las partes anteriores de este procedimiento para comprobar el estado de la tienda de administración central no son universales, todavía existe la posibilidad de que este cmdlet falle porque el almacén de administración central aún no se ha realizado correctamente. En este caso, debe corregir el almacén de administración central en función de los mensajes de error que ve y, a continuación, volver a ejecutar este cmdlet.
    
    Si ve el siguiente mensaje de error, debe cambiar el grupo de bordes de este sitio para que use una agrupación diferente como el próximo salto antes de que se produzca un error en el grupo. Para obtener más información, consulte los procedimientos que se describen al principio de este tema.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>Devolver un grupo por error

Después de que el grupo que experimentó el desastre vuelva a estar conectado (es decir, Pool1 en este ejemplo), siga estos pasos para restaurar la implementación a su estado de funcionamiento normal.

Tenga en cuenta que el proceso de recuperación tras error tarda varios minutos en completarse.Como referencia, se espera que tarde 60 minutos como máximo para un grupo de 20 000 usuarios.

Conmutar por error a los usuarios que originalmente se encontraban en Pool1 y se ha producido un error en Pool2 escribiendo el siguiente cmdlet:
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

No es necesario realizar ningún otro paso. Si se ha producido un error en el servidor de administración central, puede dejarlo en Pool2.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Conmutación por error del grupo perimetral usado para la Federación de Skype empresarial Server 

Si el grupo perimetral en el que tiene la Federación de Skype empresarial Server está desactivada, debe cambiar la Federación para usar un grupo de borde diferente para que la Federación funcione.

1.  En un servidor front-end, abra Topology Builder. Expanda **agrupaciones perimetrales**y, a continuación, haga clic con el botón derecho en el servidor perimetral o en el grupo de servidores perimetrales actualmente configurados para la Federación. Seleccione **Editar propiedades**.

2.  En **Editar propiedades** , en **General**, desactive **Habilitar Federación para este grupo perimetral (puerto 5061)**. Haga clic en **Aceptar**.

3.  Expanda **agrupaciones perimetrales**y, a continuación, haga clic con el botón derecho en el grupo de servidores perimetrales o perimetrales que desea usar para la Federación. Seleccione **Editar propiedades**.

4.  En **propiedades de edición** , en **General**, seleccione **Habilitar Federación para este grupo perimetral (puerto 5061)**. Haga clic en **Aceptar**.

5.  Haga clic en **acción**, seleccione **topología**, seleccione **publicar**. Cuando se le solicite al **publicar la topología**, haga clic en **siguiente**. Una vez finalizada la publicación, haga clic en **Finalizar**.

6.  En el servidor perimetral, abra el Asistente para la implementación de Skype empresarial Server. Haga clic en **instalar o actualizar el sistema de Skype empresarial Server**y, a continuación, haga clic en **configurar o quitar los componentes de Skype empresarial Server**. **Vuelva a**hacer clic en ejecutar.

7.  Haga clic en **Siguiente**. La pantalla resumen mostrará las acciones a medida que se ejecutan. Una vez que haya finalizado la implementación, haga clic en **Ver registro** para ver los archivos de registro disponibles. Haga clic en **Finalizar** para completar la implementación.
    
    Si el sitio que contiene el grupo perimetral con error contiene servidores front-end que aún se están ejecutando, debe actualizar el servicio de conferencias web y el servicio de conferencia A/V en estos grupos front-end para usar un grupo perimetral en un sitio remoto que aún se esté ejecutando. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Conmutación por error del grupo perimetral usado para la Federación de XMPP en Skype empresarial Server 

En su organización, hay un grupo perimetral designado como grupo para usar en la Federación XMPP. Si este grupo deja de funcionar, debe conmutar por error la Federación XMPP para usar un grupo de servidores perimetrales diferente antes de que la Federación XMPP pueda volver a funcionar.

La primera vez que instala agrupaciones de límites y habilita la Federación de XMPP, puede simplificar el proceso de recuperación ante desastres configurando registros SRV de DNS para todos los grupos de borde para la Federación de XMPP, en lugar de solo uno. Cada uno de estos registros SRV debe tener un conjunto de prioridades diferente. Todo el tráfico de Federación XMPP pasa por el grupo con el registro SRV con la prioridad más alta. 

En el procedimiento siguiente, EdgePool1 es el grupo que originalmente contenía la Federación de XMPP y EdgePool2 es el grupo que ahora hospedará la Federación XMPP.


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>Para conmutar por error el grupo perimetral usado para la Federación XMPP

1.  Si aún no tiene otra agrupación perimetral implementada (aparte de la que actualmente está desactivada), implemente ese grupo. 

2.  En cada servidor perimetral en el nuevo grupo de límites que ahora hospede la Federación XMPP (EdgePool2), ejecute el siguiente cmdlet:
    
        Stop-CsWindowsService

3.  Ejecute el cmdlet siguiente para redirigir la ruta de Federación de XMPP a EdgePool2:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    En este ejemplo, Site2 es el sitio que contiene el grupo Edge que ahora hospedará la ruta de Federación XMPP y EdgeServer2.contoso.com es el FQDN de un servidor perimetral en ese grupo.

4.  En el servidor DNS externo, cambie el registro A de DNS para la Federación XMPP para que apunte a EdgeServer2.contoso.com.

5.  Si todavía no tiene un registro SRV de DNS para la Federación de XMPP, que se resuelve en el grupo Edge que ahora hospedará la Federación XMPP, debe agregarlo, como en el ejemplo siguiente. Este registro SRV debe tener un valor de puerto de 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Verifique que el grupo de servidores perimetrales que ahora hospeda la Federación XMPP tenga el puerto 5269 abierto externamente.

7.  Inicie los servicios en todos los servidores perimetrales del grupo perimetral que ahora hospedarán la Federación de XMPP:
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Conmutación por error del grupo perimetral usado para la Federación de Skype empresarial Server o con la Federación de XMPP 

Después de que se haya vuelto a conectar un grupo perimetral que usó para hospedar la Federación, use este procedimiento para recuperar la ruta de Federación de Skype empresarial Server y/o la ruta de Federación de XMPP para volver a usar este grupo de Edge restaurado.

1.  En el grupo Edge que ya está disponible de nuevo, inicie los servicios de Edge.

2.  Si desea recuperar la conmutación por recuperación de la ruta de Federación de Skype empresarial Server para usar el servidor perimetral restaurado, haga lo siguiente:
    
      - En un servidor front-end, abra Topology Builder. Expanda **agrupaciones perimetrales**y haga clic con el botón secundario en el servidor perimetral o en el grupo de servidores perimetrales actualmente configurados para la Federación. Seleccione **Editar propiedades**.
    
      - En **Editar propiedades** , en **General**, desactive **Habilitar Federación para este grupo perimetral (puerto 5061)**. Haga clic en **Aceptar**.
    
      - Expanda **agrupaciones perimetrales**y, a continuación, haga clic con el botón secundario en el servidor perimetral original o en el grupo de servidores perimetrales que desea usar de nuevo para la Federación. Seleccione **Editar propiedades**.
    
      - En **propiedades de edición** , en **General**, seleccione **Habilitar Federación para este grupo perimetral (puerto 5061)**. Haga clic en **Aceptar**.
    
      - Haga clic en **acción**, seleccione **topología**, seleccione **publicar**. Cuando se le solicite al **publicar la topología**, haga clic en **siguiente**. Una vez finalizada la publicación, haga clic en **Finalizar**.
    
      - En el servidor perimetral, abra el Asistente para la implementación de Skype empresarial Server. Haga clic en **instalar o actualizar el sistema de Skype empresarial Server**y, a continuación, haga clic en **configurar o quitar los componentes de Skype empresarial Server**. **Vuelva a**hacer clic en ejecutar.
    
      - Haga clic en **Siguiente**. La pantalla resumen mostrará las acciones a medida que se ejecutan. Una vez que haya finalizado la implementación, haga clic en **Ver registro** para ver los archivos de registro disponibles. Haga clic en **Finalizar** para completar la implementación.

3.  Si desea recuperar la conmutación por recuperación de la ruta de Federación de XMPP para usar el servidor perimetral restaurado, haga lo siguiente:
    
      - Ejecute el siguiente cmdlet para redirigir la ruta de Federación de XMPP al conjunto de servidores perimetrales que ahora hospedan la Federación XMPP (en este ejemplo, EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        En este ejemplo, Sitio1 es el sitio que contiene el grupo Edge que ahora hospedará la ruta de Federación XMPP y EdgeServer1.contoso.com es el FQDN de un servidor perimetral en ese grupo.
    
      - Si todavía no tiene un registro SRV de DNS para la Federación de XMPP, que se resuelve en el grupo Edge que ahora hospedará la Federación XMPP, debe agregarlo, como en el ejemplo siguiente. Este registro SRV debe tener un valor de puerto de 5269.
        
            _xmpp-server._tcp.contoso.com
    
      - En el servidor DNS externo, cambie el registro A de DNS para la Federación XMPP para que apunte a EdgeServer2.contoso.com.
    
      - Verifique que el grupo de servidores perimetrales que ahora hospeda la Federación XMPP tenga el puerto 5269 abierto externamente.

4.  Si las agrupaciones front-end permanecieron ejecutándose en el sitio que contiene el grupo perimetral que falló y se han restaurado, debe actualizar el servicio de conferencias web y el servicio de conferencia A/V en estos grupos de aplicaciones para el usuario de nuevo para usar los grupos perimetrales en su sitio local.

5.  Si el grupo de servidores front-end en el mismo sitio que el grupo perimetral con errores también ha fallado, ahora puede usar Invoke-CsPoolFailback para recuperar el repositorio front-end.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Cambiar el grupo perimetral asociado a un grupo de servidores front-end

Si un grupo de servidores perimetrales deja de funcionar pero el grupo de servidores front-end en el mismo sitio aún se está ejecutando, tendrá que configurar el grupo de servidores front-end para que use un grupo de límites en un sitio diferente hasta que se restaure el grupo perimetral con error.

1.  En el generador de topología, vaya al nombre del grupo de servidores front-end que necesita cambiar.

2.  Haga clic con el botón secundario en el grupo y luego haga clic en **Editar propiedades**.

3.  En la sección **asociaciones** , en **asociar grupo perimetral (para componentes multimedia)**, use el cuadro desplegable para seleccionar el grupo perimetral al que desea asociar este grupo de servidores front-end.

4.  Haga clic en **Aceptar**.
