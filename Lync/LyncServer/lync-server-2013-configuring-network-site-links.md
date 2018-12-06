---
title: Configuración de vínculos de sitios de red
TOCTitle: Configuración de vínculos de sitios de red
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48275807
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de vínculos de sitios de red

 

_**Última modificación del tema:** 2012-11-01_

En una configuración de control de admisión de llamadas (CAC), puede crear directivas entre sitios de red que definan las limitaciones de ancho de banda entre sitios que estén directamente vinculados. Cuando los sitios de red comparten un vínculo directo, es posible definir limitaciones de ancho de banda para las conexiones de audio y vídeo entre ambos sitos. No puede usar Panel de control de Lync Server para configurar directivas de sitio de red. Para hacerlo, deberá usar cmdlets del Shell de administración de Lync Server. Puede crear, modificar y quitar un vínculo de sitio de red (que también se denomina directiva entre sitios de red) del Shell de administración de Lync Server.

## Para crear un vínculo de sitio de red

1.  Inicie sesión en un equipo que tenga instalado el Shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios que se describen en [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Desde el símbolo del sistema, escriba el comando siguiente, usando los valores aplicables a su configuración:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    Este ejemplo crea un nuevo vínculo de sitio de red denominado Reno\_Portland que establece las limitaciones de ancho de banda entre los sitios de red de Reno y Portland. El perfil de la directiva de sitios de red y de ancho de banda debe existir antes de ejecutar este comando.

Para obtener descripciones de parámetros detalladas, consulte [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterSitePolicy) en la documentación de Shell de administración de Lync Server. Para recuperar una lista de perfiles de directivas de ancho de banda que puedan aplicarse al vínculo de sitio de red, ejecute el cmdlet **Get-CsNetworkBandwidthPolicyProfile**. Para más información, consulte [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) en la documentación del Shell de administración de Lync Server.

## Para modificar un vínculo de sitio de red

1.  Inicie sesión en un equipo que tenga instalado el Shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios que se describen en [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Use el cmdlet **Set-CsNetworkInterSitePolicy** para modificar las propiedades de un vínculo de sitio de red. Puede modificar uno de los sitios conectados (o ambos), y también puede modificar el perfil de directiva de banda de ancha asociado al vínculo. Aquí tiene un ejemplo de modificación de un perfil de directiva de banda ancha de un vínculo de sitio denominado Reno\_Portland:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Para obtener descripciones de parámetros detalladas, consulte [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterSitePolicy) en la documentación de Shell de administración de Lync Server.

## Para eliminar un vínculo de sitio de red

1.  Inicie sesión en un equipo que tenga instalado el Shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios que se describen en [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Use el cmdlet **Remove-CsNetworkInterSitePolicy** para quitar un vínculo de sitio de red. En el ejemplo siguiente se elimina el vínculo de sitio de red Reno\_Portland:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Para obtener descripciones de parámetros detalladas, consulte [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterSitePolicy) en la documentación de Shell de administración de Lync Server.

## Vea también

#### Conceptos

[Cmdlets de control de admisión de llamadas](https://docs.microsoft.com/en-us/powershell/module/skype/)  

#### Otros recursos

[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

