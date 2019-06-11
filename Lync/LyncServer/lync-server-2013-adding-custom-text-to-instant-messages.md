---
title: 'Lync Server 2013: Agregar texto personalizado a los mensajes instantáneos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb6746ea5897d779a202bc428b6c7259a1191f6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a>Agregar texto personalizado a los mensajes instantáneos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-20_

Agregue una declinación de responsabilidades o advertencia al principio de cada conversación de mensajería instantánea (mi) de Lync 2013 usando los cmdlets de la consola de administración de Lync Server **New-ClientPolicy** o **set-ClientPolicy** .

El comando del ejemplo siguiente agrega un aviso de seguridad en la parte superior de la ventana de conversación cuando comienza una nueva conversación de mensajería instantánea:

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

Use **Grant-ClientPolicy** para asignar esta nueva Directiva a los usuarios. Para obtener más información, vea **New-ClientPolicy** y **Grant-ClientPolicy** en la documentación del shell de administración de Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

