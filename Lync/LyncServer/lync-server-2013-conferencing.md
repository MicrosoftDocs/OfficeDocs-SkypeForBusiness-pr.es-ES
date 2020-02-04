---
title: Conferencias de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e92f14a9f23617c55f1c09abc4daf29b5849b3bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a><span data-ttu-id="805f6-102">Conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="805f6-102">Conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="805f6-103">_**Última modificación del tema:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="805f6-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="805f6-104">Con las conferencias unificadas en Lync Server 2013, los usuarios pueden colaborar, compartir información y coordinar sus esfuerzos en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="805f6-104">With unified conferencing in Lync Server 2013, users can collaborate, share information, and coordinate their efforts in real time.</span></span> <span data-ttu-id="805f6-105">Todos los usuarios pueden usar todo el alcance de la colaboración espontánea, las reuniones programadas y las herramientas de reunión.</span><span class="sxs-lookup"><span data-stu-id="805f6-105">All your users can use the full breadth of spontaneous collaboration, scheduled meetings, and meeting tools.</span></span> <span data-ttu-id="805f6-106">Las capacidades de voz y videoconferencias se pueden usar desde cualquier ubicación con una conexión a Internet, y los usuarios lejos de un equipo pueden participar en conferencias de audio al marcar con un teléfono de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="805f6-106">Voice and video conferencing capabilities can be used from any location with an Internet connection, and users away from a computer can participate in audio conferences by dialing in with a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="805f6-107">Herramientas de reunión integradas en Outlook permite a los organizadores programar una reunión o iniciar una conferencia improvisada con un solo clic, y también facilitar la participación de los asistentes.</span><span class="sxs-lookup"><span data-stu-id="805f6-107">Meeting tools integrated into Outlook enable organizers to schedule a meeting or start an impromptu conference with a single click, and also make it just as easy for attendees to join.</span></span> <span data-ttu-id="805f6-108">Un cliente web extiende características de conferencia enriquecidas a los participantes que no están ejecutando la versión de escritorio de Lync.</span><span class="sxs-lookup"><span data-stu-id="805f6-108">A web client extends rich conference features to participants who are not running the desktop version of Lync.</span></span>

<div>

## <a name="audio-and-video-conferencing"></a><span data-ttu-id="805f6-109">Conferencias de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="805f6-109">Audio and Video Conferencing</span></span>

<span data-ttu-id="805f6-110">Lync Server proporciona una experiencia de usuario que es familiar para los usuarios de los servicios de puente de audio tradicionales, incluidos los servicios de acceso telefónico PSTN con comandos de control de llamadas por tonos.</span><span class="sxs-lookup"><span data-stu-id="805f6-110">Lync Server provides a user experience that is familiar to users of traditional audio bridge services including PSTN dial-in services with touch-tone call control commands.</span></span> <span data-ttu-id="805f6-111">Al mismo tiempo, incorpora las eficaces características de programación, Unión y administración disponibles solamente con una plataforma de comunicaciones unificadas integrada.</span><span class="sxs-lookup"><span data-stu-id="805f6-111">At the same time, it incorporates powerful scheduling, joining, and management features available only with an integrated unified communications platform.</span></span>

<span data-ttu-id="805f6-112">Con un solo clic, los usuarios pueden programar una reunión desde Outlook.</span><span class="sxs-lookup"><span data-stu-id="805f6-112">With a single click, users can schedule a meeting from Outlook.</span></span> <span data-ttu-id="805f6-113">Los detalles, como la hora de la reunión, la ubicación y los asistentes, siguen la conocida plantilla de Outlook.</span><span class="sxs-lookup"><span data-stu-id="805f6-113">Details, such as meeting time, location, and attendees, follow the familiar Outlook template.</span></span> <span data-ttu-id="805f6-114">Además, la información específica de la llamada en conferencia, como el número de acceso telefónico local, los identificadores de reunión y los avisos de número de identificación personal (PIN), se rellenarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="805f6-114">Additionally, conference call-specific information, such as dial-in number, meeting IDs, and personal identification number (PIN) reminders, are automatically populated.</span></span>

<span data-ttu-id="805f6-115">Para ayudar a garantizar que solo las personas autorizadas participen en una llamada, Lync Server proporciona varios niveles de autenticación a los participantes.</span><span class="sxs-lookup"><span data-stu-id="805f6-115">To help ensure that only the authorized people participate in a call, Lync Server provides multiple levels of authentication for participants.</span></span> <span data-ttu-id="805f6-116">Los usuarios que se unen mediante Lync ya están autenticados por los servicios de dominio de Active Directory y no necesitan escribir un PIN, un código de acceso o un identificador de reunión.</span><span class="sxs-lookup"><span data-stu-id="805f6-116">Users who join by using Lync are already authenticated by the Active Directory Domain Services and do not need to enter a PIN, pass code, or meeting ID.</span></span>

<span data-ttu-id="805f6-117">Lync simplifica la experiencia de usuario de videoconferencias incorporando video en el cliente unificado, de modo que la programación de una reunión con video o el aumento de la escala de video de forma espontánea es perfecta y sencilla.</span><span class="sxs-lookup"><span data-stu-id="805f6-117">Lync simplifies the video conferencing user experience by incorporating video into the unified client so that scheduling a meeting with video or escalating to video spontaneously is seamless and easy.</span></span>

<span data-ttu-id="805f6-118">Lync Server facilita la adición de vídeo a una llamada de teléfono estándar con tan solo un clic.</span><span class="sxs-lookup"><span data-stu-id="805f6-118">Lync Server makes it easy to add video to a standard phone call in just one click.</span></span> <span data-ttu-id="805f6-119">Cuando hay varios participantes en una videollamada o una conferencia, cada usuario puede ver el video de hasta otros cinco usuarios al mismo tiempo, o un moderador puede elegir una sola fuente de vídeo para que todos los usuarios la vean exclusivamente.</span><span class="sxs-lookup"><span data-stu-id="805f6-119">When there are multiple participants in a video call or a conference, each user can see video from up to five other users simultaneously, or a presenter can choose just one video source to be seen exclusively by everyone.</span></span>

<span data-ttu-id="805f6-120">El vídeo de alta definición (resolución 1270 x 720; relación de aspecto 16:9) y vídeo VGA (resolución de 640 x 480; relación de aspecto 4:3) se admiten para llamadas de punto a punto entre usuarios que ejecutan Lync en equipos de alta definición.</span><span class="sxs-lookup"><span data-stu-id="805f6-120">High-definition video (resolution 1270 x 720; aspect ratio 16:9) and VGA video (resolution 640 x 480; aspect ratio 4:3) are supported for peer-to-peer calls between users running Lync on high-end computers.</span></span> <span data-ttu-id="805f6-121">La resolución vista por cada participante en una sola conversación puede variar en función de las características de vídeo del hardware respectivo de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="805f6-121">The resolution viewed by each participant in a single conversation may differ, depending on the video capabilities of each user’s respective hardware.</span></span>

<span data-ttu-id="805f6-122">Los administradores de TI pueden establecer políticas para restringir o deshabilitar el video VGA o de alta definición en los clientes, en función de la capacidad del equipo, el ancho de banda de red y la presencia de una cámara capaz de ofrecer la resolución requerida.</span><span class="sxs-lookup"><span data-stu-id="805f6-122">IT administrators can set policies to restrict or disable high-definition or VGA video on clients, depending on computer capability, network bandwidth, and the presence of a camera able to deliver the required resolution.</span></span> <span data-ttu-id="805f6-123">Estas directivas se aplican mediante aprovisionamiento en banda.</span><span class="sxs-lookup"><span data-stu-id="805f6-123">These policies are enforced through in-band provisioning.</span></span>

</div>

<div>

## <a name="web-conferencing"></a><span data-ttu-id="805f6-124">Conferencia web</span><span class="sxs-lookup"><span data-stu-id="805f6-124">Web conferencing</span></span>

<span data-ttu-id="805f6-125">Lync Server integra características de uso compartido de conferencias como escritorio, aplicación, datos adjuntos, pizarra, sondeo y PowerPoint en el Lync simplificado.</span><span class="sxs-lookup"><span data-stu-id="805f6-125">Lync Server integrates conferencing sharing features such as desktop, application, attachment, whiteboard, poll and PowerPoint into the streamlined Lync.</span></span> <span data-ttu-id="805f6-126">Combinado con las conferencias de audio o vídeo, el resultado es una sesión muy envolvente y colaborativa que es simple de facilitar.</span><span class="sxs-lookup"><span data-stu-id="805f6-126">Combined with audio or video conferencing, the result is a highly immersive and collaborative session that is simple to facilitate.</span></span>

<span data-ttu-id="805f6-127">Para mejorar la experiencia general de los usuarios que presenten o visualicen presentaciones de PowerPoint, Lync Server 2013 usa Office Web Apps para controlar presentaciones de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="805f6-127">To improve the overall experience of users presenting or viewing PowerPoint presentations, Lync Server 2013 employs Office Web Apps to handle PowerPoint presentations.</span></span> <span data-ttu-id="805f6-128">Los usuarios pueden compartir una imagen o copiar y pegar texto con una pizarra en la reunión de Lync.</span><span class="sxs-lookup"><span data-stu-id="805f6-128">Users can share a picture or copy and paste text using a Whiteboard in the Lync meeting.</span></span> <span data-ttu-id="805f6-129">Los moderadores pueden realizar sondeos en la reunión de Lync para solicitar comentarios de los asistentes.</span><span class="sxs-lookup"><span data-stu-id="805f6-129">Presenters can conduct polls in the Lync meeting to solicit feedback from the attendees.</span></span>

<span data-ttu-id="805f6-130">El uso compartido de escritorio permite a los moderadores difundir elementos visuales, aplicaciones, páginas web, documentos, software o parte de sus escritorios a participantes remotos en tiempo real, directamente desde Lync.</span><span class="sxs-lookup"><span data-stu-id="805f6-130">Desktop sharing enables presenters to broadcast any visuals, applications, webpages, documents, software, or part of their desktops to remote participants in real time, right from Lync.</span></span> <span data-ttu-id="805f6-131">Los miembros de la audiencia pueden seguir los movimientos del mouse y las acciones del teclado.</span><span class="sxs-lookup"><span data-stu-id="805f6-131">Audience members can follow along with mouse movements and keyboard input.</span></span> <span data-ttu-id="805f6-132">Los moderadores pueden elegir compartir la pantalla completa o solo una parte.</span><span class="sxs-lookup"><span data-stu-id="805f6-132">Presenters can choose to share the entire screen or only a portion.</span></span> <span data-ttu-id="805f6-133">Al compartir sus escritorios, los moderadores pueden comunicarse con sus audiencias en demostraciones interactivas de productos o software desde cualquier lugar.</span><span class="sxs-lookup"><span data-stu-id="805f6-133">By sharing their desktops, presenters are able to engage with their audiences in interactive product or software demos from any location.</span></span>

<span data-ttu-id="805f6-134">El uso compartido de aplicaciones permite a los moderadores compartir el control del software en sus escritorios sin perder la vista de comentarios de los participantes o preguntas de texto.</span><span class="sxs-lookup"><span data-stu-id="805f6-134">Application sharing enables presenters to share control of software on their desktops without losing sight of participant feedback or text questions.</span></span> <span data-ttu-id="805f6-135">Los moderadores también pueden delegar el control de la aplicación a los participantes de la reunión.</span><span class="sxs-lookup"><span data-stu-id="805f6-135">Presenters can also delegate control of the application to meeting participants.</span></span>

</div>

<div>

## <a name="dial-in-conferencing"></a><span data-ttu-id="805f6-136">Conferencias de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="805f6-136">Dial-in Conferencing</span></span>

<span data-ttu-id="805f6-137">Para los usuarios que no usan un equipo personal, hay varios métodos disponibles para unirse a una llamada de conferencia de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="805f6-137">For users that are not using a personal computer, there are several methods available for joining a Lync Server conference call.</span></span> <span data-ttu-id="805f6-138">Un usuario de RTC puede marcar un número de acceso, acceder al puente de la reunión y, a continuación, especificar el identificador de la reunión.</span><span class="sxs-lookup"><span data-stu-id="805f6-138">A PSTN user can dial an access number, access the meeting bridge, and then enter the meeting ID.</span></span> <span data-ttu-id="805f6-139">Para las reuniones más seguras, el usuario también puede tener que introducir su PIN para autenticar en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="805f6-139">For more secure meetings, the user can also be required to enter his or her PIN to authenticate against Active Directory.</span></span> <span data-ttu-id="805f6-140">Lync Server también es compatible con los dispositivos de Lync Phone Edition, que son los dispositivos telefónicos IP independientes proporcionados por los socios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="805f6-140">Lync Server also supports Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

