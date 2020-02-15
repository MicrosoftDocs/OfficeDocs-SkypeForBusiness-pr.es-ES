---
title: Lync Server 2013 conferencias
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
ms.openlocfilehash: dafb39a741ac26fc6edad6362ad10f2a6c244c64
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a><span data-ttu-id="bfa27-102">Conferencias en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfa27-102">Conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfa27-103">_**Última modificación del tema:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="bfa27-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="bfa27-104">Con las conferencias unificadas en Lync Server 2013, los usuarios pueden colaborar, compartir información y coordinar sus esfuerzos en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="bfa27-104">With unified conferencing in Lync Server 2013, users can collaborate, share information, and coordinate their efforts in real time.</span></span> <span data-ttu-id="bfa27-105">Los usuarios pueden usar todas las herramientas de reuniones, reuniones programadas y colaboración espontánea.</span><span class="sxs-lookup"><span data-stu-id="bfa27-105">All your users can use the full breadth of spontaneous collaboration, scheduled meetings, and meeting tools.</span></span> <span data-ttu-id="bfa27-106">Las capacidades de conferencia de voz y vídeo se pueden usar desde cualquier ubicación con conexión a Internet; además, los usuarios que estén lejos de su equipo pueden participar en las conferencias de audio mediante un teléfono de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="bfa27-106">Voice and video conferencing capabilities can be used from any location with an Internet connection, and users away from a computer can participate in audio conferences by dialing in with a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="bfa27-107">Herramientas de reunión integradas en Outlook habilite los organizadores para programar una reunión o para iniciar una conferencia improvisada con un solo clic y hacer que sea tan fácil unirse a los asistentes.</span><span class="sxs-lookup"><span data-stu-id="bfa27-107">Meeting tools integrated into Outlook enable organizers to schedule a meeting or start an impromptu conference with a single click, and also make it just as easy for attendees to join.</span></span> <span data-ttu-id="bfa27-108">Un cliente web amplía características de conferencia enriquecidas a los participantes que no ejecutan la versión de escritorio de Lync.</span><span class="sxs-lookup"><span data-stu-id="bfa27-108">A web client extends rich conference features to participants who are not running the desktop version of Lync.</span></span>

<div>

## <a name="audio-and-video-conferencing"></a><span data-ttu-id="bfa27-109">Conferencia de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="bfa27-109">Audio and Video Conferencing</span></span>

<span data-ttu-id="bfa27-110">Lync Server proporciona una experiencia de usuario que está familiarizada con los usuarios de los servicios de puente de audio tradicionales, incluidos los servicios de acceso telefónico RTC con comandos de control de llamadas de tonos.</span><span class="sxs-lookup"><span data-stu-id="bfa27-110">Lync Server provides a user experience that is familiar to users of traditional audio bridge services including PSTN dial-in services with touch-tone call control commands.</span></span> <span data-ttu-id="bfa27-111">Al mismo tiempo, incorpora potentes funciones de programación, unión y administración disponibles únicamente con una plataforma integrada de comunicaciones unificadas.</span><span class="sxs-lookup"><span data-stu-id="bfa27-111">At the same time, it incorporates powerful scheduling, joining, and management features available only with an integrated unified communications platform.</span></span>

<span data-ttu-id="bfa27-112">Con un solo clic, los usuarios pueden programar una reunión desde Outlook.</span><span class="sxs-lookup"><span data-stu-id="bfa27-112">With a single click, users can schedule a meeting from Outlook.</span></span> <span data-ttu-id="bfa27-113">Los detalles, como la hora de la reunión, la ubicación y los asistentes, siguen la conocida plantilla de Outlook.</span><span class="sxs-lookup"><span data-stu-id="bfa27-113">Details, such as meeting time, location, and attendees, follow the familiar Outlook template.</span></span> <span data-ttu-id="bfa27-114">Además, la información específica de la llamada de conferencia como, por ejemplo, el número de acceso telefónico, los Id. de la reunión y los recordatorios del número de identificación personal (PIN) se rellenan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="bfa27-114">Additionally, conference call-specific information, such as dial-in number, meeting IDs, and personal identification number (PIN) reminders, are automatically populated.</span></span>

<span data-ttu-id="bfa27-115">Para ayudar a garantizar que solo las personas autorizadas participen en una llamada, Lync Server proporciona varios niveles de autenticación a los participantes.</span><span class="sxs-lookup"><span data-stu-id="bfa27-115">To help ensure that only the authorized people participate in a call, Lync Server provides multiple levels of authentication for participants.</span></span> <span data-ttu-id="bfa27-116">Los usuarios que se unen a través de Lync ya están autenticados por los servicios de dominio de Active Directory y no necesitan especificar un PIN, un código de acceso o un identificador de reunión.</span><span class="sxs-lookup"><span data-stu-id="bfa27-116">Users who join by using Lync are already authenticated by the Active Directory Domain Services and do not need to enter a PIN, pass code, or meeting ID.</span></span>

<span data-ttu-id="bfa27-117">Lync simplifica la experiencia de usuario de videoconferencia mediante la incorporación de vídeo en el cliente unificado, de modo que la programación de una reunión con vídeo o el aumento de la escalabilidad del vídeo de forma espontánea es sencilla y sencilla.</span><span class="sxs-lookup"><span data-stu-id="bfa27-117">Lync simplifies the video conferencing user experience by incorporating video into the unified client so that scheduling a meeting with video or escalating to video spontaneously is seamless and easy.</span></span>

<span data-ttu-id="bfa27-118">Lync Server facilita la tarea de agregar vídeo a una llamada de teléfono estándar con tan solo un clic.</span><span class="sxs-lookup"><span data-stu-id="bfa27-118">Lync Server makes it easy to add video to a standard phone call in just one click.</span></span> <span data-ttu-id="bfa27-119">Si una llamada de vídeo o una conferencia tiene varios participantes, cada usuario podrá ver vídeos de hasta cinco usuarios distintos al mismo tiempo, o el moderador podrá decidir que todo el mundo vea un único origen de vídeo.</span><span class="sxs-lookup"><span data-stu-id="bfa27-119">When there are multiple participants in a video call or a conference, each user can see video from up to five other users simultaneously, or a presenter can choose just one video source to be seen exclusively by everyone.</span></span>

<span data-ttu-id="bfa27-120">Vídeo de alta definición (resolución 1270 x 720; relación de aspecto 16:9) y vídeo VGA (resolución 640 x 480; relación de aspecto 4:3) se admiten para las llamadas punto a punto entre usuarios que ejecutan Lync en equipos high-end.</span><span class="sxs-lookup"><span data-stu-id="bfa27-120">High-definition video (resolution 1270 x 720; aspect ratio 16:9) and VGA video (resolution 640 x 480; aspect ratio 4:3) are supported for peer-to-peer calls between users running Lync on high-end computers.</span></span> <span data-ttu-id="bfa27-121">La resolución captada por cada participante en una conversación única puede diferir, dependiendo de las características de vídeo del hardware de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="bfa27-121">The resolution viewed by each participant in a single conversation may differ, depending on the video capabilities of each user’s respective hardware.</span></span>

<span data-ttu-id="bfa27-p108">Los administradores de TI pueden establecer directivas para restringir o deshabilitar vídeo de alta definición o vídeo VGA en clientes, dependiendo de la capacidad del equipo, del ancho de banda de red y de la presencia de una cámara con características para proporcionar la resolución requerida. Estas directivas se exigen a través del aprovisionamiento en banda.</span><span class="sxs-lookup"><span data-stu-id="bfa27-p108">IT administrators can set policies to restrict or disable high-definition or VGA video on clients, depending on computer capability, network bandwidth, and the presence of a camera able to deliver the required resolution. These policies are enforced through in-band provisioning.</span></span>

</div>

<div>

## <a name="web-conferencing"></a><span data-ttu-id="bfa27-124">Conferencia web</span><span class="sxs-lookup"><span data-stu-id="bfa27-124">Web conferencing</span></span>

<span data-ttu-id="bfa27-125">Lync Server integra características de uso compartido de conferencias como escritorio, aplicación, datos adjuntos, pizarra, sondeo y PowerPoint en el Lync simplificado.</span><span class="sxs-lookup"><span data-stu-id="bfa27-125">Lync Server integrates conferencing sharing features such as desktop, application, attachment, whiteboard, poll and PowerPoint into the streamlined Lync.</span></span> <span data-ttu-id="bfa27-126">En combinación con las conferencias de audio y vídeo, el resultado es una sesión de gran inmersión y colaboración que se pone a disposición muy fácilmente.</span><span class="sxs-lookup"><span data-stu-id="bfa27-126">Combined with audio or video conferencing, the result is a highly immersive and collaborative session that is simple to facilitate.</span></span>

<span data-ttu-id="bfa27-127">Para mejorar la experiencia general de los usuarios que presentan o ven presentaciones de PowerPoint, Lync Server 2013 usa Office Web Apps para controlar las presentaciones de PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="bfa27-127">To improve the overall experience of users presenting or viewing PowerPoint presentations, Lync Server 2013 employs Office Web Apps to handle PowerPoint presentations.</span></span> <span data-ttu-id="bfa27-128">Los usuarios pueden compartir una imagen, o copiar y pegar texto mediante una pizarra en la reunión de Lync.</span><span class="sxs-lookup"><span data-stu-id="bfa27-128">Users can share a picture or copy and paste text using a Whiteboard in the Lync meeting.</span></span> <span data-ttu-id="bfa27-129">Los moderadores pueden realizar sondeos en la reunión de Lync para solicitar comentarios de los asistentes.</span><span class="sxs-lookup"><span data-stu-id="bfa27-129">Presenters can conduct polls in the Lync meeting to solicit feedback from the attendees.</span></span>

<span data-ttu-id="bfa27-130">El uso compartido de escritorio permite a los moderadores difundir los elementos visuales, las aplicaciones, las páginas web, los documentos, el software o parte de sus escritorios a los participantes remotos en tiempo real, directamente desde Lync.</span><span class="sxs-lookup"><span data-stu-id="bfa27-130">Desktop sharing enables presenters to broadcast any visuals, applications, webpages, documents, software, or part of their desktops to remote participants in real time, right from Lync.</span></span> <span data-ttu-id="bfa27-131">La audiencia puede realizar el seguimiento junto con los movimientos del ratón y las entradas del teclado.</span><span class="sxs-lookup"><span data-stu-id="bfa27-131">Audience members can follow along with mouse movements and keyboard input.</span></span> <span data-ttu-id="bfa27-132">Los moderadores pueden elegir entre compartir toda su pantalla o solo una parte.</span><span class="sxs-lookup"><span data-stu-id="bfa27-132">Presenters can choose to share the entire screen or only a portion.</span></span> <span data-ttu-id="bfa27-133">Al compartir sus escritorios, los moderadores pueden integrar a la audiencia en demostraciones interactivas de productos o software desde cualquier ubicación.</span><span class="sxs-lookup"><span data-stu-id="bfa27-133">By sharing their desktops, presenters are able to engage with their audiences in interactive product or software demos from any location.</span></span>

<span data-ttu-id="bfa27-p112">El uso compartido de aplicaciones permite a los moderadores compartir el control del software de sus escritorios sin perder de vista los comentarios de los participantes o las preguntas de texto. Asimismo, también pueden delegar el control de la aplicación a los participantes en la reunión.</span><span class="sxs-lookup"><span data-stu-id="bfa27-p112">Application sharing enables presenters to share control of software on their desktops without losing sight of participant feedback or text questions. Presenters can also delegate control of the application to meeting participants.</span></span>

</div>

<div>

## <a name="dial-in-conferencing"></a><span data-ttu-id="bfa27-136">Conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="bfa27-136">Dial-in Conferencing</span></span>

<span data-ttu-id="bfa27-137">Para los usuarios que no usan un equipo personal, hay varios métodos disponibles para unirse a una llamada de conferencia de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bfa27-137">For users that are not using a personal computer, there are several methods available for joining a Lync Server conference call.</span></span> <span data-ttu-id="bfa27-138">Un usuario de RTC puede marcar un número de acceso, obtener acceso al puente de la reunión y, a continuación, introducir el Id. de reunión.</span><span class="sxs-lookup"><span data-stu-id="bfa27-138">A PSTN user can dial an access number, access the meeting bridge, and then enter the meeting ID.</span></span> <span data-ttu-id="bfa27-139">Para reuniones más seguras, puede que el usuario también tenga que introducir su PIN para autenticarse en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bfa27-139">For more secure meetings, the user can also be required to enter his or her PIN to authenticate against Active Directory.</span></span> <span data-ttu-id="bfa27-140">Lync Server también admite dispositivos de Lync Phone Edition, que son dispositivos de telefonía IP independientes proporcionados por los socios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bfa27-140">Lync Server also supports Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

