---
title: 'Lync Server 2013: (opcional) modificar la asignación de teclas para comandos DTMF'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcf6f6b2dd65d9429bf23397baff5bbe072800f0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a>Opcional Modificar la asignación de teclas para comandos DTMF en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-30_

Los usuarios de conferencia de acceso telefónico local pueden presionar las teclas del teléfono para usar los comandos de tono de marcado de frecuencia múltiple (DTMF). Los comandos DTMF permiten a los usuarios que obtengan acceso telefónico a una conferencia controlar la configuración de la conferencia (como activar o desactivar el audio propio o bloquear y desbloquear la conferencia) mediante el teclado de su teléfono. Puede usar cmdlets para modificar las teclas usadas para los comandos DTMF. Este paso es opcional.

<div>


> [!NOTE]  
> Para obtener más información sobre estos cmdlets y las posibles opciones de DTMF, consulte Lync Server Management Shell Documentation o la ayuda de línea de comandos del shell de administración de Lync Server.



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a>Para modificar la asignación de teclas de comandos DTMF

1.  Inicie sesión en el equipo como miembro del grupo **RTCUniversalServerAdmins**, o bien como miembro del rol **Cs-ServerAdministrator** o **CsAdministrator**.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

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

5.  (Opcional) Para crear conjuntos de comandos DTMF adicionales para sitios específicos, use el cmdlet **New-CsDialinConferencingDtmfConfiguration** con una identidad de sitio. Cuando se crea una configuración de DTMF para sitios, la configuración de sitio prevalece por encima de la configuración global. Para obtener más información, consulte la documentación del shell de administración de Lync Server o la ayuda de línea de comandos del shell de administración de Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

