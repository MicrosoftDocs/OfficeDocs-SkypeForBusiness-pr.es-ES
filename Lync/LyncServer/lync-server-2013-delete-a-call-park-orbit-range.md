---
title: 'Lync Server 2013: eliminar una intervalo orbitar de llamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a Call Park orbit range
ms:assetid: 85e9f916-062d-450d-ac0a-aeaefc0f7cdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182546(v=OCS.15)
ms:contentKeyID: 48184713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69144e6552f9c3688c904c8522689abc8da7add2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-call-park-orbit-range-in-lync-server-2013"></a>Eliminar un intervalo orbitar de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Use uno de los procedimientos siguientes para eliminar un intervalo de llamada en órbita.

<div>

## <a name="to-use-lync-server-control-panel-to-delete-a-call-park-orbit-range"></a>Para usar el panel de control de Lync Server para eliminar un intervalo orbitar de llamadas

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Características de voz** y, a continuación, en **Estacionamiento de llamadas**.

4.  En la página de **llamada estacionamiento** , en el campo de búsqueda, escriba todo o parte del nombre del rango de órbita que desea eliminar.

5.  En la lista resultante de órbitas, haga clic en la órbita, haga clic en **Editar**y, a continuación, haga clic en **eliminar**.

6.  Haga clic en **Aceptar**.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-call-park-orbit-range"></a>Para usar Windows PowerShell para eliminar un intervalo de llamada de Parque orbital

1.  Inicie sesión en el equipo donde está instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [permisos de configuración de delegado en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

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


[Crear o modificar un intervalo orbitar de llamadas en Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[Get-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

