---
title: 'Lync Server 2013: Novedades para clientes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: What's new for clients
ms:assetid: 5c144677-4d58-4fc3-8445-74b76c9fcf07
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204933(v=OCS.15)
ms:contentKeyID: 48184253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf37f68d0ea11e17a799956f285d8ca82eb2a27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="whats-new-for-clients-in-lync-server-2013"></a><span data-ttu-id="70254-102">Novedades para clientes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70254-102">What's new for clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70254-103">_**Última modificación del tema:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="70254-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="70254-104">Microsoft Lync 2013 tiene una interfaz de usuario rediseñada y características nuevas importantes.</span><span class="sxs-lookup"><span data-stu-id="70254-104">Microsoft Lync 2013 has a redesigned user interface and important new features.</span></span> <span data-ttu-id="70254-105">Para los administradores, el cliente está ahora incluido con el programa de instalación de Office, lo que proporciona un método más simplificado para implementar Office y personalizar clientes de su organización.</span><span class="sxs-lookup"><span data-stu-id="70254-105">For administrators, the client is now included with the Office setup program, providing a more streamlined approach to deploying Office and customizing clients in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70254-106">Para ver una vista ilustrada de actualizaciones de la interfaz de usuario de Lync 2013, vea "Novedades de <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>Lync 2013" en.</span><span class="sxs-lookup"><span data-stu-id="70254-106">For an illustrated view of Lync 2013 user interface updates, see “What’s New in Lync 2013” at <A href="http://go.microsoft.com/fwlink/?linkid=273885">http://go.microsoft.com/fwlink/?LinkId=273885</A>.</span></span>



</div>

<div>

## <a name="integration-with-office-setup"></a><span data-ttu-id="70254-107">Integración con la configuración de Office</span><span class="sxs-lookup"><span data-stu-id="70254-107">Integration with Office Setup</span></span>

<span data-ttu-id="70254-108">El cliente de Lync 2013 y el complemento de reunión en línea para Lync 2013 (que admite la administración de reuniones desde el cliente de mensajería y colaboración de Outlook) ya están incluidos en el programa de instalación de Office 2013.</span><span class="sxs-lookup"><span data-stu-id="70254-108">The Lync 2013 client and the Online Meeting Add-in for Lync 2013—which supports meeting management from within the Outlook messaging and collaboration client—are now both included with the Office 2013 Setup program.</span></span>

<span data-ttu-id="70254-109">En versiones anteriores de Lync y Office Communicator, se pueden usar las propiedades de Windows Installer para personalizar y controlar la instalación de Office.</span><span class="sxs-lookup"><span data-stu-id="70254-109">In previous versions of Lync and Office Communicator, you could use Windows Installer properties to customize and control the Office installation.</span></span> <span data-ttu-id="70254-110">Puesto que Lync 2013 está integrado con el programa de instalación de Office, puede usar los siguientes métodos para personalizar la configuración de Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="70254-110">Because Lync 2013 is integrated with Office setup, you can use the following methods to customize Lync 2013 setup:</span></span>

  - <span data-ttu-id="70254-111">Usar la Herramienta de personalización de Office (OCT)</span><span class="sxs-lookup"><span data-stu-id="70254-111">Use the Office Customization Tool (OCT)</span></span>

  - <span data-ttu-id="70254-112">Usar el archivo config. XML para realizar tareas de instalación</span><span class="sxs-lookup"><span data-stu-id="70254-112">Use the Config.xml to perform installation tasks</span></span>

  - <span data-ttu-id="70254-113">Usar las opciones de la línea de comandos de configuración</span><span class="sxs-lookup"><span data-stu-id="70254-113">Use Setup Command-Line Options</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70254-114">El programa de instalación de Lync 2013 no desinstala versiones anteriores de Lync u Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="70254-114">The Lync 2013 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="70254-115">El cliente de Lync 2013 se instala en paralelo con otros clientes de Lync u Office Communicator</span><span class="sxs-lookup"><span data-stu-id="70254-115">The Lync 2013 client installs side-by-side with other Lync or Office Communicator clients</span></span>



</div>

<span data-ttu-id="70254-116">Para obtener más información, vea [implementación de clientes de Lync en Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="70254-116">For details, see [Deploying Lync clients in Lync Server 2013](lync-server-2013-deploying-lync-clients.md).</span></span>

</div>

<div>

## <a name="group-policy-deployment"></a><span data-ttu-id="70254-117">Implementación de directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="70254-117">Group Policy Deployment</span></span>

<span data-ttu-id="70254-118">Puesto que Lync 2013 ahora está incluido en el programa de instalación de Office, el método para implementar la configuración de la Directiva de grupo de Lync ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="70254-118">Because Lync 2013 is now included in Office setup, the method for deploying Lync Group Policy settings has changed.</span></span> <span data-ttu-id="70254-119">En las versiones anteriores de Lync y Office Communicator, se puede usar Communicator. ADM para definir la configuración de directiva de grupo, mientras que en Lync 2013 ahora puede usar las plantillas administrativas de ADMX y ADML de Lync que se proporcionan junto con la Directiva de grupo de Office. Plantillas administrativas.</span><span class="sxs-lookup"><span data-stu-id="70254-119">In previous versions of Lync and Office Communicator, you could use the Communicator.adm to define Group Policy settings, whereas in Lync 2013 you can now use the Lync ADMX and ADML administrative templates that are provided along with the Office Group Policy Administrative Templates.</span></span>

<span data-ttu-id="70254-120">Para obtener más información, consulte [configuración de directiva de grupo para Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="70254-120">For details, see [Group Policy settings for Lync 2013](lync-server-2013-group-policy-settings-for-lync-2013.md).</span></span>

</div>

<div>

## <a name="outlook-scheduling-add-in-updates"></a><span data-ttu-id="70254-121">Actualizaciones de complementos de programación de Outlook</span><span class="sxs-lookup"><span data-stu-id="70254-121">Outlook Scheduling Add-in Updates</span></span>

<span data-ttu-id="70254-122">El complemento de reunión en línea para Lync 2013 incluye personalización de invitaciones de reuniones y nuevas opciones de reunión.</span><span class="sxs-lookup"><span data-stu-id="70254-122">The Online Meeting Add-in for Lync 2013 includes meeting invite customization and new meeting options.</span></span>

  - <span data-ttu-id="70254-123">Los administradores pueden personalizar las invitaciones a reuniones de la organización agregando un logotipo personalizado, una dirección URL de soporte técnico, una dirección URL de renuncia legal o texto de pie de página personalizado.</span><span class="sxs-lookup"><span data-stu-id="70254-123">Administrators can customize the organization’s meeting invitations by adding a custom logo, a support URL, a legal disclaimer URL, or custom footer text.</span></span> <span data-ttu-id="70254-124">Para obtener más información, consulte [personalizar el complemento de reunión en línea en Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="70254-124">For details, see [Customizing the Online Meeting Add-in in Lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md).</span></span>

  - <span data-ttu-id="70254-125">Los controles de silencio de nuevo asistente permiten a los organizadores de reuniones programar conferencias en las que el asistente está silenciado de audio y vídeo de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="70254-125">New attendee mute controls allow meeting organizers to schedule conferences that have attendee audio and video muted by default.</span></span>

</div>

<div>

## <a name="virtual-desktop-infrastructure-plug-in"></a><span data-ttu-id="70254-126">Complemento de infraestructura de escritorio virtual</span><span class="sxs-lookup"><span data-stu-id="70254-126">Virtual Desktop Infrastructure Plug-in</span></span>

<span data-ttu-id="70254-127">El cliente de Lync 2013 ahora admite audio y vídeo en un entorno de infraestructura de escritorio virtual (VDI).</span><span class="sxs-lookup"><span data-stu-id="70254-127">The Lync 2013 client now supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="70254-128">Un usuario puede conectar un dispositivo de audio o vídeo (por ejemplo, unos auriculares con micrófono o una cámara) al equipo local (por ejemplo, un equipo de cliente ligero o un equipo con un propósito).</span><span class="sxs-lookup"><span data-stu-id="70254-128">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="70254-129">El usuario puede conectarse a la máquina virtual, inicie sesión en el cliente de Lync 2013 que se ejecuta en la máquina virtual y participe en la comunicación de audio y vídeo en tiempo real como si el cliente se ejecuta de forma local.</span><span class="sxs-lookup"><span data-stu-id="70254-129">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communication as though the client is running locally.</span></span> <span data-ttu-id="70254-130">Las siguientes características son compatibles con un entorno de escritorio virtual:</span><span class="sxs-lookup"><span data-stu-id="70254-130">The following features are supported in a virtual desktop environment:</span></span>

  - <span data-ttu-id="70254-131">Integración de dispositivos para audio y vídeo, entre los que se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="70254-131">Device integration for audio and video, including the following:</span></span>
    
      - <span data-ttu-id="70254-132">Llamar a controles desde el dispositivo</span><span class="sxs-lookup"><span data-stu-id="70254-132">Call controls from the device</span></span>
    
      - <span data-ttu-id="70254-133">Integración de presencia en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="70254-133">Presence integration on the device</span></span>
    
      - <span data-ttu-id="70254-134">Compatibilidad con varios HID (dispositivo de interfaz humana)</span><span class="sxs-lookup"><span data-stu-id="70254-134">Multiple HID (human interface device) support</span></span>

  - <span data-ttu-id="70254-135">Soporte de servicios de emergencia y ubicación.</span><span class="sxs-lookup"><span data-stu-id="70254-135">Location and emergency services support.</span></span>

  - <span data-ttu-id="70254-136">Compatibilidad con todas las modalidades de Lync, como la mensajería instantánea, el audio, el vídeo, el uso compartido de aplicaciones, el uso compartido de PowerPoint, la pizarra y la transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="70254-136">Support for all Lync modalities, including IM, audio, video, application sharing, desktop sharing, PowerPoint sharing, whiteboard, and file transfer.</span></span>

  - <span data-ttu-id="70254-137">Compatibilidad de audio y vídeo en llamadas entre usuarios y llamadas en conferencia.</span><span class="sxs-lookup"><span data-stu-id="70254-137">Audio and video support in person-to-person calls and conference calls.</span></span>

<span data-ttu-id="70254-138">Para obtener información sobre cómo implementar el complemento VDI, consulte [implementar el complemento de VDI para Lync en Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span><span class="sxs-lookup"><span data-stu-id="70254-138">For information about deploying the VDI plug-in, see [Deploying the Lync VDI plug-in in Lync Server 2013](lync-server-2013-deploying-the-lync-vdi-plug-in.md).</span></span>

</div>

<div>

## <a name="video-enhancements"></a><span data-ttu-id="70254-139">Mejoras de video</span><span class="sxs-lookup"><span data-stu-id="70254-139">Video Enhancements</span></span>

<span data-ttu-id="70254-140">Varias características nuevas mejoran significativamente la experiencia de vídeo para los participantes de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="70254-140">Several new features significantly enhance the video experience for conference participants.</span></span>

  - <span data-ttu-id="70254-141">El video se ha mejorado con la detección de rostro y las tramas inteligentes, de modo que el video de un participante se mueve para ayudarle a mantenerlos centrados en el marco.</span><span class="sxs-lookup"><span data-stu-id="70254-141">Video is enhanced with face detection and smart framing, so that a participant’s video moves to help keep them centered in the frame.</span></span>

  - <span data-ttu-id="70254-142">Ahora se admite el video de alta definición en las llamadas de dos participantes y en las conferencias de varias partes.</span><span class="sxs-lookup"><span data-stu-id="70254-142">High-definition video is now supported in two-party calls and multiparty conferences.</span></span> <span data-ttu-id="70254-143">Los usuarios pueden tener resoluciones de hasta HD 1080P.</span><span class="sxs-lookup"><span data-stu-id="70254-143">Users can experience resolutions up to HD 1080P.</span></span>

  - <span data-ttu-id="70254-144">Los participantes pueden seleccionar entre diferentes diseños de reunión: la vista de Galería muestra las imágenes o los vídeos de todos los participantes; Vista de orador muestra el contenido de la reunión y solo el vídeo o la imagen del orador; La vista de presentación muestra solo el contenido de la reunión; La vista compacta muestra solo los controles de la reunión.</span><span class="sxs-lookup"><span data-stu-id="70254-144">Participants can select from different meeting layouts: Gallery View shows all participants’ pictures or videos; Speaker View shows the meeting content and only the current speaker’s video or picture; Presentation View shows meeting content only; Compact View shows just the meeting controls.</span></span>

  - <span data-ttu-id="70254-145">Con la nueva característica de galería, los participantes pueden ver varias fuentes de video al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="70254-145">With the new Gallery feature, participants can see multiple video feeds at the same time.</span></span> <span data-ttu-id="70254-146">Si la Conferencia tiene más de cinco participantes, las fuentes de vídeo de los participantes más activos aparecerán en la fila superior y las imágenes aparecerán para los demás participantes.</span><span class="sxs-lookup"><span data-stu-id="70254-146">If the conference has more than five participants, video feeds of only the most active participants appear in the top row, and pictures appear for the other participants.</span></span>

  - <span data-ttu-id="70254-147">Los participantes pueden usar el anclaje de video para seleccionar una o varias de las fuentes de video disponibles para que sean visibles en todo momento.</span><span class="sxs-lookup"><span data-stu-id="70254-147">Participants can use video pinning to select one or more of the available video feeds to be visible at all times.</span></span>

  - <span data-ttu-id="70254-148">Los moderadores pueden usar la característica noticias destacadas de vídeo para seleccionar una fuente de vídeo de una persona para que todos los participantes de la reunión puedan ver únicamente a ese participante.</span><span class="sxs-lookup"><span data-stu-id="70254-148">Presenters can use the Video Spotlight feature to select one person’s video feed so that every participant in the meeting sees that participant only.</span></span>

</div>

<div>

## <a name="chat-room-integration"></a><span data-ttu-id="70254-149">Integración del salón de chat</span><span class="sxs-lookup"><span data-stu-id="70254-149">Chat Room Integration</span></span>

<span data-ttu-id="70254-150">Lync 2013 ahora integra las características proporcionadas previamente por la conversación grupal de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="70254-150">Lync 2013 now integrates the features previously provided by Lync 2010 Group Chat.</span></span> <span data-ttu-id="70254-151">Ya no se necesita un cliente de conversación grupal independiente.</span><span class="sxs-lookup"><span data-stu-id="70254-151">A separate group chat client is no longer required.</span></span>

  - <span data-ttu-id="70254-152">Desde dentro de Lync 2013, los usuarios pueden buscar salas de chats, agregar salones de chat a sus contactos, supervisar la actividad de los salones de chat y leer y publicar mensajes.</span><span class="sxs-lookup"><span data-stu-id="70254-152">From within Lync 2013, users can search for chat rooms, add chat rooms to their contacts, monitor chat room activity, and read and post messages.</span></span>

  - <span data-ttu-id="70254-153">Los usuarios pueden crear fuentes de temas para que reciban una notificación si alguien de uno de sus salones de chat agrega una publicación que contiene palabras clave específicas.</span><span class="sxs-lookup"><span data-stu-id="70254-153">Users can create topic feeds so that they’ll be notified if someone in one of their chat rooms adds a post containing specific keywords.</span></span>

  - <span data-ttu-id="70254-154">Con la página nuevas opciones de **chat persistente** , los usuarios pueden configurar alertas y sonidos de notificación que se aplican cuando los usuarios publican mensajes en sus salones de chat.</span><span class="sxs-lookup"><span data-stu-id="70254-154">With the new **Persistent Chat** options page, users can set notification alerts and sounds that apply when people post messages to their chat rooms.</span></span>

</div>

<div>

## <a name="lync-web-app-updates"></a><span data-ttu-id="70254-155">Actualizaciones de Lync Web App</span><span class="sxs-lookup"><span data-stu-id="70254-155">Lync Web App Updates</span></span>

<span data-ttu-id="70254-156">Lync Web App es el cliente de conferencia basado en web para reuniones de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="70254-156">Lync Web App is the web-based conferencing client for Lync Server 2013 meetings.</span></span> <span data-ttu-id="70254-157">En esta versión, la adición de audio y vídeo de PC a Lync Web App proporciona una experiencia de reunión completa para cualquier persona que no tenga un cliente Lync instalado de forma local.</span><span class="sxs-lookup"><span data-stu-id="70254-157">In this release, the addition of computer audio and video to Lync Web App provides a complete in-meeting experience for anyone who doesn’t have a Lync client installed locally.</span></span> <span data-ttu-id="70254-158">Los participantes de las reuniones obtienen acceso a todas las características de uso compartido y colaboración, y a todos los controles de la reunión del moderador.</span><span class="sxs-lookup"><span data-stu-id="70254-158">Meeting participants have access to all collaboration and sharing features and presenter meeting controls.</span></span>

<span data-ttu-id="70254-159">Cuando un usuario intenta unirse a una reunión pero no tiene un cliente instalado localmente, se abre Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="70254-159">When a user tries to join a meeting but doesn’t have a locally installed client, Lync Web App opens.</span></span> <span data-ttu-id="70254-160">Si desea permitir opciones adicionales para unirse a la reunión, puede configurar la página de la combinación de reuniones; consulte [configurar la página de la combinación de reuniones en Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="70254-160">If you want to allow additional options for joining the meeting, you can configure the Meeting Join page; see [Configuring the meeting join page in Lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md) in the Deployment documentation.</span></span>

<span data-ttu-id="70254-161">Debido a las mejoras de Lync Web App, no está disponible una versión actualizada del Asistente para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="70254-161">Because of the enhancements to Lync Web App, an updated version of Attendee isn’t available for Lync Server 2013.</span></span> <span data-ttu-id="70254-162">Lync Web App es el cliente que elige para los participantes fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="70254-162">Lync Web App is the client of choice for participants outside your organization.</span></span> <span data-ttu-id="70254-163">No se requiere instalación de cliente local, aunque las características de audio, vídeo y uso compartido requieren que se instale un complemento al utilizar por primera vez.</span><span class="sxs-lookup"><span data-stu-id="70254-163">No local client installation is required, although audio, video, and sharing features require a plug-in to be installed at first use.</span></span>

</div>

<div>

## <a name="lync-2013-for-mobile-clients-updates"></a><span data-ttu-id="70254-164">Lync 2013 para actualizaciones de clientes móviles</span><span class="sxs-lookup"><span data-stu-id="70254-164">Lync 2013 for Mobile Clients Updates</span></span>

<span data-ttu-id="70254-165">Además de las capacidades mejoradas de presencia, contactos y mensajería instantánea, los clientes móviles de Lync 2013 ahora proporcionan llamadas y videollamadas a través de Internet y de las conexiones de datos móviles.</span><span class="sxs-lookup"><span data-stu-id="70254-165">In addition to enhanced presence, contacts, and IM capabilities, Lync 2013 mobile clients now provide voice and video calling over the Internet and cellular data connections.</span></span> <span data-ttu-id="70254-166">Con un solo toque en el vínculo de la reunión en un elemento de calendario, los usuarios móviles pueden unirse a reuniones de Lync y de vídeo.</span><span class="sxs-lookup"><span data-stu-id="70254-166">With a single tap of the meeting link in a calendar item, mobile users can join Lync voice and video meetings.</span></span> <span data-ttu-id="70254-167">Para obtener más información sobre los clientes móviles de Lync 2013, consulte [planificación de clientes móviles en Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span><span class="sxs-lookup"><span data-stu-id="70254-167">For more information about Lync 2013 mobile clients, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>

</div>

<div>

## <a name="lync-2013-user-interface-updates"></a><span data-ttu-id="70254-168">Actualizaciones de la interfaz de usuario de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="70254-168">Lync 2013 User Interface Updates</span></span>

<div>

## <a name="accessibility-updates"></a><span data-ttu-id="70254-169">Actualizaciones de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="70254-169">Accessibility Updates</span></span>

<span data-ttu-id="70254-170">Lync 2013 incorpora varias nuevas características de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="70254-170">Lync 2013 incorporates several new accessibility features.</span></span>

  - <span data-ttu-id="70254-171">Lync 2013 admite una resolución alta de PPP, lo que permite a los usuarios ajustar el texto y los gráficos de 125% y 150 puntos por pulgada.</span><span class="sxs-lookup"><span data-stu-id="70254-171">Lync 2013 supports high DPI resolution, enabling users to scale text and graphics for 125% and 150% dots per inch.</span></span>

  - <span data-ttu-id="70254-172">Lync proporciona compatibilidad de contraste alto para que la interfaz de usuario siga funcionando completamente cuando se usa con los temas de contraste alto de Windows.</span><span class="sxs-lookup"><span data-stu-id="70254-172">Lync provides high-contrast support so that the user interface remains fully functional when used with high contrast themes in Windows.</span></span>

  - <span data-ttu-id="70254-173">Lync ofrece más de 100 métodos abreviados de teclado para que los usuarios puedan obtener acceso a funciones importantes sin un mouse.</span><span class="sxs-lookup"><span data-stu-id="70254-173">Lync offers more than 100 keyboard shortcuts so that users can access important functions without a mouse.</span></span> <span data-ttu-id="70254-174">Por ejemplo, los usuarios pueden presionar ALT + C para aceptar una llamada o Alt + I para ignorarla, sin tener que utilizar la tecla TAB o establecer el foco.</span><span class="sxs-lookup"><span data-stu-id="70254-174">For example, users can press Alt+C to accept a call, or Alt + I to ignore it, without having to tab or set the focus.</span></span> <span data-ttu-id="70254-175">Si pulsa (Alt + Q) finaliza una llamada, (Ctrl + N) inicia OneNote y (Alt + T) se abre el menú herramientas.</span><span class="sxs-lookup"><span data-stu-id="70254-175">Pressing (Alt+Q) ends a call, (Ctrl+N) starts OneNote, and (Alt+T) opens the Tools menu.</span></span>

  - <span data-ttu-id="70254-176">La compatibilidad con un lector de pantalla extensivo en Lync 2013 garantiza que todas las notificaciones, las solicitudes entrantes y los mensajes instantáneos se lean en voz alta cuando se habilita un lector de pantalla.</span><span class="sxs-lookup"><span data-stu-id="70254-176">Extensive screen reader support in Lync 2013 ensures that all notifications, incoming requests, and instant messages are read aloud when a screen reader is enabled.</span></span>

</div>

<div>

## <a name="presence-while-sharing"></a><span data-ttu-id="70254-177">Presencia al compartir</span><span class="sxs-lookup"><span data-stu-id="70254-177">Presence While Sharing</span></span>

<span data-ttu-id="70254-178">Cuando Lync detecta que un usuario está compartiendo, Lync asigna automáticamente un estado de presencia para el usuario.</span><span class="sxs-lookup"><span data-stu-id="70254-178">When Lync detects that a user is sharing, Lync automatically assigns the user a Presenting presence status.</span></span> <span data-ttu-id="70254-179">Este estado bloquea todas las comunicaciones entrantes a menos que el remitente tenga asignada la relación de privacidad grupo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="70254-179">This status blocks all incoming communications unless the sender is assigned the Workgroup privacy relationship.</span></span> <span data-ttu-id="70254-180">Si el usuario usa la característica de uso compartido por completo en un monitor secundario, Lync no asigna un estado de presencia de presentación.</span><span class="sxs-lookup"><span data-stu-id="70254-180">If the user is using the sharing feature entirely on a secondary monitor, Lync does not assign a Presenting presence status.</span></span>

</div>

<div>

## <a name="conversation-window-updates"></a><span data-ttu-id="70254-181">Actualizaciones de la ventana de conversación</span><span class="sxs-lookup"><span data-stu-id="70254-181">Conversation Window Updates</span></span>

<span data-ttu-id="70254-182">La ventana de conversación rediseñada ofrece un acceso más rápido a las características importantes.</span><span class="sxs-lookup"><span data-stu-id="70254-182">The redesigned Conversation window provides quicker access to important features.</span></span>

  - <span data-ttu-id="70254-183">Con la nueva característica de conversaciones en pestañas, los usuarios pueden conservar todos los mensajes instantáneos y salones de chat en una ventana de conversación.</span><span class="sxs-lookup"><span data-stu-id="70254-183">With the new tabbed conversations feature, users can now keep all their IMs and chat rooms in one Conversation window.</span></span> <span data-ttu-id="70254-184">Las pestañas de la parte izquierda de la ventana de conversación permiten a los usuarios desplazarse fácilmente entre todas las conversaciones activas.</span><span class="sxs-lookup"><span data-stu-id="70254-184">The tabs along the left side of the Conversation window let users navigate easily among all active conversations.</span></span>

  - <span data-ttu-id="70254-185">Los usuarios pueden mostrar una conversación individual en una ventana independiente y, a continuación, cambiar el tamaño de la ventana.</span><span class="sxs-lookup"><span data-stu-id="70254-185">Users can pop out an individual conversation into a separate window, and then resize the window.</span></span> <span data-ttu-id="70254-186">También pueden volver a mostrar la ventana en la ventana de conversación principal.</span><span class="sxs-lookup"><span data-stu-id="70254-186">They can also pop the window back into the main Conversation window.</span></span>

  - <span data-ttu-id="70254-187">Lync 2013 vuelve a abrir las conversaciones de un usuario cuando el usuario cierra sesión e inicia sesión en Lync.</span><span class="sxs-lookup"><span data-stu-id="70254-187">Lync 2013 reopens a user’s conversations when the user signs out and signs back in to Lync.</span></span>

  - <span data-ttu-id="70254-188">Los usuarios pueden agregar rápidamente mensajería instantánea, vídeo, uso compartido de programas, uso compartido de escritorio o herramientas de conferencia web (pizarra, notas de reunión, blocs de notas compartidos y datos adjuntos) a cualquier conversación.</span><span class="sxs-lookup"><span data-stu-id="70254-188">Users can quickly add IM, video, program sharing, desktop sharing, or web conferencing tools (whiteboard, meeting notes, shared notebooks, and attachments) to any conversation.</span></span>

  - <span data-ttu-id="70254-189">En una reunión en la que el vídeo o contenido se comparte, los usuarios pueden mostrar el vídeo de la reunión o el contenido compartido y, a continuación, cambiar el tamaño de la ventana.</span><span class="sxs-lookup"><span data-stu-id="70254-189">In a meeting where video or content is being shared, users can pop out the meeting video or shared content, and then resize the window.</span></span>

</div>

<div>

## <a name="lync-main-window-updates"></a><span data-ttu-id="70254-190">Actualizaciones de la ventana principal de Lync</span><span class="sxs-lookup"><span data-stu-id="70254-190">Lync Main Window Updates</span></span>

<span data-ttu-id="70254-191">El nuevo aspecto simplificado conserva características conocidas, como el campo **¿Qué está sucediendo?** , el selector de estado y el selector **de ubicación** .</span><span class="sxs-lookup"><span data-stu-id="70254-191">The new streamlined look retains familiar features such as the **What’s happening today?** note field, the status selector, and the **Set Your Location** selector.</span></span>

  - <span data-ttu-id="70254-192">Cuando los salones de chat estén habilitados, los usuarios verán un nuevo icono de **salones de chat** en la Página principal de Lync.</span><span class="sxs-lookup"><span data-stu-id="70254-192">When chat rooms are enabled, users see a new **Chat Rooms** icon on the main Lync page.</span></span> <span data-ttu-id="70254-193">Con el icono de los **salones de chat** , los usuarios pueden acceder rápidamente a sus salones de chat y filtros.</span><span class="sxs-lookup"><span data-stu-id="70254-193">With the **Chat Rooms** icon, users can quickly access their chat rooms and filters.</span></span>

  - <span data-ttu-id="70254-194">Los usuarios pueden hacer clic en Ver iconos para cambiar a la vista **contactos** , a la vista de **salones de chat** , a la vista **conversaciones** o a la vista de **teléfono** .</span><span class="sxs-lookup"><span data-stu-id="70254-194">Users can click the view icons to switch to the **Contacts** view, **Chat Rooms** view, **Conversations** view, or **Phone** view.</span></span>

  - <span data-ttu-id="70254-195">Si los usuarios han migrado a Exchange 2013, pueden cargar una imagen de alta resolución.</span><span class="sxs-lookup"><span data-stu-id="70254-195">If users have been migrated to Exchange 2013, they can upload a high resolution picture.</span></span>

</div>

<div>

## <a name="contacts-view-and-contact-card-updates"></a><span data-ttu-id="70254-196">Vista contactos y actualizaciones de tarjetas de contacto</span><span class="sxs-lookup"><span data-stu-id="70254-196">Contacts View and Contact Card Updates</span></span>

<span data-ttu-id="70254-197">Lync 2013 ofrece a los usuarios distintas formas de ver los contactos y grupos en su vista **contactos** .</span><span class="sxs-lookup"><span data-stu-id="70254-197">Lync 2013 gives users different ways to view contacts and groups in their **Contacts** view.</span></span>

  - <span data-ttu-id="70254-198">Con el nuevo almacén de contactos unificado, después de migrar los contactos de Lync de los usuarios a Exchange 2013, los usuarios pueden tener acceso y administrar sus contactos desde Lync 2013, Outlook o Outlook Web App, y sus favoritos permanecen sincronizados.</span><span class="sxs-lookup"><span data-stu-id="70254-198">With the new unified contact store, after users' Lync contacts are migrated to Exchange 2013, the users can access and manage their contacts from Lync 2013, Outlook, or Outlook Web App, and their Favorites stay synchronized.</span></span> <span data-ttu-id="70254-199">Por ejemplo, si un usuario agrega un contacto a favoritos en Outlook, el contacto aparece en el grupo favoritos de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="70254-199">For example, if a user adds a contact to Favorites in Outlook, the contact appears in the Favorites group in Lync 2013.</span></span>

  - <span data-ttu-id="70254-200">Si ha agregado y configurado el proxy XMPP y la puerta de enlace XMPP, los usuarios pueden agregar contactos de socios basados en XMPP para la mensajería instantánea y la presencia.</span><span class="sxs-lookup"><span data-stu-id="70254-200">If you have added and configured the XMPP proxy and XMPP gateway, users can add contacts from XMPP-based partners for instant messaging and presence.</span></span>

  - <span data-ttu-id="70254-201">Una nueva característica **Agregar un contacto que no está en mi organización** ofrece a los usuarios una forma fácil de agregar personas externas a la organización.</span><span class="sxs-lookup"><span data-stu-id="70254-201">A new **Add a Contact That’s Not in My Organization** feature gives users an easy way to add people who are external to the organization.</span></span>

  - <span data-ttu-id="70254-202">Un nuevo grupo de **Favoritos** permite a los usuarios crear una lista de personas con las que los usuarios se comunican con mayor frecuencia para obtener acceso más rápido.</span><span class="sxs-lookup"><span data-stu-id="70254-202">A new **Favorites** group lets users build a list of people users contact most often for quicker access.</span></span>

  - <span data-ttu-id="70254-203">Los usuarios pueden usar la página de opciones de la nueva **lista de contactos** para elegir cómo desean ordenar y mostrar los contactos.</span><span class="sxs-lookup"><span data-stu-id="70254-203">Users can use the new **Contacts List** options page to choose how users want to sort and display contacts.</span></span> <span data-ttu-id="70254-204">Los usuarios pueden seleccionar una vista expandida de dos líneas en la que se muestran las imágenes de los contactos o una vista de una línea comprimida.</span><span class="sxs-lookup"><span data-stu-id="70254-204">Users can select an expanded, two-line view that shows contacts’ pictures, or a condensed one-line view.</span></span> <span data-ttu-id="70254-205">Los usuarios también pueden ordenar los contactos por orden alfabético o por disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="70254-205">Users can also sort contacts alphabetically or by availability.</span></span>

</div>

<div>

## <a name="conferencing-updates"></a><span data-ttu-id="70254-206">Actualizaciones de conferencias</span><span class="sxs-lookup"><span data-stu-id="70254-206">Conferencing Updates</span></span>

<span data-ttu-id="70254-207">Lync 2013 ofrece varias mejoras para las características de conferencia.</span><span class="sxs-lookup"><span data-stu-id="70254-207">Lync 2013 offers several enhancements to conferencing features.</span></span>

  - <span data-ttu-id="70254-208">En función del tipo de reunión, los usuarios pueden silenciar la audiencia y permitir o bloquear el uso compartido de vídeo al programar la reunión.</span><span class="sxs-lookup"><span data-stu-id="70254-208">Depending on the type of meeting, users can now mute the audience and allow or block video sharing when scheduling the meeting.</span></span> <span data-ttu-id="70254-209">Estas opciones están disponibles en la página Opciones de la **reunión** y se recomiendan para reuniones grandes con más de 20 participantes.</span><span class="sxs-lookup"><span data-stu-id="70254-209">These options are available on the **Meeting Options** page and are recommended for large meetings with more than 20 participants.</span></span>

  - <span data-ttu-id="70254-210">Los controles de audio fáciles de usar en la sala de reuniones permiten que el usuario controle las opciones de audio, como silenciar, reactivar el audio, cambiar el dispositivo, etc.</span><span class="sxs-lookup"><span data-stu-id="70254-210">Easy to use audio controls in the meeting room allow the user to control audio options, such as mute, unmute, change device, and so on.</span></span>

  - <span data-ttu-id="70254-211">Al compartir programas, los usuarios pueden seleccionar varios programas para compartirlos si necesitan trabajar con más de un programa.</span><span class="sxs-lookup"><span data-stu-id="70254-211">When sharing programs, users can select multiple programs to share if they need to work with more than one program.</span></span>

  - <span data-ttu-id="70254-212">Ahora los usuarios pueden cargar presentaciones que contienen clips de vídeo cargando el archivo de PowerPoint y haciendo clic con el mouse sobre la diapositiva para mostrar los controles de vídeo, como los controles de reproducción, pausa y audio.</span><span class="sxs-lookup"><span data-stu-id="70254-212">Users can now upload presentations that contain video clips by uploading the PowerPoint file, and pointing the mouse over the slide to display video controls, such as play, pause, and audio controls.</span></span>

  - <span data-ttu-id="70254-213">Durante una reunión, los usuarios pueden combinar otra conversación abierta en la reunión mediante la **combinación de esta llamada** en el menú **más opciones** (**...**).</span><span class="sxs-lookup"><span data-stu-id="70254-213">While in a meeting, users can merge another open conversation into the meeting by using **Merge This Call Into** on the **More Options** (**…**) menu.</span></span>

  - <span data-ttu-id="70254-214">Para ver los nombres de los participantes, los usuarios pueden situar el mouse sobre el botón **Ver participantes** o hacer clic en **Mostrar lista de participantes** para acoplar el panel en la reunión.</span><span class="sxs-lookup"><span data-stu-id="70254-214">To see the participants’ names, users can hover the mouse over the **View Participants** button, or click **Show Participant List** to dock the panel in the meeting.</span></span>

  - <span data-ttu-id="70254-215">Según el tipo de reunión, los usuarios pueden seleccionar entre varias vistas de contenido y participantes diferentes.</span><span class="sxs-lookup"><span data-stu-id="70254-215">Depending on the meeting type, users can select from several different content and participant views.</span></span>

  - <span data-ttu-id="70254-216">Las grabaciones de reuniones se guardan automáticamente en un formato que se reproduce en el reproductor de Windows Media (MP4).</span><span class="sxs-lookup"><span data-stu-id="70254-216">Meeting recordings are automatically saved in a format that plays in Windows Media Player (MP4).</span></span> <span data-ttu-id="70254-217">Los usuarios pueden compartir fácilmente el archivo con cualquier persona o usar la característica **publicar** en el administrador de grabaciones para publicar la grabación en una ubicación compartida.</span><span class="sxs-lookup"><span data-stu-id="70254-217">Users can easily share the file with anyone, or use the **Publish** feature in recording manager to post the recording on a shared location.</span></span>

  - <span data-ttu-id="70254-218">OneNote habilita nuevas maneras de colaborar en una reunión.</span><span class="sxs-lookup"><span data-stu-id="70254-218">OneNote enables new ways to collaborate in a meeting.</span></span> <span data-ttu-id="70254-219">Durante una reunión, los usuarios pueden tomar notas con OneNote para su uso personal después de la reunión, o usar blocs de notas compartidos y coautoría en la reunión en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="70254-219">During a meeting, users can take notes with OneNote for personal use after the meeting, or use shared notebooks and co-edit with meeting participants in real time.</span></span> <span data-ttu-id="70254-220">Todos los miembros del equipo pueden acceder a las notas compartidas para colaborar en la información, recopilar ideas o usar las páginas de los blocs de notas como una pizarra virtual.</span><span class="sxs-lookup"><span data-stu-id="70254-220">All team members can access the shared notes to contribute information, brainstorm ideas, or use the notebook pages as a virtual whiteboard.</span></span> <span data-ttu-id="70254-221">Las personas y el contenido compartido en la reunión se agregan automáticamente a las notas.</span><span class="sxs-lookup"><span data-stu-id="70254-221">People and content shared in the meeting are automatically added to the Notes.</span></span>

  - <span data-ttu-id="70254-222">Los usuarios pueden cambiar de un tipo de contenido a otro usando **compartir contenido y coordinar actividades** de la reunión en la parte inferior de la sala de reuniones.</span><span class="sxs-lookup"><span data-stu-id="70254-222">Users can switch between content types using **Share content and lead meeting activities** at the bottom of the meeting room.</span></span> <span data-ttu-id="70254-223">Los usuarios también pueden usar el menú **administrar contenido** presentable para elegir el contenido que desean compartir.</span><span class="sxs-lookup"><span data-stu-id="70254-223">Users can also use the **Manage Presentable Content** menu to choose which content they want to share.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="70254-224">Vea también</span><span class="sxs-lookup"><span data-stu-id="70254-224">See Also</span></span>


[<span data-ttu-id="70254-225">Planificación de clientes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70254-225">Planning for clients in Lync Server 2013</span></span>](lync-server-2013-planning-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

