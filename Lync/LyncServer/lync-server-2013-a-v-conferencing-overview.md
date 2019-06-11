---
title: Información general de conferencia de Lync Server 2013 A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d477a8423e7e5ee57e54d0bde584edeb02db4608
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="00246-102">Información general sobre las conferencias A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00246-102">Overview of A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00246-103">_**Última modificación del tema:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="00246-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="00246-104">La conferencia A/V permite comunicaciones de audio y vídeo en tiempo real entre los usuarios.</span><span class="sxs-lookup"><span data-stu-id="00246-104">A/V conferencing enables real-time audio and video communications between your users.</span></span> <span data-ttu-id="00246-105">Al implementar las conferencias, puede elegir entre habilitar y usar conferencias web y conferencias A/V, o simplemente conferencias web.</span><span class="sxs-lookup"><span data-stu-id="00246-105">When you deploy conferencing, you can choose to enable and use both web conferencing and A/V conferencing, or just web conferencing.</span></span>

<span data-ttu-id="00246-106">Para planear una conferencia A/V, necesita conocer el ancho de banda necesario para el tipo de medio de conferencia que requiere su organización.</span><span class="sxs-lookup"><span data-stu-id="00246-106">To plan for A/V conferencing, you need to understand the network bandwidth required by the type of conferencing media that your organization requires.</span></span> <span data-ttu-id="00246-107">Esto podría incluir audio, vídeo y vídeo panorámico.</span><span class="sxs-lookup"><span data-stu-id="00246-107">This could include audio, video, and panoramic video.</span></span>

<span data-ttu-id="00246-108">Antes de habilitar a los usuarios para conferencias de A/V, asegúrese de que su red puede controlar la carga resultante.</span><span class="sxs-lookup"><span data-stu-id="00246-108">Before you enable users for A/V conferencing, ensure that your network can handle the resulting load.</span></span> <span data-ttu-id="00246-109">Si el ancho de banda de red no es suficiente, la experiencia del usuario puede verse afectada en gran medida.</span><span class="sxs-lookup"><span data-stu-id="00246-109">Without sufficient network bandwidth, the user experience may be severely degraded.</span></span> <span data-ttu-id="00246-110">Puede usar control de admisión de llamadas (CAC) para administrar el ancho de banda de red usado por conferencias A/V.</span><span class="sxs-lookup"><span data-stu-id="00246-110">You can use call admission control (CAC) to manage the network bandwidth used by A/V Conferencing.</span></span> <span data-ttu-id="00246-111">Esto es importante para redes restringidas, como vínculos de ancho de banda limitados entre los sitios centrales y de sucursal.</span><span class="sxs-lookup"><span data-stu-id="00246-111">This is important for restricted networks, such as limited bandwidth links between central and branch sites.</span></span> <span data-ttu-id="00246-112">Para obtener más información, vea [información general sobre el control de admisión de llamadas en Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="00246-112">For details, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span></span> <span data-ttu-id="00246-113">Para obtener más información sobre los requisitos de ancho de banda de multimedia, consulte [requisitos de ancho de banda de red para el tráfico multimedia en Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span><span class="sxs-lookup"><span data-stu-id="00246-113">For details about media bandwidth requirements, see [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span></span>

<span data-ttu-id="00246-114">Si implementa las audioconferencias en su red, los usuarios necesitarán dispositivos de audio, como pueden ser auriculares, para participar en las audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="00246-114">If you deploy audio conferencing in your network, your users will need audio devices such as headsets to participate in an audio conference.</span></span> <span data-ttu-id="00246-115">Si implementa las videoconferencias, necesita implementar dispositivos de vídeo, como cámaras web para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="00246-115">If you deploy video conferencing, you need to deploy video devices, such as webcams for users.</span></span> <span data-ttu-id="00246-116">Le recomendamos que use dispositivos de comunicaciones unificadas (UC) certificados por Microsoft para todos los tipos de dispositivos, para garantizar una experiencia de usuario óptima.</span><span class="sxs-lookup"><span data-stu-id="00246-116">We recommend that you use unified communications (UC) devices that are certified by Microsoft for all device types, to ensure an optimal user experience.</span></span> <span data-ttu-id="00246-117">Para obtener más información sobre los dispositivos certificados por UC, consulte "teléfonos y dispositivos para [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861)Lync" en.</span><span class="sxs-lookup"><span data-stu-id="00246-117">For details about UC-certified devices, see "Phones and Devices for Lync" at [http://go.microsoft.com/fwlink/p/?LinkId=263861](http://go.microsoft.com/fwlink/p/?linkid=263861).</span></span> <span data-ttu-id="00246-118">Para los dispositivos de audio o vídeo, la implementación de dispositivos y el aprendizaje del usuario, es importante tener en cuenta y planear.</span><span class="sxs-lookup"><span data-stu-id="00246-118">For either audio or video devices, device deployment, and user training are important steps for you to consider and plan for.</span></span>

<span data-ttu-id="00246-119">En las siguientes secciones se describen las características de las conferencias de audio y vídeo, incluida la información sobre la administración del ancho de banda y la selección de los clientes apropiados.</span><span class="sxs-lookup"><span data-stu-id="00246-119">The following sections describe the features for audio and video conferencing, including information about managing bandwidth and selecting the appropriate clients.</span></span>

<div>

## <a name="audio-conferencing-features"></a><span data-ttu-id="00246-120">Características de las conferencias de audio</span><span class="sxs-lookup"><span data-stu-id="00246-120">Audio Conferencing Features</span></span>

<span data-ttu-id="00246-121">Lync Server 2013 ofrece varias características que puede usar para configurar la experiencia de audioconferencia para el usuario, entre las que se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="00246-121">Lync Server 2013 provides several features that you can use to configure the audio conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="00246-122">**Silencio**   de la audiencia el moderador puede usar esta configuración para silenciar a todos los participantes de audio de la Conferencia y poner la Conferencia en un estado en el que los usuarios no pueden reactivar el micrófono.</span><span class="sxs-lookup"><span data-stu-id="00246-122">**Audience mute**   The presenter can use this setting to mute all the audio participants in the conference and put the conference in a state where non-presenters cannot unmute themselves.</span></span>

  - <span data-ttu-id="00246-123">**Entrada de conferencia/salida de anuncios**   si ha habilitado las conferencias de acceso telefónico local, los moderadores pueden usar esta opción para activar o desactivar los anuncios de entrada y salida a fin de minimizar las distracciones mientras una conferencia está en curso.</span><span class="sxs-lookup"><span data-stu-id="00246-123">**Conferencing Entry/Exit Announcements**   If you have enabled dial-in conferencing, presenters can use this setting to turn entry and exit announcements on or off to minimize distractions while a conference is in progress.</span></span>

  - <span data-ttu-id="00246-124">**Agregar un usuario marcando**   los moderadores y los asistentes a los que se le ha concedido permiso pueden agregar números de RTC a las conferencias y hacer que la Conferencia se llame a esos números.</span><span class="sxs-lookup"><span data-stu-id="00246-124">**Adding a user by dialing out**   Presenters and attendees that have been given permission, can add PSTN numbers to the conferences and have the conference dial-out to those numbers.</span></span>

</div>

<div>

## <a name="video-conferencing-features"></a><span data-ttu-id="00246-125">Características de videoconferencias</span><span class="sxs-lookup"><span data-stu-id="00246-125">Video Conferencing Features</span></span>

<span data-ttu-id="00246-126">Lync Server 2013 ofrece varias características que puede usar para configurar la experiencia de videoconferencia para el usuario, entre las que se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="00246-126">Lync Server 2013 provides several features that you can use to configure the video conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="00246-127">**Vista de Galería**   en las videoconferencias que tengan más de dos personas, los usuarios verán automáticamente a todos los participantes de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="00246-127">**Gallery View**   In video conferences that have more than two people, users automatically see everyone in the conference.</span></span> <span data-ttu-id="00246-128">Si la conferencia tiene más de cinco participantes, el vídeo de los participantes más activos se muestra en la fila superior y solo se muestra la foto de los demás participantes.</span><span class="sxs-lookup"><span data-stu-id="00246-128">If the conference has more than five participants, the video of the most active participants appear in the top row and only the photo appears for the other participants.</span></span> <span data-ttu-id="00246-129">De forma predeterminada, el vídeo entre varias partes está activado.</span><span class="sxs-lookup"><span data-stu-id="00246-129">Multiparty video is turned on by default.</span></span> <span data-ttu-id="00246-130">Para obtener detalles sobre la configuración o desactivación del vídeo de varias partes, vea [configurar el ancho de banda de vídeo en Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span><span class="sxs-lookup"><span data-stu-id="00246-130">For details about configuring or turning off multiparty video, see [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

  - <span data-ttu-id="00246-131">**Vídeo panorámico si**   un dispositivo de videoconferencia Roundtable está instalado en el salón de conferencias, esta característica proporciona una vista completa de 360 grados de la sala de conferencias.</span><span class="sxs-lookup"><span data-stu-id="00246-131">**Panoramic Video**   If a RoundTable video conferencing device is installed in the conferencing room, this feature provides a full 360 degree view of the conference room.</span></span> <span data-ttu-id="00246-132">La tira de vídeo panorámico solo está disponible con dispositivos RoundTable.</span><span class="sxs-lookup"><span data-stu-id="00246-132">The panoramic video strip is only available with RoundTable devices.</span></span>

  - <span data-ttu-id="00246-133">**Moderador solo**   los moderadores de modo de vídeo pueden configurar la reunión para que solo se muestre el vídeo del moderador.</span><span class="sxs-lookup"><span data-stu-id="00246-133">**Presenter only video mode**   Presenters can configure the meeting so that only the video from the presenter is shown.</span></span> <span data-ttu-id="00246-134">Así se evitan distracciones en reuniones grandes cuando hay disponibles varias secuencias de vídeo y se bloquean los diferentes orígenes.</span><span class="sxs-lookup"><span data-stu-id="00246-134">This prevents distractions in large meetings when multiple video streams are available and locking to different sources.</span></span> <span data-ttu-id="00246-135">Este modo también se aplica al vídeo capturado y proporcionado por dispositivos RoundTable.</span><span class="sxs-lookup"><span data-stu-id="00246-135">This mode also applies to video captured and provided by RoundTable devices.</span></span>

  - <span data-ttu-id="00246-136">\*\*\*\*   Los usuarios de video de alta definición pueden experimentar resoluciones de hasta 1080p HD en llamadas de dos participantes y en conferencias de varias partes.</span><span class="sxs-lookup"><span data-stu-id="00246-136">**HD video**   Users can experience resolutions up to HD 1080P in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="00246-137">\*\*\*\*   Los moderadores de Spotlight de vídeo pueden configurar la reunión para que los demás participantes de la Conferencia solo vean el vídeo de un participante seleccionado que sea una fuente de video.</span><span class="sxs-lookup"><span data-stu-id="00246-137">**Video Spotlight**   Presenters can configure the meeting so that only the video from a selected participant who is a video source is seen by the other participants in the conference.</span></span> <span data-ttu-id="00246-138">Este modo también se aplica al vídeo capturado y proporcionado por dispositivos RoundTable de vídeo panorámico.</span><span class="sxs-lookup"><span data-stu-id="00246-138">This mode also applies to video captured and provided by RoundTable devices for panoramic video.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

