---
title: 'Lync Server 2013: configuración de vínculos a sitios de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e379a8195dd0a50d97a514307ac594908be4736c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a>Configuración de vínculos a sitios de red en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Dentro de una configuración de control de admisión de llamadas (CAC), puede crear directivas entre sitios de red que definan limitaciones de ancho de banda entre sitios directamente vinculados. Cuando los sitios de red comparten un vínculo directo, se pueden definir limitaciones de ancho de banda para conexiones de audio y vídeo entre esos dos sitios. No puede usar el panel de control de Lync Server para configurar directivas de sitio de red, esto solo se puede realizar mediante cmdlets desde el shell de administración de Lync Server. Puede crear, modificar y quitar un vínculo de sitio de red (también conocido como una directiva entre sitios de red) desde el shell de administración de Lync Server.

<div>

## <a name="to-create-a-network-site-link"></a>Para crear un vínculo de sitio de red

1.  Inicie sesión en el equipo donde está instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [permisos de configuración de delegado en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  En el símbolo del sistema, escriba el siguiente comando y cambie los valores que sean válidos para su configuración:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    Este ejemplo crea un nuevo vínculo de sitio de red\_denominado Reno Portland que establece limitaciones de ancho de banda entre los sitios de red de Reno y Portland. Los sitios de red y el perfil de directiva de ancho de banda ya deben existir antes de ejecutar este comando.

Para obtener descripciones detalladas de parámetros, consulte [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) en la documentación del shell de administración de Lync Server. Para recuperar una lista de perfiles de directiva de ancho de banda que se pueden aplicar al vínculo de sitio de red, llame al cmdlet **Get-CsNetworkBandwidthPolicyProfile** . Para obtener más información, vea [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) en la documentación del shell de administración de Lync Server.

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>Para modificar un vínculo de sitio de red

1.  Inicie sesión en el equipo donde está instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [permisos de configuración de delegado en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Use el cmdlet **set-CsNetworkInterSitePolicy** para modificar las propiedades de un vínculo de sitio de red determinado. Puede modificar uno (o ambos) o los sitios conectados, y puede modificar el perfil de directiva de ancho de banda asociado con el vínculo. Este es un ejemplo de cómo modificar el perfil de directiva de ancho de banda de un\_vínculo a sitios denominado Reno Portland:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Para obtener descripciones detalladas de parámetros, consulte [set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) en la documentación del shell de administración de Lync Server.

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>Para eliminar un vínculo de sitio de red

1.  Inicie sesión en el equipo donde está instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [permisos de configuración de delegado en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Use el cmdlet **Remove-CsNetworkInterSitePolicy** para quitar un vínculo de sitio de red. En el siguiente ejemplo se elimina el\_vínculo de sitio de la red Reno Portland:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Para obtener descripciones detalladas de parámetros, consulte [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) en la documentación del shell de administración de Lync Server.

</div>

<div>

## <a name="see-also"></a>Vea también


[Cmdlets de control de admisión de llamadas en Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)  


[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

