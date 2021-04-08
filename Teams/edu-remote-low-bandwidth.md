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
ms.openlocfilehash: 17520645f23500550c6bc991c9d25ad2f72b2b6e
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598429"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a><span data-ttu-id="c25a4-104">Ayuda para las situaciones de ancho de banda bajo para Teams para EDU</span><span class="sxs-lookup"><span data-stu-id="c25a4-104">Help for low-bandwidth situations for Teams for EDU</span></span>

<span data-ttu-id="c25a4-105">Intervienen muchos elementos de red al trabajar con Microsoft Teams que pueden afectar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c25a4-105">There are numerous network elements when it comes to working with Microsoft Teams that can affect performance.</span></span> <span data-ttu-id="c25a4-106">El ancho de banda bajo es una de las situaciones que pueden resultar completamente fuera de su control.</span><span class="sxs-lookup"><span data-stu-id="c25a4-106">Low bandwidth is one of the situations that can feel entirely out of your control.</span></span> <span data-ttu-id="c25a4-107">Tenga en cuenta las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="c25a4-107">Consider the following situations:</span></span>

- <span data-ttu-id="c25a4-108">Una conexión a Internet de baja velocidad para la escuela.</span><span class="sxs-lookup"><span data-stu-id="c25a4-108">A low-speed internet connection for the school.</span></span>
- <span data-ttu-id="c25a4-109">Una conexión a Internet de baja velocidad para uno o más alumnos.</span><span class="sxs-lookup"><span data-stu-id="c25a4-109">A low-speed internet connection for one or more students.</span></span>
- <span data-ttu-id="c25a4-110">Horas del día en que el ancho de banda se reduce debido al uso de la red en un área.</span><span class="sxs-lookup"><span data-stu-id="c25a4-110">Times of the day when there's low bandwidth because of network usage in an area.</span></span>
- <span data-ttu-id="c25a4-111">Períodos de ancho de banda bajo causados por interrupciones locales no por las escuelas ni por los alumnos, pero que afecta negativamente al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c25a4-111">Low-bandwidth periods because of outages local to neither the school nor to students, but, which affect performance nonetheless.</span></span>
- <span data-ttu-id="c25a4-112">Problemas que no son de ancho de banda (por ejemplo, problema con el hardware) que se hacen pasar por problemas de ancho de banda bajo.</span><span class="sxs-lookup"><span data-stu-id="c25a4-112">Non-bandwidth issues (for example, issues with hardware) that masquerade as low-bandwidth issues.</span></span>

<span data-ttu-id="c25a4-113">Este artículo le proporcionará las mejores prácticas para realizar diversas actividades de Teams cuando se enfrente a un problema de ancho de banda bajo.</span><span class="sxs-lookup"><span data-stu-id="c25a4-113">This article will give you best practices to follow for various Teams activities when you're faced with a low-bandwidth issue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c25a4-114">Aquí encontrará información sobre [Cómo Microsoft Teams usa la memoria](teams-memory-usage-perf.md), porque además de los problemas de ancho de banda bajo, es posible que tenga problemas de recursos en su dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c25a4-114">There's information here on [How Microsoft Teams uses memory](teams-memory-usage-perf.md), because in addition to low bandwidth problems, you may be having resource issues on your device.</span></span> <span data-ttu-id="c25a4-115">Si está buscando una guía de red para Microsoft Teams, consulte [Preparar la red de la organización para Microsoft Teams](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="c25a4-115">If you're looking for network guidance for Microsoft Teams, review [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

## <a name="resolving-low-bandwidth-issues-for-admins"></a><span data-ttu-id="c25a4-116">Resolver problemas de ancho de banda bajo para administradores</span><span class="sxs-lookup"><span data-stu-id="c25a4-116">Resolving low-bandwidth issues for Admins</span></span>

<span data-ttu-id="c25a4-117">Lo importante es recordar que, como administrador de TI, a pesar de que tiene soluciones para los problemas de ancho de banda bajo que se sabe que resolverán los problemas rápidamente, deben considerarse cuidadosamente las soluciones.</span><span class="sxs-lookup"><span data-stu-id="c25a4-117">The important thing to remember, as an IT Admin, is that while you have solutions for low-bandwidth issues that are wide-spread that will resolve problems quickly, solutions should be considered carefully.</span></span> <span data-ttu-id="c25a4-118">Algunos problemas pueden solucionarse con una estrategia más limitada al nivel del formador o incluso del alumno/padre.</span><span class="sxs-lookup"><span data-stu-id="c25a4-118">Some issues may be able to resolve with a more narrow focus taken at the educator or even the student/parent level.</span></span>

<span data-ttu-id="c25a4-119">Es decir, si se produce un problema de ancho de banda bajo para un amplio grupo de alumnos, tomar medidas como un administrador de TI tiene sentido y también tiene sentido si las acciones emprendidas en el nivel de alumno/formador no le han sido útiles.</span><span class="sxs-lookup"><span data-stu-id="c25a4-119">In short, if the low-bandwidth issue occurs for a wide group of students, taking action as an IT Admin makes sense, and it also makes sense if the actions taken at the student/educator level haven't been helpful.</span></span>

> [!NOTE]
> <span data-ttu-id="c25a4-120">Si tiene tiempo, inviértalo leyendo la [guía de revisión de la calidad de la experiencia](quality-of-experience-review-guide.md), es una lectura valiosa (que aunque no es específica de EDU, aún tendrá información valiosa).</span><span class="sxs-lookup"><span data-stu-id="c25a4-120">If you've got the time to invest, the [Quality of Experience Review Guide](quality-of-experience-review-guide.md) is a worthwhile read (this is not EDU-specific, but it will still have valuable information).</span></span> <span data-ttu-id="c25a4-121">Esta guía permitirá que los administradores de TI experimentados podrán profundizar en la experiencia de los formadores y alumnos.</span><span class="sxs-lookup"><span data-stu-id="c25a4-121">This guide will allow experienced IT Admins to go in-depth on the experience for their educators and students.</span></span>

### <a name="meetings-and-video"></a><span data-ttu-id="c25a4-122">Reuniones y vídeo</span><span class="sxs-lookup"><span data-stu-id="c25a4-122">Meetings and video</span></span>

<span data-ttu-id="c25a4-123">Un enfoque principal para los problemas de ancho de banda bajo son las reuniones y, específicamente, el vídeo en las reuniones.</span><span class="sxs-lookup"><span data-stu-id="c25a4-123">A primary focus for low-bandwidth issues is meetings; specifically, video in meetings.</span></span> <span data-ttu-id="c25a4-124">Un administrador de TI debe considerar las siguientes acciones cuando se trata de problemas informados por alumnos o formadores con respecto a tener la mejor experiencia de reunión en un entorno educativo.</span><span class="sxs-lookup"><span data-stu-id="c25a4-124">An IT Admin should consider the actions below when dealing with issues reported by students or educators in regard to having the best meeting experience in an educational setting.</span></span>

#### <a name="meeting-policies"></a><span data-ttu-id="c25a4-125">Directivas de reunión</span><span class="sxs-lookup"><span data-stu-id="c25a4-125">Meeting policies</span></span>

<span data-ttu-id="c25a4-126">En lo que respecta a las reuniones, una de las áreas más relacionadas para las situaciones de ancho de banda baja tiene que ver con los vídeos.</span><span class="sxs-lookup"><span data-stu-id="c25a4-126">Regarding meetings, one of the most concerning areas for low-bandwidth situations has to do with videos.</span></span> <span data-ttu-id="c25a4-127">Además de que Teams puede escalar el ancho de banda detectado automáticamente, usted, como administrador de TI, dispone de opciones de directivas que puede establecer en el nivel de organizador y/o usuario.</span><span class="sxs-lookup"><span data-stu-id="c25a4-127">In addition to Teams being able to scale to detected bandwidth automatically, you as an IT Admin have policy options you can set at the per-organizer and/or per-user level.</span></span> <span data-ttu-id="c25a4-128">Estas opciones le permiten brindar a todos la mejor experiencia considerando el ancho de banda que tienen para trabajar en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="c25a4-128">These options allow you to give everyone the best experience in light of the bandwidth they have to work with at a given time.</span></span>

<span data-ttu-id="c25a4-129">Entre las cosas que puede establecer mediante la directiva se incluyen:</span><span class="sxs-lookup"><span data-stu-id="c25a4-129">Some of the things you can set via policy include:</span></span>

- <span data-ttu-id="c25a4-130">Deshabilitar el vídeo completamente, para que nadie pueda habilitarlo.</span><span class="sxs-lookup"><span data-stu-id="c25a4-130">Disabling video altogether, so no one could enable it.</span></span>
- <span data-ttu-id="c25a4-131">Tasa de bits multimedia (este ajuste se define por usuario).</span><span class="sxs-lookup"><span data-stu-id="c25a4-131">Media bit rate (this setting is set per-user).</span></span>

<span data-ttu-id="c25a4-132">Para obtener más información sobre sus opciones y para ver las especificaciones específicas de las directivas que necesitaría establecer para las reuniones y el vídeo, consulte [Configuración de la directiva de reuniones en Teams: audio y vídeo](meeting-policies-audio-and-video.md).</span><span class="sxs-lookup"><span data-stu-id="c25a4-132">To learn more about your options, and to walk through the specifics of what policies you'd need to set for meetings and video, check out [Meeting policy settings in Teams: Audio and video](meeting-policies-audio-and-video.md).</span></span>

#### <a name="screen-sharing-policies"></a><span data-ttu-id="c25a4-133">Directivas de uso compartido de pantalla</span><span class="sxs-lookup"><span data-stu-id="c25a4-133">Screen sharing policies</span></span>

<span data-ttu-id="c25a4-134">En otros casos, los formadores pueden compartir toda la pantalla con los alumnos, cuando el uso compartido debe limitarse a una aplicación relevante para la lección que se está impartiendo.</span><span class="sxs-lookup"><span data-stu-id="c25a4-134">In other cases, educators may be sharing their entire screen to students, when sharing should be limited to an application relevant to the lesson being taught.</span></span> <span data-ttu-id="c25a4-135">Esta configuración también puede establecerse con una directiva, si esa es una forma más deseable de hacerlo que hacer que los formadores tomen esa decisión individualmente.</span><span class="sxs-lookup"><span data-stu-id="c25a4-135">This setting can also be set via policy, if that's a more desirable way to do it than to have educators making that choice individually.</span></span>

<span data-ttu-id="c25a4-136">Para tener una buena idea de lo que puede hacer para limitar la pantalla el uso compartido de la pantalla con la configuración de directivas, consulte [Configuración de la directiva de reunión en Teams: audio y vídeo](meeting-policies-audio-and-video.md).</span><span class="sxs-lookup"><span data-stu-id="c25a4-136">For a good idea of what you can do about limiting screen sharing via policy settings, check out [Meeting policy settings in Teams: Audio and video](meeting-policies-audio-and-video.md).</span></span>

#### <a name="dial-in-number-for-meetings"></a><span data-ttu-id="c25a4-137">Número de acceso telefónico para una reunión</span><span class="sxs-lookup"><span data-stu-id="c25a4-137">Dial-in number for meetings</span></span>

<span data-ttu-id="c25a4-138">Puede ser más fácil para algunos alumnos intentar llamar en algunas sesiones de clase.</span><span class="sxs-lookup"><span data-stu-id="c25a4-138">It may be easier for some students to attempt to dial in to some classroom sessions.</span></span> <span data-ttu-id="c25a4-139">Puede proporcionar un número de acceso telefónico para reuniones de Teams, de modo que los alumnos que tienen problemas pueden llamar como alternativa para asistir a una reunión de vídeo.</span><span class="sxs-lookup"><span data-stu-id="c25a4-139">You can provide a dial-in number for Teams meetings, so students with issues can phone in as an alternative to attending a video meeting.</span></span>

<span data-ttu-id="c25a4-140">Para obtener más información sobre esto, puede leer [Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="c25a4-140">For more information on this, you can read [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="low-bandwidth-scenarios-as-an-educator"></a><span data-ttu-id="c25a4-141">Escenarios de ancho de banda bajo como formador</span><span class="sxs-lookup"><span data-stu-id="c25a4-141">Low-bandwidth scenarios as an educator</span></span>

<span data-ttu-id="c25a4-142">Los formadores deben sentirse capacitados para tomar medidas para resolver problemas de ancho de banda bajo y puede ser una mejor opción que la acción del administrador de TI en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c25a4-142">Educators should feel empowered to take steps to resolve low-bandwidth issues, and may be a superior choice to IT Admin action in the following situations:</span></span>

- <span data-ttu-id="c25a4-143">Si el problema es intermitente o relativamente transitorio.</span><span class="sxs-lookup"><span data-stu-id="c25a4-143">If the problem is intermittent, or relatively transitory.</span></span>
- <span data-ttu-id="c25a4-144">Si hay un momento específico del día, puede anticiparse a un problema o el ancho de banda bajo tiene alguna previsibilidad.</span><span class="sxs-lookup"><span data-stu-id="c25a4-144">If there is a specific time of the day you can anticipate there being an issue, or the low bandwidth period has some predictability to it.</span></span>

<span data-ttu-id="c25a4-145">En estas situaciones, puede llevar a cabo algunas acciones.</span><span class="sxs-lookup"><span data-stu-id="c25a4-145">In these situations, you can take some actions.</span></span>

<span data-ttu-id="c25a4-146">Para obtener más información, consulte [Usar Teams para el trabajo escolar cuando el ancho de banda es bajo](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span><span class="sxs-lookup"><span data-stu-id="c25a4-146">For more information, check out [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).</span></span>

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a><span data-ttu-id="c25a4-147">Escenarios de ancho de banda bajo como padre o alumno</span><span class="sxs-lookup"><span data-stu-id="c25a4-147">Low-bandwidth scenarios as a parent or student</span></span>

<span data-ttu-id="c25a4-148">También hay situaciones, y debe analizarlas de manera proactiva con los formadores, donde el problema de ancho de banda se encuentra en el lado del alumno (por ejemplo, un gran número de alumnos pueden ver las lecciones de vídeo sin problemas, pero un pequeño número de alumnos tienen dificultades).</span><span class="sxs-lookup"><span data-stu-id="c25a4-148">There are also situations, and you should proactively discuss them with your educators, where the bandwidth problem may be on the student's side (for example, a large number of students are able to watch the video lessons without issue, but a small number of students have difficulties).</span></span>

<span data-ttu-id="c25a4-149">Es poco probable que sean muchos los padres que puedan solucionar estos problemas.</span><span class="sxs-lookup"><span data-stu-id="c25a4-149">It's not reasonable to expect many parents to be able to troubleshoot these issues.</span></span> <span data-ttu-id="c25a4-150">Los problemas de ancho de banda bajo pueden estar fuera del control de un alumno o de los padres (su hogar puede no tener acceso a un ancho de banda alto, pueden que haya muchas personas en el área de consumo inmediato consumiendo ancho de banda y afectando lo que pueden hacer, probablemente el Internet es inestable, etc.).</span><span class="sxs-lookup"><span data-stu-id="c25a4-150">Low-bandwidth issues may be out of a student or parent's control (their home may not have access to high bandwidth, they may have numerous people in their immediate area consuming bandwidth and affecting what they can do, there may be internet instability, and so on).</span></span>

<span data-ttu-id="c25a4-151">Hemos incorporado una guía en nuestro artículo [Usar Teams para el trabajo escolar cuando el ancho de banda es bajo](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) para padres y alumnos, también puede revisar y probar estas recomendaciones si tiene algún problema.</span><span class="sxs-lookup"><span data-stu-id="c25a4-151">We've put together guidance in our [Use Teams for schoolwork when bandwidth is low](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) article for parents and students as well, you can review and try these recommendations if you're having any problems.</span></span>