---
title: 'Lync Server 2013: eliminar un salón de chat o una categoría'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e94068337747feee592ec25669e9d7b5fc10bc3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a>Eliminar un salón de chat o una categoría en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Se pueden eliminar los salones de chat persistente. Si tiene un salón de chat que ya no se usa, puede deshabilitarlo. Para obtener más información, consulte [deshabilitar o habilitar un salón de chat en Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).

Un administrador de chat persistente puede consultar los salones de chat deshabilitados y, de forma periódica, purgar y eliminar de forma permanente los salones de chat, mediante el cmdlet de Windows PowerShell, **Remove-CsPersistentChatRoom**.

Las categorías se pueden eliminar. Pero para eliminar una categoría, primero debe eliminar todos los salones de chat incluidos en ella o mover los salones de chat a una nueva categoría, y dejar esa categoría vacía para su eliminación. El servidor de chat persistente no permite eliminar una categoría que contiene salones de chat. Para obtener más información, consulte [mover un salón de chat de una categoría a otra en Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).

Para obtener información detallada sobre cómo eliminar categorías vacías mediante la interfaz de línea de comandos de Windows PowerShell, consulte "administración de salones" en [Configuring persistent chat Server by Using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Para obtener más información sobre las categorías y los salones de chat, vea [Configure Rooms in Lync server 2013](lync-server-2013-configure-rooms.md) y [Configure Categories in Lync Server 2013](lync-server-2013-configure-categories.md) en la documentación sobre implementación.

</div>

<span> </span>

</div>

</div>

</div>

