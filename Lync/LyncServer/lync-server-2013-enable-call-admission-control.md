---
title: 'Lync Server 2013: habilitar el control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e129e109a62006d72b8b1db44c28effa8911e6c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528767"
---
# <a name="enable-call-admission-control-in-lync-server-2013"></a>Habilitar el control de admisión de llamadas en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Después de configurar las opciones de red para la implementación del control de admisión de llamadas, debe habilitar el CAC para que se apliquen las directivas de ancho de banda.

Para obtener más información, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:

  - [Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a>Para habilitar el control de admisión de llamadas usando el shell de administración

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet Set-CsNetworkConfiguration para habilitar el CAC en su red. Por ejemplo, ejecute lo siguiente:
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    Si desea deshabilitar el CAC en la red, ejecute lo siguiente:
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a>Para habilitar el control de admisión de llamadas usando el Panel de control de Lync Server

1.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  En la barra de navegación izquierda, haga clic en **Configuración de red**.

3.  Haga clic en el botón de navegación **Global**.

4.  Haga clic en **Global** en la lista y, a continuación, seleccione **Mostrar detalles** en el menú **Edición**.

5.  En la página **Editar configuración global**, active la casilla **Habilitar control de admisión de llamadas**.
    
    <div>
    

    > [!NOTE]  
    > Si desea deshabilitar el control de admisión de llamadas en toda la implementación, desactive esta casilla.

    
    </div>

6.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

