---
title: 'Lync Server 2013: habilitar el control de admisión de llamadas'
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
ms.openlocfilehash: b89c9b888dc610d60b2abbcefd4c9c67e9b0572e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a>Habilitar el control de admisión de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

El control de admisión de llamadas (CAC) es una red de regiones, sitios y subredes que permiten colocar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible. Después de configurar la red CAC, debe habilitar CAC para exigir las limitaciones de ancho de banda. Puede usar el panel de control de Lync Server para hacerlo.

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a>Para habilitar CAC desde el panel de control de Lync Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en **global**.

4.  En la página **global** , haga clic en la configuración **global** .
    
    <div>
    

    > [!NOTE]  
    > Solo se puede configurar una red para cualquier implementación de Microsoft Lync Server 2013, por lo que nunca habrá más de una configuración de red en la lista. No puede cambiar el nombre de la configuración global.

    
    </div>

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar configuración global** , active la casilla **Habilitar control de admisión de llamadas** y, a continuación, haga clic en **confirmar**.

Al hacer clic en **confirmar**, se ejecuta una prueba de la configuración. Se cerrará el cuadro de diálogo **Editar configuración global** y volverá a la página **global** . Recibirá una advertencia si se detectan errores o incoherencias en la configuración de red que le impedirán que funcione correctamente (por ejemplo, si cada región no está conectada a ninguna otra región a través de una ruta interregion).

Si realiza cambios en la configuración de red, puede volver a ejecutar la comprobación de validación abriendo la configuración global y haciendo clic en **confirmar**. No es necesario deshabilitar CAC en primer lugar: deje la casilla activada y haga clic en **confirmar**. Puede hacerlo en cualquier momento sin realizar cambios en la configuración.

</div>

<div>

## <a name="see-also"></a>Vea también


[Información general sobre el control de admisión de llamadas en Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)  


[Planear el control de admisión de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
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

