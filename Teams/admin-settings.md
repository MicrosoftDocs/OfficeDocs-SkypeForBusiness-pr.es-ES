---
title: Configurar la administración para aplicaciones en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/18/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, lajin
description: Obtenga información sobre las directivas y la configuración que puede usar para administrar aplicaciones para la organización en Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.apppolicies.adminsettings
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 034ac8eeb5529179013540b1911a7bbc34b49014
ms.sourcegitcommit: a505869a3cc2fe6fe4ee18bcbe99bf980aa91a86
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "31520151"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="2ae00-103">Configurar la administración para aplicaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ae00-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon.md)]

<span data-ttu-id="2ae00-104">Proporcionan las aplicaciones del cuadro herramientas para la organización obtener más provecho de los equipos.</span><span class="sxs-lookup"><span data-stu-id="2ae00-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="2ae00-105">Estas aplicaciones de combinan la funcionalidad de las fichas, las extensiones de mensajería, conectores y bots proporcionados por Microsoft, creada por un tercero, o por los programadores de la organización.</span><span class="sxs-lookup"><span data-stu-id="2ae00-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="2ae00-106">Administración de aplicaciones para la organización en las **aplicaciones de los equipos** en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2ae00-106">You manage apps for your organization in **Teams apps** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="2ae00-107">Puede establecer directivas para controlar qué aplicaciones están disponibles para los usuarios de los equipos de la organización, personalizar los equipos mediante fijación de aplicaciones que son más importantes para los usuarios y especificar si los usuarios pueden cargar aplicaciones personalizadas (también conocido como sideloading).</span><span class="sxs-lookup"><span data-stu-id="2ae00-107">You can set policies to control what apps are available to Teams users in your organization, customize Teams by pinning apps that are most important for your users, and specify whether users can upload custom apps (also known as sideloading).</span></span> <span data-ttu-id="2ae00-108">Estas directivas y configuración proporciona un control granular sobre qué aplicaciones están disponibles, cómo aparecen en los equipos y quién puede utilizarlos en función de las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="2ae00-108">These policies and settings give you granular control over what apps are available, how they appear in Teams, and who can use them based on the needs of your organization.</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="2ae00-109">Directivas de permisos de aplicación</span><span class="sxs-lookup"><span data-stu-id="2ae00-109">App permission policies</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="2ae00-110">Con las directivas de permisos de aplicación, puede bloquear o permitir aplicaciones, toda la organización o para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="2ae00-110">With app permission policies, you can block or allow apps, either org-wide or for specific users.</span></span>  <span data-ttu-id="2ae00-111">Cuando se bloquea una aplicación, se deshabilitan todas las interacciones con esa aplicación y la aplicación no aparece en los equipos de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2ae00-111">When you block an app, all interactions with that app are disabled and the app doesn't appear in Teams for users.</span></span>

<span data-ttu-id="2ae00-112">Por ejemplo, puede usar las directivas de permisos de aplicación para:</span><span class="sxs-lookup"><span data-stu-id="2ae00-112">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="2ae00-113">Deshabilitar una aplicación que supone un permiso o el riesgo de pérdida de datos para la organización.</span><span class="sxs-lookup"><span data-stu-id="2ae00-113">Disable an app that poses a permission or data loss risk to your organization.</span></span>
- <span data-ttu-id="2ae00-114">Gradualmente desplegar nuevas aplicaciones de terceros o aplicaciones personalizadas de integrado a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="2ae00-114">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="2ae00-115">Simplificar la experiencia del usuario, especialmente cuando se inicie implantar los equipos en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="2ae00-115">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="2ae00-116">Para obtener más información, vaya a [administrar las directivas de permisos de aplicación en los equipos](teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2ae00-116">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="2ae00-117">Directivas del programa de instalación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="2ae00-117">App setup policies</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="2ae00-118">Las directivas de aplicación del programa de instalación le permiten personalizar la experiencia de la aplicación para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2ae00-118">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="2ae00-119">Elija las aplicaciones que desea anclar a la barra de aplicaciones en los clientes de los equipos y el orden en que aparecen, en clientes móviles, de escritorio y web.</span><span class="sxs-lookup"><span data-stu-id="2ae00-119">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="2ae00-120">Presentamos algunos ejemplos de cómo puede usar las directivas de aplicación del programa de instalación:</span><span class="sxs-lookup"><span data-stu-id="2ae00-120">Here's some examples of how you can use app setup policies:</span></span>
- <span data-ttu-id="2ae00-121">Mejorar el conocimiento y la adopción de aplicaciones principales.</span><span class="sxs-lookup"><span data-stu-id="2ae00-121">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="2ae00-122">Por ejemplo, anclar una aplicación de administración de contratación y talento personalizada para los usuarios en el equipo de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="2ae00-122">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="2ae00-123">Anclar las características de los equipos de núcleo, como Chat, equipos y llamar de forma selectiva.</span><span class="sxs-lookup"><span data-stu-id="2ae00-123">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="2ae00-124">Al hacerlo, puede ayudar a garantizar que los usuarios están ocupados en actividades específicas dentro de los equipos.</span><span class="sxs-lookup"><span data-stu-id="2ae00-124">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="2ae00-125">Para obtener más información, consulte [Administrar directivas de configuración de aplicación en los equipos](teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2ae00-125">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="2ae00-126">Configuración y las directivas de aplicación personalizada</span><span class="sxs-lookup"><span data-stu-id="2ae00-126">Custom app policies and settings</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="2ae00-127">Los equipos permite a los programadores de la organización para crear, probar e implementar aplicaciones personalizadas a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="2ae00-127">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="2ae00-128">Aplicaciones personalizadas se pueden agregar a los equipos mediante la carga de un paquete de aplicación en un archivo .zip directamente a un equipo o en el contexto personal.</span><span class="sxs-lookup"><span data-stu-id="2ae00-128">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="2ae00-129">Puede usar directivas de configuración de aplicación para controlar quién en la organización puede cargar sus aplicaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="2ae00-129">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="2ae00-130">También puede establecer la configuración de toda la organización para controlar si los usuarios pueden interactuar con aplicaciones personalizadas específicas.</span><span class="sxs-lookup"><span data-stu-id="2ae00-130">You can also set org-wide settings to control whether users can interact with specific custom  apps.</span></span>

<span data-ttu-id="2ae00-131">Para obtener más información, vaya a [directivas de aplicación personalizada de administrar y configuración de los equipos](teams-custom-app-policies-and-settings.md).</span><span class="sxs-lookup"><span data-stu-id="2ae00-131">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>