---
title: 'Lync Server 2013: habilitar el parque de llamadas para los usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16538ba00571c429493a2bc0ce1ef14b0a331305
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a>Habilitar el parque de llamadas para los usuarios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-11_

Los usuarios no pueden detener llamadas ni recuperar llamadas estacionadas hasta que estén habilitadas para el parque de llamadas en la Directiva de voz.

<div>


> [!NOTE]  
> De forma predeterminada, el parque de llamadas está deshabilitado para todos los usuarios.



</div>

Puede habilitar el parque de llamadas en el ámbito global o en el ámbito del sitio o ámbito de usuario. El ámbito de usuario tiene prioridad sobre el ámbito de sitio y el ámbito de sitio tiene prioridad sobre el ámbito global. Si tiene varias directivas de voz, revise todas las directivas para habilitar el parque de llamadas, no solo la directiva global.

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a>Para usar el panel de control de Lync Server para habilitar el parque de llamadas para los usuarios

1.  Inicie sesión en el equipo como miembro del grupo **RTCUniversalServerAdmins** o bien como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.

4.  Haga clic en la pestaña **Directiva de voz**.

5.  Haga doble clic en una directiva de voz existente para abrir el cuadro de diálogo **Editar directiva de voz**.

6.  En **Características de llamada**, seleccione **Habilitar estacionamiento de llamadas**.

7.  Haga clic en **Aceptar** para guardar la directiva de voz.

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Para usar cmdlets para habilitar el parque de llamadas para los usuarios

1.  Inicie sesión en el equipo como un miembro del grupo RTCUniversalServerAdmins o bien, como un miembro del rol administrativo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    Por ejemplo, para habilitar el parque de llamadas para la Directiva de voz global predeterminada:
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

