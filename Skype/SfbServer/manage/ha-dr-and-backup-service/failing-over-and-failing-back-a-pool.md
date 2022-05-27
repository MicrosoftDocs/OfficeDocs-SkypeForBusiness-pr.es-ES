---
title: Conmutar por error y conmutar por recuperación un grupo
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: .
ms.openlocfilehash: 0b1f79ff40584c82d6da603ede49004f3c0c8968
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675042"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>Conmutación por error y conmutación por recuperación de un grupo en Skype Empresarial Server

Use los procedimientos siguientes si se ha producido un error en un único grupo de Front-End y es necesario conmutar por error, o si el grupo que experimentó el desastre vuelve a estar en línea y necesita restaurar la implementación al estado de trabajo normal. Obtenga información sobre cómo conmutar por error y conmutar por recuperación el grupo perimetral usado para Skype Empresarial federación o federación XMPP, o cambiar el grupo de servidores perimetrales asociado a un grupo de Front-End.

- [Conmutación por error de un grupo de servidores front-end](#fail-over-a-front-end-pool)
- [Conmutación por recuperación de un grupo](#fail-back-a-pool)
- [Conmutación por error del grupo de servidores perimetrales que se usa para Skype Empresarial Server federación](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [Conmutación por error del grupo de servidores perimetrales utilizado para la federación XMPP en Skype Empresarial Server](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [Conmutación por recuperación del grupo de Servidores perimetrales que se usa para Skype Empresarial Server federación o federación XMPP](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [Cambio del grupo de servidores perimetrales asociado a un grupo de servidores front-end](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Conmutación por error de un grupo de Front-End

Datacenter1 contiene Pool1 y se produjo un error en Pool1. Está conmutando por error a Pool2 ubicado en Datacenter2.

La mayor parte del trabajo para la conmutación por error del grupo implica la conmutación por error del almacén de administración central, si es necesario. El almacén de administración central debe ser funcional cuando se conmutan por error los usuarios del grupo.

Si se produce un error en un grupo de Front-End, pero el grupo perimetral de ese sitio sigue ejecutándose, debe saber si el grupo perimetral usa el grupo con errores como grupo de próximo salto. Si lo hace, debe cambiar el grupo de servidores perimetrales para usar un grupo de Front-End diferente antes de conmutar por error el grupo de Front-End con errores. La manera en que cambie la configuración del próximo salto depende de si el servidor perimetral usará un grupo de servidores en el mismo sitio que el grupo de servidores perimetrales, o un sitio diferente.

**Para establecer un grupo perimetral para usar un grupo de próximo salto en el mismo sitio**

1. Abra el Generador de topologías, haga clic con el botón derecho en el grupo perimetral que debe cambiarse y seleccione **Editar propiedades**.

2. Seleccione **Próximo salto**. En la lista **Grupo de próximos saltos:** , seleccione el grupo que ahora actuará como grupo de próximos saltos.

3. Seleccione **Aceptar** y, a continuación, publique los cambios.

**Para establecer un grupo perimetral para usar un grupo de próximo salto en otro sitio**

1. Abra una ventana del Shell de administración de Skype Empresarial Server y escriba el siguiente cmdlet:

    ```powershell
    Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>
    ```

**Para conmutar por error un grupo en un desastre**

1. Busque el grupo host del servidor de administración central escribiendo el siguiente cmdlet en un servidor de Front-End en Pool2:

    ```powershell
    Invoke-CsManagementServerFailover -Whatif
    ```

    Los resultados de este cmdlet muestran qué grupo hospeda actualmente el servidor de administración central. En el resto de este procedimiento, este grupo se conoce como grupo de CMS\_.

2. Use el Generador de topologías para buscar la versión de Skype Empresarial Server que se ejecuta en el grupo de CMS\_. Si ejecuta Skype Empresarial Server, use el siguiente cmdlet para buscar el grupo de copia de seguridad del grupo 1.

    ```powershell
    Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    ```

    Deje que el grupo de copias de seguridad\_sea el grupo de copia de seguridad.

3. Compruebe el estado del almacén de Administración central con el siguiente cmdlet:

    ```powershell
    Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
    ```

    Este cmdlet debe mostrar que ActiveMasterFQDN y ActiveFileTransferAgents apuntan al FQDN del grupo de CMS\_. Si están vacíos, el servidor de administración central no está disponible y debe conmutar por error.

4.  Si el almacén de administración central no está disponible o si el almacén de administración central se estaba ejecutando en Pool1 (es decir, el grupo que ha producido un error), debe conmutar por error el servidor de administración central antes de conmutar por error el grupo. Si necesita conmutar por error el servidor de administración central hospedado en un grupo que ejecuta Skype Empresarial Server, use el cmdlet en el paso 5 de este procedimiento. Si no necesita conmutar por error el servidor de administración central, vaya al paso 7 de este procedimiento.

5.  Para conmutar por error el almacén de Administración central en un grupo que ejecuta Skype Empresarial Server, haga lo siguiente:

    1. En primer lugar, compruebe qué Back-End Server del grupo de copias de seguridad\_ejecuta la instancia principal del almacén de Administración central escribiendo lo siguiente:

        ```powershell
        Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
        ```
    
    1. Si el servidor de Back-End principal del grupo de copias de seguridad\_es la entidad de seguridad, escriba:

        ```powershell        
        Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        ```
        
    1. Si la entidad de seguridad reflejada Back-End Server en el grupo de copias de seguridad\_es la entidad de seguridad, escriba:
    
        ```powershell
        Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
        ```
    
    1. Valide que la conmutación por error de Central Management Server está completa. Escriba el siguiente comando:
    
        ```powershell    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        Compruebe que ActiveMasterFQDN y ActiveFileTransferAgents apuntan al FQDN del grupo de copias de seguridad\_.
    
    1. Por último, compruebe el estado de la réplica para todos los servidores Front-End escribiendo lo siguiente:
        
        ```powershell
        Get-CsManagementStoreReplicationStatus 
        ```
        
        Compruebe que todas las réplicas tengan un valor de True.
        
        Vaya al paso 7 de este procedimiento.

6.  Instale el almacén de administración central en el servidor back-end del grupo de copia de seguridad\_.
    
    1. En primer lugar, ejecute el siguiente comando:

        ```powershell
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
    1. Ejecute el siguiente comando en uno de los servidores front-end del grupo de copia de seguridad\_para forzar el traslado del almacén de administración central:

        ```powershell
        Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force
        ```
    
    1. La validación del movimiento se ha completado:

        ```powershell
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        Compruebe que ActiveMasterFQDN y ActiveFileTransferAgents apuntan al FQDN del grupo de copias de seguridad\_.
    
    1. Compruebe el estado de réplica para todos los servidores front-end escribiendo lo siguiente:

        ```powershell
        Get-CsManagementStoreReplicationStatus
        ```
        
        Compruebe que todas las réplicas tengan un valor de True.
    
    1. Instale el servicio Central Management Server en el resto de servidores front-end del grupo de copias de seguridad\_. Para ello, ejecute el siguiente comando en todos los servidores front-end, excepto en el que usó al forzar el movimiento del almacén de administración central anteriormente en este procedimiento:

        ```console
        Bootstrapper /Setup
        ```

7.  Realice la conmutación por error de los usuarios de Pool1 a Pool2 ejecutando el siguiente cmdlet en una ventana del Shell de administración de Skype Empresarial Server:

    ```powershell
    Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    ```
    
    Dado que los pasos realizados en las partes anteriores de este procedimiento para comprobar el estado del almacén de Administración central no son universales, existe la posibilidad de que se produzca un error en este cmdlet porque el almacén de Administración central aún no se ha conmutado por error por completo. En este caso, debe corregir el almacén de Administración central en función de los mensajes de error que vea y, a continuación, volver a ejecutar este cmdlet.
    
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

El proceso de conmutación por recuperación tarda varios minutos en completarse. Como referencia, se espera que un grupo de 20 000 usuarios tardará hasta 60 minutos.

Realice la recuperación de los usuarios que estaban hospedados originalmente en el Grupo1 y se han conmutado por error al Grupo2 escribiendo el siguiente cmdlet:

```powershell
Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose
```

No es necesario realizar otros. Si ha conmutado por error el servidor de administración central, puede dejarlo en Pool2.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>Conmutación por error del grupo de servidores perimetrales que se usa para Skype Empresarial Server federación 

Si el grupo de servidores perimetrales donde tiene configurada Skype Empresarial Server federación deja de funcionar, debe cambiar la federación para usar un grupo perimetral diferente para que funcione la federación.

1.  En un servidor front-end, abra el Generador de topologías. Expanda **Grupos perimetrales** y, a continuación, haga clic con el botón derecho en el servidor perimetral o el grupo de servidores perimetrales que está configurado actualmente para federación. Seleccione **Editar propiedades**.

2.  En **Editar propiedades**, en la pestaña **General**, desactive **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Seleccione **Aceptar**.

3.  Expanda **Grupos perimetrales** y, a continuación, haga clic con el botón derecho en el servidor perimetral o el grupo de servidores perimetrales que ahora desea usar para federación. Seleccione **Editar propiedades**.

4.  En **Editar propiedades**, en **General**, seleccione **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Seleccione **Aceptar**.

5.  Seleccione **Acción****, topología y** **publicación**. Cuando se le pida en **Publicar la topología**, seleccione **Siguiente**. Cuando finalice la publicación, seleccione **Finalizar**.

6.  En el servidor perimetral, abra el Asistente para la implementación de Skype Empresarial Server. Seleccione **Instalar o actualizar Skype Empresarial Server Sistema** y, a continuación, seleccione **Configurar o Quitar componentes de Skype Empresarial Server**. Seleccione **Ejecutar de nuevo**.

7.  Seleccione **Siguiente**. La pantalla de resumen mostrará las acciones a medida que se ejecuten. Una vez finalizada la implementación, seleccione **Ver registro** para ver los archivos de registro disponibles. Seleccione **Finalizar** para completar la implementación.
    
    Si el sitio que contiene el grupo perimetral con errores contiene servidores front-end que todavía se están ejecutando, debe actualizar el servicio de conferencia web y el servicio de conferencia A/V en estos grupos de Front-End para usar un grupo perimetral en un sitio remoto que todavía se está ejecutando. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>Conmutación por error del grupo de servidores perimetrales utilizado para la federación XMPP en Skype Empresarial Server 

En su organización, hay un grupo perimetral designada como el grupo para la federación XMPP. Si este grupo se desactiva, debe conmutar por error la federación XMPP para que use otro grupo perimetral antes de que la federación XMPP pueda volver a trabajar.

Al instalar primero los grupos perimetrales y habilitar la federación XMPP, puede simplificar el proceso de recuperación ante desastres estableciendo registros SRV de DNS externos para todos los grupos perimetrales para la federación XMPP, en lugar de solo uno. Cada uno de estos registros SRV debe tener establecida una prioridad diferente. Todo el tráfico de la federación XMPP atraviesa el grupo con el registro SRV con la prioridad más alta. 

En el procedimiento siguiente, EdgePool1 es el grupo, que hospedaba originalmente la federación XMPP, y EdgePool2 es el grupo que ahora hospedará la federación XMPP.
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>Para conmutar por error el grupo perimetral usado para la federación XMPP

1.  Si aún no tiene implementado otro grupo de Edge (además del que está actualmente inactivo), implemente ese grupo. 

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

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>Conmutación por recuperación del grupo de Servidores perimetrales que se usa para Skype Empresarial Server federación o federación XMPP 

Después de que se haya vuelto a poner en línea un grupo perimetral con errores que se usaba para hospedar la federación, use este procedimiento para conmutar por recuperación la ruta de federación Skype Empresarial Server o la ruta de federación XMPP para volver a usar este grupo perimetral restaurado.

1.  En el grupo de servidores perimetrales que vuelve a estar disponible, inicie los servicios perimetrales.

2.  Si desea conmutar por recuperación la ruta de federación Skype Empresarial Server para usar el servidor perimetral restaurado, haga lo siguiente:
    
    1. En un servidor front-end, abra el Generador de topologías. Expanda **Grupos perimetrales** y, a continuación, haga clic con el botón derecho en el servidor perimetral o en el grupo de servidores perimetrales que está configurado actualmente para federación. Seleccione **Editar propiedades**.
    
    1. En **Editar propiedades**, en la pestaña **General**, desactive **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Seleccione **Aceptar**.
    
    1. Expanda **Grupos perimetrales** y, a continuación, haga clic con el botón derecho en el servidor perimetral original o en el grupo de servidores perimetrales que quiera usar de nuevo para federación. Seleccione **Editar propiedades**.
    
    1. En **Editar propiedades**, en **General**, seleccione **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Seleccione **Aceptar**.
    
    1. Seleccione **Acción****, topología y** **publicación**. Cuando se le pida en **Publicar la topología**, seleccione **Siguiente**. Cuando finalice la publicación, seleccione **Finalizar**.
    
    1. En el servidor perimetral, abra el Asistente para la implementación de Skype Empresarial Server. Seleccione **Instalar o actualizar Skype Empresarial Server Sistema** y, a continuación, seleccione **Configurar o Quitar componentes de Skype Empresarial Server**. Seleccione **Ejecutar de nuevo**.
    
    1. Seleccione **Siguiente**. La pantalla de resumen mostrará las acciones a medida que se ejecuten. Una vez finalizada la implementación, seleccione **Ver registro** para ver los archivos de registro disponibles. Seleccione **Finalizar** para completar la implementación.

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


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>Cambio del grupo de servidores perimetrales asociado a un grupo de servidores front-end

Si se produce un error en un grupo perimetral pero el grupo de front-end del mismo sitio sigue en ejecución, deberá establecer el grupo de servidores front-end para que use un grupo perimetral de otro sitio hasta que se restablezca el grupo perimetral en el que se ha producido el error.

1.  En el Generador de topologías, navegue hasta el nombre del grupo de servidores front-end que desea cambiar.

2.  Haga clic con el botón derecho en el grupo y, a continuación, seleccione **Editar propiedades**.

3.  En la sección **Asociaciones**, en **Asociar grupo perimetral (para componentes multimedia)**, use el cuadro desplegable para seleccionar el grupo perimetral al que desea asociar este grupo de servidores front-end.

4.  Seleccione **Aceptar**.
