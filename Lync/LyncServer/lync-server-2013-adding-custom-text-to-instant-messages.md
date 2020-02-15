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
ms.openlocfilehash: 0681df9803615fee04c20e52258120bd6616e57d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a><span data-ttu-id="fbfdd-102">Agregar texto personalizado a los mensajes instantáneos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbfdd-102">Adding custom text to instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbfdd-103">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="fbfdd-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="fbfdd-104">Agregue una declinación de responsabilidades o una advertencia al principio de cada conversación de mensajería instantánea (mi) de Lync 2013 usando los cmdlets de la consola de administración de Lync Server **New-CSClientPolicy** o **set-CSClientPolicy** con el parámetro imwarning.</span><span class="sxs-lookup"><span data-stu-id="fbfdd-104">Add a disclaimer or warning to the beginning of every Lync 2013 instant messaging (IM) conversation by using the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the IMWarning parameter.</span></span>

<span data-ttu-id="fbfdd-105">El comando del siguiente ejemplo agrega un recordatorio de seguridad en la parte superior de la ventana de conversación siempre que se inicia una nueva conversación de mensajería instantánea:</span><span class="sxs-lookup"><span data-stu-id="fbfdd-105">The command in the following example adds a security reminder at the top of the Conversation window whenever a new IM conversation begins:</span></span>

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

<span data-ttu-id="fbfdd-106">Use **Grant-CSClientPolicy** para asignar esta nueva directiva a usuarios.</span><span class="sxs-lookup"><span data-stu-id="fbfdd-106">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="fbfdd-107">Para obtener más información, consulte **New-CSClientPolicy** y **Grant-CSClientPolicy** en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fbfdd-107">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

