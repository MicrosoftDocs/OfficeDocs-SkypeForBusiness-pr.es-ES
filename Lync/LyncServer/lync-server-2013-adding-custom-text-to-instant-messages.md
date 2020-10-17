---
title: 'Lync Server 2013: agregar texto personalizado a los mensajes instantáneos'
description: 'Lync Server 2013: agregar texto personalizado a los mensajes instantáneos.'
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
ms.openlocfilehash: 54f5cf031da0ba4d5bd0b6dbaa7f5ebc9d0b3a6c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569346"
---
# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a><span data-ttu-id="49284-103">Agregar texto personalizado a los mensajes instantáneos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49284-103">Adding custom text to instant messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49284-104">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="49284-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="49284-105">Agregue una declinación de responsabilidades o una advertencia al principio de cada conversación de mensajería instantánea (mi) de Lync 2013 usando los cmdlets de la consola de administración de Lync Server **New-CSClientPolicy** o **set-CSClientPolicy** con el parámetro imwarning.</span><span class="sxs-lookup"><span data-stu-id="49284-105">Add a disclaimer or warning to the beginning of every Lync 2013 instant messaging (IM) conversation by using the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the IMWarning parameter.</span></span>

<span data-ttu-id="49284-106">El comando del siguiente ejemplo agrega un recordatorio de seguridad en la parte superior de la ventana de conversación siempre que se inicia una nueva conversación de mensajería instantánea:</span><span class="sxs-lookup"><span data-stu-id="49284-106">The command in the following example adds a security reminder at the top of the Conversation window whenever a new IM conversation begins:</span></span>

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

<span data-ttu-id="49284-107">Use **Grant-CSClientPolicy** para asignar esta nueva directiva a usuarios.</span><span class="sxs-lookup"><span data-stu-id="49284-107">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="49284-108">Para obtener más información, consulte **New-CSClientPolicy** y **Grant-CSClientPolicy** en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49284-108">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

