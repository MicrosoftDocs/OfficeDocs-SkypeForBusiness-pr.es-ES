---
title: Configurar la administración para aplicaciones en Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: Obtenga información sobre las directivas y la configuración que puede usar para administrar aplicaciones para su organización en Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f78069aea098b6318e49808245f5b17bd90509e0
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856059"
---
# <a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="7bf34-103">Configurar la administración para aplicaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7bf34-103">Admin settings for apps in Microsoft Teams</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="7bf34-104">Las aplicaciones proporcionan herramientas personalizadas para que su organización obtenga más información sobre Teams.</span><span class="sxs-lookup"><span data-stu-id="7bf34-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="7bf34-105">Estas aplicaciones combinan la funcionalidad de pestañas, extensiones de mensajería, conectores y bots proporcionados por Microsoft, creados por un tercero o por desarrolladores de su organización.</span><span class="sxs-lookup"><span data-stu-id="7bf34-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="7bf34-106">Administra aplicaciones para su organización en Teams **en** el Centro de administración.</span><span class="sxs-lookup"><span data-stu-id="7bf34-106">You manage apps for your organization in **Teams apps** in the admin center.</span></span> <span data-ttu-id="7bf34-107">(Vea [Usar Teams de administrador para](./using-admin-roles.md) administrar Teams para obtener permisos y roles de administrador). Por ejemplo, puede permitir o bloquear aplicaciones en el nivel de organización, establecer directivas para controlar qué aplicaciones están disponibles para los usuarios de Teams y personalizar Teams anclando las aplicaciones que son más importantes para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7bf34-107">(See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.) For example, you can allow or block apps at the org level, set policies to control what apps are available to Teams users, and customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="7bf34-108">Estamos mejorando continuamente la experiencia de la aplicación en Teams y agregando características y funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="7bf34-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="7bf34-109">Con el tiempo, crearemos capacidades de administración de aplicaciones adicionales, así que vuelve a buscar la información más actualizada sobre las directivas de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7bf34-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="manage-apps"></a><span data-ttu-id="7bf34-110">Administrar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="7bf34-110">Manage apps</span></span>

<span data-ttu-id="7bf34-111">Use la **página Administrar aplicaciones** para ver y administrar todas las Teams en el catálogo de aplicaciones de su organización.</span><span class="sxs-lookup"><span data-stu-id="7bf34-111">Use the **Manage apps** page to view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="7bf34-112">Puede ver el estado y las propiedades de las aplicaciones a nivel de organización, bloquear o permitir aplicaciones en el nivel de la organización, cargar nuevas aplicaciones personalizadas en el catálogo de inquilinos y administrar la configuración de aplicaciones de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="7bf34-112">You can see the org-level status and properties of apps, block or allow apps at the org level, upload new custom apps to your tenant catalog, and manage org-wide app settings.</span></span>

<span data-ttu-id="7bf34-113">La **página Administrar aplicaciones** le ofrece una vista de todas las aplicaciones disponibles en el catálogo de inquilinos, lo que le proporciona la información que necesita para decidir qué aplicaciones permitir o bloquear en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="7bf34-113">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="7bf34-114">A continuación, puede usar directivas de [](#custom-app-policies-and-settings) permisos [de aplicación,](#app-permission-policies)directivas de configuración de [aplicaciones](#app-setup-policies)y directivas y configuraciones de aplicaciones personalizadas para configurar la experiencia de la aplicación para usuarios específicos de su organización.</span><span class="sxs-lookup"><span data-stu-id="7bf34-114">You can then use [app permission policies](#app-permission-policies), [app setup policies](#app-setup-policies), and [custom app policies and settings](#custom-app-policies-and-settings) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="7bf34-115">Para obtener más información, vea [Administrar aplicaciones en Teams](manage-apps.md).</span><span class="sxs-lookup"><span data-stu-id="7bf34-115">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="7bf34-116">Directivas de permisos de aplicación</span><span class="sxs-lookup"><span data-stu-id="7bf34-116">App permission policies</span></span>

<span data-ttu-id="7bf34-117">Con las directivas de permisos de aplicación, puede controlar qué aplicaciones están disponibles para usuarios específicos de su organización.</span><span class="sxs-lookup"><span data-stu-id="7bf34-117">With app permission policies, you can control what apps are available to specific users in your organization.</span></span> <span data-ttu-id="7bf34-118">Puede permitir o bloquear todas las aplicaciones publicadas por Microsoft, por terceros o por su organización.</span><span class="sxs-lookup"><span data-stu-id="7bf34-118">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="7bf34-119">Por ejemplo, puede usar directivas de permisos de aplicación para:</span><span class="sxs-lookup"><span data-stu-id="7bf34-119">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="7bf34-120">Gradualmente, se irán lanzando nuevas aplicaciones de terceros o personalizadas para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="7bf34-120">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="7bf34-121">Simplifique la experiencia del usuario, especialmente cuando empiece a implementar Teams en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="7bf34-121">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="7bf34-122">Para obtener más información, vaya a Administrar directivas [de permisos de aplicación en Teams](teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7bf34-122">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="7bf34-123">Directivas de configuración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="7bf34-123">App setup policies</span></span>

<span data-ttu-id="7bf34-124">Las directivas de configuración de aplicaciones le permiten personalizar la experiencia de la aplicación para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7bf34-124">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="7bf34-125">Elija las aplicaciones que desea anclar a la barra de aplicaciones en los clientes de Teams y el orden en que aparecen, en clientes web, de escritorio y móviles.</span><span class="sxs-lookup"><span data-stu-id="7bf34-125">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="7bf34-126">Estos son algunos ejemplos de cómo puede usar directivas de configuración de aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="7bf34-126">Here's some examples of how you can use app setup policies:</span></span>

- <span data-ttu-id="7bf34-127">Impulsar el conocimiento y la adopción de aplicaciones principales.</span><span class="sxs-lookup"><span data-stu-id="7bf34-127">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="7bf34-128">Por ejemplo, anclar una aplicación personalizada de contratación y administración de talentos para los usuarios de su equipo de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="7bf34-128">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="7bf34-129">Anclar selectivamente las Teams principales, como Chat, Teams y Llamadas.</span><span class="sxs-lookup"><span data-stu-id="7bf34-129">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="7bf34-130">Hacerlo puede ayudar a garantizar que los usuarios se dedican a actividades específicas dentro de Teams.</span><span class="sxs-lookup"><span data-stu-id="7bf34-130">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="7bf34-131">Para obtener más información, consulte Administrar directivas [de configuración de aplicaciones en Teams](teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7bf34-131">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="7bf34-132">Configuración y directivas de aplicaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="7bf34-132">Custom app policies and settings</span></span>

<span data-ttu-id="7bf34-133">Teams permite a los desarrolladores de su organización crear, probar e implementar aplicaciones personalizadas a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="7bf34-133">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="7bf34-134">Las aplicaciones personalizadas se pueden agregar a Teams cargando un paquete de aplicación en un archivo de .zip directamente a un equipo o en el contexto personal.</span><span class="sxs-lookup"><span data-stu-id="7bf34-134">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="7bf34-135">Puede usar directivas de configuración de aplicaciones para controlar quién en su organización puede cargar aplicaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="7bf34-135">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="7bf34-136">También puede establecer la configuración de toda la organización para controlar si los usuarios pueden interactuar con aplicaciones personalizadas específicas.</span><span class="sxs-lookup"><span data-stu-id="7bf34-136">You can also set org-wide settings to control whether users can interact with specific custom apps.</span></span>

<span data-ttu-id="7bf34-137">Para obtener más información, vaya a Administrar directivas y configuraciones de aplicaciones [personalizadas en Teams](teams-custom-app-policies-and-settings.md).</span><span class="sxs-lookup"><span data-stu-id="7bf34-137">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>