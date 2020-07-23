---
title: Configurar la administración para aplicaciones en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: Obtenga más información sobre las directivas y la configuración que puede usar para administrar aplicaciones de su organización en Microsoft Teams.
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
f1.keywords:
- CSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ae1776cf57368ea0f18cb6b0e46e5a11dffe447
ms.sourcegitcommit: 863347fb6e5916d8d936adc4ddcebb2e32a91d1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "45228906"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="06218-103">Configurar la administración para aplicaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="06218-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="06218-104">Las aplicaciones proporcionan herramientas para su organización para obtener más provecho de Teams.</span><span class="sxs-lookup"><span data-stu-id="06218-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="06218-105">Estas aplicaciones combinan la funcionalidad de las pestañas, las extensiones de mensajería, los conectores y los bots proporcionados por Microsoft, creados por un tercero o por los programadores de su organización.</span><span class="sxs-lookup"><span data-stu-id="06218-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="06218-106">Administre las aplicaciones de su organización en las **aplicaciones de Teams** en el centro de administración.</span><span class="sxs-lookup"><span data-stu-id="06218-106">You manage apps for your organization in **Teams apps** in the admin center.</span></span> <span data-ttu-id="06218-107">(Consulte [usar los roles de administrador de Teams para administrar equipos](https://docs.microsoft.com/microsoftteams/using-admin-roles) para obtener información sobre cómo obtener roles y permisos de administrador). Por ejemplo, puede permitir o bloquear aplicaciones en el nivel de organización, configurar directivas para controlar qué aplicaciones están disponibles para los usuarios de Teams y personalizar Teams anclando las aplicaciones más importantes para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="06218-107">(See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.) For example, you can allow or block apps at the org level, set policies to control what apps are available to Teams users, and customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="06218-108">Mejoramos continuamente la experiencia de la aplicación en Teams y agregamos características y funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="06218-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="06218-109">A lo largo del tiempo, crearemos otras funciones de administración de aplicaciones, así que vuelve a consultar la información más actualizada sobre las directivas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="06218-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="manage-apps"></a><span data-ttu-id="06218-110">Administrar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="06218-110">Manage apps</span></span>

<span data-ttu-id="06218-111">Use la página **Administrar aplicaciones** para ver y administrar todas las aplicaciones de Teams en el catálogo de aplicaciones de su organización.</span><span class="sxs-lookup"><span data-stu-id="06218-111">Use the **Manage apps** page to view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="06218-112">Puede ver el estado de organización y las propiedades de las aplicaciones, bloquear o permitir aplicaciones en el nivel de la organización, cargar nuevas aplicaciones personalizadas a su catálogo de inquilinos y administrar la configuración de la aplicación en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="06218-112">You can see the org-level status and properties of apps, block or allow apps at the org level, upload new custom apps to your tenant catalog, and manage org-wide app settings.</span></span>

<span data-ttu-id="06218-113">La página **Manage apps** le ofrece una vista de todas las aplicaciones disponibles en el catálogo de inquilinos, y le proporciona la información que necesita para decidir qué aplicaciones quiere permitir o bloquear en su organización.</span><span class="sxs-lookup"><span data-stu-id="06218-113">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="06218-114">Después, puede usar [las directivas de permisos](#app-permission-policies)de la aplicación, [las directivas de configuración](#app-setup-policies)de la aplicación y [las directivas de aplicaciones personalizadas y la configuración](#custom-app-policies-and-settings) para configurar la experiencia de la aplicación para usuarios específicos de su organización.</span><span class="sxs-lookup"><span data-stu-id="06218-114">You can then use [app permission policies](#app-permission-policies), [app setup policies](#app-setup-policies), and [custom app policies and settings](#custom-app-policies-and-settings) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="06218-115">Para obtener más información, consulte [Administrar aplicaciones en Teams](manage-apps.md).</span><span class="sxs-lookup"><span data-stu-id="06218-115">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="06218-116">Directivas de permisos de aplicación</span><span class="sxs-lookup"><span data-stu-id="06218-116">App permission policies</span></span>

<span data-ttu-id="06218-117">Con las directivas de permisos de aplicaciones, puede controlar qué aplicaciones están disponibles para determinados usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="06218-117">With app permission policies, you can control what apps are available to specific users in your organization.</span></span> <span data-ttu-id="06218-118">Puede permitir o bloquear todas las aplicaciones o aplicaciones específicas publicadas por Microsoft, terceros y su organización.</span><span class="sxs-lookup"><span data-stu-id="06218-118">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="06218-119">Por ejemplo, puede usar las directivas de permisos de aplicaciones para:</span><span class="sxs-lookup"><span data-stu-id="06218-119">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="06218-120">Implemente gradualmente nuevas aplicaciones integradas o personalizadas de terceros para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="06218-120">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="06218-121">Simplifique la experiencia del usuario, especialmente cuando empiece a implementar equipos en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="06218-121">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="06218-122">Para obtener más información, vaya a [Administrar directivas de permisos de aplicaciones en Teams](teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="06218-122">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="06218-123">Directivas de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="06218-123">App setup policies</span></span>

<span data-ttu-id="06218-124">Las directivas de configuración de la aplicación le permiten personalizar la experiencia de la aplicación para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="06218-124">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="06218-125">Elija las aplicaciones que quiere anclar a la barra de la aplicación en los clientes de Teams y el orden en el que aparecen, en los clientes Web, de escritorio y móviles.</span><span class="sxs-lookup"><span data-stu-id="06218-125">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="06218-126">Estos son algunos ejemplos de cómo puede usar las directivas de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="06218-126">Here's some examples of how you can use app setup policies:</span></span>

- <span data-ttu-id="06218-127">Impulsar la detección y la adopción de aplicaciones principales.</span><span class="sxs-lookup"><span data-stu-id="06218-127">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="06218-128">Por ejemplo, anclar una aplicación personalizada de administración de talento y reclutamiento de los usuarios de su equipo de RRHH.</span><span class="sxs-lookup"><span data-stu-id="06218-128">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="06218-129">Anclar selectivamente las características principales de Teams, como chat, equipos y llamadas.</span><span class="sxs-lookup"><span data-stu-id="06218-129">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="06218-130">Esto puede ayudar a garantizar que los usuarios participen en actividades específicas dentro de Teams.</span><span class="sxs-lookup"><span data-stu-id="06218-130">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="06218-131">Para obtener más información, consulte [Administrar directivas de configuración de aplicaciones en Teams](teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="06218-131">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="06218-132">Configuración y directivas de la aplicación personalizadas</span><span class="sxs-lookup"><span data-stu-id="06218-132">Custom app policies and settings</span></span>

<span data-ttu-id="06218-133">Teams permite a los desarrolladores de su organización crear, probar e implementar aplicaciones personalizadas para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="06218-133">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="06218-134">Las aplicaciones personalizadas se pueden agregar a teams cargando un paquete de la aplicación en un archivo. zip directamente en un equipo o en el contexto personal.</span><span class="sxs-lookup"><span data-stu-id="06218-134">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="06218-135">Puede usar las directivas de configuración de la aplicación para controlar quién puede cargar aplicaciones personalizadas en la organización.</span><span class="sxs-lookup"><span data-stu-id="06218-135">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="06218-136">También puede establecer la configuración de toda la organización para controlar si los usuarios pueden interactuar con aplicaciones personalizadas específicas.</span><span class="sxs-lookup"><span data-stu-id="06218-136">You can also set org-wide settings to control whether users can interact with specific custom apps.</span></span>

<span data-ttu-id="06218-137">Para obtener más información, vaya a [administrar la configuración y las directivas de la aplicación personalizada en Teams](teams-custom-app-policies-and-settings.md).</span><span class="sxs-lookup"><span data-stu-id="06218-137">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
