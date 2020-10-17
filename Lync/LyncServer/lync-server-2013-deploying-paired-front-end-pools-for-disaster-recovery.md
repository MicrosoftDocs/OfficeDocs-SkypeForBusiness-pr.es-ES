---
title: 'Lync Server 2013: implementación de grupos de servidores front-end emparejados para la recuperación ante desastres'
description: 'Lync Server 2013: implementación de grupos de servidores front-end emparejados para la recuperación ante desastres.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4846121f301d2bc7be1af9b58f0a0fef3f88e6d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555906"
---
# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a>Implementación de grupos de servidores front-end emparejados para la recuperación ante desastres en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Puede implementar fácilmente la topología de recuperación ante desastres de grupos de servidores front-end emparejados con el generador de topologías.

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a>Para implementar un par de grupos de servidores front-end

1.  Si los grupos son nuevos y aún no están definidos, use el generador de topologías para crear los grupos.

2.  En el generador de topologías, haga clic con el botón secundario en uno de los dos grupos y, a continuación, haga clic en **Editar propiedades**.

3.  Haga clic en **Resistencia** en el panel izquierdo y, a continuación, seleccione **Grupo de servidores de copia de seguridad asociado** en el panel derecho.

4.  En el cuadro de debajo de **Grupo de servidores de copia de seguridad asociado**, seleccione el grupo que desea emparejar con este grupo. Solo los grupos existentes que aún no están emparejados con otro grupo estarán disponibles para su selección.
    
    ![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")  

5.  Seleccione **Conmutación por error y conmutación por recuperación automática para voz** y haga clic en **Aceptar**.
    
    Cuando visualice los detalles sobre este grupo, el grupo asociado aparecerá en el panel derecho bajo **Resistencia**.

6.  Use el generador de topologías para publicar la topología.

7.  Si los dos grupos aún no se han implementado, impleméntelos ahora y se completará la configuración. Puede omitir los dos últimos pasos de este procedimiento.
    
    Sin embargo, si ya se implementaron los grupos antes de definir la relación emparejada, debe completar los dos pasos finales siguientes.

8.  En cada servidor front-end de ambos grupos, ejecute lo siguiente:
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    Esto configura otros servicios necesarios para que el emparejamiento de copia de seguridad funcione correctamente.

9.  Desde el símbolo del sistema del shell de administración de Lync Server, ejecute lo siguiente:
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. Haga que los datos de conferencia y usuarios de ambos grupos de servidores se sincronicen entre sí, con los siguientes cmdlets:
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    La sincronización de los datos puede tardar algún tiempo. Puede usar los siguientes cmdlets para comprobar el estado. Asegúrese de que el estado en ambas direcciones está en estado estable.
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> La opción <STRONG>conmutación por error automática y conmutación por recuperación para la opción de voz</STRONG> y los intervalos de tiempo asociados en el generador de topologías solo se aplican a las características de resistencia de voz que se introdujeron en Lync Server 2010. La selección de esta opción no implica que la conmutación por error de grupos de servidores tratada en este documento sea automática. La conmutación por error y la conmutación por recuperación de grupos de servidores siempre requieren que un administrador invoque manualmente los cmdlets de conmutación por error y de conmutación por recuperación, respectivamente.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

