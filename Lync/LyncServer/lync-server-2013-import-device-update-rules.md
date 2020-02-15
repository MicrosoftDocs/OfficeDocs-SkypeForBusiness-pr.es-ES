---
title: 'Lync Server 2013: importar reglas de actualización de dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import Device Update rules
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994056(v=OCS.15)
ms:contentKeyID: 51803967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7c0700606966713d9828f538d37600a718dcd43
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-device-update-rules-in-lync-server-2013"></a>Importar reglas de actualización de dispositivos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Las reglas de actualización de dispositivos solo se pueden importar mediante Windows PowerShell y el cmdlet **Import-CsDeviceUpdate** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.

<div>


> [!NOTE]  
> Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 mediante PowerShell remoto" en.



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a>Para importar reglas de actualización de dispositivos en un único servidor Web

  - El siguiente comando importa reglas de actualización de dispositivos en el servidor Web atl-cs-001.litwareinc.com:
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a>Para importar reglas de actualización de dispositivos a todos los servidores Web

  - En este ejemplo, las reglas de actualización de dispositivos se importan a todos los servidores web implementados en la organización. Para que este comando funcione, la carpeta \\ \\ATL-FS-001.litwareinc.com\\actualizaciones debe estar compartida y disponible para todos los servidores Web.
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

Para obtener más información, consulte el tema de ayuda del cmdlet [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Ver información sobre las reglas de actualización de dispositivos en Lync Server 2013](lync-server-2013-view-information-about-device-update-rules.md)  
[Aprobar una regla de actualización de dispositivos en Lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

