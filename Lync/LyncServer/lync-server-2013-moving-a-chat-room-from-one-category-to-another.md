---
title: 'Lync Server 2013: mover un salón de chat de una categoría a otra'
description: 'Lync Server 2013: mover un salón de chat de una categoría a otra.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4066732a90a94414b55d6a567fde0d496e4faf13
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542006"
---
# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a>Mover un salón de chat de una categoría a otra en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Le recomendamos que no cambie la categoría de un salón de chat persistente una vez que se haya creado el salón de chat. Sin embargo, si el administrador del salón de chat tiene privilegios de **Creador** en otra categoría, puede mover el salón de una categoría a otra. El salón no se eliminará y volverá a crearse. Es un cambio de asociación dentro de la base de datos.

Ocasionalmente podrá realizarse un cambio de categoría del salón de chat. Una categoría determina la pertenencia permitida para el salón de chat, por lo tanto, cuando un salón de chat se mueve a otra categoría, se eliminan todas las listas de control de acceso del sistema (SACL) que ya no son compatibles con la nueva categoría. Por ejemplo, si un usuario era miembro del salón y ya no es un **AllowedMember** en la nueva categoría, la pertenencia del salón se modificará y el usuario se eliminará de el.

Para obtener información detallada sobre cómo mover un salón de chat mediante la interfaz de línea de comandos de Windows PowerShell, consulte "administración de salones" en [Configuring persistent chat Server by Using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Para obtener más información sobre cómo configurar salones de chat, vea [Configure Rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) en la documentación sobre implementación.

</div>

<span> </span>

</div>

</div>

</div>

