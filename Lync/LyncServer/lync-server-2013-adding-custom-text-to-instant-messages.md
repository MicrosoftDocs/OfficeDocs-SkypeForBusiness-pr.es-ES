---
title: 'Lync Server 2013: agregar texto personalizado a los mensajes instantáneos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 466eac15cf75728578e7d517d15ddb222d1c4b70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521367"
---
# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a>Agregar texto personalizado a los mensajes instantáneos en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Agregue una declinación de responsabilidades o una advertencia al principio de cada conversación de mensajería instantánea (mi) de Lync 2013 usando los cmdlets de la consola de administración de Lync Server **New-CSClientPolicy** o **set-CSClientPolicy** con el parámetro imwarning.

El comando del siguiente ejemplo agrega un recordatorio de seguridad en la parte superior de la ventana de conversación siempre que se inicia una nueva conversación de mensajería instantánea:

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

Use **Grant-CSClientPolicy** para asignar esta nueva directiva a usuarios. Para obtener más información, consulte **New-CSClientPolicy** y **Grant-CSClientPolicy** en la documentación del shell de administración de Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

