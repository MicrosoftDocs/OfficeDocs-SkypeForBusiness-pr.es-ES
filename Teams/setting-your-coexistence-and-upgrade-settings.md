---
title: Configurar su coexistencia y la configuración de actualización
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: Este artículo le ayudará a elegir el modo de coexistencia y establecer otra configuración de coexistencia.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 581aab3067dcc2e8dbdc579236f340259b5c6e74
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243189"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a><span data-ttu-id="d8375-103">Configurar su coexistencia y la configuración de actualización</span><span class="sxs-lookup"><span data-stu-id="d8375-103">Setting your coexistence and upgrade settings</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="d8375-104">Al actualizar los usuarios de Skype empresarial para que usen Teams, dispone de varias opciones para ayudarle a convertirlo en un proceso sin problemas para sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="d8375-104">When you upgrade your Skype for Business users to use Teams, you have several options to help you make it a seamless process for your users.</span></span> <span data-ttu-id="d8375-105">Tiene la opción de hacer la coexistencia y la configuración de actualización de todos los usuarios de la organización a la vez, o puede realizar cambios de configuración para un único o un conjunto de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="d8375-105">You have the option to make coexistence and upgrade settings for all of the users in your organization at once, or you can make settings changes for a single or set of users in your organization.</span></span> <span data-ttu-id="d8375-106">Tenga en cuenta que es posible que las versiones más antiguas de clientes de Skype empresarial no cumplan con esta configuración.</span><span class="sxs-lookup"><span data-stu-id="d8375-106">Note that older versions of Skype for Business clients may not honor these settings.</span></span> <span data-ttu-id="d8375-107">Para obtener más información sobre las versiones de cliente de Skype empresarial, vaya a la [Página de descargas y actualizaciones de Skype empresarial](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates).</span><span class="sxs-lookup"><span data-stu-id="d8375-107">For more information about Skype for Business client versions, go to the [Skype for Business downloads and updates page](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates).</span></span> 

<span data-ttu-id="d8375-108">Puede obtener una mejor comprensión de los tipos de modos que tiene a su disposición leyendo [comprender Microsoft Teams y](teams-and-skypeforbusiness-coexistence-and-interoperability.md) la coexistencia e interoperabilidad de Skype empresarial o coexistencia [con Skype empresarial](coexistence-chat-calls-presence.md).</span><span class="sxs-lookup"><span data-stu-id="d8375-108">You can get a better understanding of the types of modes that are available to you by reading [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) or [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a><span data-ttu-id="d8375-109">Establecer las opciones de actualización para todos los usuarios de la organización</span><span class="sxs-lookup"><span data-stu-id="d8375-109">Set upgrade options for all users in your organization</span></span>

<span data-ttu-id="d8375-110">![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="d8375-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d8375-111">En el navegación de la izquierda, vaya a la actualización de la **configuración** > de**equipos**de la organización.</span><span class="sxs-lookup"><span data-stu-id="d8375-111">In the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="d8375-112">En la parte superior de la página de **actualización** de Teams, realice los cambios siguientes si así lo hacen.</span><span class="sxs-lookup"><span data-stu-id="d8375-112">At the top of the **Teams upgrade** page, make the following changes if they will work for you.</span></span>
    - <span data-ttu-id="d8375-113">Establecer el \*\*\*\* modo de coexistencia.</span><span class="sxs-lookup"><span data-stu-id="d8375-113">Set the **Coexistence** mode.</span></span>
        - <span data-ttu-id="d8375-114">**Islas** : Use esta configuración si quiere que los usuarios puedan usar Skype empresarial y Teams de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="d8375-114">**Islands** - Use this setting if you want users to be able to use both Skype for Business and Teams simultaneously.</span></span>
        - <span data-ttu-id="d8375-115">**Solo para Skype empresarial** : Use esta configuración si desea que los usuarios solo usen Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d8375-115">**Skype for Business only** - Use this setting if you want your users to only use Skype for Business.</span></span>
        - <span data-ttu-id="d8375-116">**Solo equipos** (en versión preliminar para algunas organizaciones): Use esta opción si quiere que los usuarios solo usen equipos de equipo.</span><span class="sxs-lookup"><span data-stu-id="d8375-116">**Teams only** (in preview for some organizations) - Use this setting if you want your users to use only Teams.</span></span> <span data-ttu-id="d8375-117">Tenga en cuenta que, incluso con esta configuración, los usuarios pueden unirse a reuniones hospedadas en Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d8375-117">Note that even with this setting, users can still join meetings hosted in Skype for Business.</span></span>
    - <span data-ttu-id="d8375-118">Establezca **notificar a los usuarios de Skype empresarial que Teams está disponible para su actualización**.</span><span class="sxs-lookup"><span data-stu-id="d8375-118">Set **Notify Skype for Business users that Teams is available for upgrade**.</span></span> <span data-ttu-id="d8375-119">Si activa esta opción, se le indicará a los usuarios de Skype empresarial que pronto se actualizarán a la aplicación de Teams.</span><span class="sxs-lookup"><span data-stu-id="d8375-119">If you turn this on, it will tell the Skype for Business users that they will soon be upgraded to the Teams app.</span></span>
    - <span data-ttu-id="d8375-120">Establezca la **aplicación preferida para que los usuarios se unan a reuniones de Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="d8375-120">Set the **Preferred app for users to join Skype for Business meetings**.</span></span> <span data-ttu-id="d8375-121">Esta opción determina qué aplicación se usa para unirse a reuniones de Skype empresarial y se acepta independientemente del valor del modo de coexistencia.</span><span class="sxs-lookup"><span data-stu-id="d8375-121">This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
      - <span data-ttu-id="d8375-122">**Aplicación reuniones de Skype**</span><span class="sxs-lookup"><span data-stu-id="d8375-122">**Skype Meetings app**</span></span>
      - <span data-ttu-id="d8375-123">**Skype empresarial con características limitadas**</span><span class="sxs-lookup"><span data-stu-id="d8375-123">**Skype for Business with limited features**</span></span>
    - <span data-ttu-id="d8375-124">Establezca si desea **descargar la aplicación de Teams en segundo plano para los usuarios de Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="d8375-124">Set whether to **Download the Teams app in the background for Skype for Business users**.</span></span>  <span data-ttu-id="d8375-125">Esta configuración descarga silenciosamente la aplicación de Teams para los usuarios que ejecutan Skype empresarial en Windows.</span><span class="sxs-lookup"><span data-stu-id="d8375-125">This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="d8375-126">Solo se admite si el modo de coexistencia para el usuario solo es de equipos o si las notificaciones de actualización pendiente están habilitadas en Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d8375-126">It is honored only if coexistence mode for the user is Teams only or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
3. <span data-ttu-id="d8375-127">Haga clic en **Guardar** después de realizar los cambios.</span><span class="sxs-lookup"><span data-stu-id="d8375-127">Click **Save** after you make your changes.</span></span>

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a><span data-ttu-id="d8375-128">Establecer las opciones de actualización para un único usuario de su organización</span><span class="sxs-lookup"><span data-stu-id="d8375-128">Set upgrade options for a single user in your organization</span></span>

<span data-ttu-id="d8375-129">![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="d8375-129">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d8375-130">En el navegación de la izquierda, vaya a **usuarios**y, a continuación, seleccione el usuario de la lista.</span><span class="sxs-lookup"><span data-stu-id="d8375-130">In the left navigation, go to **Users**, and then select the user from the list.</span></span> 
2. <span data-ttu-id="d8375-131">En la pestaña **cuenta** del usuario, en **actualización**de Teams, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d8375-131">On the **Account** tab for the user, under **Teams upgrade**, click **Edit**.</span></span>
3. <span data-ttu-id="d8375-132">Puede establecer el **modo**de coexistencia.</span><span class="sxs-lookup"><span data-stu-id="d8375-132">You can set the **Coexistence mode**.</span></span> <span data-ttu-id="d8375-133">Elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d8375-133">Choose from the following options:</span></span>
     - <span data-ttu-id="d8375-134">**Usar la configuración de toda la organización** : Use esta configuración si desea que el usuario Use la configuración en la configuración de **toda la organización** .</span><span class="sxs-lookup"><span data-stu-id="d8375-134">**Use Org-wide settings** - Use this setting if you want the user to use the settings in the **Org-wide** settings.</span></span> 
     - <span data-ttu-id="d8375-135">**Islas** : Use esta configuración si quiere que el usuario pueda usar tanto Skype empresarial como Teams.</span><span class="sxs-lookup"><span data-stu-id="d8375-135">**Islands** - Use this setting if you want the user to be able to use both Skype for Business and Teams.</span></span> 
     - <span data-ttu-id="d8375-136">**Solo para Skype empresarial** : Use esta configuración si desea que el usuario use Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d8375-136">**Skype for Business only** - Use this setting if you want the user to use Skype for Business.</span></span> 
     - <span data-ttu-id="d8375-137">**Solo equipos** : Use esta configuración si desea que el usuario solo use equipos.</span><span class="sxs-lookup"><span data-stu-id="d8375-137">**Teams only** - Use this setting if you want the user to use only Teams.</span></span> <span data-ttu-id="d8375-138">El usuario seguirá pudiendo unirse a reuniones de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d8375-138">The user will still be able to join Skype for Business meetings.</span></span>
4. <span data-ttu-id="d8375-139">Si selecciona cualquier **modo** de coexistencia distinto de **usar la configuración de toda la organización**, tendrá la opción de habilitar las notificaciones en la aplicación Skype empresarial del usuario que la actualización a teams estará disponible próximamente.</span><span class="sxs-lookup"><span data-stu-id="d8375-139">If you select any **Coexistence mode** other than **Use Org-wide settings**, you have the option to enable notifications in the user's Skype for Business app that upgrade to Teams is coming soon.</span></span> <span data-ttu-id="d8375-140">Puede habilitar esta notificación para el usuario activando la opción **notificar al usuario de Skype empresarial** .</span><span class="sxs-lookup"><span data-stu-id="d8375-140">You can enable this notification for the user by turning on the **Notify the Skype for Business user** option.</span></span>
5. <span data-ttu-id="d8375-141">Haga clic en **Guardar** después de realizar los cambios.</span><span class="sxs-lookup"><span data-stu-id="d8375-141">Click **Save** after you make your changes.</span></span>

### <a name="related-topics"></a><span data-ttu-id="d8375-142">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d8375-142">Related topics</span></span>
[<span data-ttu-id="d8375-143">Planear el viaje</span><span class="sxs-lookup"><span data-stu-id="d8375-143">Plan the journey</span></span>](upgrade-plan-journey.md)

[<span data-ttu-id="d8375-144">Comprender el viaje de coexistencia y actualización de Skype empresarial y Teams</span><span class="sxs-lookup"><span data-stu-id="d8375-144">Understand the coexistence and upgrade journey for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[<span data-ttu-id="d8375-145">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="d8375-145">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)
