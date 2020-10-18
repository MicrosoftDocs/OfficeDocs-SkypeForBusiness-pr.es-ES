---
title: 'Lync Server 2013: eliminación de un mensaje o depuración de mensajes obsoletos'
description: 'Lync Server 2013: eliminación de un mensaje o depuración de mensajes obsoletos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a message or purging obsolete messages
ms:assetid: 3f0c612d-6dfd-41a4-a5fe-5ff3448eb0ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215874(v=OCS.15)
ms:contentKeyID: 48706000
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 928e34d2ab52b02155568c7da96e4ac1d8154b7a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575826"
---
# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a>Eliminación de un mensaje o depuración de mensajes obsoletos en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

Un administrador de chat persistente puede eliminar un mensaje de un salón de chat persistente (y, opcionalmente, puede reemplazarlo por otro mensaje). Los administradores también pueden depurar mensajes obsoletos como parte del mantenimiento en curso, para minimizar el crecimiento de la base de datos. Por ejemplo, este comando de Windows PowerShell quita todos los mensajes del salón de chat de ITChatRoom que publicó el usuario kenmyer@litwareinc.com:

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

Y en este ejemplo se reemplazan los mensajes quitados por la nota de que el mensaje ya no está disponible:

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) .

</div>

<span> </span>

</div>

</div>

</div>

