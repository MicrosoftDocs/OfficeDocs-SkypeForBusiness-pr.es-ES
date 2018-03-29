---
title: Implementación de grupos de servidores front-end emparejados para la recuperación ante desastres en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 9/1/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Puede decidir usar grupos de servidores front-end para proporcionar protección de recuperación ante desastres emparejados, pero hacerlo no es un requisito.
ms.openlocfilehash: e13694c364908cfef70edafc1e7eb0484c5fe1bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server-2015"></a>Implementación de grupos de servidores front-end emparejados para la recuperación ante desastres en Skype Empresarial Server 2015
 
Puede decidir usar grupos de servidores front-end para proporcionar protección de recuperación ante desastres emparejados, pero hacerlo no es un requisito.
  
Puede implementar fácilmente la topología de recuperación ante desastres de grupos emparejados de Front-End mediante el generador de topología. 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>Para implementar un par de grupos de servidores front-end

1. Si los grupos son nuevos y aún no está definido, utilice el generador de topología para crear los grupos.
    
2. Generador de topología, haga clic en uno de los dos grupos y, a continuación, haga clic en **Editar propiedades**.
    
3. Haga clic en **Resistencia** en el panel izquierdo y, a continuación, seleccione **Grupo de servidores de copia de seguridad asociado** en el panel derecho.
    
4. En el cuadro de debajo de **Grupo de servidores de copia de seguridad asociado**, seleccione el grupo que desea emparejar con este grupo. Solo los grupos existentes que aún no están emparejados con otro grupo estarán disponibles para su selección.
    
5. Seleccione **Conmutación por error y conmutación por recuperación automática para voz** y después haga clic en **Aceptar**.
    
    Cuando vea los detalles de este grupo, el grupo asociado aparecerá en el panel derecho debajo de **Resistencia**.  
    
6. Utilice el generador de topología para publicar la topología.
    
7. Si los dos grupos aún no se han implementado, impleméntelos ahora y se completará la configuración. Puede omitir los dos últimos pasos de este procedimiento.
    
    Sin embargo, si ya se implementaron los grupos antes de definir la relación emparejada, debe completar los dos pasos finales siguientes.
    
8. En cada servidor front-end de ambos grupos, ejecute lo siguiente:
    
   ```
   <system drive>\Program Files\Skype for Business Server 2015\Deployment\Bootstrapper.exe 
   ```

    Esto configura otros servicios necesarios para que el emparejamiento de copia de seguridad funcione correctamente.
    
9. Desde un Skype para la línea de comandos de Shell de administración de servidor de Business, ejecute lo siguiente: 
    
   ```
   Start-CsWindowsService -Name LYNCBACKUP
   ```

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
> La opción **automático failover y failback de voz** y los intervalos de tiempo asociado en el generador de topología sólo se aplican a las características de resistencia de voz que se introdujeron en Lync Server. La selección de esta opción no implica que la conmutación por error de grupos de servidores tratada en este documento sea automática. La conmutación por error y la conmutación por recuperación de los grupos de servidores siempre requieren que un administrador invoque manualmente los cmdlets de conmutación por error y de conmutación por recuperación, respectivamente.
  
## <a name="see-also"></a>Vea también

#### 

[Frontal de recuperación de desastres de grupo final en Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)

