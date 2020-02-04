---
title: 'Lync Server 2013: eliminar perfiles de directiva de ancho de banda de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d01bdea6efb632d95a15c631715e9ebe0c9a3bd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a>Eliminar perfiles de directiva de ancho de banda de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Como parte de control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir limitaciones de ancho de banda para determinadas modalidades. En Microsoft Lync Server 2013, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo. Puede establecer limitaciones generales de ancho de banda y limitaciones de sesión. Puede usar el panel de control de Lync Server para crear, modificar o eliminar un perfil de contenedor para estas directivas. Use los procedimientos siguientes para eliminar los perfiles de la Directiva de ancho de banda de red. Para obtener más información sobre cómo crear o modificar un perfil de directiva de ancho de banda de red, vea [crear o modificar perfiles de directiva de ancho de banda en Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a>Para eliminar un perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **configuración de red** y, después, en Directiva de **ancho de banda**.

4.  En la página **Directiva de ancho de banda** , haga clic en el perfil de directiva de ancho de banda que desea eliminar.
    
    <div>
    

    > [!NOTE]  
    > Puede eliminar más de un perfil a la vez. Para ello, presione CTRL y seleccione varios perfiles manteniendo presionada la tecla CTRL. O bien, para seleccionar todos los perfiles, haga clic en <STRONG>seleccionar todo</STRONG> en el menú <STRONG>edición</STRONG> .

    
    </div>

5.  En el menú **Editar** , haga clic en **eliminar**.
    
    <div>
    

    > [!WARNING]  
    > No se puede eliminar un perfil de directiva de ancho de banda asociado a un sitio de red. Primero debe quitar la asociación con el sitio de red para poder eliminar el perfil. Para obtener más información sobre cómo modificar el sitio de red, vea <A href="lync-server-2013-creating-or-modifying-network-sites.md">crear o modificar sitios de red en Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear o modificar perfiles de directiva de ancho de banda en Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Ver la información de Perfil de la Directiva de ancho de banda en Lync Server 2013](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[Configurar el control de admisión de llamadas en Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

