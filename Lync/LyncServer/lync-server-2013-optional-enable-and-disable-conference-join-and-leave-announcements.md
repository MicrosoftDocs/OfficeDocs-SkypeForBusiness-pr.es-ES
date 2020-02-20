---
title: Opcional Habilitar y deshabilitar la Unión de conferencia y dejar anuncios
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67939f67e90e6c0cc044ea871560647cae9e4021
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a>Opcional Habilitar y deshabilitar la Unión a Conferencia y dejar anuncios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-30_

Cuando los usuarios de acceso telefónico local se unen a una conferencia o la abandonan, la aplicación de anuncio de conferencia puede anunciar su entrada o salida reproduciendo un tono o diciendo sus nombres. Puede cambiar el funcionamiento de los anuncios ejecutando cmdlets. Este paso es opcional.

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>Para modificar el comportamiento de los anuncios al unirse y abandonar conferencias

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-ServerAdministrator** o **CsAdministrator**.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Ejecute los siguientes comandos en símbolo del sistema:
    
        Get-CsDialinConferencingConfiguration
    
    Este cmdlet recupera información sobre si los participantes deben grabar su nombre al unirse a una conferencia y cómo responde Lync Server cuando los participantes se unen a una conferencia de acceso telefónico local o la abandonan.

4.  Ejecute los siguientes comandos en símbolo del sistema:
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording**   determina si se pide a los participantes anónimos que registren su nombre antes de entrar en la Conferencia. El valor predeterminado es "$true," lo que significa que se pide a los participantes anónimos que indiquen su nombre cuando se unan a una conferencia. (Los participantes autenticados no graban su nombre porque se usa el nombre para mostrar).
    
    **EntryExitAnnouncementsEnabledByDefault**   indica si los anuncios están activados o desactivados de forma predeterminada. El valor predeterminado es "$false," lo que significa que no hay anuncios de forma predeterminada cuando los participantes se unen a una conferencia o la abandonan. El organizador de la reunión puede invalidar esta opción cuando programa una reunión.
    
    **EntryExitAnnouncementsType**   indica la acción que se realiza siempre que un participante se une a una conferencia en la que los anuncios están habilitados o sale de la misma. El valor predeterminado es "UseNames," lo que significa que hay un anuncio parecido al siguiente: "Ken Myer se ha unido a la conferencia" cuando los anuncios están activados.
    
    Puede configurar estas opciones en el ámbito global o en el ámbito del sitio. Las opciones configuradas en el ámbito del sitio tienen precedencia sobre las opciones configuradas en el ámbito global.
    
    Por ejemplo:
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    En este ejemplo, las opciones están configuradas en el ámbito del sitio de Redmond. Los anuncios están activados, pero no se pide a los participantes que digan su nombre cuando se unen a una conferencia. Suena un tono cuando los participantes se unen a una conferencia o la abandonan.

</div>

</div>

<span> </span>

</div>

</div>

</div>

