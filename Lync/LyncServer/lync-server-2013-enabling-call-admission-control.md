---
title: 'Lync Server 2013: habilitar el control de admisión de llamadas'
description: 'Lync Server 2013: habilitar el control de admisión de llamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f5737f83a1965b920f2a23e1aabbbaec2af7b3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572646"
---
# <a name="enabling-call-admission-control-in-lync-server-2013"></a>Habilitación del control de admisión de llamadas en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

El control de admisión de llamadas (CAC) consiste en una red de regiones, sitios y subredes que permiten aplicar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible. Una vez configurada la red CAC, debe habilitar el CAC para aplicar las limitaciones de ancho de banda. Puede usar el panel de control de Lync Server para hacerlo.

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a>Para habilitar CAC desde el panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Global**.

4.  En la página **Global**, haga clic en la configuración **Global**.
    
    <div>
    

    > [!NOTE]  
    > Solo se puede configurar una red para cualquier implementación de Microsoft Lync Server 2013, por lo que nunca habrá más de una configuración de red en la lista. No podrá cambiar el nombre de la configuración Global.

    
    </div>

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar configuración global**, active la casilla **Habilitar control de admisión de llamadas** y, a continuación, haga clic en **Confirmar**.

Al hacer clic en **Confirmar**, realizará una prueba de la configuración. Se cerrará el cuadro de diálogo **Editar configuración global** y el programa le devolverá a la página **Global**. Recibirá una advertencia si se descubren errores o incoherencias en la configuración de red que pudieran impedir el buen funcionamiento de la red (por ejemplo, si cada región no está conectada a otra región en una ruta interregional).

Si hace cambios en la configuración de red, puede volver a ejecutar la comprobación de validación abriendo la configuración Global y haciendo clic en **Confirmar**. No es necesario deshabilitar previamente el CAC: deje activada la casilla y haga clic en **Confirmar**. Puede hacerlo en cualquier momento aunque no haga cambios en la configuración.

</div>

<div>

## <a name="see-also"></a>Consulte también


[Información general sobre el control de admisión de llamadas en Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)  


[Planeación del control de admisión de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Configurar el control de admisión de llamadas en Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

