---
title: 'Lync Server 2013: validar la configuración de Office Web Apps Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35844ae2ae73937d6840e480dc57393b91d13eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="870af-102">Validar la configuración de Office Web Apps Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="870af-102">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="870af-103">_**Última modificación del tema:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="870af-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="870af-104">Después de agregar Office Web Apps Server a la topología y después de que se haya publicado la topología, debe ver dos nuevos eventos de registro de eventos en el registro de eventos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="870af-104">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="870af-105">En primer lugar, se debe agregar un evento LS Data MCU (identificador de evento 41034). Este evento notificará que se ha descubierto el servidor de Office Web Apps:</span><span class="sxs-lookup"><span data-stu-id="870af-105">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="870af-106">**Se ha detectado el servidor de conferencia web Office Web Apps Server, se ha habilitado el contenido de PowerPoint.**</span><span class="sxs-lookup"><span data-stu-id="870af-106">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="870af-p102">Además, debe ver otro evento LS Data MCU (Id. de evento 41032) que informa sobre las direcciones URL de Office Web Apps Server. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="870af-p102">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>

<span data-ttu-id="870af-109">**Se ha detectado correctamente el servidor de conferencia web de Office Web Apps Server.**</span><span class="sxs-lookup"><span data-stu-id="870af-109">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="870af-110">**Página del moderador interno de Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="870af-110">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="870af-111">**Página de asistente interno de Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="870af-111">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="870af-112">**Página de moderador externo de Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="870af-112">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="870af-113">**Página de asistente interno de Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="870af-113">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="870af-114">Si ve un evento LS Data MCU con el identificador de evento de 41033, significa que se ha producido un error en la detección de Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="870af-114">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="870af-115">En ese caso, Microsoft Lync Server 2013 probará tantas veces como sea necesario para descubrir el servidor de Office Web Apps recién configurado.</span><span class="sxs-lookup"><span data-stu-id="870af-115">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="870af-116">Si el proceso de detección falla varias veces, debería quitar Office Web Apps Server del documento de topología, publicar la topología actualizada y, a continuación, intentar volver a agregar Office Web Apps Server a la topología después de haber resuelto los problemas de conectividad.</span><span class="sxs-lookup"><span data-stu-id="870af-116">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="870af-117">Si el servidor de Office Web Apps parece estar configurado correctamente y ha sido reconocido por el proceso de detección, puede comprobar que Office Web Apps Server funciona como se espera compartiendo una presentación de PowerPoint entre un par de clientes de Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="870af-117">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="870af-118">Si el usuario A puede cargar y mostrar la presentación de PowerPoint y si el usuario B se puede unir a la reunión y ver la presentación, Office Web Apps Server está funcionando.</span><span class="sxs-lookup"><span data-stu-id="870af-118">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="870af-119">Incluso si Office Web Apps Server parece estar configurado correctamente, es posible que reciba el mensaje de error "algunas características de uso compartido no están disponibles debido a problemas de Conectividad del servidor" al intentar compartir una presentación de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="870af-119">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="870af-120">Si recibe este mensaje de error, debe reiniciar el servidor front-end (o servidores) asociado con el nuevo servidor de Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="870af-120">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

