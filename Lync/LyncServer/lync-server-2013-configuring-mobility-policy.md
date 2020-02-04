---
title: 'Lync Server 2013: Configuración de la directiva de movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39a7f0791def99e0b42a57b1f13aae88abbfafa4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a>Configuración de la directiva de movilidad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 proporciona directivas de movilidad que determinan quién puede usar las características de movilidad, llamar a través del trabajo, voz sobre IP (VoIP) o vídeo, y si se necesitará WiFi para VoIP o video. La característica llamar a través del trabajo permite a un usuario móvil realizar y recibir llamadas en un teléfono móvil con un número de teléfono del trabajo en lugar del número de teléfono móvil. Esta característica impide que la persona llamada Vea el número de teléfono móvil de la persona que llama y permite a un usuario evitar cargos por llamadas salientes. La configuración de VoIP y vídeo permite que los usuarios reciban y realicen llamadas y videollamadas con VoIP. Configuración para uso de WiFi defina si el dispositivo de un usuario necesita usar una red WiFi a través de una red de datos móviles.

De forma predeterminada, la movilidad, la llamada a través del trabajo y las características de VoIP y vídeo están habilitadas. La configuración para requerir WiFi para VoIp y vídeo está deshabilitada. Los administradores pueden determinar quién tiene acceso a estas características ejecutando un cmdlet. Puede desactivar las opciones globalmente, por sitio o por usuario.

Para poder usar las características de movilidad y llamar a través del trabajo, los usuarios deben cumplir los siguientes requisitos previos:

  - Los usuarios deben estar habilitados para Lync Server 2013.

  - Los usuarios deben estar habilitados para telefonía IP empresarial.

  - Los usuarios deben tener asignada una directiva de movilidad que tenga la opción **EnableMobility** establecida en true.

Para que los usuarios puedan usar las llamadas a través del trabajo, deben cumplir los siguientes dos requisitos previos adicionales:

  - A los usuarios se les debe asignar una directiva de voz que tenga seleccionada la opción **Habilitar llamadas simultáneas a teléfonos** .

  - Los usuarios deben tener asignada una directiva de movilidad que tenga la opción **EnableOutsideVoice** establecida en true.

<div>


> [!NOTE]  
> Los usuarios que no tienen habilitada la telefonía IP empresarial pueden usar sus dispositivos móviles para hacer llamadas de voz sobre IP (VoIP) de Lync a Lync o pueden unirse a conferencias con el vínculo haga clic para unirse en sus dispositivos móviles, si asigna a esos usuarios las opciones adecuadas para la Directiva de voz. Para obtener más información, vea <A href="lync-server-2013-defining-your-mobility-requirements.md">definir los requisitos de movilidad para Lync Server 2013</A>.



</div>

Para obtener más información sobre cómo habilitar usuarios para Lync Server 2013, vea [deshabilitar o volver a habilitar la cuenta de usuario para Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Para obtener más información sobre cómo habilitar usuarios para telefonía IP empresarial, consulte [Habilitar usuarios para telefonía IP empresarial en Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md). Para obtener más información sobre cómo configurar las opciones de directiva de voz, consulte [modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).

<div>

## <a name="to-modify-global-mobility-policy"></a>Para modificar la Directiva de movilidad global

1.  Inicie sesión en cualquier equipo donde esté instalado shell de administración de Lync Server y Ocscore como miembro del rol CsAdministrator.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Desactiva el acceso a la movilidad y llama a través del trabajo de forma global. En la línea de comandos, escriba:
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > Puede desactivar la llamada por trabajo sin desactivar el acceso a la movilidad. Sin embargo, no puede desactivar la movilidad sin desactivar también la llamada a través del trabajo.

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>Para modificar la Directiva de movilidad por sitio

1.  Inicie sesión en cualquier equipo donde esté instalado shell de administración de Lync Server y Ocscore como miembro del rol CsAdministrator.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Cree una directiva de nivel de sitio, desactive VoIP y vídeo, y habilite la opción requerir WiFi para audio IP y para video IP por sitio. En la línea de comandos, escriba:
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>Para modificar la Directiva de movilidad por usuario

1.  Inicie sesión en cualquier equipo donde esté instalado shell de administración de Lync Server y Ocscore como miembro del rol CsAdministrator.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Crear directivas de movilidad de nivel de usuario y desactivar la movilidad y la llamada a través del trabajo por usuario. En la línea de comandos, escriba:
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    Puede desactivar la llamada por trabajo sin desactivar el acceso a la movilidad. Sin embargo, no puede desactivar la movilidad sin desactivar también la llamada a través del trabajo.
    
    Por ejemplo:
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>Vea también


[Deshabilitar o volver a habilitar la cuenta de usuario para Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Habilitar usuarios para telefonía IP empresarial en Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[Definir los requisitos de movilidad para Lync Server 2013](lync-server-2013-defining-your-mobility-requirements.md)  


[New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

