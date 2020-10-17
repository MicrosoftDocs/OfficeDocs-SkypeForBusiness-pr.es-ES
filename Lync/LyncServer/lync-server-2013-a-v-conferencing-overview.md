---
title: Lync Server 2013 información general sobre conferencias A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: A/V conferencing overview
ms:assetid: 9583de87-4618-4a99-a47a-45e8cc4cc221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619186(v=OCS.15)
ms:contentKeyID: 49733747
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f35ef9adaf4f19023ebe2220494fdb315c782515
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523267"
---
# <a name="overview-of-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="d6729-102">Información general sobre la conferencia A/V en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6729-102">Overview of A/V conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6729-103">_**Última modificación del tema:** 2012-10-13_</span><span class="sxs-lookup"><span data-stu-id="d6729-103">_**Topic Last Modified:** 2012-10-13_</span></span>

<span data-ttu-id="d6729-p101">Las conferencias A/V permiten las comunicaciones de audio y vídeo en tiempo real entre los usuarios. Cuando se implementan conferencias, puede optarse por habilitar y usar conferencia web y conferencia A/V, o únicamente conferencia web.</span><span class="sxs-lookup"><span data-stu-id="d6729-p101">A/V conferencing enables real-time audio and video communications between your users. When you deploy conferencing, you can choose to enable and use both web conferencing and A/V conferencing, or just web conferencing.</span></span>

<span data-ttu-id="d6729-p102">Para planear una conferencia A/V, necesita conocer el ancho de banda necesario para el tipo de medio de conferencia que requiere su organización. Esto podría incluir audio, vídeo y vídeo panorámico.</span><span class="sxs-lookup"><span data-stu-id="d6729-p102">To plan for A/V conferencing, you need to understand the network bandwidth required by the type of conferencing media that your organization requires. This could include audio, video, and panoramic video.</span></span>

<span data-ttu-id="d6729-108">Antes de permitir que los usuarios realicen conferencias A/V, asegúrese de que la red pueda administrar la carga resultante.</span><span class="sxs-lookup"><span data-stu-id="d6729-108">Before you enable users for A/V conferencing, ensure that your network can handle the resulting load.</span></span> <span data-ttu-id="d6729-109">Si el ancho de banda de red no es suficiente, la experiencia del usuario puede verse afectada en gran medida.</span><span class="sxs-lookup"><span data-stu-id="d6729-109">Without sufficient network bandwidth, the user experience may be severely degraded.</span></span> <span data-ttu-id="d6729-110">Puede usar control de admisión de llamadas (CAC) para administrar el ancho de banda de red que usan las conferencias A/V.</span><span class="sxs-lookup"><span data-stu-id="d6729-110">You can use call admission control (CAC) to manage the network bandwidth used by A/V Conferencing.</span></span> <span data-ttu-id="d6729-111">Esto es importante para redes restringidas, como vínculos de ancho de banda limitado entre los sitios central y de sucursal.</span><span class="sxs-lookup"><span data-stu-id="d6729-111">This is important for restricted networks, such as limited bandwidth links between central and branch sites.</span></span> <span data-ttu-id="d6729-112">Para obtener más información, consulte [información general sobre el control de admisión de llamadas en Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="d6729-112">For details, see [Overview of call admission control in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md).</span></span> <span data-ttu-id="d6729-113">Para obtener más información sobre los requisitos de ancho de banda de medios, consulte [requisitos de ancho de banda de red para el tráfico multimedia en Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span><span class="sxs-lookup"><span data-stu-id="d6729-113">For details about media bandwidth requirements, see [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md).</span></span>

<span data-ttu-id="d6729-114">Si implementa una conferencia de audio en la red, los usuarios necesitarán dispositivos de audio, como pueden ser auriculares, para participar en ella.</span><span class="sxs-lookup"><span data-stu-id="d6729-114">If you deploy audio conferencing in your network, your users will need audio devices such as headsets to participate in an audio conference.</span></span> <span data-ttu-id="d6729-115">Si implemente una conferencia de vídeo, necesitará implementar dispositivos de vídeo, como cámaras web para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d6729-115">If you deploy video conferencing, you need to deploy video devices, such as webcams for users.</span></span> <span data-ttu-id="d6729-116">Le recomendamos que use dispositivos de comunicaciones unificadas (UC) certificados por Microsoft para todos los tipos de dispositivos, para garantizar una experiencia de usuario óptima.</span><span class="sxs-lookup"><span data-stu-id="d6729-116">We recommend that you use unified communications (UC) devices that are certified by Microsoft for all device types, to ensure an optimal user experience.</span></span> <span data-ttu-id="d6729-117">Para obtener más información sobre los dispositivos certificados para UC, consulte "teléfonos y dispositivos para Lync" en [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861) .</span><span class="sxs-lookup"><span data-stu-id="d6729-117">For details about UC-certified devices, see "Phones and Devices for Lync" at [https://go.microsoft.com/fwlink/p/?LinkId=263861](https://go.microsoft.com/fwlink/p/?linkid=263861).</span></span> <span data-ttu-id="d6729-118">Tanto para los dispositivos de audio como los de vídeo, la implementación de los dispositivos y el aprendizaje de los usuarios son pasos importantes que hay que tener en cuenta y planear.</span><span class="sxs-lookup"><span data-stu-id="d6729-118">For either audio or video devices, device deployment, and user training are important steps for you to consider and plan for.</span></span>

<span data-ttu-id="d6729-119">En las secciones siguientes se describen las características de las conferencias de audio y vídeo, incluida información sobre cómo administrar el ancho de banda y seleccionar los clientes apropiados.</span><span class="sxs-lookup"><span data-stu-id="d6729-119">The following sections describe the features for audio and video conferencing, including information about managing bandwidth and selecting the appropriate clients.</span></span>

<div>

## <a name="audio-conferencing-features"></a><span data-ttu-id="d6729-120">Características de las conferencias de audio</span><span class="sxs-lookup"><span data-stu-id="d6729-120">Audio Conferencing Features</span></span>

<span data-ttu-id="d6729-121">Lync Server 2013 proporciona varias características que puede usar para configurar la experiencia de audioconferencia del usuario, entre las que se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="d6729-121">Lync Server 2013 provides several features that you can use to configure the audio conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="d6729-122">Silencio de la **audiencia**     El moderador puede usar esta configuración para silenciar a todos los participantes de audio de la Conferencia y poner la Conferencia en un estado en el que no los moderadores no puedan reactivarse.</span><span class="sxs-lookup"><span data-stu-id="d6729-122">**Audience mute**   The presenter can use this setting to mute all the audio participants in the conference and put the conference in a state where non-presenters cannot unmute themselves.</span></span>

  - <span data-ttu-id="d6729-123">Anuncios de entrada **y salida de conferencia**     Si ha habilitado las conferencias de acceso telefónico local, los moderadores pueden usar esta opción para activar o desactivar los anuncios de entrada y salida para minimizar las distracciones mientras una conferencia está en curso.</span><span class="sxs-lookup"><span data-stu-id="d6729-123">**Conferencing Entry/Exit Announcements**   If you have enabled dial-in conferencing, presenters can use this setting to turn entry and exit announcements on or off to minimize distractions while a conference is in progress.</span></span>

  - <span data-ttu-id="d6729-124">**Adición de un usuario mediante llamadas salientes**     Los moderadores y asistentes a los que se haya concedido permiso pueden agregar números RTC a las conferencias y hacer que la Conferencia realice llamadas de salida a esos números.</span><span class="sxs-lookup"><span data-stu-id="d6729-124">**Adding a user by dialing out**   Presenters and attendees that have been given permission, can add PSTN numbers to the conferences and have the conference dial-out to those numbers.</span></span>

</div>

<div>

## <a name="video-conferencing-features"></a><span data-ttu-id="d6729-125">Características de las conferencias de vídeo</span><span class="sxs-lookup"><span data-stu-id="d6729-125">Video Conferencing Features</span></span>

<span data-ttu-id="d6729-126">Lync Server 2013 proporciona varias características que puede usar para configurar la experiencia de las conferencias de vídeo del usuario, entre las que se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="d6729-126">Lync Server 2013 provides several features that you can use to configure the video conferencing experience for the user, including the following:</span></span>

  - <span data-ttu-id="d6729-127">**Vista**     de Galería En las conferencias de vídeo que tienen más de dos personas, los usuarios ven automáticamente a todos los usuarios de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="d6729-127">**Gallery View**   In video conferences that have more than two people, users automatically see everyone in the conference.</span></span> <span data-ttu-id="d6729-128">Si la conferencia tiene más de cinco participantes, el vídeo de los participantes más activos se muestra en la fila superior y solo se muestra la foto de los demás participantes.</span><span class="sxs-lookup"><span data-stu-id="d6729-128">If the conference has more than five participants, the video of the most active participants appear in the top row and only the photo appears for the other participants.</span></span> <span data-ttu-id="d6729-129">De forma predeterminada, el vídeo entre varias partes está activado.</span><span class="sxs-lookup"><span data-stu-id="d6729-129">Multiparty video is turned on by default.</span></span> <span data-ttu-id="d6729-130">Para obtener información detallada acerca de la configuración o desactivación de vídeo entre varias partes, consulte [configuración del ancho de banda de vídeo en Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span><span class="sxs-lookup"><span data-stu-id="d6729-130">For details about configuring or turning off multiparty video, see [Configuring video bandwidth in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).</span></span>

  - <span data-ttu-id="d6729-131">**Vídeo panorámico**     Si hay instalado un dispositivo de videoconferencia RoundTable en la sala de conferencias, esta característica ofrece una vista completa de 360 grados de la sala de conferencias.</span><span class="sxs-lookup"><span data-stu-id="d6729-131">**Panoramic Video**   If a RoundTable video conferencing device is installed in the conferencing room, this feature provides a full 360 degree view of the conference room.</span></span> <span data-ttu-id="d6729-132">La tira de vídeo panorámico solo está disponible con dispositivos RoundTable.</span><span class="sxs-lookup"><span data-stu-id="d6729-132">The panoramic video strip is only available with RoundTable devices.</span></span>

  - <span data-ttu-id="d6729-133">Modo de vídeo **solo Presenter**     Los moderadores pueden configurar la reunión para que solo se muestre el vídeo del moderador.</span><span class="sxs-lookup"><span data-stu-id="d6729-133">**Presenter only video mode**   Presenters can configure the meeting so that only the video from the presenter is shown.</span></span> <span data-ttu-id="d6729-134">Así se evitan distracciones en reuniones grandes cuando hay disponibles varias secuencias de vídeo y se bloquean los diferentes orígenes.</span><span class="sxs-lookup"><span data-stu-id="d6729-134">This prevents distractions in large meetings when multiple video streams are available and locking to different sources.</span></span> <span data-ttu-id="d6729-135">Este modo también se aplica al vídeo capturado y proporcionado por dispositivos RoundTable.</span><span class="sxs-lookup"><span data-stu-id="d6729-135">This mode also applies to video captured and provided by RoundTable devices.</span></span>

  - <span data-ttu-id="d6729-136">**Vídeo HD**     Los usuarios pueden experimentar resoluciones de hasta HD 1080P en llamadas de dos participantes y conferencias con varios participantes.</span><span class="sxs-lookup"><span data-stu-id="d6729-136">**HD video**   Users can experience resolutions up to HD 1080P in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="d6729-137">**Foco**     de vídeo Los moderadores pueden configurar la reunión para que los otros participantes de la Conferencia solo vean el vídeo de un participante seleccionado que sea un origen de vídeo.</span><span class="sxs-lookup"><span data-stu-id="d6729-137">**Video Spotlight**   Presenters can configure the meeting so that only the video from a selected participant who is a video source is seen by the other participants in the conference.</span></span> <span data-ttu-id="d6729-138">Este modo también se aplica al vídeo capturado y proporcionado por dispositivos RoundTable de vídeo panorámico.</span><span class="sxs-lookup"><span data-stu-id="d6729-138">This mode also applies to video captured and provided by RoundTable devices for panoramic video.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

