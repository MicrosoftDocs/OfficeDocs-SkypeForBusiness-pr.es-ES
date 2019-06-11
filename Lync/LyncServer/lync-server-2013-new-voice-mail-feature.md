---
title: 'Lync Server 2013: Característica nueva de correo de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New voice mail feature
ms:assetid: 84d13238-67ef-42cc-801a-2d8147ba3b7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688117(v=OCS.15)
ms:contentKeyID: 49733715
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40db78aa126521ddce496721681ceb322f72beda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-voice-mail-feature-in-lync-server-2013"></a><span data-ttu-id="a4aa8-102">Característica nueva de correo de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4aa8-102">New voice mail feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4aa8-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="a4aa8-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="a4aa8-104">Lync Server 2013 incluye escape de correo de voz, una mejora para administrar el correo de voz.</span><span class="sxs-lookup"><span data-stu-id="a4aa8-104">Lync Server 2013 introduces Voice mail Escape, an enhancement for managing voice mail.</span></span> <span data-ttu-id="a4aa8-105">Esta nueva característica puede detectar cuándo se ha enrutado la llamada al correo de voz y evitar que la llamada se enrute al correo de voz del teléfono móvil del usuario sin dar al usuario la oportunidad de contestar la llamada.</span><span class="sxs-lookup"><span data-stu-id="a4aa8-105">This new feature can detect when a call has been routed to voice mail, and prevent the call from being immediately routed to the user’s mobile phone voice mail without giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="a4aa8-106">Este escenario se produce cuando el usuario habilita llamadas simultáneas a su teléfono móvil y su teléfono móvil está apagado, agotada la batería o fuera de intervalo.</span><span class="sxs-lookup"><span data-stu-id="a4aa8-106">This scenario occurs when the user enables simultaneous ringing to their mobile phone, and their mobile phone is turned off, out of battery, or out of range.</span></span> <span data-ttu-id="a4aa8-107">El buzón de voz ESC detecta que la llamada fue respondida inmediatamente por el correo de voz del teléfono móvil del usuario y desconecta la llamada al correo de voz del teléfono móvil.</span><span class="sxs-lookup"><span data-stu-id="a4aa8-107">Voicemail Escape detects that the call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="a4aa8-108">La llamada continúa sonando en los otros puntos de conexión del usuario, lo que ofrece al usuario la oportunidad de contestar la llamada.</span><span class="sxs-lookup"><span data-stu-id="a4aa8-108">The call continues to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="a4aa8-109">Si el usuario no responde a la llamada, la llamada se dirige al correo de voz de la empresa.</span><span class="sxs-lookup"><span data-stu-id="a4aa8-109">If the user does not answer the call, then the call is routed to the corporate voice mail.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a4aa8-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4aa8-110">See Also</span></span>


[<span data-ttu-id="a4aa8-111">Configurar el escape del correo de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4aa8-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="a4aa8-112">Nuevas características de la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4aa8-112">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

