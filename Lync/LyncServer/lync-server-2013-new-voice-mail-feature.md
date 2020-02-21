---
title: 'Lync Server 2013: nueva característica de correo de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New voice mail feature
ms:assetid: 84d13238-67ef-42cc-801a-2d8147ba3b7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688117(v=OCS.15)
ms:contentKeyID: 49733715
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f82c1994f49d6284d26e7677ab7f940f88fab9ac
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-voice-mail-feature-in-lync-server-2013"></a><span data-ttu-id="6c3b9-102">Nueva característica de correo de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c3b9-102">New voice mail feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c3b9-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="6c3b9-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="6c3b9-104">Lync Server 2013 introduce el escape de correo de voz, una mejora para administrar el correo de voz.</span><span class="sxs-lookup"><span data-stu-id="6c3b9-104">Lync Server 2013 introduces Voice mail Escape, an enhancement for managing voice mail.</span></span> <span data-ttu-id="6c3b9-105">Esta nueva característica puede detectar cuando se enruta una llamada al correo de voz y evitar que la llamada se enrute inmediatamente al correo de voz del teléfono móvil del usuario sin ofrecer al usuario la oportunidad de responder la llamada.</span><span class="sxs-lookup"><span data-stu-id="6c3b9-105">This new feature can detect when a call has been routed to voice mail, and prevent the call from being immediately routed to the user’s mobile phone voice mail without giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="6c3b9-106">Este escenario se produce cuando el usuario habilita las llamadas simultáneas en su dispositivo móvil y el teléfono móvil está apagado, no tiene batería o está fuera de intervalo.</span><span class="sxs-lookup"><span data-stu-id="6c3b9-106">This scenario occurs when the user enables simultaneous ringing to their mobile phone, and their mobile phone is turned off, out of battery, or out of range.</span></span> <span data-ttu-id="6c3b9-107">Voicemail Escape detecta que la llamada fue contestada inmediatamente por el correo de voz el usuario y desconecta la llamada del correo de voz del teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="6c3b9-107">Voicemail Escape detects that the call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="6c3b9-108">La llamada continúa sonando en el extremo del usuario, ofreciéndole al usuario la oportunidad de responder la llamada.</span><span class="sxs-lookup"><span data-stu-id="6c3b9-108">The call continues to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="6c3b9-109">Si el usuario no responde la llamada, esta llamada se enrutará al correo de voz corporativo.</span><span class="sxs-lookup"><span data-stu-id="6c3b9-109">If the user does not answer the call, then the call is routed to the corporate voice mail.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6c3b9-110">Consulta también</span><span class="sxs-lookup"><span data-stu-id="6c3b9-110">See Also</span></span>


[<span data-ttu-id="6c3b9-111">Configurar el escape de correo de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c3b9-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="6c3b9-112">Nuevas características de Enterprise Voice en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c3b9-112">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

