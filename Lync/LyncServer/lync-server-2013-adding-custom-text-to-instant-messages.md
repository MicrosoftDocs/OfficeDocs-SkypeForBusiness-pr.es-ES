---
title: 'Lync Server 2013: Agregar texto personalizado a los mensajes instantáneos'
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
ms.openlocfilehash: b54b4724568a4f57bebc7ef6162a553cfdd9a091
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a><span data-ttu-id="32f75-102">Agregar texto personalizado a los mensajes instantáneos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32f75-102">Adding custom text to instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32f75-103">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="32f75-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="32f75-104">Agregue una declinación de responsabilidades o advertencia al principio de cada conversación de mensajería instantánea (mi) de Lync 2013 usando los cmdlets de la consola de administración de Lync Server **New-ClientPolicy** o **set-ClientPolicy** .</span><span class="sxs-lookup"><span data-stu-id="32f75-104">Add a disclaimer or warning to the beginning of every Lync 2013 instant messaging (IM) conversation by using the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the IMWarning parameter.</span></span>

<span data-ttu-id="32f75-105">El comando del ejemplo siguiente agrega un aviso de seguridad en la parte superior de la ventana de conversación cuando comienza una nueva conversación de mensajería instantánea:</span><span class="sxs-lookup"><span data-stu-id="32f75-105">The command in the following example adds a security reminder at the top of the Conversation window whenever a new IM conversation begins:</span></span>

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

<span data-ttu-id="32f75-106">Use **Grant-ClientPolicy** para asignar esta nueva Directiva a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="32f75-106">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="32f75-107">Para obtener más información, vea **New-ClientPolicy** y **Grant-ClientPolicy** en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="32f75-107">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

