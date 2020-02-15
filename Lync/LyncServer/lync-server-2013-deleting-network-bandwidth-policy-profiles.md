---
title: 'Lync Server 2013: eliminación de perfiles de directiva de ancho de banda de red'
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
ms.openlocfilehash: a340cae47a73cb2b7926cf3f3b3832d22432ab2b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a>Eliminación de perfiles de directiva de ancho de banda de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Como parte del control de admisión de llamadas (CAC), se usa una directiva de ancho de banda para definir las limitaciones de ancho de banda para ciertas modalidades. En Microsoft Lync Server 2013, solo se pueden asignar limitaciones de ancho de banda a las modalidades de audio y vídeo. Puede establecer limitaciones generales de ancho de banda y sesión. Puede usar el panel de control de Lync Server para crear, modificar o eliminar un perfil de contenedor para estas directivas. Use los siguientes procedimientos para eliminar perfiles de directiva de ancho de banda de red. Para obtener información detallada sobre cómo crear o modificar un perfil de directiva de ancho de banda de red, consulte [creación o modificación de perfiles de directiva de ancho de banda en Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a>Para eliminar un perfil de directiva de ancho de banda

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Configuración de red** y, a continuación, en **Directiva de ancho de banda**.

4.  En la página **Directiva de ancho de banda**, haga clic en el perfil de directiva de ancho de banda que desea eliminar.
    
    <div>
    

    > [!NOTE]  
    > Puede eliminar más de un perfil en la misma operación. Para hacerlo, pulse CTRL y seleccione varios perfiles manteniendo pulsada la tecla CTRL. O bien, para seleccionar todos los perfiles, haga clic en <STRONG>Seleccionar todo</STRONG> en el menú <STRONG>Editar</STRONG>.

    
    </div>

5.  En el menú **Editar **, haga clic en **Eliminar **.
    
    <div>
    

    > [!WARNING]  
    > No puede eliminar un perfil de directiva de ancho de banda que esté asociado a un sitio de red. Primero debe eliminar la asociación establecida con el sitio de red para poder eliminar el perfil. Para obtener más información sobre cómo modificar el sitio de red, vea <A href="lync-server-2013-creating-or-modifying-network-sites.md">crear o modificar sitios de red en Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Creación o modificación de perfiles de directiva de ancho de banda en Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Ver la información de Perfil de la Directiva de ancho de banda de red en Lync Server 2013](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[Configurar el control de admisión de llamadas en Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

