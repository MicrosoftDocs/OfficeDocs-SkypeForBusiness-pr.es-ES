---
title: "(Opcional) Habilitar/deshabilitar anuncios de participación/abandono de conferencias"
TOCTitle: (Opcional) Habilitar y deshabilitar los anuncios de participación y abandono de conferencias
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48276656
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Opcional) Habilitar y deshabilitar los anuncios de participación y abandono de conferencias en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-30_

Cuando los usuarios de acceso telefónico se unen a una conferencia o la abandonan, la Aplicación de anuncio de conferencia puede anunciar su entrada o salida haciendo sonar un tono o diciendo su nombre. Puede cambiar el funcionamiento de los anuncios ejecutando cmdlets. Este paso es opcional.

## Para modificar el comportamiento de los anuncios al unirse y abandonar conferencias

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-ServerAdministrator** o **CsAdministrator** .

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute los siguientes comandos en símbolo del sistema:
    
        Get-CsDialinConferencingConfiguration
    
    Este cmdlet recupera información sobre si los participantes deben grabar su nombre cuando se unen a una conferencia y sobre cómo responde Lync Server cuando los participantes se unen a una conferencia de acceso telefónico o la abandonan.

4.  Ejecute los siguientes comandos en símbolo del sistema:
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording**   Determina si se pedirá a los participantes anónimos que graben su nombre antes de unirse a la conferencia. El valor predeterminado es "$true," lo que significa que se pide a los participantes anónimos que indiquen su nombre cuando se unan a una conferencia. (Los participantes autenticados no graban su nombre porque se usa el nombre para mostrar).
    
    **EntryExitAnnouncementsEnabledByDefault**   Indica si los anuncios están activados o desactivados de forma predeterminada. El valor predeterminado es "$false," lo que significa que no hay anuncios de forma predeterminada cuando los participantes se unen a una conferencia o la abandonan. El organizador de la reunión puede invalidar esta opción cuando programa una reunión.
    
    **EntryExitAnnouncementsType**   Indica la acción que se realiza siempre que un participante se une a una conferencia para la que tiene habilitados los anuncios o la abandona. El valor predeterminado es "UseNames," lo que significa que hay un anuncio parecido al siguiente: "Ken Myer se ha unido a la conferencia" cuando los anuncios están activados.
    
    Puede configurar estas opciones en el ámbito global o en el ámbito del sitio. Las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global.
    
    Por ejemplo:
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    En este ejemplo, las opciones están configuradas en el ámbito del sitio de Redmond. Los anuncios están activados, pero no se pide a los participantes que digan su nombre cuando se unen a una conferencia. Suena un tono cuando los participantes se unen a una conferencia o la abandonan.

