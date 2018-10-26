---
title: "Implementación de grupos front-end emparejados para recuperación ante desastres"
TOCTitle: Implementación de grupos front-end emparejados para recuperación ante desastres
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48274810
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementación de grupos front-end emparejados para recuperación ante desastres en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

Puede implementar fácilmente la topología de recuperación ante desastres de Grupos de servidores front-end emparejados con la Generador de topologías.

## Para implementar un par de grupos de servidores front-end

1.  Si los grupos son nuevos y aún no están definidos, use la Generador de topologías para crear los grupos.

2.  En Generador de topologías, haga clic con el botón secundario en uno de los dos grupos y, a continuación, haga clic en **Editar propiedades**.

3.  Haga clic en **Resistencia** en el panel izquierdo y, a continuación, seleccione **Grupo de servidores de copia de seguridad asociado** en el panel derecho.

4.  En el cuadro de debajo de **Grupo de servidores de copia de seguridad asociado**, seleccione el grupo que desea emparejar con este grupo. Solo los grupos existentes que aún no están emparejados con otro grupo estarán disponibles para su selección.
    
    ![Cuadro de diálogo Resiliencia](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "Cuadro de diálogo Resiliencia")  

5.  Seleccione **Conmutación por error y conmutación por recuperación automática para voz** y después haga clic en **Aceptar**.
    
    Cuando vea los detalles de este grupo, el grupo asociado aparecerá en el panel derecho debajo de **Resistencia**.

6.  Use la Generador de topologías para publicar la topología.

7.  Si los dos grupos aún no se han implementado, impleméntelos ahora y se completará la configuración. Puede omitir los dos últimos pasos de este procedimiento.
    
    Sin embargo, si ya se implementaron los grupos antes de definir la relación emparejada, debe completar los dos pasos finales siguientes.

8.  En cada servidor front-end de ambos grupos, ejecute lo siguiente:
    
        <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    
    Esto configura otros servicios necesarios para que el emparejamiento de copia de seguridad funcione correctamente.

9.  Desde un símbolo del sistema de Shell de administración de Lync Server, ejecute lo siguiente:
    
        Start-CsWindowsService -Name LYNCBACKUP

10. Haga que los datos de conferencia y usuarios de ambos grupos de servidores se sincronicen entre sí, con los siguientes cmdlets:
    
    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```
    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    La sincronización de datos podría llevar unos minutos. Puede utilizar los siguientes cmdlets para ver el estado. Asegúrese de que el estado de ambas direcciones sea parejo
    
    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```
    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```


> [!NOTE]
> La opción <STRONG>Conmutación por error y conmutación por recuperación automática para voz</STRONG> y los intervalos de tiempo asociados en la Generador de topologías solo se aplican a las características de resistencia de voz que se introdujeron en Lync Server 2010. La selección de esta opción no implica que la conmutación por error de grupos de servidores tratada en este documento sea automática. La conmutación por error y la conmutación por recuperación de grupos de servidores siempre requieren que un administrador invoque manualmente los cmdlets de conmutación por error y de conmutación por recuperación, respectivamente.


