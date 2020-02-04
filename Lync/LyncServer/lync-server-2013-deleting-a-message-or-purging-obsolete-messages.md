---
title: 'Lync Server 2013: Eliminación de un mensaje o depuración de mensajes obsoletos'
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
ms.openlocfilehash: d8040d52690628b6085727d6a1fdac9288b94d5e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a>Eliminación de un mensaje o depuración de mensajes obsoletos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

Un administrador de chat persistente puede eliminar un mensaje de un salón de chat persistente (y, opcionalmente, puede reemplazarlo por otro mensaje). Los administradores también pueden purgar mensajes obsoletos como parte del mantenimiento continuo para minimizar el crecimiento de la base de datos. Por ejemplo, este comando de Windows PowerShell quita todos los mensajes del salón de chat de ITChatRoom que publicó el usuario kenmyer@litwareinc.com:

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

Y este ejemplo reemplaza cualquier mensaje eliminado con la nota de que el mensaje ya no está disponible:

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) .

</div>

<span> </span>

</div>

</div>

</div>

