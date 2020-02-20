---
title: 'Lync Server 2013: eliminar un intervalo de órbitas de estacionamiento de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Call Park orbit range
ms:assetid: 85e9f916-062d-450d-ac0a-aeaefc0f7cdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182546(v=OCS.15)
ms:contentKeyID: 48184713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33da856002239c3fed100c3fa519199e48afee15
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-call-park-orbit-range-in-lync-server-2013"></a>Eliminar un intervalo de órbitas de estacionamiento de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Use uno de los siguientes procedimientos para eliminar un intervalo de órbitas de estacionamiento de llamadas.

<div>

## <a name="to-use-lync-server-control-panel-to-delete-a-call-park-orbit-range"></a>Para usar el panel de control de Lync Server para eliminar un intervalo de órbitas de estacionamiento de llamadas

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Características de voz** y, a continuación, en **Estacionamiento de llamadas**.

4.  En la página **Estacionamiento de llamadas**, en el campo de búsqueda, escriba la totalidad o parte del nombre de intervalo de órbitas que desea eliminar.

5.  En la lista de órbitas resultante, haga clic en la órbita, en **Editar** y, a continuación, en **Eliminar**.

6.  Haga clic en **Aceptar**.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-call-park-orbit-range"></a>Para usar Windows PowerShell para eliminar un intervalo de órbitas de estacionamiento de llamadas

1.  Inicie sesión en el equipo donde esté instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  En la línea de comandos, escriba lo siguiente:
    
        Remove-CsCallParkOrbit -Identity "<orbit range name>" 
    
    Por ejemplo:
    
        Remove-CsCallParkOrbit -Identity "Redmond orbit 1"
    
    <div>
    

    > [!NOTE]  
    > Para obtener más información sobre más opciones, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear o modificar un intervalo de órbitas de estacionamiento de llamadas en Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[Get-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

