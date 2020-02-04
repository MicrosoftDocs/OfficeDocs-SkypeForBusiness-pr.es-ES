---
title: 'Lync Server 2013: habilitar o deshabilitar un dispositivo de conferencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a conferencing device
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994070(v=OCS.15)
ms:contentKeyID: 51803981
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a4a0f582f57d4e096001d508d3983facdded74c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a>Habilitar o deshabilitar un dispositivo de conferencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Habilitar y deshabilitar un dispositivo de Conferencia mediante el cmdlet **enable-CsMeetingRoom** y el cmdlet **Disable-CsMeetingRoom** . Estos cmdlets se pueden ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.

<div>


> [!NOTE]  
> Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 mediante PowerShell remoto" en.



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a>Habilitar un dispositivo de conferencia

  - Para habilitar un dispositivo de conferencia, use el cmdlet **enable-CsMeetingRoom** . Al habilitar un dispositivo de conferencia, debe incluir una) la identidad del dispositivo de conferencia, b) el registrador en el que se va a alojar la cuenta de sala, y c) la dirección SIP que se va a asignar a esa cuenta.
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a>Deshabilitar un dispositivo de conferencia

  - Para deshabilitar un dispositivo de conferencia, use el cmdlet **Disable-CsMeetingRoom** . Asegúrese de especificar la identidad del dispositivo de conferencia que se va a deshabilitar:
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

Para obtener más información, consulte los temas de ayuda para el cmdlet [enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) y el cmdlet [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

