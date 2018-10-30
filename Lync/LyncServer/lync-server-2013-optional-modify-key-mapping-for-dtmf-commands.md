---
title: "Lync Server 2013: (Opcional) Modificar la asignación de teclas para comandos DTMF"
TOCTitle: (Opcional) Modificar la asignación de teclas para comandos DTMF
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48276828
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Opcional) Modificar la asignación de teclas para comandos DTMF en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-30_

Los usuarios de conferencia de acceso telefónico local pueden presionar las teclas del teléfono para usar los comandos de tono de marcado de frecuencia múltiple (DTMF). Los comandos DTMF permiten a los usuarios que obtengan acceso telefónico a una conferencia controlar la configuración de la conferencia (como activar o desactivar el audio propio o bloquear y desbloquear la conferencia) mediante el teclado de su teléfono. Puede usar cmdlets para modificar las teclas usadas para los comandos DTMF. Este paso es opcional.


> [!NOTE]
> Para obtener información sobre estos cmdlets y las posibles opciones de DTMF, consulte la documentación del Shell de administración de Lync Server o la Ayuda de la línea de comandos del Shell de administración de Lync Server.



## Para modificar la asignación de teclas de comandos DTMF

1.  Inicie sesión en el equipo como miembro del grupo **RTCUniversalServerAdmins**, o bien como miembro del rol **Cs-ServerAdministrator** o **CsAdministrator**.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute los siguientes comandos en símbolo del sistema:
    
        Get-CsDialinConferencingDtmfConfiguration
    
    Este cmdlet devuelve la configuración de DTMF usada para conferencias de acceso telefónico local.

4.  Ejecute el cmdlet siguiente y especifique la tecla que se debe presionar para cada una de las opciones que desea cambiar:
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    Este cmdlet modifica la configuración de DTMF usada para conferencias de acceso telefónico local.
    
    Por ejemplo:
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    En este ejemplo se cambia la tecla que se presiona para habilitar o deshabilitar anuncios y la tecla que se presiona para activar o desactivar el audio de todos los participantes. Como no se ha especificado el parámetro Identity, estos cambios se aplican a la configuración de DTMF global.

5.  (Opcional) Para crear conjuntos de comandos DTMF adicionales para sitios específicos, use el cmdlet **New-CsDialinConferencingDtmfConfiguration** con una identidad de sitio. Cuando se crea una configuración de DTMF para sitios, la configuración de sitio prevalece por encima de la configuración global. Para más información, consulte la documentación del Shell de administración de Lync Server o la Ayuda de la línea de comandos del Shell de administración de Lync Server.

