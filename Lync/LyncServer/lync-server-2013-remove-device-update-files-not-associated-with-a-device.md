---
title: 'Lync Server 2013: quitar archivos de actualización de dispositivos no asociados con un dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42a2579360fbb4af8d6f3c491f5a56c380b593d0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a>Quitar los archivos de actualización de dispositivo que no estén asociados con un dispositivo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Cada vez que se carguen nuevas actualizaciones de dispositivos en el sistema, se creará una regla de actualización de dispositivo correspondiente. De forma predeterminada, estas nuevas reglas de actualización de dispositivos se asignan al estado pendiente. Esto significa que las reglas se pueden descargar e instalar en dispositivos de prueba, pero no en dispositivos de producción, lo que le permite probar las actualizaciones antes de hacerlas disponibles para los usuarios. En función de las pruebas, acepta e implementa o rechaza y elimina la actualización. Cuando rechaza una actualización, la actualización del dispositivo se anula de su regla de actualización de dispositivo.

<div>


Los archivos de actualización de dispositivos que ya no están asociados con un dispositivo se pueden quitar con Windows PowerShell y el cmdlet **Clear-CsDeviceUpdateFile** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.

<div>


> [!NOTE]  
> Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 mediante PowerShell remoto" en.



</div>

<div>


  - Por ejemplo, el siguiente comando quita todas las reglas de actualización de dispositivos en el servidor Web atl-cs-001.litwareinc.com que ya no están asociadas a un dispositivo:
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

Para obtener más información, vea el tema de ayuda sobre el cmdlet [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

