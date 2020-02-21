---
title: 'Lync Server 2013: usar Call me en con un teléfono habilitado para Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 157ce646e606f6327e6d7a5fd1957da1480797e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a><span data-ttu-id="0ac42-102">Usar la llamada me en con un teléfono habilitado para Lync y Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ac42-102">Using Call Me At with a Lync-enabled phone and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ac42-103">_**Última modificación del tema:** 2013-08-09_</span><span class="sxs-lookup"><span data-stu-id="0ac42-103">_**Topic Last Modified:** 2013-08-09_</span></span>

<span data-ttu-id="0ac42-104">La característica llamarme a en Lync permite a los usuarios unirse a la parte de audio de una conferencia mediante un teléfono móvil, "Land Line" u otro dispositivo conectado a la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="0ac42-104">The Call Me At feature in Lync provides a way for users to join the audio portion of a conference by using a cell phone, “land line,” or other device connected to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="0ac42-105">Al intentar unirse a una reunión con Lync, normalmente se le presentará el cuadro de diálogo **unirse al audio** de la reunión:</span><span class="sxs-lookup"><span data-stu-id="0ac42-105">When you attempt to join a meeting by using Lync, you will typically be presented with the **Join Meeting Audio** dialog box:</span></span>

<span data-ttu-id="0ac42-106">![Pantalla de uso de Lync para unirse a la reunión de audio](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Pantalla de uso de Lync para unirse a la reunión de audio")</span><span class="sxs-lookup"><span data-stu-id="0ac42-106">![Use Lync to join meeting audio window screenshot](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Use Lync to join meeting audio window screenshot")</span></span>

<span data-ttu-id="0ac42-107">Si selecciona **llamarme al**, puede elegir un número de teléfono en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0ac42-107">If you select **Call me at**, you can then pick a phone number from the dropdown list.</span></span> <span data-ttu-id="0ac42-108">Lync Server 2013 realizará una llamada telefónica al número seleccionado y podrá usar ese teléfono para participar en la parte de audio de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="0ac42-108">Lync Server 2013 will place a phone call to the selected number, and you can then use that phone to participate in the audio portion of the conference.</span></span>

<span data-ttu-id="0ac42-109">La lista desplegable se rellena con los números de teléfono (para teléfonos móviles, teléfonos domésticos u otros teléfonos) que escribió en la pestaña **teléfonos** del cuadro de diálogo **Lync – opciones** :</span><span class="sxs-lookup"><span data-stu-id="0ac42-109">The dropdown list is populated by the phone numbers (for mobile phone, home phone, or other phone) that you have entered on the **Phones** tab in the **Lync – Options** dialog box:</span></span>

<span data-ttu-id="0ac42-110">![Captura de pantalla de opciones de configuración de teléfonos de Lync](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Captura de pantalla de opciones de configuración de teléfonos de Lync")</span><span class="sxs-lookup"><span data-stu-id="0ac42-110">![Lync Phones set up options screenshot](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync Phones set up options screenshot")</span></span>

<span data-ttu-id="0ac42-111">Si no ha especificado ningún número de teléfono en la pestaña **teléfonos** , no tendrá ningún número disponible en el cuadro desplegable.</span><span class="sxs-lookup"><span data-stu-id="0ac42-111">If you have not entered any phone numbers on the **Phones** tab then you will not have any numbers available in the dropdown box.</span></span> <span data-ttu-id="0ac42-112">Sin embargo, siempre puede hacer clic en **nuevo número** y hacer que Lync Server llame a cualquier número de teléfono que quiera:</span><span class="sxs-lookup"><span data-stu-id="0ac42-112">However, you can always click **New Number** and have Lync Server dial out to any phone number you wish:</span></span>

<span data-ttu-id="0ac42-113">![Captura de pantalla de llamada de audio de reunión de Lync unirse](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Captura de pantalla de llamada de audio de reunión de Lync unirse")</span><span class="sxs-lookup"><span data-stu-id="0ac42-113">![Lync join meeting audio call me window screenshot](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync join meeting audio call me window screenshot")</span></span>

<span data-ttu-id="0ac42-114">La característica llamarme cuando funciona muy bien, siempre que la use como estaba previsto: haciendo que Lync Server llame a un número de teléfono RTC.</span><span class="sxs-lookup"><span data-stu-id="0ac42-114">The Call Me At feature works extremely well provided that you use it in the way it was intended: by having Lync Server call a PSTN phone number.</span></span> <span data-ttu-id="0ac42-115">Sin embargo, puede tener una experiencia menor que-óptima si solicita a Lync Server que le llame en un punto de conexión habilitado para Lync (por ejemplo, un teléfono en una sala de conferencias).</span><span class="sxs-lookup"><span data-stu-id="0ac42-115">However, you can run into a less-than-optimal experience if you ask Lync Server to call you at a Lync-enabled endpoint (for example, a phone in a conference room).</span></span> <span data-ttu-id="0ac42-116">A continuación se indica el problema en el que se puede ejecutar, así como dos maneras de solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="0ac42-116">Following is the issue you might run into, as well as two ways to work around the problem.</span></span>

<span data-ttu-id="0ac42-117">Para empezar, esto es lo que sucede cuando se proporciona la característica llamarme al con el número de teléfono de un teléfono habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="0ac42-117">To begin, here’s what happens when you provide the Call Me At feature with the phone number of a Lync-enabled phone.</span></span> <span data-ttu-id="0ac42-118">Supongamos que Ken Myer intenta unirse a una reunión haciendo que Lync Server le llame al 1-206-555-1219, un número de teléfono habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0ac42-118">Suppose Ken Myer tries to join a meeting by having Lync Server call him at 1-206-555-1219, a Lync Server-enabled phone number.</span></span> <span data-ttu-id="0ac42-119">Ken se conectará inicialmente a la reunión, pero después de unos segundos Lync mostrará que la llamada al mensaje **no se completó o ha finalizado**, y parece que Ken se ha quitado de la reunión:</span><span class="sxs-lookup"><span data-stu-id="0ac42-119">Ken will initially be connected to the meeting, but after a few seconds Lync will display the message **Call was not completed or has ended**, and Ken will appear to have been dropped from the meeting:</span></span>

<span data-ttu-id="0ac42-120">![Captura de pantalla de la ventana de conferencia de llamadas de Lync](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Captura de pantalla de la ventana de conferencia de llamadas de Lync")</span><span class="sxs-lookup"><span data-stu-id="0ac42-120">![Screen shot of Lync call conferencing window](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Screen shot of Lync call conferencing window")</span></span>

<span data-ttu-id="0ac42-121">Sin embargo, tenga en cuenta que hay una discrepancia dentro de la ventana de conversación de Lync.</span><span class="sxs-lookup"><span data-stu-id="0ac42-121">Notice, however, that there is a discrepancy within the Lync conversation window.</span></span> <span data-ttu-id="0ac42-122">Ken Myer es el único nombre que aparece en el encabezado de los **participantes** .</span><span class="sxs-lookup"><span data-stu-id="0ac42-122">Ken Myer is the only name listed under the **Participants** heading.</span></span> <span data-ttu-id="0ac42-123">Sin embargo, si mira en la barra de título de la ventana, verá que la Conferencia contiene un total de 4 participantes.</span><span class="sxs-lookup"><span data-stu-id="0ac42-123">However, if you look in the title bar of the window, you’ll see that the conference contains a total of 4 participants.</span></span>

<span data-ttu-id="0ac42-124">Del mismo modo, si mira en la ventana de conversación de cualquiera de los otros participantes de la Conferencia, no verá Ken Myer enumerado en cualquier lugar:</span><span class="sxs-lookup"><span data-stu-id="0ac42-124">Likewise, if you look in the conversation window of any of the other conference participants you will not see Ken Myer listed anywhere:</span></span>

<span data-ttu-id="0ac42-125">![Captura de pantalla de la ventana Lista de participantes de Lync](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Captura de pantalla de la ventana Lista de participantes de Lync")</span><span class="sxs-lookup"><span data-stu-id="0ac42-125">![Lync participant list window screenshot](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync participant list window screenshot")</span></span>

<span data-ttu-id="0ac42-126">Y, sin embargo, al mismo tiempo, Ken Myer podrá participar en la parte de audio de la llamada mediante su teléfono habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="0ac42-126">And yet, at the same time, Ken Myer will be able to participate in the audio portion of the call by using his Lync-enabled phone.</span></span> <span data-ttu-id="0ac42-127">La característica llamarme a en ha trabajado realmente, pero la experiencia del usuario es inferior a la óptima.</span><span class="sxs-lookup"><span data-stu-id="0ac42-127">The Call Me At feature has actually worked, but the user experience is less than optimal.</span></span>

<span data-ttu-id="0ac42-128">Hay al menos dos maneras de solucionar este problema.</span><span class="sxs-lookup"><span data-stu-id="0ac42-128">There are at least two ways to work around this problem.</span></span> <span data-ttu-id="0ac42-129">Si ya se ha unido a una conferencia de este modo (como Ken Myer funcionó), normalmente puede resolver el problema realizando una modalidad diferente.</span><span class="sxs-lookup"><span data-stu-id="0ac42-129">If you have already joined a conference in this fashion (like Ken Myer did), you can typically resolve the issue by engaging in a different modality.</span></span> <span data-ttu-id="0ac42-130">Por ejemplo, si envía un mensaje instantáneo, ahora la ventana conversación mostrará todos los participantes de la Conferencia, incluidos usted:</span><span class="sxs-lookup"><span data-stu-id="0ac42-130">For example, if you send an instant message the conversation window will now show all the conference participants, including yourself:</span></span>

<span data-ttu-id="0ac42-131">![Captura de pantalla de conversación y lista de participantes de Lync](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Captura de pantalla de conversación y lista de participantes de Lync")</span><span class="sxs-lookup"><span data-stu-id="0ac42-131">![Lync conversation and participant list screenshot](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync conversation and participant list screenshot")</span></span>

<span data-ttu-id="0ac42-132">En este momento, podrá participar en la reunión de la manera prevista.</span><span class="sxs-lookup"><span data-stu-id="0ac42-132">At this point you should be able to participate in the meeting in the expected fashion.</span></span>

<span data-ttu-id="0ac42-133">Como alternativa, puede evitar todo este problema cambiando la forma de unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="0ac42-133">Alternatively, you can avoid this issue altogether by changing the way you join the meeting.</span></span> <span data-ttu-id="0ac42-134">Si necesita que Lync Server llame a un teléfono habilitado para Lync Server, debe empezar a unirse a la reunión sin una conexión de audio.</span><span class="sxs-lookup"><span data-stu-id="0ac42-134">If you need to have Lync Server call a Lync Server-enabled phone, you should begin by joining the meeting without an audio connection.</span></span> <span data-ttu-id="0ac42-135">Para ello, seleccione no unirse al audio cuando aparezca el cuadro de diálogo unirse al audio de la reunión:</span><span class="sxs-lookup"><span data-stu-id="0ac42-135">To do that, select Don’t join audio when presented with the Join Meeting Audio dialog box:</span></span>

<span data-ttu-id="0ac42-136">![Pantalla de Lync no unirse a la ventana audio de la reunión](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Pantalla de Lync no unirse a la ventana audio de la reunión")</span><span class="sxs-lookup"><span data-stu-id="0ac42-136">![Lync don't join meeting audio window screenshot](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync don't join meeting audio window screenshot")</span></span>

<span data-ttu-id="0ac42-137">Una vez que se haya conectado correctamente a la reunión, ahora puede "invitar" al teléfono habilitado para Lync Server a unirse también a la reunión.</span><span class="sxs-lookup"><span data-stu-id="0ac42-137">After you have successfully connected to the meeting, you can now “invite” the Lync Server-enabled phone to join the meeting as well.</span></span> <span data-ttu-id="0ac42-138">Para ello, ponga el mouse sobre el icono contactos y, a continuación, haga clic en **invitar a más personas**:</span><span class="sxs-lookup"><span data-stu-id="0ac42-138">To do that, place the mouse over the People icon and then click **Invite More People**:</span></span>

<span data-ttu-id="0ac42-139">![Captura de pantalla de la ventana invita más participantes en Lync](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Captura de pantalla de la ventana invita más participantes en Lync")</span><span class="sxs-lookup"><span data-stu-id="0ac42-139">![Lync invite more participants window screenshot](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync invite more participants window screenshot")</span></span>

<span data-ttu-id="0ac42-140">Se abrirá el cuadro de diálogo **Enviar un mensaje instantáneo** .</span><span class="sxs-lookup"><span data-stu-id="0ac42-140">That will bring up the **Send an IM** dialog box.</span></span> <span data-ttu-id="0ac42-141">Ignore el título del cuadro de diálogo (en realidad, no está enviando un mensaje instantáneo) y escriba el número de teléfono del teléfono habilitado para Lync:</span><span class="sxs-lookup"><span data-stu-id="0ac42-141">Ignore the dialog box title (you’re not actually sending an instant message) and type the phone number of the Lync-enabled phone:</span></span>

<span data-ttu-id="0ac42-142">![Captura de pantalla del cuadro de diálogo enviar mi](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Captura de pantalla del cuadro de diálogo enviar mi")</span><span class="sxs-lookup"><span data-stu-id="0ac42-142">![Send an IM dialog box screenshot](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Send an IM dialog box screenshot")</span></span>

<span data-ttu-id="0ac42-143">Después de hacer clic en **Aceptar**, Lync Server llamará al número escrito en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0ac42-143">After you click **OK**, Lync Server will call the number entered in the dialog box.</span></span> <span data-ttu-id="0ac42-144">Una vez realizada la conexión, dispondrá de capacidades de audio completas a través del teléfono habilitado para Lync y podrá ver e interactuar con la lista de conferencias completa.</span><span class="sxs-lookup"><span data-stu-id="0ac42-144">When the connection is made, you will have full audio capabilities through the Lync-enabled phone, and you will be able to see and interact with the full conference roster.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

