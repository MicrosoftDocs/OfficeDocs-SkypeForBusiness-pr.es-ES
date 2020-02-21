---
title: 'Lync Server 2013: quitar archivos de actualización de dispositivo no asociados con un dispositivo'
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
ms.openlocfilehash: 1376e82ac29efbe2fcbf996445a75fc3bea1492d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a>Quitar los archivos de actualización de dispositivos que no estén asociados con un dispositivo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Cada vez que se carga una nueva actualización de dispositivo en el sistema, se crea la regla de actualización de dispositivos correspondiente. De forma predeterminada, estas nuevas reglas de actualización de dispositivos se asignan al estado pendiente. Esto significa que las reglas se pueden descargar e instalar en dispositivos de prueba, pero no en dispositivos de producción, lo que permite probar las actualizaciones antes de ponerlas a disposición de los usuarios. En función de las pruebas, puede aceptar e implementar o rechazar y eliminar la actualización. Cuando rechaza una actualización, la actualización del dispositivo no está asociada a su regla de actualización de dispositivos.

<div>


Los archivos de actualización de dispositivos que ya no están asociados con un dispositivo se pueden quitar con Windows PowerShell y el cmdlet **Clear-CsDeviceUpdateFile** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.

<div>


> [!NOTE]  
> Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 mediante PowerShell remoto" en.



</div>

<div>


  - Por ejemplo, el siguiente comando quita las reglas de actualización de dispositivos en el servidor Web atl-cs-001.litwareinc.com que ya no están asociados con un dispositivo:
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

