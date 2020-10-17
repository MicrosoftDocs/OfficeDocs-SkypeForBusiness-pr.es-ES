---
title: 'Lync Server 2013: novedades para clientes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6103c6cd8ae762402a94412a56eda107f43a58fd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518207"
---
# <a name="whats-new-for-clients-in-lync-server-2013"></a><span data-ttu-id="9a487-102">Novedades para clientes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a487-102">What's new for clients in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a487-103">_**Última modificación del tema:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="9a487-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="9a487-104">Microsoft Lync 2013 tiene una interfaz de usuario rediseñada y nuevas características importantes.</span><span class="sxs-lookup"><span data-stu-id="9a487-104">Microsoft Lync 2013 has a redesigned user interface and important new features.</span></span> <span data-ttu-id="9a487-105">Para los administradores, el cliente se incluye ahora con el programa de instalación de Office, lo que proporciona un método más simplificado para implementar Office y personalizar clientes en su organización.</span><span class="sxs-lookup"><span data-stu-id="9a487-105">For administrators, the client is now included with the Office setup program, providing a more streamlined approach to deploying Office and customizing clients in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a487-106">Para obtener una vista ilustrada de las actualizaciones de la interfaz de usuario de Lync 2013, consulte "What's New in Lync 2013" en <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A> .</span><span class="sxs-lookup"><span data-stu-id="9a487-106">For an illustrated view of Lync 2013 user interface updates, see “What’s New in Lync 2013” at <A href="https://go.microsoft.com/fwlink/?linkid=273885">https://go.microsoft.com/fwlink/?LinkId=273885</A>.</span></span>



</div>

<div>

## <a name="integration-with-office-setup"></a><span data-ttu-id="9a487-107">Integración con el programa de instalación de Office</span><span class="sxs-lookup"><span data-stu-id="9a487-107">Integration with Office Setup</span></span>

<span data-ttu-id="9a487-108">El cliente de Lync 2013 y el complemento de reunión en línea para Lync 2013 (que admite la administración de reuniones desde el cliente de mensajería y colaboración de Outlook) se incluyen ahora ambos con el programa de instalación de Office 2013.</span><span class="sxs-lookup"><span data-stu-id="9a487-108">The Lync 2013 client and the Online Meeting Add-in for Lync 2013—which supports meeting management from within the Outlook messaging and collaboration client—are now both included with the Office 2013 Setup program.</span></span>

<span data-ttu-id="9a487-109">En versiones anteriores de Lync y Office Communicator, podía usar las propiedades de Windows Installer para personalizar y controlar la instalación de Office.</span><span class="sxs-lookup"><span data-stu-id="9a487-109">In previous versions of Lync and Office Communicator, you could use Windows Installer properties to customize and control the Office installation.</span></span> <span data-ttu-id="9a487-110">Como Lync 2013 está integrado con el programa de instalación de Office, puede usar los siguientes métodos para personalizar la instalación de Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="9a487-110">Because Lync 2013 is integrated with Office setup, you can use the following methods to customize Lync 2013 setup:</span></span>

  - <span data-ttu-id="9a487-111">Usar la Herramienta de personalización de Office (OCT)</span><span class="sxs-lookup"><span data-stu-id="9a487-111">Use the Office Customization Tool (OCT)</span></span>

  - <span data-ttu-id="9a487-112">Usar el Config.xml para realizar tareas de instalación</span><span class="sxs-lookup"><span data-stu-id="9a487-112">Use the Config.xml to perform installation tasks</span></span>

  - <span data-ttu-id="9a487-113">Uso de opciones de Command-Line de configuración</span><span class="sxs-lookup"><span data-stu-id="9a487-113">Use Setup Command-Line Options</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a487-114">El programa de instalación de Lync 2013 no desinstala versiones anteriores de Lync u Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="9a487-114">The Lync 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="9a487-115">El cliente de Lync 2013 se instala en paralelo con otros clientes de Lync u Office Communicator</span><span class="sxs-lookup"><span data-stu-id="9a487-115">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span>



</div>

<span data-ttu-id="9a487-116">Para obtener más información, consulte [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="9a487-116">For details, see [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span></span>

</div>

<div>

## <a name="group-policy-deployment"></a><span data-ttu-id="9a487-117">Implementación de la Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="9a487-117">Group Policy Deployment</span></span>

<span data-ttu-id="9a487-118">Como Lync 2013 ahora se incluye en el programa de instalación de Office, el método para implementar la configuración de la Directiva de grupo de Lync ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="9a487-118">Because Lync 2013 is now included in Office setup, the method for deploying Lync Group Policy settings has changed.</span></span> <span data-ttu-id="9a487-119">En versiones anteriores de Lync y Office Communicator, podía usar Communicator. ADM para definir la configuración de la Directiva de grupo, mientras que en Lync 2013 ahora puede usar las plantillas administrativas de ADMX y ADML de Lync que se proporcionan junto con las plantillas administrativas de directiva de grupo de Office.</span><span class="sxs-lookup"><span data-stu-id="9a487-119">In previous versions of Lync and Office Communicator, you could use the Communicator.adm to define Group Policy settings, whereas in Lync 2013 you can now use the Lync ADMX and ADML administrative templates that are provided along with the Office Group Policy Administrative Templates.</span></span>

<span data-ttu-id="9a487-120">Para obtener más información, consulte [configuración de directiva de grupo para Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="9a487-120">For details, see [Group Policy settings for Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span></span>

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a><span data-ttu-id="9a487-121">Actualizaciones de complementos de programación de Outlook</span><span class="sxs-lookup"><span data-stu-id="9a487-121">Outlook Scheduling Add-in Updates</span></span>

<span data-ttu-id="9a487-122">El complemento para reunión en línea para Lync 2013 incluye personalización de invitaciones de reunión y nuevas opciones de reunión.</span><span class="sxs-lookup"><span data-stu-id="9a487-122">The Online Meeting Add-in for Lync 2013 includes meeting invite customization and new meeting options.</span></span>

  - <span data-ttu-id="9a487-123">Los administradores pueden personalizar las invitaciones a reuniones de la organización agregando un logotipo personalizado, una dirección URL de soporte, una dirección URL de exención de responsabilidad legal o un texto de pie de página personalizado.</span><span class="sxs-lookup"><span data-stu-id="9a487-123">Administrators can customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span> <span data-ttu-id="9a487-124">Para obtener más información, consulte [Customizing the online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="9a487-124">For details, see [Customizing the Online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span></span>

  - <span data-ttu-id="9a487-125">Los controles de silencio de los nuevos asistentes permiten que los organizadores de la reunión programen conferencias en las que el audio y el vídeo del asistente están silenciados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9a487-125">New attendee mute controls allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span>

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a><span data-ttu-id="9a487-126">Complemento de infraestructura de escritorio virtual</span><span class="sxs-lookup"><span data-stu-id="9a487-126">Virtual Desktop Infrastructure Plug-in</span></span>

<span data-ttu-id="9a487-127">El cliente de Lync 2013 ahora admite audio y vídeo en un entorno de infraestructura de escritorio virtual (VDI).</span><span class="sxs-lookup"><span data-stu-id="9a487-127">The Lync 2013 client now supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="9a487-128">Un usuario puede conectar un dispositivo de audio o vídeo (por ejemplo, un auricular o una cámara) al equipo local (por ejemplo, un cliente ligero o un equipo con un repropósito).</span><span class="sxs-lookup"><span data-stu-id="9a487-128">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="9a487-129">El usuario puede conectarse a la máquina virtual, iniciar sesión en el cliente de Lync 2013 que se ejecuta en la máquina virtual y participar en la comunicación de audio y vídeo en tiempo real como si el cliente se ejecuta de forma local.</span><span class="sxs-lookup"><span data-stu-id="9a487-129">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communication as though the client is running locally.</span></span> <span data-ttu-id="9a487-130">Las siguientes características se admiten en un entorno de escritorio virtual:</span><span class="sxs-lookup"><span data-stu-id="9a487-130">The following features are supported in a virtual desktop environment:</span></span>

  - <span data-ttu-id="9a487-131">Integración de dispositivos para audio y vídeo, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9a487-131">Device integration for audio and video, including the following:</span></span>
    
      - <span data-ttu-id="9a487-132">Llamar a controles desde el dispositivo</span><span class="sxs-lookup"><span data-stu-id="9a487-132">Call controls from the device</span></span>
    
      - <span data-ttu-id="9a487-133">Integración de presencia en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="9a487-133">Presence integration on the device</span></span>
    
      - <span data-ttu-id="9a487-134">Compatibilidad con varios HID (dispositivos de interfaz humana)</span><span class="sxs-lookup"><span data-stu-id="9a487-134">Multiple HID (human interface device) support</span></span>

  - <span data-ttu-id="9a487-135">Compatibilidad con servicios de emergencia y ubicación.</span><span class="sxs-lookup"><span data-stu-id="9a487-135">Location and emergency services support.</span></span>

  - <span data-ttu-id="9a487-136">Soporte para todas las modalidades de Lync, como mensajería instantánea, audio, vídeo, uso compartido de aplicaciones, uso compartido de escritorio, uso compartido de PowerPoint, pizarra y transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="9a487-136">Support for all Lync modalities, including IM, audio, video, application sharing, desktop sharing, PowerPoint sharing, whiteboard, and file transfer.</span></span>

  - <span data-ttu-id="9a487-137">Compatibilidad con audio y vídeo en llamadas de persona a persona y llamadas de conferencia.</span><span class="sxs-lookup"><span data-stu-id="9a487-137">Audio and video support in person-to-person calls and conference calls.</span></span>

<span data-ttu-id="9a487-138">Para obtener información acerca de la implementación del complemento VDI, consulte [Deploying The Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span><span class="sxs-lookup"><span data-stu-id="9a487-138">For information about deploying the VDI plug-in, see [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span></span>

</div>

<div>

## <a name="video-enhancements"></a><span data-ttu-id="9a487-139">Mejoras de vídeo</span><span class="sxs-lookup"><span data-stu-id="9a487-139">Video Enhancements</span></span>

<span data-ttu-id="9a487-140">Varias características nuevas mejoran significativamente la experiencia de vídeo para los participantes de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="9a487-140">Several new features significantly enhance the video experience for conference participants.</span></span>

  - <span data-ttu-id="9a487-141">El vídeo se ha mejorado con la detección de rostro y las tramas inteligentes, de modo que el vídeo de un participante se mueva para ayudarle a centrarse en el marco.</span><span class="sxs-lookup"><span data-stu-id="9a487-141">Video is enhanced with face detection and smart framing, so that a participant’s video moves to help keep them centered in the frame.</span></span>

  - <span data-ttu-id="9a487-142">El vídeo de alta definición ahora es compatible con llamadas de dos participantes y conferencias de varios participantes.</span><span class="sxs-lookup"><span data-stu-id="9a487-142">High-definition video is now supported in two-party calls and multiparty conferences.</span></span> <span data-ttu-id="9a487-143">Los usuarios pueden disfrutar de resoluciones de hasta HD 1080P.</span><span class="sxs-lookup"><span data-stu-id="9a487-143">Users can experience resolutions up to HD 1080P.</span></span>

  - <span data-ttu-id="9a487-144">Los participantes pueden seleccionar entre diferentes diseños de reunión: la vista de Galería muestra las imágenes o vídeos de todos los participantes; La vista de orador muestra el contenido de la reunión y solo el vídeo o la imagen del orador actual; La vista de presentación muestra solo el contenido de la reunión; La vista compacta muestra solo los controles de la reunión.</span><span class="sxs-lookup"><span data-stu-id="9a487-144">Participants can select from different meeting layouts: Gallery View shows all participants’ pictures or videos; Speaker View shows the meeting content and only the current speaker’s video or picture; Presentation View shows meeting content only; Compact View shows just the meeting controls.</span></span>

  - <span data-ttu-id="9a487-145">Con la nueva característica de galería, los participantes pueden ver varias fuentes de vídeo al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="9a487-145">With the new Gallery feature, participants can see multiple video feeds at the same time.</span></span> <span data-ttu-id="9a487-146">Si la Conferencia tiene más de cinco participantes, las fuentes de vídeo de los participantes más activos aparecen en la fila superior y las imágenes aparecen para los demás participantes.</span><span class="sxs-lookup"><span data-stu-id="9a487-146">If the conference has more than five participants, video feeds of only the most active participants appear in the top row, and pictures appear for the other participants.</span></span>

  - <span data-ttu-id="9a487-147">Los participantes pueden usar el anclaje de vídeo para seleccionar una o varias de las fuentes de vídeo disponibles para que sean visibles en todo momento.</span><span class="sxs-lookup"><span data-stu-id="9a487-147">Participants can use video pinning to select one or more of the available video feeds to be visible at all times.</span></span>

  - <span data-ttu-id="9a487-148">Los moderadores pueden usar la característica de foco de vídeo para seleccionar la fuente de vídeo de una persona para que todos los participantes de la reunión solo vean a ese participante.</span><span class="sxs-lookup"><span data-stu-id="9a487-148">Presenters can use the Video Spotlight feature to select one person’s video feed so that every participant in the meeting sees that participant only.</span></span>

</div>

<div>

## <a name="chat-room-integration"></a><span data-ttu-id="9a487-149">Integración del salón de chat</span><span class="sxs-lookup"><span data-stu-id="9a487-149">Chat Room Integration</span></span>

<span data-ttu-id="9a487-150">Lync 2013 ahora integra las características proporcionadas anteriormente por el chat en grupo de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="9a487-150">Lync 2013 now integrates the features previously provided by Lync 2010 Group Chat.</span></span> <span data-ttu-id="9a487-151">Ya no se necesita un cliente de chat en grupo independiente.</span><span class="sxs-lookup"><span data-stu-id="9a487-151">A separate group chat client is no longer required.</span></span>

  - <span data-ttu-id="9a487-152">Desde dentro de Lync 2013, los usuarios pueden buscar salones de chat, agregar salones de chat a sus contactos, supervisar la actividad de los salones de chat y leer y publicar mensajes.</span><span class="sxs-lookup"><span data-stu-id="9a487-152">From within Lync 2013, users can search for chat rooms, add chat rooms to their contacts, monitor chat room activity, and read and post messages.</span></span>

  - <span data-ttu-id="9a487-153">Los usuarios pueden crear suministros de temas para que reciban una notificación si alguien de uno de sus salones de chat agrega una publicación que contiene palabras clave específicas.</span><span class="sxs-lookup"><span data-stu-id="9a487-153">Users can create topic feeds so that they’ll be notified if someone in one of their chat rooms adds a post containing specific keywords.</span></span>

  - <span data-ttu-id="9a487-154">Con la nueva página Opciones de **chat persistente** , los usuarios pueden configurar alertas y sonidos de notificación que se aplican cuando los usuarios envían mensajes a sus salones de chat.</span><span class="sxs-lookup"><span data-stu-id="9a487-154">With the new **Persistent Chat** options page, users can set notification alerts and sounds that apply when people post messages to their chat rooms.</span></span>

</div>

<div>

## <a name="lync-web-app-updates"></a><span data-ttu-id="9a487-155">Actualizaciones de Lync Web App</span><span class="sxs-lookup"><span data-stu-id="9a487-155">Lync Web App Updates</span></span>

<span data-ttu-id="9a487-156">Lync Web App es el cliente de conferencia basado en web para reuniones de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a487-156">Lync Web App is the web-based conferencing client for Lync Server 2013 meetings.</span></span> <span data-ttu-id="9a487-157">En esta versión, la adición de audio y vídeo de equipo a Lync Web App ofrece una experiencia de reunión completa para todos los usuarios que no tengan un cliente de Lync instalado de forma local.</span><span class="sxs-lookup"><span data-stu-id="9a487-157">In this release, the addition of computer audio and video to Lync Web App provides a complete in-meeting experience for anyone who doesn’t have a Lync client installed locally.</span></span> <span data-ttu-id="9a487-158">Los participantes de la reunión tienen acceso a todas las características de colaboración y uso compartido, así como a los controles de la reunión del mediador.</span><span class="sxs-lookup"><span data-stu-id="9a487-158">Meeting participants have access to all collaboration and sharing features and presenter meeting controls.</span></span>

<span data-ttu-id="9a487-159">Cuando un usuario intenta unirse a una reunión, pero no tiene un cliente instalado localmente, se abre Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="9a487-159">When a user tries to join a meeting but doesn’t have a locally installed client, Lync Web App opens.</span></span> <span data-ttu-id="9a487-160">Si desea permitir opciones adicionales para unirse a la reunión, puede configurar la página de participación en la reunión; consulte [configurar la página de participación en la reunión en Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="9a487-160">If you want to allow additional options for joining the meeting, you can configure the Meeting Join page; see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in the Deployment documentation.</span></span>

<span data-ttu-id="9a487-161">Debido a las mejoras realizadas en Lync Web App, hay una versión actualizada del asistente que no está disponible para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a487-161">Because of the enhancements to Lync Web App, an updated version of Attendee isn’t available for Lync Server 2013.</span></span> <span data-ttu-id="9a487-162">Lync Web App es el cliente preferido para los participantes externos a la organización.</span><span class="sxs-lookup"><span data-stu-id="9a487-162">Lync Web App is the client of choice for participants outside your organization.</span></span> <span data-ttu-id="9a487-163">No es necesaria una instalación de cliente local, a pesar de que las características de audio, vídeo y uso compartido requieren que se instale un complemento al utilizar por primera vez.</span><span class="sxs-lookup"><span data-stu-id="9a487-163">No local client installation is required, although audio, video, and sharing features require a plug-in to be installed at first use.</span></span>

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a><span data-ttu-id="9a487-164">Lync 2013 para actualizaciones de clientes móviles</span><span class="sxs-lookup"><span data-stu-id="9a487-164">Lync 2013 for Mobile Clients Updates</span></span>

<span data-ttu-id="9a487-165">Además de la presencia mejorada, los contactos y las capacidades de mensajería instantánea, los clientes móviles de Lync 2013 proporcionan ahora llamadas de voz y vídeo a través de Internet y conexiones de datos móviles.</span><span class="sxs-lookup"><span data-stu-id="9a487-165">In addition to enhanced presence, contacts, and IM capabilities, Lync 2013 mobile clients now provide voice and video calling over the Internet and cellular data connections.</span></span> <span data-ttu-id="9a487-166">Con un solo punteo en el vínculo de la reunión en un elemento de calendario, los usuarios móviles pueden unirse a reuniones de Lync Voice y vídeo.</span><span class="sxs-lookup"><span data-stu-id="9a487-166">With a single tap of the meeting link in a calendar item, mobile users can join Lync voice and video meetings.</span></span> <span data-ttu-id="9a487-167">Para obtener más información sobre los clientes móviles de Lync 2013, consulte [Planning for Mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="9a487-167">For more information about Lync 2013 mobile clients, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a><span data-ttu-id="9a487-168">Actualizaciones de la interfaz de usuario de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="9a487-168">Lync 2013 User Interface Updates</span></span>

<div>

## <a name="accessibility-updates"></a><span data-ttu-id="9a487-169">Actualizaciones de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="9a487-169">Accessibility Updates</span></span>

<span data-ttu-id="9a487-170">Lync 2013 incorpora varias características de accesibilidad nuevas.</span><span class="sxs-lookup"><span data-stu-id="9a487-170">Lync 2013 incorporates several new accessibility features.</span></span>

  - <span data-ttu-id="9a487-171">Lync 2013 admite alta resolución de PPP, lo que permite a los usuarios ajustar el texto y los gráficos del 125% y el 150% de puntos por pulgada.</span><span class="sxs-lookup"><span data-stu-id="9a487-171">Lync 2013 supports high DPI resolution, enabling users to scale text and graphics for 125% and 150% dots per inch.</span></span>

  - <span data-ttu-id="9a487-172">Lync ofrece compatibilidad de alto contraste para que la interfaz de usuario permanezca completamente operativa cuando se usa con temas de contraste alto en Windows.</span><span class="sxs-lookup"><span data-stu-id="9a487-172">Lync provides high-contrast support so that the user interface remains fully functional when used with high contrast themes in Windows.</span></span>

  - <span data-ttu-id="9a487-173">Lync ofrece más de 100 métodos abreviados de teclado para que los usuarios puedan acceder a las funciones importantes sin el mouse.</span><span class="sxs-lookup"><span data-stu-id="9a487-173">Lync offers more than 100 keyboard shortcuts so that users can access important functions without a mouse.</span></span> <span data-ttu-id="9a487-174">Por ejemplo, los usuarios pueden presionar ALT + C para aceptar una llamada o Alt + I para omitirla, sin tener que usar el tabulador o establecer el foco.</span><span class="sxs-lookup"><span data-stu-id="9a487-174">For example, users can press Alt+C to accept a call, or Alt + I to ignore it, without having to tab or set the focus.</span></span> <span data-ttu-id="9a487-175">Al presionar (Alt + Q), se finaliza una llamada, (Ctrl + N) se inicia OneNote y (Alt + T) se abre el menú herramientas.</span><span class="sxs-lookup"><span data-stu-id="9a487-175">Pressing (Alt+Q) ends a call, (Ctrl+N) starts OneNote, and (Alt+T) opens the Tools menu.</span></span>

  - <span data-ttu-id="9a487-176">La compatibilidad con un lector de pantalla extensivo en Lync 2013 garantiza que todas las notificaciones, las solicitudes entrantes y los mensajes instantáneos se lean en voz alta cuando se habilita un lector de pantalla.</span><span class="sxs-lookup"><span data-stu-id="9a487-176">Extensive screen reader support in Lync 2013 ensures that all notifications, incoming requests, and instant messages are read aloud when a screen reader is enabled.</span></span>

</div>

<div>

## <a name="presence-while-sharing"></a><span data-ttu-id="9a487-177">Presencia al compartir</span><span class="sxs-lookup"><span data-stu-id="9a487-177">Presence While Sharing</span></span>

<span data-ttu-id="9a487-178">Cuando Lync detecta que un usuario está compartiendo un usuario, Lync asigna automáticamente un estado de presencia en el que se presenta el usuario.</span><span class="sxs-lookup"><span data-stu-id="9a487-178">When Lync detects that a user is sharing, Lync automatically assigns the user a Presenting presence status.</span></span> <span data-ttu-id="9a487-179">Este estado bloquea todas las comunicaciones entrantes a menos que el remitente tenga asignada la relación de privacidad grupo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9a487-179">This status blocks all incoming communications unless the sender is assigned the Workgroup privacy relationship.</span></span> <span data-ttu-id="9a487-180">Si el usuario usa la característica de uso compartido en un monitor secundario, Lync no asigna un estado de presencia de presentación.</span><span class="sxs-lookup"><span data-stu-id="9a487-180">If the user is using the sharing feature entirely on a secondary monitor, Lync does not assign a Presenting presence status.</span></span>

</div>

<div>

## <a name="conversation-window-updates"></a><span data-ttu-id="9a487-181">Actualizaciones de la ventana de conversación</span><span class="sxs-lookup"><span data-stu-id="9a487-181">Conversation Window Updates</span></span>

<span data-ttu-id="9a487-182">La ventana de conversación rediseñada proporciona un acceso más rápido a características importantes.</span><span class="sxs-lookup"><span data-stu-id="9a487-182">The redesigned Conversation window provides quicker access to important features.</span></span>

  - <span data-ttu-id="9a487-183">Con la nueva característica de conversaciones en pestañas, ahora los usuarios pueden mantener todos sus salones de chat y IMs en una ventana de conversación.</span><span class="sxs-lookup"><span data-stu-id="9a487-183">With the new tabbed conversations feature, users can now keep all their IMs and chat rooms in one Conversation window.</span></span> <span data-ttu-id="9a487-184">Las pestañas situadas en el lado izquierdo de la ventana de conversación permiten a los usuarios desplazarse fácilmente entre todas las conversaciones activas.</span><span class="sxs-lookup"><span data-stu-id="9a487-184">The tabs along the left side of the Conversation window let users navigate easily among all active conversations.</span></span>

  - <span data-ttu-id="9a487-185">Los usuarios pueden extraer una conversación individual en una ventana independiente y, a continuación, cambiar el tamaño de la ventana.</span><span class="sxs-lookup"><span data-stu-id="9a487-185">Users can pop out an individual conversation into a separate window, and then resize the window.</span></span> <span data-ttu-id="9a487-186">También pueden volver a extraer la ventana en la ventana de conversación principal.</span><span class="sxs-lookup"><span data-stu-id="9a487-186">They can also pop the window back into the main Conversation window.</span></span>

  - <span data-ttu-id="9a487-187">Lync 2013 vuelve a abrir las conversaciones de un usuario cuando el usuario cierra sesión y vuelve a iniciar sesión en Lync.</span><span class="sxs-lookup"><span data-stu-id="9a487-187">Lync 2013 reopens a user’s conversations when the user signs out and signs back in to Lync.</span></span>

  - <span data-ttu-id="9a487-188">Los usuarios pueden agregar rápidamente mensajería instantánea, vídeo, uso compartido de programas, uso compartido de escritorio o herramientas de conferencia web (pizarra, notas de reunión, blocs de notas compartidos y datos adjuntos) a cualquier conversación.</span><span class="sxs-lookup"><span data-stu-id="9a487-188">Users can quickly add IM, video, program sharing, desktop sharing, or web conferencing tools (whiteboard, meeting notes, shared notebooks, and attachments) to any conversation.</span></span>

  - <span data-ttu-id="9a487-189">En una reunión en la que se comparte el vídeo o el contenido, los usuarios pueden extraer el contenido compartido o el vídeo de la reunión y, a continuación, cambiar el tamaño de la ventana.</span><span class="sxs-lookup"><span data-stu-id="9a487-189">In a meeting where video or content is being shared, users can pop out the meeting video or shared content, and then resize the window.</span></span>

</div>

<div>

## <a name="lync-main-window-updates"></a><span data-ttu-id="9a487-190">Actualizaciones de la ventana principal de Lync</span><span class="sxs-lookup"><span data-stu-id="9a487-190">Lync Main Window Updates</span></span>

<span data-ttu-id="9a487-191">El nuevo aspecto simplificado conserva características familiares, como el campo **¿Qué está ocurriendo?** , el selector de estado y el selector **de ubicación** .</span><span class="sxs-lookup"><span data-stu-id="9a487-191">The new streamlined look retains familiar features such as the **What’s happening today?** note field, the status selector, and the **Set Your Location** selector.</span></span>

  - <span data-ttu-id="9a487-192">Cuando los salones de chat están habilitados, los usuarios ven un icono nuevo de **salones de chat** en la Página principal de Lync.</span><span class="sxs-lookup"><span data-stu-id="9a487-192">When chat rooms are enabled, users see a new **Chat Rooms** icon on the main Lync page.</span></span> <span data-ttu-id="9a487-193">Con el icono de los **salones de chat** , los usuarios pueden acceder rápidamente a sus salones de chat y filtros.</span><span class="sxs-lookup"><span data-stu-id="9a487-193">With the **Chat Rooms** icon, users can quickly access their chat rooms and filters.</span></span>

  - <span data-ttu-id="9a487-194">Los usuarios pueden hacer clic en el icono Ver iconos para cambiar a la vista de **contactos** , a la vista de **salones de chat** , a la vista **conversaciones** o a la vista de **teléfono** .</span><span class="sxs-lookup"><span data-stu-id="9a487-194">Users can click the view icons to switch to the **Contacts** view, **Chat Rooms** view, **Conversations** view, or **Phone** view.</span></span>

  - <span data-ttu-id="9a487-195">Si los usuarios se han migrado a Exchange 2013, pueden cargar una imagen de alta resolución.</span><span class="sxs-lookup"><span data-stu-id="9a487-195">If users have been migrated to Exchange 2013, they can upload a high resolution picture.</span></span>

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a><span data-ttu-id="9a487-196">Vista de contactos y actualizaciones de tarjetas de contacto</span><span class="sxs-lookup"><span data-stu-id="9a487-196">Contacts View and Contact Card Updates</span></span>

<span data-ttu-id="9a487-197">Lync 2013 proporciona a los usuarios distintas formas de ver los contactos y grupos en su vista de **contactos** .</span><span class="sxs-lookup"><span data-stu-id="9a487-197">Lync 2013 gives users different ways to view contacts and groups in their **Contacts** view.</span></span>

  - <span data-ttu-id="9a487-198">Con el nuevo almacén de contactos unificado, después de migrar los contactos de Lync de los usuarios a Exchange 2013, los usuarios pueden tener acceso a los contactos y administrarlos desde Lync 2013, Outlook o Outlook Web App, y sus favoritos se mantienen sincronizados.</span><span class="sxs-lookup"><span data-stu-id="9a487-198">With the new unified contact store, after users' Lync contacts are migrated to Exchange 2013, the users can access and manage their contacts from Lync 2013, Outlook, or Outlook Web App, and their Favorites stay synchronized.</span></span> <span data-ttu-id="9a487-199">Por ejemplo, si un usuario agrega un contacto a favoritos en Outlook, el contacto aparece en el grupo favoritos en Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9a487-199">For example, if a user adds a contact to Favorites in Outlook, the contact appears in the Favorites group in Lync 2013.</span></span>

  - <span data-ttu-id="9a487-200">Si ha agregado y configurado el proxy XMPP y la puerta de enlace XMPP, los usuarios pueden agregar contactos de socios basados en XMPP para la mensajería instantánea y la presencia.</span><span class="sxs-lookup"><span data-stu-id="9a487-200">If you have added and configured the XMPP proxy and XMPP gateway, users can add contacts from XMPP-based partners for instant messaging and presence.</span></span>

  - <span data-ttu-id="9a487-201">Una nueva característica **Agregar un contacto que no está en mi organización** ofrece a los usuarios una forma sencilla de agregar personas externas a la organización.</span><span class="sxs-lookup"><span data-stu-id="9a487-201">A new **Add a Contact That’s Not in My Organization** feature gives users an easy way to add people who are external to the organization.</span></span>

  - <span data-ttu-id="9a487-202">Un nuevo grupo de **Favoritos** permite a los usuarios crear una lista de personas a las que se puede contactar con mayor frecuencia para obtener un acceso más rápido.</span><span class="sxs-lookup"><span data-stu-id="9a487-202">A new **Favorites** group lets users build a list of people users contact most often for quicker access.</span></span>

  - <span data-ttu-id="9a487-203">Los usuarios pueden usar la página nuevas opciones de **lista de contactos** para elegir el modo en que los usuarios desean ordenar y mostrar los contactos.</span><span class="sxs-lookup"><span data-stu-id="9a487-203">Users can use the new **Contacts List** options page to choose how users want to sort and display contacts.</span></span> <span data-ttu-id="9a487-204">Los usuarios pueden seleccionar una vista expandida de dos líneas que muestre las imágenes de los contactos o una vista de una línea comprimida.</span><span class="sxs-lookup"><span data-stu-id="9a487-204">Users can select an expanded, two-line view that shows contacts’ pictures, or a condensed one-line view.</span></span> <span data-ttu-id="9a487-205">Los usuarios también pueden ordenar los contactos alfabéticamente o por disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="9a487-205">Users can also sort contacts alphabetically or by availability.</span></span>

</div>

<div>

## <a name="conferencing-updates"></a><span data-ttu-id="9a487-206">Actualizaciones de conferencia</span><span class="sxs-lookup"><span data-stu-id="9a487-206">Conferencing Updates</span></span>

<span data-ttu-id="9a487-207">Lync 2013 ofrece varias mejoras a las características de conferencia.</span><span class="sxs-lookup"><span data-stu-id="9a487-207">Lync 2013 offers several enhancements to conferencing features.</span></span>

  - <span data-ttu-id="9a487-208">En función del tipo de reunión, los usuarios ahora pueden silenciar la audiencia y permitir o bloquear el uso compartido de vídeo al programar la reunión.</span><span class="sxs-lookup"><span data-stu-id="9a487-208">Depending on the type of meeting, users can now mute the audience and allow or block video sharing when scheduling the meeting.</span></span> <span data-ttu-id="9a487-209">Estas opciones están disponibles en la página **Opciones de reunión** y se recomiendan para reuniones grandes con más de 20 participantes.</span><span class="sxs-lookup"><span data-stu-id="9a487-209">These options are available on the **Meeting Options** page and are recommended for large meetings with more than 20 participants.</span></span>

  - <span data-ttu-id="9a487-210">Los controles de audio fáciles de usar en la sala de reuniones permiten al usuario controlar las opciones de audio, como silenciar, reactivar audio, cambiar dispositivo, etc.</span><span class="sxs-lookup"><span data-stu-id="9a487-210">Easy to use audio controls in the meeting room allow the user to control audio options, such as mute, unmute, change device, and so on.</span></span>

  - <span data-ttu-id="9a487-211">Al compartir programas, los usuarios pueden seleccionar varios programas para compartir si necesitan trabajar con más de un programa.</span><span class="sxs-lookup"><span data-stu-id="9a487-211">When sharing programs, users can select multiple programs to share if they need to work with more than one program.</span></span>

  - <span data-ttu-id="9a487-212">Ahora, los usuarios pueden cargar presentaciones que contienen clips de vídeo cargando el archivo de PowerPoint y señalando el mouse sobre la diapositiva para mostrar controles de vídeo, como los controles de reproducción, pausa y audio.</span><span class="sxs-lookup"><span data-stu-id="9a487-212">Users can now upload presentations that contain video clips by uploading the PowerPoint file, and pointing the mouse over the slide to display video controls, such as play, pause, and audio controls.</span></span>

  - <span data-ttu-id="9a487-213">Durante una reunión, los usuarios pueden combinar otra conversación abierta con la reunión mediante la **combinación de esta llamada** en el menú **más opciones** (**...**).</span><span class="sxs-lookup"><span data-stu-id="9a487-213">While in a meeting, users can merge another open conversation into the meeting by using **Merge This Call Into** on the **More Options** (**…**) menu.</span></span>

  - <span data-ttu-id="9a487-214">Para ver los nombres de los participantes, los usuarios pueden situar el mouse sobre el botón **Ver participantes** o hacer clic en **Mostrar lista de participantes** para acoplar el panel en la reunión.</span><span class="sxs-lookup"><span data-stu-id="9a487-214">To see the participants’ names, users can hover the mouse over the **View Participants** button, or click **Show Participant List** to dock the panel in the meeting.</span></span>

  - <span data-ttu-id="9a487-215">Según el tipo de reunión, los usuarios pueden seleccionar entre varias vistas de contenido y participantes diferentes.</span><span class="sxs-lookup"><span data-stu-id="9a487-215">Depending on the meeting type, users can select from several different content and participant views.</span></span>

  - <span data-ttu-id="9a487-216">Las grabaciones de reuniones se guardan automáticamente en un formato que se reproduce en el reproductor de Windows Media (MP4).</span><span class="sxs-lookup"><span data-stu-id="9a487-216">Meeting recordings are automatically saved in a format that plays in Windows Media Player (MP4).</span></span> <span data-ttu-id="9a487-217">Los usuarios pueden compartir fácilmente el archivo con cualquier usuario o usar la característica **publicar** del administrador de grabaciones para publicar la grabación en una ubicación compartida.</span><span class="sxs-lookup"><span data-stu-id="9a487-217">Users can easily share the file with anyone, or use the **Publish** feature in recording manager to post the recording on a shared location.</span></span>

  - <span data-ttu-id="9a487-218">OneNote habilita nuevas formas de colaborar en una reunión.</span><span class="sxs-lookup"><span data-stu-id="9a487-218">OneNote enables new ways to collaborate in a meeting.</span></span> <span data-ttu-id="9a487-219">Durante una reunión, los usuarios pueden tomar notas con OneNote para su uso personal después de la reunión, o usar blocs de notas compartidos y realizar la edición conjunta con participantes en la reunión en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="9a487-219">During a meeting, users can take notes with OneNote for personal use after the meeting, or use shared notebooks and co-edit with meeting participants in real time.</span></span> <span data-ttu-id="9a487-220">Todos los miembros del equipo pueden acceder a las notas compartidas para colaborar en la información, recopilar ideas o usar las páginas de los blocs de notas como una pizarra virtual.</span><span class="sxs-lookup"><span data-stu-id="9a487-220">All team members can access the shared notes to contribute information, brainstorm ideas, or use the notebook pages as a virtual whiteboard.</span></span> <span data-ttu-id="9a487-221">Las personas y el contenido compartido en la reunión se agregan automáticamente a las notas.</span><span class="sxs-lookup"><span data-stu-id="9a487-221">People and content shared in the meeting are automatically added to the Notes.</span></span>

  - <span data-ttu-id="9a487-222">Los usuarios pueden cambiar entre los tipos de contenido mediante **compartir contenido y coordinar actividades de reunión** en la parte inferior de la sala de reuniones.</span><span class="sxs-lookup"><span data-stu-id="9a487-222">Users can switch between content types using **Share content and lead meeting activities** at the bottom of the meeting room.</span></span> <span data-ttu-id="9a487-223">Los usuarios también pueden usar el menú **administrar contenido** presentable para elegir el contenido que desean compartir.</span><span class="sxs-lookup"><span data-stu-id="9a487-223">Users can also use the **Manage Presentable Content** menu to choose which content they want to share.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9a487-224">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9a487-224">See Also</span></span>


[<span data-ttu-id="9a487-225">Planeación de clientes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a487-225">Planning for clients in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

