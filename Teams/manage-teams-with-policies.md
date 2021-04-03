---
title: Administrar Teams con directivas
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Límese sobre las directivas de Teams.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77afc1cbb71fff9cb54decbbf6e5cfd10d6c4e59
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574189"
---
# <a name="manage-teams-with-policies"></a><span data-ttu-id="55ca5-103">Administrar Teams con directivas</span><span class="sxs-lookup"><span data-stu-id="55ca5-103">Manage Teams with policies</span></span>

<span data-ttu-id="55ca5-104">Las directivas son una parte importante de la administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="55ca5-104">Policies are an important part of managing Teams.</span></span> <span data-ttu-id="55ca5-105">Use este artículo para navegar por cómo usar directivas para beneficiar a su organización.</span><span class="sxs-lookup"><span data-stu-id="55ca5-105">Use this article to navigate how to use policies to benefit your organization.</span></span>

## <a name="what-you-use-policies-for"></a><span data-ttu-id="55ca5-106">Para qué usa las directivas</span><span class="sxs-lookup"><span data-stu-id="55ca5-106">What you use policies for</span></span>

<span data-ttu-id="55ca5-107">Las directivas se usan para realizar muchas tareas de su organización en diferentes áreas, como mensajería, reuniones y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="55ca5-107">Policies are used to accomplish many tasks in your organization across different areas such as messaging, meetings, and applications.</span></span> <span data-ttu-id="55ca5-108">Algunas de las cosas que puede hacer incluyen permitir a los usuarios programar reuniones en un canal de teams, permitir a los usuarios editar mensajes enviados y controlar si los usuarios pueden anclar aplicaciones a la barra de aplicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="55ca5-108">Some of the things you can do include allowing users to schedule meetings in a teams channel, enabling users to edit sent messages, and controlling whether users can pin apps to the Teams app bar.</span></span>

## <a name="how-to-assign-policies"></a><span data-ttu-id="55ca5-109">Cómo asignar directivas</span><span class="sxs-lookup"><span data-stu-id="55ca5-109">How to assign policies</span></span>

<span data-ttu-id="55ca5-110">Las directivas se pueden asignar de varias maneras diferentes en función de lo que su organización esté intentando lograr.</span><span class="sxs-lookup"><span data-stu-id="55ca5-110">Policies can be assigned in several different ways depending on what your organization is trying to accomplish.</span></span> <span data-ttu-id="55ca5-111">Puede realizar y ver tareas en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="55ca5-111">You can make and view assignments in the Teams admin center.</span></span>

![Captura de pantalla de la asignación de directivas de grupo.](media/group-policy-assignment.png)

<span data-ttu-id="55ca5-113">Obtenga más información sobre cómo asignar directivas [aquí.](policy-assignment-overview.md)</span><span class="sxs-lookup"><span data-stu-id="55ca5-113">Learn more about assigning policies [here](policy-assignment-overview.md).</span></span>

## <a name="how-to-manage-policies"></a><span data-ttu-id="55ca5-114">Cómo administrar directivas</span><span class="sxs-lookup"><span data-stu-id="55ca5-114">How to manage policies</span></span>

<span data-ttu-id="55ca5-115">Las directivas se administran con el Centro de administración de Microsoft Teams o [con PowerShell.](./teams-powershell-managing-teams.md#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="55ca5-115">Policies are managed with the Microsoft Teams admin center or [using PowerShell](./teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

<span data-ttu-id="55ca5-116">Por ejemplo, una directiva de configuración de aplicaciones puede permitirle a los usuarios cargar aplicaciones personalizadas, instalar aplicaciones en nombre de los usuarios y anclar aplicaciones a la barra de aplicaciones de Teams.</span><span class="sxs-lookup"><span data-stu-id="55ca5-116">For example, an app setup policy can allow you to enable users to upload custom apps, install apps on behalf of your users, and pin apps to the Teams app bar.</span></span> <span data-ttu-id="55ca5-117">Estas directivas se configuran en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="55ca5-117">These policies are configured in the Teams admin center.</span></span>

![Captura de pantalla de la directiva de configuración de la aplicación.](media/app-setup-policy.png)

<span data-ttu-id="55ca5-119">Además, se puede usar una directiva de reunión para controlar la configuración de audio y vídeo en reuniones de Teams, como transcripciones, grabaciones en la nube y audio/vídeo IP.</span><span class="sxs-lookup"><span data-stu-id="55ca5-119">Additionally, a meeting policy can be used to control audio and video settings in Teams meetings such as transcriptions, cloud recordings, and IP audio/video.</span></span>

![Captura de pantalla de la directiva de reunión.](media/engineering-meeting-policy.png)

### <a name="teams-for-education"></a><span data-ttu-id="55ca5-121">Teams para el ámbito educativo</span><span class="sxs-lookup"><span data-stu-id="55ca5-121">Teams for Education</span></span>

<span data-ttu-id="55ca5-122">También puede usar el Asistente para directivas [de Teams para](easy-policy-setup-edu.md) educación para configurar y administrar fácilmente directivas para su entorno de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="55ca5-122">You can also use the [Teams for Education policy wizard](easy-policy-setup-edu.md) to easily set up and manage policies for your learning environment.</span></span>

![Captura de pantalla del Asistente para directivas de Teams para el sector educativo.](media/easy-policy-setup-quick-setup.png)

## <a name="types-of-policies"></a><span data-ttu-id="55ca5-124">Tipos de directivas</span><span class="sxs-lookup"><span data-stu-id="55ca5-124">Types of policies</span></span>

<span data-ttu-id="55ca5-125">Las siguientes directivas se pueden administrar con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="55ca5-125">The following policies can be managed with Microsoft Teams.</span></span>

<span data-ttu-id="55ca5-126">Tipo de directiva</span><span class="sxs-lookup"><span data-stu-id="55ca5-126">Policy type</span></span> | <span data-ttu-id="55ca5-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="55ca5-127">Description</span></span>
------------|------------
[<span data-ttu-id="55ca5-128">Paquetes de directivas</span><span class="sxs-lookup"><span data-stu-id="55ca5-128">Policy packages</span></span>](manage-policy-packages.md) | <span data-ttu-id="55ca5-129">Un paquete de directivas en Microsoft Teams es una colección de directivas y configuraciones predefinidas que puede asignar a usuarios que tienen roles similares en su organización.</span><span class="sxs-lookup"><span data-stu-id="55ca5-129">A policy package in Microsoft Teams is a collection of predefined policies and settings you can assign to users who have similar roles in your organization.</span></span>
[<span data-ttu-id="55ca5-130">Directivas de reunión</span><span class="sxs-lookup"><span data-stu-id="55ca5-130">Meeting policies</span></span>](meeting-policies-in-teams.md) | <span data-ttu-id="55ca5-131">Una directiva de reunión se usa para controlar las características que están disponibles para los participantes de la reunión para las reuniones programadas por los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="55ca5-131">A meeting policy is used to control the features that are available to meeting participants for meetings scheduled by users in your organization.</span></span> <span data-ttu-id="55ca5-132">Las directivas de reunión incluyen los temas siguientes.</span><span class="sxs-lookup"><span data-stu-id="55ca5-132">Meeting policies include the following topics.</span></span><br> <span data-ttu-id="55ca5-133">- Directivas de audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="55ca5-133">- Audio and video policies</span></span><br> <span data-ttu-id="55ca5-134">- Directivas de uso compartido de pantalla y contenido</span><span class="sxs-lookup"><span data-stu-id="55ca5-134">- Content and screen sharing policies</span></span><br> <span data-ttu-id="55ca5-135">- Participantes, invitados y directivas de acceso</span><span class="sxs-lookup"><span data-stu-id="55ca5-135">- Participants, guests, and access policies</span></span><br> <span data-ttu-id="55ca5-136">- Directivas generales</span><span class="sxs-lookup"><span data-stu-id="55ca5-136">- General policies</span></span>
[<span data-ttu-id="55ca5-137">Directivas de voz y llamadas</span><span class="sxs-lookup"><span data-stu-id="55ca5-137">Voice and calling policies</span></span>](voice-and-calling-policies.md)| <span data-ttu-id="55ca5-138">Las directivas de llamadas y llamadas administran esta configuración a través de equipos como llamadas de emergencia, enrutamiento de llamadas e id. de llamada.</span><span class="sxs-lookup"><span data-stu-id="55ca5-138">Voice and calling policies manage these settings through teams such as emergency calling, call routing, and caller ID.</span></span>
[<span data-ttu-id="55ca5-139">Directivas de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="55ca5-139">App policies</span></span>](app-policies.md)| <span data-ttu-id="55ca5-140">Las directivas de aplicación se usan para controlar las aplicaciones en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="55ca5-140">App policies are used to control applications in Microsoft Teams.</span></span> <span data-ttu-id="55ca5-141">Los administradores pueden permitir o bloquear las aplicaciones que los usuarios pueden instalar, anclar aplicaciones a la barra de aplicaciones de Teams de un usuario e instalar la aplicación en nombre de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="55ca5-141">Admins can allow or block which apps users can install, pin applications to a user's Teams app bar, and install application on behalf of your users.</span></span>
[<span data-ttu-id="55ca5-142">Directivas de mensajería</span><span class="sxs-lookup"><span data-stu-id="55ca5-142">Messaging policies</span></span>](messaging-policies-in-teams.md)| <span data-ttu-id="55ca5-143">Las directivas de mensajería controlan la disponibilidad de las características de chat y canal.</span><span class="sxs-lookup"><span data-stu-id="55ca5-143">Messaging policies control chat and channel feature availability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="55ca5-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="55ca5-144">Related topics</span></span>

* [<span data-ttu-id="55ca5-145">Asignar directivas en Teams: introducción</span><span class="sxs-lookup"><span data-stu-id="55ca5-145">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)
* [<span data-ttu-id="55ca5-146">Administrar directivas de comentarios en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55ca5-146">Manage feedback policies in Microsoft Teams</span></span>](manage-feedback-policies-in-teams.md)
* [<span data-ttu-id="55ca5-147">Administrar directivas de equipos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55ca5-147">Manage teams policies in Microsoft Teams</span></span>](teams-policies.md)
* [<span data-ttu-id="55ca5-148">Definir eventos en directo en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="55ca5-148">Set up for live events in Microsoft Teams</span></span>](teams-live-events/set-up-for-teams-live-events.md)
* [<span data-ttu-id="55ca5-149">Directivas y paquetes de directivas de Teams for Education</span><span class="sxs-lookup"><span data-stu-id="55ca5-149">Teams for Education policies and policy packages</span></span>](policy-packages-edu.md)