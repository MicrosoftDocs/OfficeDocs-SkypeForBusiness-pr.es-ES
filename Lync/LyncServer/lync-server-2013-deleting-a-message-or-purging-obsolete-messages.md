---
title: 'Lync Server 2013: eliminación de un mensaje o depuración de mensajes obsoletos'
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
ms.openlocfilehash: c806de25b6936916f99eb262d40acb10aaa8e1f6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a><span data-ttu-id="26d90-102">Eliminación de un mensaje o depuración de mensajes obsoletos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26d90-102">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26d90-103">_**Última modificación del tema:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="26d90-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="26d90-104">Un administrador de chat persistente puede eliminar un mensaje de un salón de chat persistente (y, opcionalmente, puede reemplazarlo por otro mensaje).</span><span class="sxs-lookup"><span data-stu-id="26d90-104">A Persistent Chat administrator can delete a message from a Persistent Chat room (and, optionally, can replace it with another message).</span></span> <span data-ttu-id="26d90-105">Los administradores también pueden depurar mensajes obsoletos como parte del mantenimiento en curso, para minimizar el crecimiento de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="26d90-105">Administrators can also purge obsolete messages as part of ongoing maintenance, to minimize growth of the database.</span></span> <span data-ttu-id="26d90-106">Por ejemplo, este comando de Windows PowerShell quita todos los mensajes del salón de chat de ITChatRoom que publicó el usuario kenmyer@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="26d90-106">For example, this Windows PowerShell command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@litwareinc.com:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="26d90-107">Y en este ejemplo se reemplazan los mensajes quitados por la nota de que el mensaje ya no está disponible:</span><span class="sxs-lookup"><span data-stu-id="26d90-107">And this example replaces any removed messages with the note that the message is no longer available:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

<span data-ttu-id="26d90-108">Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) .</span><span class="sxs-lookup"><span data-stu-id="26d90-108">For more information, see the help topic for the [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

