---
title: 'Lync Server 2013: Eliminar un salón de chat o una categoría'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f64b89abd0b3266d2be52e300458ceabf3f9b915
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a>Eliminar un salón de chat o una categoría en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Se pueden eliminar los salones de chat persistentes. Si tiene un salón de chat que ya no se usa, puede deshabilitarlo. Para obtener más información, vea [deshabilitar o habilitar un salón de chat en Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).

Un administrador de chat persistente puede consultar salones de chat desactivados y, de forma periódica, purgar y eliminar de forma permanente los salones de chat, mediante el cmdlet de Windows PowerShell, **Remove-CsPersistentChatRoom**.

Las categorías se pueden eliminar. Sin embargo, para eliminar una categoría, primero debes eliminar todos los salones de chat que haya debajo o mover los salones de chat a una nueva categoría, dejando una categoría vacía para eliminarla. El servidor de chat persistente no le permite eliminar una categoría que contiene salones de chat. Para obtener más información, vea [mover un salón de chat de una categoría a otra en Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).

Para obtener detalles acerca de cómo eliminar categorías vacías mediante la interfaz de línea de comandos de Windows PowerShell, consulte "administración de salas" en [configurar el servidor de chat persistente mediante cmdlets de Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Para obtener más información sobre los salones de chat y las categorías, consulte [configurar salas en Lync server 2013](lync-server-2013-configure-rooms.md) y [configurar categorías en Lync Server 2013](lync-server-2013-configure-categories.md) en la documentación de implementación.

</div>

<span> </span>

</div>

</div>

</div>

