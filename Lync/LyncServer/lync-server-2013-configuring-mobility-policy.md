---
title: 'Lync Server 2013: Configuración de la directiva de movilidad'
TOCTitle: Configuración de la directiva de movilidad
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48275353
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de la directiva de movilidad en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 proporciona directivas de movilidad que determinan quién puede utilizar las características de movilidad, Vía trabajo, voz sobre IP (VoIP) o vídeo, y si se requerirá WiFi para VoIP o vídeo. La característica Vía trabajo permite a un usuario móvil realizar y recibir llamadas en un teléfono móvil usando un número de teléfono de trabajo en lugar del número de teléfono móvil. Esta característica impide que la parte que recibe la llamada vea el número de teléfono móvil del autor y permite que los usuarios eviten cargos de llamadas salientes. La configuración de VoIP y vídeo permite que los usuarios reciban y realicen llamadas VoIP y vídeo. La configuración del uso de WiFi define si será necesario que el dispositivo de un usuario use una red WiFi además de una red de datos de telefonía móvil.

De manera predeterminada, las características de movilidad, Vía trabajo y VoIP y vídeo están habilitadas. El valor para requerir WiFi para VoIP y vídeo está deshabilitado. Los administradores pueden determinar quién tiene acceso a estas características ejecutando un cmdlet. Puede desactivar las opciones globalmente, por sitio o por usuario.

Para poder usar las características de movilidad y Vía trabajo, los usuarios deben cumplir los requisitos previos siguientes:

  - Los usuarios deben estar habilitados para Lync Server 2013.

  - Los usuarios deben estar habilitados para Telefonía IP empresarial.

  - Los usuarios deben tener asignada una directiva de movilidad que tenga la opción **EnableMobility** configurada en True.

Para que los usuarios puedan usar Vía trabajo, deben cumplir los dos requisitos previos adicionales siguientes:

  - Los usuarios deben tener asignada una directiva de voz que tenga la opción **Habilitar llamadas simultáneas** seleccionada.

  - Se debe asignar a los usuarios una directiva de movilidad que contenga la opción **EnableOutsideVoice** configurada en True.


> [!NOTE]
> Los usuarios que no están habilitados para Telefonía IP empresarial pueden usar sus dispositivos móviles para realizar llamadas de voz sobre IP (VoIP) de Lync a Lync o pueden unirse a conferencias usando el vínculo de participación mediante clic en sus dispositivos móviles, si asigna a estos usuarios las opciones adecuadas para la directiva de voz. Para obtener detalles, consulte <A href="lync-server-2013-defining-your-mobility-requirements.md">Definir los requisitos de movilidad para Lync Server 2013</A>.



Para obtener detalles sobre cómo habilitar a los usuarios para Lync Server 2013, consulte [Deshabilitación o rehabilitación de la cuenta de usuario de Lync Server en Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Para obtener detalles sobre cómo habilitar a los usuarios para Telefonía IP empresarial, consulte [Habilitar a los usuarios para la telefonía IP empresarial en Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md). Para obtener información sobre la configuración de las opciones de la directiva de voz, consulte [Modificar una directiva de voz y configurar registros de uso de RTC en Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).

## Para modificar la directiva de movilidad global

1.  Inicie sesión en cualquier equipo que tenga instalado Shell de administración de Lync Server y Ocscore como miembro del rol CsAdministrator.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Desactive el acceso a la movilidad y a Vía trabajo de forma global. En la línea de comandos, escriba:
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    

    > [!NOTE]
    > Puede desactivar Vía trabajo sin desactivar el acceso a la movilidad. Sin embargo, no puede desactivar la movilidad sin desactivar también Vía trabajo.



## Para modificar la directiva de movilidad por sitio

1.  Inicie sesión en cualquier equipo que tenga instalado Shell de administración de Lync Server y Ocscore como miembro del rol CsAdministrator.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Cree una directiva de nivel de sitio, desactive VoIP y vídeo, y habilite Requerir WiFi para audio IP y para vídeo IP por sitio. En la línea de comandos, escriba:
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

## Para modificar la directiva de movilidad por usuario

1.  Inicie sesión en cualquier equipo que tenga instalado Shell de administración de Lync Server y Ocscore como miembro del rol CsAdministrator.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Cree directivas de movilidad a nivel de usuario y desactive la movilidad y Vía trabajo por usuario. En la línea de comandos, escriba:
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    Puede desactivar Vía trabajo sin desactivar el acceso a la movilidad. Sin embargo, no puede desactivar la movilidad sin desactivar también Vía trabajo.
    
    Por ejemplo:
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

## Vea también

#### Tareas

[Deshabilitación o rehabilitación de la cuenta de usuario de Lync Server en Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Habilitar a los usuarios para la telefonía IP empresarial en Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Modificar una directiva de voz y configurar registros de uso de RTC en Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  

#### Conceptos

[Definir los requisitos de movilidad para Lync Server 2013](lync-server-2013-defining-your-mobility-requirements.md)  

#### Otros recursos

[New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy)  
[Set-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMobilityPolicy)  
[Grant-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsMobilityPolicy)

