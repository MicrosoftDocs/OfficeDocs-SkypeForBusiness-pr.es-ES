---
title: 'Lync Server 2013: configurar el escape de correo de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cad247f2643261e02e475c459e703db843f18fbe
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a><span data-ttu-id="ce36f-102">Configurar el escape de correo de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce36f-102">Configuring voice mail escape in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce36f-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="ce36f-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="ce36f-104">Cuando un usuario configura llamadas simultáneas a un teléfono móvil, normalmente se enrutará al autor de la llamada al buzón de voz personal del usuario si el teléfono móvil está apagado, fuera de cobertura o se ha quedado sin batería.</span><span class="sxs-lookup"><span data-stu-id="ce36f-104">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user’s personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="ce36f-105">Con Lync Server 2013, los usuarios pueden optar por hacer que las llamadas relacionadas con la empresa se enruten a su sistema de correo de voz corporativo.</span><span class="sxs-lookup"><span data-stu-id="ce36f-105">With Lync Server 2013, users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="ce36f-106">En concreto, se puede configurar un temporizador y, si la llamada se responde por el correo de voz del transportista dentro del intervalo de tiempo definido, Lync Server se desconectará del sistema de correo de voz del operador (y del correo de voz personal del usuario), mientras que el resto del usuario los puntos de conexión del sistema corporativo continúan sonando.</span><span class="sxs-lookup"><span data-stu-id="ce36f-106">Specifically, a timer can be configured, and if the call is answered by the carrier’s voice mail within the range of time defined, Lync Server will disconnect from the carrier’s voice mail system (and the user’s personal voice mail), while the user’s remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="ce36f-107">De esta manera, se enrutará automáticamente al autor de la llamada al buzón de voz corporativo del usuario.</span><span class="sxs-lookup"><span data-stu-id="ce36f-107">This way, the caller is automatically routed to the user’s corporate voice mail.</span></span>

<span data-ttu-id="ce36f-108">Esta configuración se lleva a cabo mediante el cmdlet del shell de administración de Lync Server, **set-CsVoicePolicy**, en el nivel de la Directiva de voz, con los siguientes parámetros.</span><span class="sxs-lookup"><span data-stu-id="ce36f-108">This configuration is performed using the Lync Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

<div>

## <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="ce36f-109">Para configurar el escape de correo de voz</span><span class="sxs-lookup"><span data-stu-id="ce36f-109">To configure voice mail escape</span></span>

1.  <span data-ttu-id="ce36f-110">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ce36f-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ce36f-111">Especificar los siguientes parámetros en **Set-CsVoicePolicy**:</span><span class="sxs-lookup"><span data-stu-id="ce36f-111">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>
    
      - <span data-ttu-id="ce36f-112">**EnableVoicemailEscapeTimer**: habilita o deshabilita el temporizador de escape.</span><span class="sxs-lookup"><span data-stu-id="ce36f-112">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>
    
      - <span data-ttu-id="ce36f-p102">**PSTNVoicemailEscapeTimer**: especifica el valor de tiempo de espera en milisegundos. El valor predeterminado es 1500 milisegundos y puede variar de 0 a 8000 milisegundos.</span><span class="sxs-lookup"><span data-stu-id="ce36f-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="ce36f-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce36f-115">Example</span></span>

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ce36f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce36f-116">See Also</span></span>


[<span data-ttu-id="ce36f-117">Configurar directivas de voz y registros de uso de RTC para autorizar características y privilegios de llamada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce36f-117">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

