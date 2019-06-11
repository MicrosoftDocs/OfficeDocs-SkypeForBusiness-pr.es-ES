---
title: 'Lync Server 2013: crear o modificar perfiles de directiva de ancho de banda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38f44d759a77fea03b285d2e1af10838d508a6ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a>Crear o modificar perfiles de directiva de ancho de banda en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-15_

Como parte de control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir limitaciones de ancho de banda para determinadas modalidades. En Microsoft Lync Server 2013, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo. Puede establecer limitaciones generales de ancho de banda y limitaciones de sesión. Puede usar el panel de control de Lync Server para crear, modificar o eliminar un perfil de contenedor para estas directivas. Cada perfil de directiva de ancho de banda se puede asociar a uno o varios sitios de red. Use los procedimientos siguientes para crear o modificar un perfil de directiva de ancho de banda. Para eliminar un perfil de directiva de ancho de banda, consulte [eliminar perfiles de directiva de ancho de banda de red en Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a>Para crear un nuevo perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en Directiva de **ancho de banda**.

4.  En la página **Directiva de ancho de banda** , haga clic en **nuevo**.

5.  En **nuevo perfil de directiva de ancho de banda**, escriba un nombre en el campo **nombre** . Este nombre debe ser único entre todos los perfiles de directiva de ancho de banda.

6.  En el campo **límite de audio** , escriba un valor numérico. Este valor es la cantidad máxima de ancho de banda que se asignará a todas las conexiones de audio, expresadas en kbps.

7.  Escriba un valor numérico en el campo límite de la **sesión de audio** . Este valor es la cantidad máxima de ancho de banda que se asignará a una conexión de audio individual, expresada en kbps. Este valor debe ser 40 o superior.

8.  Escriba un valor numérico en el campo **límite de video** . Este valor es la cantidad máxima de ancho de banda que se asignará a todas las conexiones de vídeo, expresadas en kbps.

9.  Escriba un valor numérico en el campo límite de la **sesión de vídeo** . Este valor es la cantidad máxima de ancho de banda que se asignará a una conexión de video individual, expresada en kbps. Este valor debe ser 100 o superior.

10. Faculta Escriba un valor en el campo **Descripción** para proporcionar más información sobre este perfil de directiva de ancho de banda que no se puede expresar solo con el nombre.

11. Haga clic en **Confirmar**.
    
    <div>
    

    > [!NOTE]  
    > La creación de un nuevo perfil de directiva de ancho de banda no aplica automáticamente restricciones de ancho de banda. Primero debe asociar el perfil de directiva con un sitio. Para obtener más información sobre cómo asociar un perfil de directiva con un sitio, vea <A href="lync-server-2013-creating-or-modifying-network-sites.md">crear o modificar sitios de red en Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a>Para modificar un perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en Directiva de **ancho de banda**.

4.  En la página **Directiva de ancho de banda** , haga clic en el perfil de directiva de ancho de banda que desea modificar.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar perfil de directiva de ancho de banda** , modifique los campos según sea necesario (para obtener información detallada, consulte la sección "para crear un perfil de directiva de ancho de banda" anteriormente en este tema).

7.  Haga clic en **Confirmar**.
    
    <div>
    

    > [!NOTE]  
    > Al modificar el perfil de directiva de ancho de banda, se actualizarán inmediatamente las limitaciones de ancho de banda de todos los sitios de red asociados a este perfil de directiva de ancho de banda.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Eliminar perfiles de directiva de ancho de banda de red en Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Configurar el control de admisión de llamadas en Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

