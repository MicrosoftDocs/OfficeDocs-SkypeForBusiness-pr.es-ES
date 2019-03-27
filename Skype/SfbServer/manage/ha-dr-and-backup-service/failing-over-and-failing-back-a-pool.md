---
title: Conmutar por error y conmutar por recuperación un grupo
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: 809d0305eaa4c8e2197c5137a647ff9354cbf9bd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899781"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Con errores más y a falta de vuelta un grupo de servidores en Skype para Business Server 

Use los procedimientos siguientes si ha generado un error en un único grupo de servidores Front-End y las necesidades de conmutación por error, o el grupo que experimentó el desastre es nuevo en línea y necesita restaurar su implementación al estado de funcionamiento normal. También Obtenga información sobre cómo conmutar por error y conmutar por recuperación del grupo perimetral usado para Skype para la federación de negocio o la federación XMPP o cambiar el grupo de servidores perimetrales asociado con un grupo de servidores Front-End.

- [Conmutar por error un grupo de servidores Front-End](#fail-over-a-front-end-pool)
- [Conmutar por un grupo de servidores](#fail-back-a-pool)
- [Conmutar por error el grupo de servidores perimetrales para Skype para la federación de Business Server](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Conmutar por error el grupo de servidores perimetrales para la federación XMPP en Skype para Business Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Conmutar por recuperación del grupo perimetral usado para Skype para la federación de Business Server o la federación XMPP](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Cambiar el grupo de servidores perimetrales asociado con un grupo de servidores Front-End](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Conmutar por error un grupo de servidores Front-End

En este procedimiento, Datacenter1 contiene grupo1 y grupo1 ha generado un error. Se conmuta a grupo2 que se encuentra en Datacenter2.

La mayoría del trabajo para el grupo de servidores de conmutación por error implica la conmutación en el almacén de Administración Central, si es necesario. Esto es importante porque el almacén de Administración Central debe ser funcional cuando los usuarios del grupo de servidores se conmutan por error.

Además, si se produce un error en un grupo de servidores Front-End, pero todavía se está ejecutando el grupo de servidores perimetrales en ese sitio, es necesario saber si el grupo de servidores perimetrales utiliza el grupo de servidores con error como un grupo del próximo salto. Si es así, debe cambiar el grupo de servidores perimetrales para utilizar un grupo de servidores Front-End diferente antes de dar error sobre el grupo de servidores Front-End con errores. Cómo cambiar la configuración de salto siguiente depende de si el borde usará un grupo de servidores en el mismo sitio que el grupo de servidores perimetrales, o en un sitio diferente.

**Para establecer un grupo de servidores perimetrales para usar un grupo del próximo salto en el mismo sitio**

1.  Abra el generador, haga clic en el grupo de servidores perimetrales que debe cambiarse y haga clic en **Editar propiedades**.

2.  Haga clic en **próximo salto**. Desde el **del próximo salto del grupo:** de lista, seleccione el grupo que ahora servirá como el próximo salto.

3.  Haga clic en **Aceptar**y, a continuación, publique los cambios.

**Para establecer un grupo de servidores perimetrales para usar un grupo del próximo salto en un sitio diferente**

1.  Abra un Skype para la ventana de Shell de administración de servidor empresarial y escriba el siguiente cmdlet:
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**Para conmutar por error un grupo de servidores en un desastre**

1.  Busque qué grupo es el host para el servidor de Administración Central escribiendo el siguiente cmdlet en un servidor Front-End en el grupo2:
    
        Invoke-CsManagementServerFailover -Whatif
    
    Los resultados de esta presentación de cmdlet qué grupo actualmente hospeda el servidor de Administración Central. En el resto de este procedimiento, este grupo de servidores se conoce como CMS\_grupo de servidores.

2.  Usar el generador de topología para buscar la versión de Skype para Business Server que se ejecutan en el CMS\_grupo de servidores. Si se está ejecutando Skype para Business Server, use el siguiente cmdlet para buscar el grupo de copia de seguridad del grupo de servidores 1.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    Permitir que la copia de seguridad\_grupo de ser el grupo de copia de seguridad.

3.  Compruebe el estado del almacén de Administración Central con el siguiente cmdlet:
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    Este cmdlet se debe mostrar que ActiveMasterFQDN y activefiletransferagents apunten señalen al FQDN de CMS\_grupo de servidores. Si están vacíos, el servidor de Administración Central no está disponible y deberá conmutar.

4.  Si el almacén de Administración Central no está disponible o si el almacén de Administración Central se estaba ejecutando en el grupo1 (es decir, el grupo de servidores que ha generado un error), deberá conmutar el servidor de Administración Central antes de dar error el grupo de servidores. Si necesita conmutar por error el servidor de Administración Central que se hospedan en un grupo de servidores que ejecuta Skype para Business Server, use el cmdlet en el paso 5 de este procedimiento. Si no es necesario conmutar por error el servidor de Administración Central, vaya al paso 7 de este procedimiento.

5.  Para conmutar por error el almacén de Administración Central en un grupo de servidores que ejecuta Skype para Business Server, realice lo siguiente:
    
      - En primer lugar, compruebe qué servidor Back-End en copia de seguridad\_grupo de servidores ejecuta la instancia de entidad de seguridad del almacén de Administración Central, escriba lo siguiente:
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - Si el principal servidor Back-End en copia de seguridad\_grupo de servidores es el tipo de entidad de seguridad,:
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        Si el servidor Back-End en copia de seguridad de reflejo\_grupo de servidores es el tipo de entidad de seguridad,:
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - Validar que el servidor de Administración Central de conmutación por error está completa. Escriba lo siguiente:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Compruebe que el nombre de dominio completo de copia de seguridad se ActiveMasterFQDN y activefiletransferagents apunten\_grupo de servidores.
    
      - Por último, compruebe el estado de réplica para todos los servidores Front-End escribiendo lo siguiente:
        
            Get-CsManagementStoreReplicationStatus 
        
        Compruebe que todas las réplicas tengan un valor de True.
        
        Vaya al paso 7 de este procedimiento.

6.  Instalar el almacén de Administración Central en el Back End Server de copia de seguridad\_grupo de servidores.
    
      - En primer lugar, ejecute el siguiente comando:
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - Ejecute el comando siguiente en uno de los Front-End los servidores de copia de seguridad\_grupo de servidores para forzar el desplazamiento del almacén de Administración Central:
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - Validar el movimiento es completado:
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        Compruebe que el nombre de dominio completo de copia de seguridad se ActiveMasterFQDN y activefiletransferagents apunten\_grupo de servidores.
    
      - Compruebe el estado de réplica para todos los servidores Front-End escribiendo lo siguiente:
        
            Get-CsManagementStoreReplicationStatus 
        
        Compruebe que todas las réplicas tengan un valor de True.
    
      - Instalar el servicio de servidor de Administración Central en el resto de los servidores Front-End en copia de seguridad\_grupo de servidores. Para ello, ejecute el comando siguiente en todos los servidores Front-End, excepto el utilizado para forzar la Administración Central se mueva almacén anteriormente en este procedimiento:
        
            Bootstrapper /Setup 

7.  Conmutación por error los usuarios del Grupo1 al grupo2 ejecutando el siguiente cmdlet en un Skype para la ventana de Shell de administración de servidor empresarial:
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    Debido a que los pasos realizados en los elementos anteriores de este procedimiento para comprobar el estado del almacén de Administración Central no son universales, sigue siendo una oportunidad de que este cmdlet se producirá un error debido a que el almacén de Administración Central no se aún totalmente conmuta por error. En este caso, debe corregir el almacén de Administración Central en función de los mensajes de error que aparecen y, a continuación, vuelva a ejecutar este cmdlet.
    
    Si ve el mensaje de error siguiente, debe cambiar el grupo de servidores perimetrales en este sitio para utilizar un grupo de servidores diferente como su próximo salto antes de dar error sobre el grupo de servidores. Para obtener información detallada, vea los procedimientos al principio de este tema.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>Conmutar por un grupo de servidores

Después de que el grupo que experimentó el desastre es nuevo en línea (es decir, el grupo1 en este ejemplo), siga estos pasos para restaurar su implementación al estado de funcionamiento normal.

Tenga en cuenta que el proceso de la conmutación por recuperación tarda varios minutos para llevar a cabo.Como referencia, se espera que tarde 60 minutos como máximo para un grupo de 20 000 usuarios.

Conmutar por recuperación los usuarios que estaban hospedados originalmente en el grupo1 y han sido conmuta por error al grupo2 escribiendo el siguiente cmdlet:
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

No hay otros pasos son necesarios. Si no se pudo a través del servidor de Administración Central, puede dejar en el grupo2.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Conmutar por error el grupo de servidores perimetrales para Skype para la federación de Business Server 

Si el grupo de servidores perimetrales donde tenga Skype para configurado la federación de Business Server deja de funcionar, debe cambiar la federación para usar un grupo de servidores perimetrales diferente para la federación para que funcione.

1.  En un servidor Front-End, abra el generador de topología. Expanda **grupos de servidores perimetrales**y, a continuación, haga clic en el servidor perimetral o grupo de servidores perimetrales que actualmente está configurado para la federación. Seleccione **Editar propiedades**.

2.  En **Editar propiedades** en **General**, desactive **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Haga clic en **Aceptar**.

3.  Expanda **grupos de servidores perimetrales**y, a continuación, haga clic en el servidor perimetral o grupo de servidores perimetrales que ahora desea usar para la federación. Seleccione **Editar propiedades**.

4.  En **Editar propiedades** en **General**, seleccione **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Haga clic en **Aceptar**.

5.  Haga clic en **acción**, seleccione la **topología**, seleccione **Publicar**. Cuando se le solicite en **publicar la topología**, haga clic en **siguiente**. Cuando finalice la publicación, haga clic en **Finalizar**.

6.  En el servidor perimetral, abra el Skype para el Asistente para la implementación de servidor empresarial. Haga clic en **instalar o actualización de Skype para Business Server System**y, a continuación, haga clic en **el programa de instalación o quitar Skype para los componentes de servidor empresariales**. Haga clic en **volver a ejecutar**.

7.  Haga clic en **Siguiente**. La pantalla de resumen mostrará acciones cuando se ejecutan. Una vez que se realiza la implementación, haga clic en **Ver registro** para ver los archivos de registro disponibles. Haga clic en **Finalizar** para completar la implementación.
    
    Si el sitio que contiene el grupo de servidores perimetrales con errores contiene servidores Front-End que todavía se está ejecutando, debe actualizar el servicio de conferencia Web y A / servicio de conferencia A/v en estos grupos de servidores Front-End para usar un grupo de servidores perimetrales en un control remoto de sitios es decir ejecución fija. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Conmutar por error el grupo de servidores perimetrales para la federación XMPP en Skype para Business Server 

En la organización, hay un grupo de servidores perimetrales designado como el grupo de servidores que se usará para la federación XMPP. Si este grupo de servidores deja de funcionar, deberá conmutar federación XMPP para usar un grupo de servidores perimetrales diferente antes de la federación XMPP puede trabajar de nuevo.

Cuando en primer lugar instalar grupos de servidores perimetrales y habilitar la federación XMPP, puede simplificar el proceso de recuperación ante desastres mediante la configuración de registros SRV de DNS externos para todos los grupos de servidores perimetrales para la federación XMPP, en lugar de sólo uno. Cada uno de estos registros SRV debe tener una prioridad diferente para establecer. Todo el tráfico de federación XMPP circula a través del grupo de servidores con el registro SRV con la prioridad más alta. 

En el procedimiento siguiente, EdgePool1 es el grupo que originalmente la federación XMPP y EdgePool2 es el grupo que alojará ahora la federación XMPP.


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>Para conmutar por error el grupo de servidores perimetrales para la federación XMPP

1.  Si ya no dispone de otro grupo de servidores perimetrales implementado (además de la que actualmente está inactivo), implemente ese grupo. 

2.  En cada servidor perimetral en el nuevo grupo de servidores perimetrales que alojará ahora la federación XMPP (EdgePool2), ejecute el siguiente cmdlet:
    
        Stop-CsWindowsService

3.  Ejecute el siguiente cmdlet para cambiar la ruta de federación XMPP a EdgePool2:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    En este ejemplo, Site2 es el sitio que contiene el grupo de servidores perimetrales que alojará ahora la ruta de federación XMPP y EdgeServer2.contoso.com es el FQDN de un servidor perimetral en ese grupo.

4.  En el servidor DNS externo, cambie el registro A DNS para la federación XMPP para que apunte a EdgeServer2.contoso.com.

5.  Si aún no tiene un registro SRV de DNS para la federación XMPP que se resuelve en el grupo de servidores perimetrales que alojará ahora la federación XMPP, debe agregarlo, como en el ejemplo siguiente. Este registro SRV debe tener un valor de puerto de 5269.
    
        _xmpp-server._tcp.contoso.com

6.  Compruebe que el grupo de servidores perimetrales que alojará ahora la federación XMPP tiene abierto el puerto 5269 externamente.

7.  Iniciar los servicios en todos los servidores perimetrales en el grupo de servidores perimetrales que alojará ahora la federación XMPP:
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Conmutar por recuperación del grupo perimetral usado para Skype para la federación de Business Server o la federación XMPP 

Después de un borde con errores grupo de servidores que usa para la federación de host ha sido puesta en línea, use este procedimiento para conmutar por recuperación la Skype para la ruta de federación Business Server o la ruta de federación XMPP para volver a usar este grupo de servidores perimetrales restaurado.

1.  En el grupo de servidores perimetrales que ahora esté disponible de nuevo, inicie los Servicios perimetrales.

2.  Si desea conmutar por recuperación la Skype para ruta de federación Business Server para usar el servidor perimetral restaurado, haga lo siguiente:
    
      - En un servidor Front-End, abra el generador de topología. Expanda **grupos de servidores perimetrales**, a continuación, haga clic en el servidor perimetral o grupo de servidores perimetrales que actualmente está configurado para la federación. Seleccione **Editar propiedades**.
    
      - En **Editar propiedades** en **General**, desactive **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Haga clic en **Aceptar**.
    
      - Expanda **grupos de servidores perimetrales**, a continuación, haga clic en el servidor perimetral original o el grupo de servidores perimetrales que desea volver a usar para la federación. Seleccione **Editar propiedades**.
    
      - En **Editar propiedades** en **General**, seleccione **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Haga clic en **Aceptar**.
    
      - Haga clic en **acción**, seleccione la **topología**, seleccione **Publicar**. Cuando se le solicite en **publicar la topología**, haga clic en **siguiente**. Cuando finalice la publicación, haga clic en **Finalizar**.
    
      - En el servidor perimetral, abra el Skype para el Asistente para la implementación de servidor empresarial. Haga clic en **instalar o actualización de Skype para Business Server System**y, a continuación, haga clic en **el programa de instalación o quitar Skype para los componentes de servidor empresariales**. Haga clic en **volver a ejecutar**.
    
      - Haga clic en **Siguiente**. La pantalla de resumen mostrará acciones cuando se ejecutan. Una vez que se realiza la implementación, haga clic en **Ver registro** para ver los archivos de registro disponibles. Haga clic en **Finalizar** para completar la implementación.

3.  Si desea conmutar por recuperación la ruta de federación XMPP para usar el servidor perimetral restaurado, haga lo siguiente:
    
      - Ejecute el siguiente cmdlet para cambiar la ruta de federación XMPP para el grupo de servidores perimetrales que alojará ahora la federación XMPP (en este ejemplo, EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        En este ejemplo, sitio1 es el sitio que contiene el grupo de servidores perimetrales que alojará ahora la ruta de federación XMPP y EdgeServer1.contoso.com es el FQDN de un servidor perimetral en ese grupo.
    
      - Si aún no tiene un registro SRV de DNS para la federación XMPP que se resuelve en el grupo de servidores perimetrales que alojará ahora la federación XMPP, debe agregarlo, como en el ejemplo siguiente. Este registro SRV debe tener un valor de puerto de 5269.
        
            _xmpp-server._tcp.contoso.com
    
      - En el servidor DNS externo, cambie el registro A DNS para la federación XMPP para que apunte a EdgeServer2.contoso.com.
    
      - Compruebe que el grupo de servidores perimetrales que alojará ahora la federación XMPP tiene abierto el puerto 5269 externamente.

4.  Si los grupos de servidores Front-End se mantuvo que se está ejecutando en el sitio que contiene el grupo de servidores perimetrales que errores y se ha restaurado, deberá actualizar el servicio de conferencia Web y A grupos de servicio de conferencia A/v en estos Front-End para volver a usar los grupos de servidores perimetrales en su sitio local.

5.  Si el grupo de servidores Front-End en el mismo sitio que el grupo de servidores perimetrales con errores también falla, ahora puede usar Invoke – CsPoolFailback para conmutar por recuperación del grupo de servidores Front-End.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Cambiar el grupo de servidores perimetrales asociado con un grupo de servidores Front-End

Si un grupo de servidores perimetrales deja de funcionar, pero todavía se está ejecutando el grupo de servidores Front-End en el mismo sitio, debe establecer el grupo de servidores Front-End para usar un grupo de servidores perimetrales en un sitio diferente hasta que se restaura el grupo de servidores perimetrales con errores.

1.  En el generador, desplácese hasta el nombre del grupo de servidores Front-End que desea cambiar.

2.  Haga clic en el grupo de servidores y, a continuación, haga clic en **Editar propiedades**.

3.  En la sección **asociaciones** , en **Asociar grupo de servidores perimetrales (para componentes multimedia)**, utilice el cuadro desplegable para seleccionar el grupo de servidores perimetrales que desea asociar este grupo de servidores Front-End con.

4.  Haga clic en **Aceptar**.
