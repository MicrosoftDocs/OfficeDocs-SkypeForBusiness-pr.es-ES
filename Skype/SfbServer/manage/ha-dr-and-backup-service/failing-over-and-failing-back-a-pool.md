---
title: Conmutar por error y conmutar por recuperación un grupo
ms.reviewer: ''
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: .
ms.openlocfilehash: 55377e77a5b365a4db149ee69b6cd796e373a80b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849973"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Con error y con error de un grupo de servidores en Skype Empresarial Server

Use los siguientes procedimientos si un único grupo de servidores de Front-End ha fallado y necesita que se le haya fallado, o si el grupo de servidores que experimentó el desastre está de nuevo en línea y necesita restaurar la implementación a un estado de trabajo normal. Obtenga información sobre cómo conmutar por error y devolver la conmutación por error del grupo de servidores perimetrales usado para una federación Skype Empresarial o una federación XMPP, o cambiar el grupo de servidores perimetrales asociado a un grupo de servidores Front-End servidor.

- [Conmutación por error de un grupo de servidores front-end](#fail-over-a-front-end-pool)
- [Conmutación por recuperación de un grupo](#fail-back-a-pool)
- [Conmutación por error del grupo de servidores perimetrales usado Skype Empresarial Server federación](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Conmutar por error el grupo de servidores perimetrales usado para la federación XMPP en Skype Empresarial Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Conmutación por recuperación del grupo de servidores perimetrales usado Skype Empresarial Server federación o federación XMPP](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Cambiar el grupo de servidores perimetrales asociado a un grupo de servidores front-end](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Conmutación por error de un Front-End de servidores

Datacenter1 contiene Pool1 y Pool1 ha fallado. Está fallando en Pool2 ubicado en Datacenter2.

La mayoría del trabajo para la conmutación por error del grupo implica la conmutación por error del almacén de administración central, si es necesario. El almacén de administración central debe funcionar cuando se con error a los usuarios del grupo.

Si se produce un error Front-End grupo de servidores perimetrales, pero el grupo de servidores perimetrales en ese sitio aún se está ejecutando, debe saber si el grupo perimetral usa el grupo con errores como grupo de servidores de próximo salto. Si lo hace, debe cambiar el grupo de servidores perimetrales para que use un grupo de servidores Front-End antes de realizar una con error en el grupo de servidores Front-End servidor. La manera en que cambie la configuración del próximo salto depende de si el servidor perimetral usará un grupo de servidores en el mismo sitio que el grupo de servidores perimetrales, o un sitio diferente.

**Para establecer un grupo de servidores perimetrales para usar un grupo de servidores de próximo salto en el mismo sitio**

1. Abra el Generador de topologías, haga clic con el botón secundario en el grupo de servidores perimetrales que debe cambiarse y seleccione **Editar propiedades**.

2. Seleccione **Next Hop**. En la **lista Grupo de servidores del** próximo salto: seleccione el grupo que ahora servirá como grupo de servidores de próximo salto.

3. Seleccione **Aceptar** y, a continuación, publique los cambios.

**Para establecer un grupo de servidores perimetrales para usar un grupo de servidores de próximo salto en un sitio diferente**

1. Abra una ventana Skype Empresarial Server Shell de administración y escriba el siguiente cmdlet:

    ```powershell
    Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>
    ```

**Para conmutar por error un grupo de servidores en un desastre**

1. Para buscar el grupo de servidores host para el servidor de administración central, escriba el siguiente cmdlet en un servidor Front-End en el grupo2:

    ```powershell
    Invoke-CsManagementServerFailover -Whatif
    ```

    Los resultados de este cmdlet muestran qué grupo hospeda actualmente el servidor de administración central. En el resto de este procedimiento, este grupo se conoce como grupo de \_ CMS.

2. Use el Generador de topologías para buscar la versión de Skype Empresarial Server se ejecuta en el grupo de \_ CMS. Si está ejecutando Skype Empresarial Server, use el siguiente cmdlet para buscar el grupo de copia de seguridad del grupo 1.

    ```powershell
    Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    ```

    Deje que el \_ grupo de copia de seguridad sea el grupo de copias de seguridad.

3. Compruebe el estado del almacén de administración central con el siguiente cmdlet:

    ```powershell
    Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
    ```

    Este cmdlet debe mostrar que ActiveMasterFQDN y ActiveFileTransferAgents apuntan al FQDN del grupo de \_ CMS. Si están vacíos, el servidor de administración central no está disponible y debe conmutar por error.

4.  Si el almacén de administración central no está disponible o si el almacén de administración central se estaba ejecutando en el grupo1 (es decir, el grupo que ha fallado), debe conmutar por error el servidor de administración central antes de conmutar por error el grupo. Si necesita conmutar por error el servidor de administración central hospedado en un grupo que ejecuta Skype Empresarial Server, use el cmdlet en el paso 5 de este procedimiento. Si no necesita conmutar por error el servidor de administración central, vaya al paso 7 de este procedimiento.

5.  Para conmutar por error el almacén de administración central en un grupo que Skype Empresarial Server, haga lo siguiente:

    1. En primer lugar, compruebe Back-End servidor de copia de seguridad ejecuta la instancia principal del almacén \_ de administración central escribiendo lo siguiente:

        ```powershell
        Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
        ```
    
    1. Si el servidor Back-End principal del grupo de copia de \_ seguridad es la entidad de seguridad, escriba:

        ```powershell        
        Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        ```
        
    1. Si el servidor Back-End servidor de copia de \_ seguridad es la entidad de seguridad, escriba:
    
        ```powershell
        Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
        ```
    
    1. Valide que se haya completado la conmutación por error del servidor de administración central. Escriba el siguiente comando:
    
        ```powershell    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        Compruebe que ActiveMasterFQDN y ActiveFileTransferAgents apunten al FQDN del grupo de servidores de \_ copia de seguridad.
    
    1. Por último, compruebe el estado de la réplica para todos Front-End servidores escribiendo lo siguiente:
        
        ```powershell
        Get-CsManagementStoreReplicationStatus 
        ```
        
        Compruebe que todas las réplicas tengan un valor de True.
        
        Vaya al paso 7 de este procedimiento.

6.  Instale el almacén de administración central en el servidor back-end del grupo de servidores de \_ copia de seguridad.
    
    1. En primer lugar, ejecute el siguiente comando:

        ```powershell
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
    1. Ejecute el siguiente comando en uno de los servidores front-end del grupo de servidores de copia de seguridad para forzar el \_ movimiento del almacén de administración central:

        ```powershell
        Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force
        ```
    
    1. La validación del movimiento se ha completado:

        ```powershell
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        Compruebe que ActiveMasterFQDN y ActiveFileTransferAgents apunten al FQDN del grupo de servidores de \_ copia de seguridad.
    
    1. Compruebe el estado de réplica para todos los servidores front-end escribiendo lo siguiente:

        ```powershell
        Get-CsManagementStoreReplicationStatus
        ```
        
        Compruebe que todas las réplicas tengan un valor de True.
    
    1. Instale el servicio servidor de administración central en el resto de los servidores front-end en el grupo de servidores de \_ copia de seguridad. Para ello, ejecute el siguiente comando en todos los servidores front-end, excepto el que usó al forzar el movimiento del almacén de administración central anteriormente en este procedimiento:

        ```console
        Bootstrapper /Setup
        ```

7.  Para conmutar por error a los usuarios de Pool1 a Pool2, ejecute el siguiente cmdlet en una ventana Skype Empresarial Server Shell de administración:

    ```powershell
    Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    ```
    
    Dado que los pasos que se han realizado en las partes anteriores de este procedimiento para comprobar que el estado del almacén de administración central no son universales, todavía existe la posibilidad de que este cmdlet falle porque el almacén de administración central aún no se ha conmutado por completo. En este caso, debe corregir el almacén de administración central en función de los mensajes de error que vea y, a continuación, volver a ejecutar este cmdlet.
    
    Si ve el siguiente mensaje de error, tiene que cambiar el grupo de servidores perimetrales en este sitio para que use un grupo de servidores diferente al del próximo salto antes de conmutar por error el grupo de servidores. Para obtener detalles, vea los procedimientos al comienzo de este tema.
    
    ```console
    Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
    topology as the next hop for the Edge server. Failing over this pool may cause External
    access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
    change the Edge internal next hop setting to point to a different Front-end pool,  before you
    proceed.
    ```


## <a name="fail-back-a-pool"></a>Conmutación por recuperación de un grupo

Una vez que el grupo que experimentó el desastre está de nuevo en línea (es decir, el Grupo1 en este ejemplo), siga los pasos siguientes para restaurar su implementación al estado de funcionamiento normal.

El proceso de conmutación por recuperación tarda varios minutos en completarse. Como referencia, se espera que tarde hasta 60 minutos en un grupo de 20 000 usuarios.

Realice la recuperación de los usuarios que estaban hospedados originalmente en el Grupo1 y se han conmutado por error al Grupo2 escribiendo el siguiente cmdlet:

```powershell
Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose
```

No es necesario realizar otros. Si ha fallado por error en el servidor de administración central, puede dejarlo en Pool2.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Conmutación por error del grupo de servidores perimetrales usado Skype Empresarial Server federación 

Si el grupo de servidores perimetrales en el que Skype Empresarial Server la federación está configurado, debe cambiar la federación para usar un grupo perimetral diferente para que funcione la federación.

1.  En un servidor front-end, abra el Generador de topologías. Expanda **Grupos de servidores** perimetrales y, a continuación, haga clic con el botón secundario en el servidor perimetral o grupo de servidores perimetrales que está configurado actualmente para federación. Seleccione **Editar propiedades**.

2.  En **Editar propiedades**, en la pestaña **General**, desactive **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Seleccione **Aceptar**.

3.  Expanda **Grupos perimetrales** y, a continuación, haga clic con el botón secundario en el servidor perimetral o grupo de servidores perimetrales que ahora desea usar para federación. Seleccione **Editar propiedades**.

4.  En **Editar propiedades**, en **General**, seleccione **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Seleccione **Aceptar**.

5.  Select **Action**, select **Topology**, select **Publish**. Cuando se le pida **en Publicar la topología,** seleccione **Siguiente**. Cuando finalice la publicación, seleccione **Finalizar**.

6.  En el servidor perimetral, abra el asistente Skype Empresarial Server implementación. Seleccione **Instalar o actualizar Skype Empresarial Server System** y, a continuación, seleccione Configurar o Quitar Skype Empresarial Server **componentes**. Seleccione **Ejecutar de nuevo**.

7.  Seleccione **Siguiente**. La pantalla de resumen mostrará las acciones a medida que se ejecuten. Una vez realizada la implementación, seleccione **Ver registro** para ver los archivos de registro disponibles. Seleccione **Finalizar** para completar la implementación.
    
    Si el sitio que contiene el grupo de servidores perimetrales con errores contiene servidores front-end que todavía se están ejecutando, debe actualizar el servicio de conferencia web y el servicio de conferencia A/V en estos grupos de servidores de Front-End para usar un grupo de servidores perimetrales en un sitio remoto que todavía se está ejecutando. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Conmutar por error el grupo de servidores perimetrales usado para la federación XMPP en Skype Empresarial Server 

En su organización, hay un grupo perimetral designada como el grupo para la federación XMPP. Si este grupo se desactiva, debe conmutar por error la federación XMPP para que use otro grupo perimetral antes de que la federación XMPP pueda volver a trabajar.

Al instalar primero los grupos perimetrales y habilitar la federación XMPP, puede simplificar el proceso de recuperación ante desastres estableciendo registros SRV de DNS externos para todos los grupos perimetrales para la federación XMPP, en lugar de solo uno. Cada uno de estos registros SRV debe tener establecida una prioridad diferente. Todo el tráfico de la federación XMPP atraviesa el grupo con el registro SRV con la prioridad más alta. 

En el siguiente procedimiento, EdgePool1 es el grupo de servidores, que originalmente hospedaba la federación XMPP, y EdgePool2 es el grupo que ahora hospedará la federación XMPP.
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>Para conmutar por error el grupo de servidores perimetrales usado para la federación XMPP

1.  Si aún no tiene implementado otro grupo de servidores perimetrales (además del que está actualmente en desan), implemente ese grupo. 

2.  En cada servidor perimetral del nuevo grupo perimetral que alojará ahora la federación XMPP (EdgePool2), ejecute el siguiente cmdlet:

    ```powershell
    Stop-CsWindowsService
    ```

3.  Ejecute el siguiente cmdlet para cambiar la ruta de la federación XMPP a EdgePool2:

    ```powershell
    Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    ```
    
    En este ejemplo, Site2 es el sitio que contiene el grupo perimetral que alojará ahora la federación XMPP y EdgeServer2.contoso.com es el FQDN de un servidor perimetral del grupo.

4.  En el servidor DNS externo, cambie el registro de DNS A de la federación XMPP para que apunte a EdgeServer2.contoso.com.

5.  Si aún no tiene un registro SRV de DNS para la federación XMPP que resuelva al grupo perimetral que alojará ahora la federación de XMPP, debe agregarlo, como en el ejemplo siguiente. Este registro SRV debe tener un valor de puerto de 5269.

    ```console
    _xmpp-server._tcp.contoso.com
    ```

6.  Compruebe que el grupo perimetral que alojará ahora la federación XMPP tiene abierto el puerto 5269 externamente.

7.  Inicie los servicios en todos los servidores perimetrales del grupo perimetral que alojará ahora la federación XMPP:

    ```powershell
    Start-CsWindowsService
    ```

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Conmutación por recuperación del grupo de servidores perimetrales usado Skype Empresarial Server federación o federación XMPP 

Después de que un grupo perimetral con errores que usaba para hospedar la federación se haya vuelto a en línea, use este procedimiento para devolver la conmutación por recuperación de la ruta de federación de Skype Empresarial Server o la ruta de federación XMPP para volver a usar este grupo perimetral restaurado.

1.  En el grupo de servidores perimetrales que vuelve a estar disponible, inicie los servicios perimetrales.

2.  Si desea devolver la conmutación por recuperación Skype Empresarial Server de federación para usar el servidor perimetral restaurado, haga lo siguiente:
    
    1. En un servidor front-end, abra el Generador de topologías. Expanda **Grupos de servidores perimetrales** y, a continuación, haga clic con el botón secundario en el servidor perimetral o grupo de servidores perimetrales que está configurado actualmente para federación. Seleccione **Editar propiedades**.
    
    1. En **Editar propiedades**, en la pestaña **General**, desactive **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Seleccione **Aceptar**.
    
    1. Expanda **Grupos de servidores** perimetrales y, a continuación, haga clic con el botón secundario en el servidor perimetral original o el grupo de servidores perimetrales que de nuevo desea usar para federación. Seleccione **Editar propiedades**.
    
    1. En **Editar propiedades**, en **General**, seleccione **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Seleccione **Aceptar**.
    
    1. Select **Action**, select **Topology**, select **Publish**. Cuando se le pida **en Publicar la topología,** seleccione **Siguiente**. Cuando finalice la publicación, seleccione **Finalizar**.
    
    1. En el servidor perimetral, abra el asistente Skype Empresarial Server implementación. Seleccione **Instalar o actualizar Skype Empresarial Server system** y, a continuación, seleccione Configurar o Quitar Skype Empresarial Server **componentes**. Seleccione **Ejecutar de nuevo**.
    
    1. Seleccione **Siguiente**. La pantalla de resumen mostrará las acciones a medida que se ejecuten. Una vez realizada la implementación, seleccione **Ver registro** para ver los archivos de registro disponibles. Seleccione **Finalizar** para completar la implementación.

3.  Si quiere conmutar por recuperación la ruta de la federación XMPP para usar el servidor perimetral restaurado, haga lo siguiente:
    
    1. Ejecute el cmdlet siguiente para volver a apuntar la ruta de la federación XMPP al grupo de servidores perimetrales que ahora hospedarán la federación XMPP (en este ejemplo, EdgeServer1):
  
        ```powershell
        Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        ```
        
        En este ejemplo, Site1 es el sitio que contiene el grupo de servidores perimetrales que ahora contendrá la ruta de la federación XMPP y EdgeServer1.contoso.com es el FQDN de un servidor perimetral de ese grupo de servidores.
    
    1. Si todavía no tiene un registro DNS SRV para la federación XMPP que se resuelva en el grupo de servidores perimetrales que ahora hospedará la federación XMPP, agréguelo, como en el ejemplo siguiente. Este registro SRV debe tener un valor de puerto de 5269.

        ```console
        _xmpp-server._tcp.contoso.com
        ```
    
    1. En el servidor DNS externo, cambie el registro DNS A para la federación XMPP para que apunte a EdgeServer2.contoso.com.
    
    1. Compruebe que el grupo de servidores perimetrales que ahora hospedará la federación XMPP tiene el puerto 5269 abierto externamente.

4.  Si los grupos de servidores front-end siguieron ejecutándose en el sitio que contiene el grupo de servidores perimetrales que tuvo el error y que se ha restaurado, actualice el servicio de conferencia web y el servicio de conferencia A/V en estos grupos de servidores front-end para que vuelvan a usar los grupos de servidores perimetrales en su sitio local.

5.  Si el grupo de servidores front-end del mismo sitio que el grupo de servidores perimetrales también tuvo errores, ahora puede usar Invoke–CsPoolFailback para conmutar por recuperación el grupo de servidores front-end.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Cambiar el grupo de servidores perimetrales asociado a un grupo de servidores front-end

Si se produce un error en un grupo perimetral pero el grupo de front-end del mismo sitio sigue en ejecución, deberá establecer el grupo de servidores front-end para que use un grupo perimetral de otro sitio hasta que se restablezca el grupo perimetral en el que se ha producido el error.

1.  En el Generador de topologías, navegue hasta el nombre del grupo de servidores front-end que desea cambiar.

2.  Haga clic con el botón secundario en el grupo y, a continuación, **seleccione Editar propiedades**.

3.  En la sección **Asociaciones**, en **Asociar grupo perimetral (para componentes multimedia)**, use el cuadro desplegable para seleccionar el grupo perimetral al que desea asociar este grupo de servidores front-end.

4.  Seleccione **Aceptar**.
