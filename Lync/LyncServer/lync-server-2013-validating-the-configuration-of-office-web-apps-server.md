---
title: 'Lync Server 2013: validar la configuración de Office Web Apps Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 068c3fcfd33668918eb330b64d816ceca818de27
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="3830e-102">Validación de la configuración de Office Web Apps Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3830e-102">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3830e-103">_**Última modificación del tema:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="3830e-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="3830e-104">Después de que se haya agregado Office Web Apps Server a la topología y después de que se haya publicado la topología, verá dos nuevos eventos de registro de eventos en el registro de eventos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3830e-104">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="3830e-105">En primer lugar, se debe agregar un evento LS Data MCU (identificador de evento 41034); Este evento informará de que se ha descubierto el servidor de Office Web Apps:</span><span class="sxs-lookup"><span data-stu-id="3830e-105">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="3830e-106">**Se ha descubierto el servidor de conferencia Web de Office Web Apps Server, se ha habilitado el contenido de PowerPoint.**</span><span class="sxs-lookup"><span data-stu-id="3830e-106">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="3830e-p102">Además, debe ver otro evento LS Data MCU (Id. de evento 41032) que informa sobre las direcciones URL de Office Web Apps Server. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3830e-p102">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>

<span data-ttu-id="3830e-109">**Servidor de conferencia web la detección del servidor de Office Web Apps se ha realizado correctamente.**</span><span class="sxs-lookup"><span data-stu-id="3830e-109">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="3830e-110">**Página de moderadores internos de Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="3830e-110">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="3830e-111">**Página de asistentes internos de Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="3830e-111">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="3830e-112">**Página de moderadores externos de Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="3830e-112">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="3830e-113">**Página de asistentes internos de Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="3830e-113">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="3830e-114">Si ve un evento LS Data MCU con el Id. de evento 41033, indicará un error en la detección de Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="3830e-114">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="3830e-115">En ese caso, Microsoft Lync Server 2013 probará tantas veces como sea necesario para descubrir el servidor de Office Web Apps recién configurado.</span><span class="sxs-lookup"><span data-stu-id="3830e-115">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="3830e-116">Si el proceso de detección falla repetidas veces, deberá quitar Office Web Apps Server del documento de la topología, publicar la topología actualizada y, a continuación, cuando los problemas de conectividad estén resueltos, agregar de nuevo Office Web Apps Server a la topología.</span><span class="sxs-lookup"><span data-stu-id="3830e-116">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="3830e-117">Si Office Web Apps Server parece estar configurado correctamente y el proceso de detección lo ha reconocido, puede comprobar que Office Web Apps Server funciona como se esperaba compartiendo una presentación de PowerPoint entre un par de clientes de Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3830e-117">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="3830e-118">Si el usuario A puede cargar y visualizar la presentación de PowerPoint y el usuario B puede unirse a la reunión y ver esa presentación, significa que Office Web Apps Server funciona.</span><span class="sxs-lookup"><span data-stu-id="3830e-118">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="3830e-p105">Aún cuando parezca que Office Web Apps Server está correctamente configurado, podría recibir el mensaje de error "Algunas características de uso compartido no están disponibles debido a problemas de conectividad del servidor” cuando intente compartir una presentación de PowerPoint.Si recibe ese mensaje de error, reinicie el servidor (o servidores) front-end asociado al nuevo servidor Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="3830e-p105">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation. If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

