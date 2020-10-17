---
title: 'Lync Server 2013: ver información de Perfil de la Directiva de ancho de banda de red'
description: 'Lync Server 2013: ver la información de Perfil de la Directiva de ancho de banda de red.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c72a3533ae6f49f91db91b2c3b515c0b5153ec27
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565406"
---
# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a>Ver la información de Perfil de la Directiva de ancho de banda de red en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Como parte del control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir las limitaciones de ancho de banda para ciertas modalidades. En Microsoft Lync Server 2013, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo. Puede establecer limitaciones generales de ancho de banda y sesión. Puede usar el panel de control de Lync Server para crear, modificar o eliminar un perfil de contenedor para estas directivas. Cada perfil de directiva de ancho de banda se puede asociar a uno o más sitios de red. Utilice los siguientes procedimientos para ver un perfil de directiva de ancho de banda. Para crear o modificar un perfil de directiva de ancho de banda, consulte [creación o modificación de perfiles de directiva de ancho de banda en Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a>Para ver un perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ancho de banda**.

4.  En la página **Directiva de ancho de banda** , haga clic en el perfil de directiva de ancho de banda que desea ver.

5.  En el menú **Editar **, haga clic en **Mostrar detalles **.

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Ver información de Perfil de la Directiva de ancho de banda de red mediante cmdlets de Windows PowerShell

Los perfiles de ancho de banda de red se pueden ver con Windows PowerShell y el cmdlet Get-CsNetworkBandwidthPolicyProfile. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a>Para ver la información del perfil de la Directiva de ancho de banda de red

  - Para ver información sobre todos los perfiles de directiva de ancho de banda de red, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Devolverá información similar a la siguiente:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

Si desea más información, consulte el tema de ayuda relativo al cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).

</div>

<div>

## <a name="see-also"></a>Consulte también


[Creación o modificación de perfiles de directiva de ancho de banda en Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Eliminación de perfiles de directiva de ancho de banda de red en Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Configurar el control de admisión de llamadas en Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

