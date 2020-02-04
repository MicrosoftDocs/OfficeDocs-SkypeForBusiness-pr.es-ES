---
title: 'Lync Server 2013: (Opcional) Modificar la asignación de teclas para comandos DTMF'
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
ms.openlocfilehash: 036092f1199ad0e361f8509b36930410685ece21
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a>(Opcional) Modificar la asignación de teclas para comandos DTMF en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-30_

Los usuarios de conferencia de acceso telefónico local pueden presionar las teclas en el teclado numérico del teléfono para usar los comandos de tono de marcado de frecuencia múltiple (DTMF). Los comandos DTMF permiten a los usuarios que obtengan acceso telefónico local a una conferencia controlar la configuración de la conferencia (como activar o desactivar el audio propio o bloquear y desbloquear la conferencia) con el teclado numérico de su teléfono. Puede usar cmdlets para modificar las claves que se usan para los comandos de DTMF. Este paso es opcional.

<div>


> [!NOTE]  
> Para obtener más información sobre estos cmdlets y las posibles opciones de DTMF, consulte la documentación del shell de administración de Lync Server o la ayuda de la línea de comandos del shell de administración de Lync Server Management.



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a>Para modificar la asignación de teclas de los comandos DTMF

1.  Inicie sesión en el equipo como miembro del grupo **RTCUniversalServerAdmins** o como miembro del rol **CS-ServerAdministrator** o **CsAdministrator** .

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute los siguientes comandos en símbolo del sistema:
    
        Get-CsDialinConferencingDtmfConfiguration
    
    Este cmdlet devuelve la configuración de DTMF usada para las conferencias de acceso telefónico local.

4.  Ejecute el cmdlet siguiente y especifique la tecla que se va a presionar para cada opción que quiera cambiar:
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    Este cmdlet modifica la configuración de DTMF que se usa para las conferencias de acceso telefónico local.
    
    Por ejemplo:
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    Este ejemplo intercambia la tecla que se presiona para habilitar o deshabilitar anuncios, y la tecla que se presiona para silenciar y reactivar el audio de todos los participantes. Dado que no se especifica ninguna identidad, estos cambios se aplican a la configuración de DTMF global.

5.  (Opcional) Para crear conjuntos de comandos DTMF adicionales para sitios específicos, use el cmdlet **New-CsDialinConferencingDtmfConfiguration** con una identidad de sitio. Cuando se crea una configuración de DTMF para sitios, la configuración de sitio prevalece por encima de la configuración global. Para obtener más información, consulte documentación del shell de administración de Lync Server o la ayuda de la línea de comandos del shell de administración de Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

