---
title: 'Lync Server 2013: administración de nodos de monitor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27d2afd025897df4f9b98e235d408a264d2cceb2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a>Administración de nodos de monitor en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-20_

Además de modificar las transacciones sintéticas que se ejecutan en un nodo de monitor, los administradores también pueden usar el cmdlet **set-CsWatcherNodeConfiguration** para llevar a cabo otras dos tareas importantes: habilitar y deshabilitar el nodo de supervisor, y configurar el nodo de monitor para usar direcciones URL internas o externas al ejecutar sus pruebas.

De forma predeterminada, los nodos de monitor están diseñadas para ejecutar periódicamente todas sus transacciones sintéticas habilitadas. Sin embargo, a veces es posible que debas suspender dichas transacciones. Por ejemplo, si el nodo de monitor está desconectado temporalmente de la red y, a continuación, no hay ningún motivo para ejecutar las transacciones sintéticas. Sin la conectividad de red, se garantizará el error de esas transacciones. Si desea deshabilitar temporalmente un nodo de monitor, ejecute un comando similar a este desde el shell de administración de Lync Server:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

Este comando deshabilitará la ejecución de transacciones sintéticas en el nodo de monitor ATL-Watcher-001.litwareinc.com. Para volver a ejecutarlas, establezca la propiedad Enabled en True ($True):

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> La propiedad Enabled sirve para activar y desactivar nodos de monitor. En caso de que quiera eliminar un nodo de monitor permanentemente, use el cmdlet <STRONG>Remove-CsWatcherNodeConfiguration</STRONG>:<BR>Remove-CsWatcherNodeConfiguration: Identity "atl-watcher-001.litwareinc.com"<BR>Ese comando quita todos los parámetros de configuración de nodo de monitor del equipo especificado, lo que impide que el equipo ejecute automáticamente transacciones sintéticas. Sin embargo, el comando no desinstala los archivos del agente de System Center ni los archivos de sistema de Lync Server 2013.



</div>

De forma predeterminada, los nodos de monitor usan las direcciones URL externas de una organización al realizar sus pruebas. Sin embargo, los nodos de monitor también se pueden configurar para usar las direcciones URL internas de la organización. Esto permite a los administradores comprobar el acceso a la dirección URL para los usuarios que se encuentran dentro de la red perimetral. Para configurar un nodo de monitor para que use direcciones URL internas en lugar de direcciones URL externas, establece la propiedad UseInternalWebUrls en true ($True):

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

Si restablece esta propiedad en el valor predeterminado de falso ($False), el observador usará las direcciones URL externas:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

