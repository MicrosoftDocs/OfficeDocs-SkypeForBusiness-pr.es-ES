---
title: Implementar grupos de servidores front-end emparejados para la recuperación ante desastres en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Puede decidir usar grupos de servidores front-end emparejados para proporcionar protección de recuperación ante desastres, pero hacerlo no es un requisito.
ms.openlocfilehash: 9aec106905b2d8628e30461dce130f301aef1b25
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741336"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>Implementar grupos de servidores front-end emparejados para la recuperación ante desastres en Skype Empresarial Server
 
Puede decidir usar grupos de servidores front-end emparejados para proporcionar protección de recuperación ante desastres, pero hacerlo no es un requisito.
  
Puede implementar fácilmente la topología de recuperación ante desastres de grupos de servidores front-end emparejados mediante el Generador de topologías. 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>Para implementar un par de grupos de servidores front-end

1. Si los grupos de servidores son nuevos y aún no están definidos, use el Generador de topologías para crear los grupos de servidores.
    
2. En el Generador de topologías, haga clic con el botón secundario en uno de los dos grupos de servidores y, a continuación, haga clic **en Editar propiedades**.
    
3. Haga clic en **Resistencia** en el panel izquierdo y, a continuación, seleccione **Grupo de servidores de copia de seguridad asociado** en el panel derecho.
    
4. En el cuadro de debajo de **Grupo de servidores de copia de seguridad asociado**, seleccione el grupo que desea emparejar con este grupo. Solo los grupos existentes que aún no están emparejados con otro grupo estarán disponibles para su selección.
    
5. Seleccione **Conmutación por error y conmutación por recuperación automática para voz** y haga clic en **Aceptar**.
    
    Cuando visualice los detalles sobre este grupo, el grupo asociado aparecerá en el panel derecho bajo **Resistencia**. 
    
6. Use el Generador de topologías para publicar la topología.
    
7. Si los dos grupos aún no se han implementado, impleméntelos ahora y se completará la configuración. Puede omitir los pasos finales de este procedimiento.
    
    Sin embargo, si los grupos de servidores ya se implementaron antes de definir la relación emparejada, debe completar los siguientes pasos finales.
    
8. En cada servidor front-end de ambos grupos, ejecute lo siguiente:
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    Esto configura otros servicios necesarios para que el emparejamiento de copia de seguridad funcione correctamente.
    
9. Una vez que Bootstrapper termine de instalar los componentes necesarios para el emparejamiento de copias de seguridad en todos los servidores front-end de ambos grupos de servidores, asegúrese de volver a aplicar cualquier actualización acumulativa existente que se haya aplicado anteriormente en estos servidores front-end en ambos grupos de servidores y, a continuación, continúe con el paso siguiente.

10. Desde un Skype Empresarial Server de comandos del Shell de administración, ejecute lo siguiente: 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. Forzar que los datos de usuario y conferencia de ambos grupos se sincronicen entre sí con los cmdlets siguientes:
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    La sincronización de los datos puede tardar algún tiempo. Puede usar los cmdlets siguientes para comprobar el estado. Asegúrese de que el estado en ambas direcciones está en estado estable.
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> La **opción Conmutación por** error automática y conmutación por recuperación de voz y los intervalos de tiempo asociados en el Generador de topologías solo se aplican a las características de resistencia de voz que se introdujeron en Lync Server. La selección de esta opción no implica que la conmutación por error de grupos de servidores tratada en este documento sea automática. La conmutación por error y la conmutación por recuperación de grupos de servidores siempre requieren que un administrador invoque manualmente los cmdlets de conmutación por error y de conmutación por recuperación, respectivamente.
  
## <a name="see-also"></a>Consulte también

[Recuperación ante desastres del grupo front-end en Skype Empresarial Server](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
