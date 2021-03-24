---
title: Guía ancho de banda bajo de Microsoft Teams para EDU
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Artículo de Microsoft Teams para EDU que le ayudará con los problemas de reunión y vídeo relacionados con el ancho de banda bajo. Tanto si es un padre, un formador o un administrador de TI, tiene opciones para mejorar la experiencia con Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: b254bfb89a96efed65e2c1fdba1c345825d81dc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111086"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a><span data-ttu-id="060ba-104">Ayuda para las situaciones de ancho de banda bajo para Teams para EDU</span><span class="sxs-lookup"><span data-stu-id="060ba-104">Help for low bandwidth situations for Teams for EDU</span></span>

<span data-ttu-id="060ba-105">Hay muchos elementos de red cuando se trata de trabajar con Microsoft Teams que pueden afectar el rendimiento, y el ancho de banda bajo es una de las situaciones que pueden resultar completamente fuera de su control.</span><span class="sxs-lookup"><span data-stu-id="060ba-105">There are a lot of network elements when it comes to working with Microsoft Teams that can affect performance, and low bandwidth is one of the situations that can feel entirely out of your control.</span></span> <span data-ttu-id="060ba-106">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="060ba-106">Consider the following:</span></span>

- <span data-ttu-id="060ba-107">Una conexión a Internet de baja velocidad para la escuela.</span><span class="sxs-lookup"><span data-stu-id="060ba-107">A low-speed internet connection for the school.</span></span>
- <span data-ttu-id="060ba-108">Una conexión a Internet de baja velocidad para uno o más alumnos.</span><span class="sxs-lookup"><span data-stu-id="060ba-108">A low-speed internet connection for one or more students.</span></span>
- <span data-ttu-id="060ba-109">Horas del día en que el ancho de banda se reduce debido al uso de la red en un área.</span><span class="sxs-lookup"><span data-stu-id="060ba-109">Times of the day when there is low bandwidth due to network usage in an area.</span></span>
- <span data-ttu-id="060ba-110">Períodos de ancho de banda bajo causados por interrupciones locales no por las escuelas ni por los alumnos, pero que afecta negativamente al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="060ba-110">Low bandwidth periods due to outages local to neither the school nor to students, but which impact performance nonetheless.</span></span>
- <span data-ttu-id="060ba-111">Problemas que no son de ancho de banda (por ejemplo, problema con el hardware) que se hacen pasar por problemas de ancho de banda bajo.</span><span class="sxs-lookup"><span data-stu-id="060ba-111">Non-bandwidth issues (for example, issues with hardware) that masquerade as low bandwidth issues.</span></span>

<span data-ttu-id="060ba-112">Este artículo le proporcionará las mejores prácticas para realizar una amplia variedad de actividades de Teams cuando se enfrente a un problema de ancho de banda bajo.</span><span class="sxs-lookup"><span data-stu-id="060ba-112">This article will give you best practices to follow for a variety of Teams activities when you're faced with a low-bandwidth issue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="060ba-113">Aquí encontrará información sobre [Cómo Microsoft Teams usa la memoria](teams-memory-usage-perf.md), porque además de los problemas de ancho de banda bajo, es posible que tenga problemas de recursos en su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="060ba-113">There's information here on [How Microsoft Teams uses memory](teams-memory-usage-perf.md), because in addition to low bandwidth problems, you may be having resource issues on your device.</span></span> <span data-ttu-id="060ba-114">Si está buscando una guía de red para Microsoft Teams, consulte [Preparar la red de la organización para Microsoft Teams](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="060ba-114">If you're looking for network guidance for Microsoft Teams, review [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

## <a name="resolving-low-bandwidth-issues-for-itadmins"></a><span data-ttu-id="060ba-115">Resolver problemas de ancho de banda bajo para administradores de TI</span><span class="sxs-lookup"><span data-stu-id="060ba-115">Resolving low bandwidth issues for ITAdmins</span></span>

<span data-ttu-id="060ba-116">Lo más importante que debe recordar, como administrador de TI, es que, aunque tenga soluciones para problemas de ancho de banda bajo que sean de amplia difusión y que resolverán los problemas rápidamente, esto debe considerarse con cuidado, ya que algunos problemas pueden resolverse con un enfoque más limitado tomado a nivel del formador o incluso del alumno/padre.</span><span class="sxs-lookup"><span data-stu-id="060ba-116">The important thing to remember, as an ITAdmin, is that while you have solutions for low bandwidth issues that are wide-spread that will resolve problems quickly, this should be considered carefully, as some issues may be able to resolved with a more narrow focus taken at the educator or even the student/parent level.</span></span>

<span data-ttu-id="060ba-117">Es decir, si se produce un problema de ancho de banda bajo para un amplio grupo de alumnos, tomar medidas como un administrador de TI tiene sentido y también tiene sentido si las acciones emprendidas en el nivel de alumno/formador no le han sido útiles.</span><span class="sxs-lookup"><span data-stu-id="060ba-117">In short, if the low bandwidth issue occurs for a wide group of students, taking action as an ITAdmin makes sense, and it also makes sense if the actions taken at the student/educator level haven't been helpful.</span></span>

> [!NOTE]
> <span data-ttu-id="060ba-118">Si tiene tiempo, inviértalo leyendo la [guía de revisión de la calidad de la experiencia](quality-of-experience-review-guide.md), es una lectura valiosa (que aunque no es específica de EDU, aún tendrá información valiosa).</span><span class="sxs-lookup"><span data-stu-id="060ba-118">If you've got the time to invest, the [Quality of Experience Review Guide](quality-of-experience-review-guide.md) is a worthwhile read (this is not EDU-specific, but it will still have valuable information).</span></span> <span data-ttu-id="060ba-119">De esta forma, los administradores de TI experimentados podrán profundizar en la experiencia de los formadores y alumnos.</span><span class="sxs-lookup"><span data-stu-id="060ba-119">This will allow experienced ITAdmins to go in-depth on the experience for their educators and students.</span></span>

### <a name="meetings-and-video"></a><span data-ttu-id="060ba-120">Reuniones y vídeo</span><span class="sxs-lookup"><span data-stu-id="060ba-120">Meetings and video</span></span>

<span data-ttu-id="060ba-121">Un enfoque principal para los problemas de ancho de banda bajo son las reuniones y específicamente el vídeo en las reuniones.</span><span class="sxs-lookup"><span data-stu-id="060ba-121">A primary focus for low bandwidth issues are meetings, and specifically video in meetings.</span></span> <span data-ttu-id="060ba-122">A continuación, tenemos algunas de las acciones que un administrador de TI debe considerar cuando se trata de problemas informados por alumnos o formadores con respecto a tener la mejor experiencia de reunión en un entorno educativo.</span><span class="sxs-lookup"><span data-stu-id="060ba-122">We have some of the actions below that an ITAdmin should consider when dealing with issues reported by students or educators in regard to having the best meeting experience in an educational setting.</span></span>

#### <a name="meeting-policies"></a><span data-ttu-id="060ba-123">Directivas de reunión</span><span class="sxs-lookup"><span data-stu-id="060ba-123">Meeting policies</span></span>

<span data-ttu-id="060ba-124">En lo que respecta a las reuniones, una de las áreas más relacionadas para las situaciones de ancho de banda baja tiene que ver con los vídeos.</span><span class="sxs-lookup"><span data-stu-id="060ba-124">In regards to meetings, one of the most concerning areas for low bandwidth situations has to do with videos.</span></span> <span data-ttu-id="060ba-125">Por fortuna, además de que Teams puede escalar el ancho de banda detectado automáticamente, usted, como administrador de TI dispone de opciones de directiva que puede establecer en el nivel de organizador y/o usuario, para brindar a todos la mejor experiencia considerando el ancho de banda que tienen para trabajar en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="060ba-125">Fortunately, in addition to Teams being able to scale to detected bandwidth automatically, you as an ITAdmin have policy options you can set at the per-organizer and/or per-user level to give everyone the best experience in light of the bandwidth they have to work with at a given time.</span></span>

<span data-ttu-id="060ba-126">Entre las cosas que puede establecer mediante la directiva se incluyen:</span><span class="sxs-lookup"><span data-stu-id="060ba-126">Some of the things you can set via policy include:</span></span>

- <span data-ttu-id="060ba-127">Deshabilitar el vídeo completamente, para que nadie pueda habilitarlo.</span><span class="sxs-lookup"><span data-stu-id="060ba-127">Disabling video altogether, so no one could enable it.</span></span>
- <span data-ttu-id="060ba-128">Tasa de bits multimedia (se define por usuario).</span><span class="sxs-lookup"><span data-stu-id="060ba-128">Media bit rate (this is set per-user).</span></span>

<span data-ttu-id="060ba-129">Para obtener más información sobre sus opciones, y para ver las especificaciones específicas de las directivas que necesitaría establecer para las reuniones y el vídeo, consulte [Configuración de la directiva de reuniones en Teams: audio y vídeo](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video) para obtener información detallada.</span><span class="sxs-lookup"><span data-stu-id="060ba-129">To learn more about your options, and to walk through the specifics of what policies you'd need to set for meetings and video, check out [Meeting policy settings in Teams: Audio and video](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video) for detailed walk-through information.</span></span>

#### <a name="screen-sharing-policies"></a><span data-ttu-id="060ba-130">Directivas de uso compartido de pantalla</span><span class="sxs-lookup"><span data-stu-id="060ba-130">Screen sharing policies</span></span>

<span data-ttu-id="060ba-131">En otros casos, los formadores pueden compartir toda la pantalla con los alumnos, cuando el uso compartido debe limitarse a una aplicación relevante para la lección que se está impartiendo.</span><span class="sxs-lookup"><span data-stu-id="060ba-131">In other cases, educators may be sharing their entire screen to students, when sharing should be limited to an application relevant to the lesson being taught.</span></span> <span data-ttu-id="060ba-132">Esto también puede establecerse con una directiva, si esa es una forma más deseable de hacerlo que hacer que los formadores tomen esa decisión individualmente.</span><span class="sxs-lookup"><span data-stu-id="060ba-132">This can also be set via policy, if that's a more desirable way to do it than to have educators making that choice individually.</span></span>

<span data-ttu-id="060ba-133">Para tener una buena idea de lo que puede hacer para limitar la pantalla el uso compartido de la pantalla con la configuración de directivas, consulte [Configuración de la directiva de reuniones en Teams: uso compartido de la pantalla](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video).</span><span class="sxs-lookup"><span data-stu-id="060ba-133">For a good idea of what you can do about limiting screen sharing via policy settings, check out [Meeting policy settings in Teams: Screen sharing](./meeting-policies-in-teams.md#meeting-policy-settings---audio--video).</span></span>

#### <a name="dial-in-number-for-meetings"></a><span data-ttu-id="060ba-134">Número de acceso telefónico para una reunión</span><span class="sxs-lookup"><span data-stu-id="060ba-134">Dial-in number for meetings</span></span>

<span data-ttu-id="060ba-135">Puede ser más fácil para algunos alumnos intentar llamar en algunas sesiones de clase.</span><span class="sxs-lookup"><span data-stu-id="060ba-135">It may be easier for some students to attempt to dial in to some classroom sessions.</span></span> <span data-ttu-id="060ba-136">Puede proporcionar un número de acceso telefónico para reuniones de Teams, de modo que los alumnos que tienen problemas pueden llamar como alternativa para asistir a una reunión de vídeo.</span><span class="sxs-lookup"><span data-stu-id="060ba-136">You can provide a dial-in number for Teams meetings, so students with issues can phone in as an alternative to attending a video meeting.</span></span>

<span data-ttu-id="060ba-137">Para obtener más información sobre esto, puede leer [Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="060ba-137">For more information on this, you can read [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="low-bandwidth-scenarios-as-an-educator"></a><span data-ttu-id="060ba-138">Escenarios de ancho de banda bajo como formador</span><span class="sxs-lookup"><span data-stu-id="060ba-138">Low bandwidth scenarios as an educator</span></span>

<span data-ttu-id="060ba-139">Los formadores deben sentirse capacitados para tomar medidas para resolver problemas de ancho de banda bajo y puede ser una mejor opción que la acción del administrador de TI en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="060ba-139">Educators should feel empowered to take steps to resolve low bandwidth issues, and may be a superior choice to ITAdmin action in the following situations:</span></span>

- <span data-ttu-id="060ba-140">Si el problema es intermitente o relativamente transitorio.</span><span class="sxs-lookup"><span data-stu-id="060ba-140">If the problem is intermittent, or relatively transitory.</span></span>
- <span data-ttu-id="060ba-141">Si hay un momento específico del día, puede anticiparse a un problema o el ancho de banda bajo tiene alguna previsibilidad.</span><span class="sxs-lookup"><span data-stu-id="060ba-141">If there is a specific time of the day you can anticipate there being an issue, or the low bandwidth period has some predictability to it.</span></span>

<span data-ttu-id="060ba-142">En estas situaciones, puede llevar a cabo algunas acciones.</span><span class="sxs-lookup"><span data-stu-id="060ba-142">In these situations, you can take some actions.</span></span>

<span data-ttu-id="060ba-143">Para obtener más información, consulte [Usar Teams para el trabajo escolar cuando el ancho de banda es bajo](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span><span class="sxs-lookup"><span data-stu-id="060ba-143">For more information, check out [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span></span>

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a><span data-ttu-id="060ba-144">Escenarios de ancho de banda bajo como padre o alumno</span><span class="sxs-lookup"><span data-stu-id="060ba-144">Low bandwidth scenarios as a parent or student</span></span>

<span data-ttu-id="060ba-145">También hay situaciones, y debe analizarlas de manera proactiva con los formadores, donde el problema de ancho de banda se encuentra en el lado del alumno (por ejemplo, un gran número de alumnos pueden ver las lecciones de vídeo sin problemas, pero un pequeño número de alumnos tienen dificultades).</span><span class="sxs-lookup"><span data-stu-id="060ba-145">There are also situations, and you should proactively discuss them with your educators, where the bandwidth problem may be on the student's side (for example, a large number of students are able to watch the video lessons without issue, but a small number of students have difficulties).</span></span>

<span data-ttu-id="060ba-146">Es poco probable que sean muchos los padres que puedan solucionar estos problemas. Los problemas de ancho de banda bajo pueden estar fuera del control de un alumno o de los padres (su hogar puede no tener acceso a un ancho de banda alto, pueden que haya muchas personas en el área de consumo inmediato consumiendo ancho de banda y afectando lo que pueden hacer, probablemente el Internet es inestable, etc.).</span><span class="sxs-lookup"><span data-stu-id="060ba-146">It's not reasonable to expect many parents to be able to troubleshoot these issues, and low bandwidth issues may be out of a student or parent's control (their home may not have access to high bandwidth, they may have a lot of people in their immediate area consuming bandwidth and affecting what they can do, there may be internet instability, and so on).</span></span>

<span data-ttu-id="060ba-147">Hemos incorporado una guía en nuestro artículo [Usar Teams para el trabajo escolar cuando el ancho de banda es bajo](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) para padres y alumnos, también puede revisar y probar estas recomendaciones si tiene algún problema.</span><span class="sxs-lookup"><span data-stu-id="060ba-147">We've put together guidance in our [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) article for parents and students as well, you can review and try these recommendations if you're having any problems.</span></span>