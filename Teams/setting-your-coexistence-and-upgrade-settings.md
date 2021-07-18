---
title: Establecer configuración de actualización y coexistencia
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: Obtenga información sobre cómo establecer la configuración de coexistencia y actualización para todos los usuarios de su organización a la vez, o para un único o conjunto de usuarios de su organización.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9419e8ba7339db1fb202e3b5add66935caff7486
ms.sourcegitcommit: 1a622397b5c7fe05e687bb47493fcbca63915d97
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53447978"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a><span data-ttu-id="46a0c-103">Establecer configuración de actualización y coexistencia</span><span class="sxs-lookup"><span data-stu-id="46a0c-103">Set your coexistence and upgrade settings</span></span>


<span data-ttu-id="46a0c-104">Al actualizar su Skype Empresarial usuarios para que usen Teams, tiene varias opciones para ayudarle a que sea un proceso sin problemas para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="46a0c-104">When you upgrade your Skype for Business users to use Teams, you have several options to help you make it a seamless process for your users.</span></span> <span data-ttu-id="46a0c-105">Tiene la opción de realizar la configuración de coexistencia y actualización para todos los usuarios de su organización a la vez, o puede realizar cambios de configuración para un único o conjunto de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="46a0c-105">You have the option to make coexistence and upgrade settings for all of the users in your organization at once, or you can make settings changes for a single or set of users in your organization.</span></span> <span data-ttu-id="46a0c-106">Tenga en cuenta que las versiones anteriores de Skype Empresarial clientes pueden no respetar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="46a0c-106">Note that older versions of Skype for Business clients may not honor these settings.</span></span> <span data-ttu-id="46a0c-107">Para obtener más información sobre Skype Empresarial de cliente, vaya a la [página Skype Empresarial descargas y actualizaciones.](/skypeforbusiness/software-updates)</span><span class="sxs-lookup"><span data-stu-id="46a0c-107">For more information about Skype for Business client versions, go to the [Skype for Business downloads and updates page](/skypeforbusiness/software-updates).</span></span> 

<span data-ttu-id="46a0c-108">Puede comprender mejor los modos disponibles leyendo Comprender [Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) y Skype Empresarial coexistencia e interoperabilidad o Coexistencia con [Skype Empresarial](coexistence-chat-calls-presence.md).</span><span class="sxs-lookup"><span data-stu-id="46a0c-108">You can get a better understanding of the modes that are available to you by reading [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) or [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a><span data-ttu-id="46a0c-109">Establecer opciones de actualización para todos los usuarios de su organización</span><span class="sxs-lookup"><span data-stu-id="46a0c-109">Set upgrade options for all users in your organization</span></span>

<span data-ttu-id="46a0c-110">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**</span><span class="sxs-lookup"><span data-stu-id="46a0c-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="46a0c-111">En el [Microsoft Teams de administración](https://admin.teams.microsoft.com/), en el panel de navegación izquierdo, vaya a Configuración **de** toda la organización  >  **Teams actualización.**</span><span class="sxs-lookup"><span data-stu-id="46a0c-111">In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), in the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="46a0c-112">En la parte superior de la **Teams de** actualización, modifique las siguientes opciones según lo desee.</span><span class="sxs-lookup"><span data-stu-id="46a0c-112">At the top of the **Teams upgrade** page, modify the following options as desired.</span></span>

    - <span data-ttu-id="46a0c-113">Establecer el **modo coexistencia.**</span><span class="sxs-lookup"><span data-stu-id="46a0c-113">Set the **Coexistence** mode.</span></span>
        - <span data-ttu-id="46a0c-114">**Islas:** use esta configuración si desea que los usuarios puedan usar tanto Skype Empresarial como Teams simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="46a0c-114">**Islands** - Use this setting if you want users to be able to use both Skype for Business and Teams simultaneously.</span></span>
        - <span data-ttu-id="46a0c-115">**Skype Empresarial:** use esta configuración si desea que los usuarios solo usen Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="46a0c-115">**Skype for Business only** - Use this setting if you want your users to only use Skype for Business.</span></span>
        - <span data-ttu-id="46a0c-116">**Skype Empresarial con Teams** colaboración: use esta configuración si desea que los usuarios usen Skype Empresarial además de usar Teams para la colaboración de grupo (canales).</span><span class="sxs-lookup"><span data-stu-id="46a0c-116">**Skype for Business with Teams collaboration** - Use this setting if you want your users to use Skype for Business in addition to using Teams for group collaboration (channels).</span></span>
        - <span data-ttu-id="46a0c-117">Skype Empresarial con Teams colaboración y reuniones: use esta configuración si desea que los usuarios usen Skype Empresarial además de usar Teams para la colaboración de grupo **(canales)** y Teams reuniones.</span><span class="sxs-lookup"><span data-stu-id="46a0c-117">**Skype for Business with Teams collaboration and meetings** - Use this setting if you want your users to use Skype for Business in addition to using Teams for group collaboration (channels) and Teams meetings.</span></span>
        - <span data-ttu-id="46a0c-118">**Teams:** use esta configuración si desea que los usuarios solo usen Teams.</span><span class="sxs-lookup"><span data-stu-id="46a0c-118">**Teams only** - Use this setting if you want your users to use only Teams.</span></span> <span data-ttu-id="46a0c-119">Tenga en cuenta que, incluso con esta configuración, los usuarios aún pueden unirse a reuniones hospedadas en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="46a0c-119">Note that even with this setting, users can still join meetings hosted in Skype for Business.</span></span>

          > [!IMPORTANT]
          > <span data-ttu-id="46a0c-120">Solo puede asignar el modo TeamsOnly a todo el espacio empresarial después de completar los dos pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="46a0c-120">You can only assign TeamsOnly mode to the entire tenant after both of the following steps ahve been completed:</span></span>
          >  - <span data-ttu-id="46a0c-121">Todos los usuarios locales se han movido a Teams solo con Move-CsUser en el conjunto de herramientas Skype Empresarial Server local.</span><span class="sxs-lookup"><span data-stu-id="46a0c-121">All on-premises users have been moved to Teams Only using Move-CsUser in the Skype for Business Server on-premises toolset.</span></span>
          >  - <span data-ttu-id="46a0c-122">Ha actualizado todos los Skype Empresarial DNS para que apunten a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="46a0c-122">You have updated any Skype for Business DNS records to point to Microsoft 365.</span></span> 
          >
          > <span data-ttu-id="46a0c-123">Para obtener más información, vea [Deshabilitar la configuración híbrida para completar](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)la migración a Teams solo .</span><span class="sxs-lookup"><span data-stu-id="46a0c-123">For more detail, see [Disable your hybrid configuration to complete migration to Teams Only](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>
        
    - <span data-ttu-id="46a0c-124">Establezca **Notificar Skype Empresarial usuarios que Teams está disponible para la actualización.**</span><span class="sxs-lookup"><span data-stu-id="46a0c-124">Set **Notify Skype for Business users that Teams is available for upgrade**.</span></span> <span data-ttu-id="46a0c-125">Si activa esta opción, le dirá a Skype Empresarial usuarios que pronto se actualizarán a la Teams aplicación.</span><span class="sxs-lookup"><span data-stu-id="46a0c-125">If you turn this on, it will tell the Skype for Business users that they will soon be upgraded to the Teams app.</span></span>

    - <span data-ttu-id="46a0c-126">Establezca la **aplicación Preferida para que los usuarios se unan Skype Empresarial reuniones.**</span><span class="sxs-lookup"><span data-stu-id="46a0c-126">Set the **Preferred app for users to join Skype for Business meetings**.</span></span> <span data-ttu-id="46a0c-127">Esta configuración determina qué aplicación se usa para unirse Skype Empresarial reuniones y se respeta independientemente del valor del modo de coexistencia.</span><span class="sxs-lookup"><span data-stu-id="46a0c-127">This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
      - <span data-ttu-id="46a0c-128">**Skype Aplicación Reuniones**</span><span class="sxs-lookup"><span data-stu-id="46a0c-128">**Skype Meetings app**</span></span>
      - <span data-ttu-id="46a0c-129">**Skype Empresarial con características limitadas**</span><span class="sxs-lookup"><span data-stu-id="46a0c-129">**Skype for Business with limited features**</span></span>

    - <span data-ttu-id="46a0c-130">Establezca si desea descargar la Teams en segundo plano para **Skype Empresarial usuarios.**</span><span class="sxs-lookup"><span data-stu-id="46a0c-130">Set whether to **Download the Teams app in the background for Skype for Business users**.</span></span>  <span data-ttu-id="46a0c-131">Esta configuración descarga silenciosamente la aplicación Teams para los usuarios que Skype Empresarial en Windows.</span><span class="sxs-lookup"><span data-stu-id="46a0c-131">This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="46a0c-132">Solo se respeta si el modo de coexistencia del usuario Teams o si las notificaciones de actualización pendiente están habilitadas en Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="46a0c-132">It is honored only if coexistence mode for the user is Teams only or if notifications of pending upgrade are enabled in Skype for Business.</span></span>

3. <span data-ttu-id="46a0c-133">Haga **clic en Guardar** después de realizar los cambios.</span><span class="sxs-lookup"><span data-stu-id="46a0c-133">Click **Save** after you make your changes.</span></span>

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a><span data-ttu-id="46a0c-134">Establecer opciones de actualización para un solo usuario de la organización</span><span class="sxs-lookup"><span data-stu-id="46a0c-134">Set upgrade options for a single user in your organization</span></span>

<span data-ttu-id="46a0c-135">![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**</span><span class="sxs-lookup"><span data-stu-id="46a0c-135">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="46a0c-136">En el panel de navegación izquierdo, vaya **a Usuarios** y, a continuación, seleccione el usuario de la lista.</span><span class="sxs-lookup"><span data-stu-id="46a0c-136">In the left navigation, go to **Users**, and then select the user from the list.</span></span> 
2. <span data-ttu-id="46a0c-137">En la **pestaña Cuenta** del usuario, en **Teams,** haga clic en **Editar.**</span><span class="sxs-lookup"><span data-stu-id="46a0c-137">On the **Account** tab for the user, under **Teams upgrade**, click **Edit**.</span></span>
3. <span data-ttu-id="46a0c-138">Puede establecer el modo **coexistencia.**</span><span class="sxs-lookup"><span data-stu-id="46a0c-138">You can set the **Coexistence mode**.</span></span> <span data-ttu-id="46a0c-139">Los modos distintos de Teams Solo se pueden aplicar a los usuarios que se aloen en Skype Empresarial Server local y, por el contrario, solo los usuarios que se aloen en la nube pueden tener el modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="46a0c-139">Modes other than Teams Only can only be applied to users homed in Skype for Business Server on-premises, and conversely only users homed in the cloud can have TeamsOnly mode.</span></span>  <span data-ttu-id="46a0c-140">Elija una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="46a0c-140">Choose from the following options:</span></span>
     - <span data-ttu-id="46a0c-141">**Usar la configuración de toda la** organización: use esta configuración si desea que el usuario use la configuración de toda **la** organización.</span><span class="sxs-lookup"><span data-stu-id="46a0c-141">**Use Org-wide settings** - Use this setting if you want the user to use the settings in the **Org-wide** settings.</span></span> 
     - <span data-ttu-id="46a0c-142">**Islas:** use esta configuración si desea que el usuario pueda usar tanto Skype Empresarial como Teams.</span><span class="sxs-lookup"><span data-stu-id="46a0c-142">**Islands** - Use this setting if you want the user to be able to use both Skype for Business and Teams.</span></span> 
     - <span data-ttu-id="46a0c-143">**Skype Empresarial:** use esta configuración si desea que el usuario use Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="46a0c-143">**Skype for Business only** - Use this setting if you want the user to use Skype for Business.</span></span>
     - <span data-ttu-id="46a0c-144">**Skype Empresarial con Teams** colaboración: use esta configuración si desea que el usuario use Skype Empresarial además de usar Teams para la colaboración de grupo (canales).</span><span class="sxs-lookup"><span data-stu-id="46a0c-144">**Skype for Business with Teams collaboration** - Use this setting if you want the user to use Skype for Business in addition to using Teams for group collaboration (channels).</span></span>
      - <span data-ttu-id="46a0c-145">Skype Empresarial con Teams colaboración y reuniones: use esta configuración si desea que el usuario use Skype Empresarial además de usar Teams para la colaboración de grupo **(canales)** y Teams reuniones.</span><span class="sxs-lookup"><span data-stu-id="46a0c-145">**Skype for Business with Teams collaboration and meetings** - Use this setting if you want the user to use Skype for Business in addition to using Teams for group collaboration (channels) and Teams meetings.</span></span>
     - <span data-ttu-id="46a0c-146">**Teams:** use esta configuración si desea que el usuario solo use Teams.</span><span class="sxs-lookup"><span data-stu-id="46a0c-146">**Teams only** - Use this setting if you want the user to use only Teams.</span></span> <span data-ttu-id="46a0c-147">El usuario podrá seguir unirse a Skype Empresarial reuniones.</span><span class="sxs-lookup"><span data-stu-id="46a0c-147">The user will still be able to join Skype for Business meetings.</span></span>
4. <span data-ttu-id="46a0c-148">Si selecciona  cualquier modo de coexistencia que no sea Usar la configuración de toda la **organización,** tiene la opción de habilitar las notificaciones en la aplicación Skype Empresarial del usuario que actualicen a Teams próximamente.</span><span class="sxs-lookup"><span data-stu-id="46a0c-148">If you select any **Coexistence mode** other than **Use Org-wide settings**, you have the option to enable notifications in the user's Skype for Business app that upgrade to Teams is coming soon.</span></span> <span data-ttu-id="46a0c-149">Puede habilitar esta notificación para el usuario activando la opción Notificar **al Skype Empresarial** usuario.</span><span class="sxs-lookup"><span data-stu-id="46a0c-149">You can enable this notification for the user by turning on the **Notify the Skype for Business user** option.</span></span>
5. <span data-ttu-id="46a0c-150">Haga **clic en Guardar** después de realizar los cambios.</span><span class="sxs-lookup"><span data-stu-id="46a0c-150">Click **Save** after you make your changes.</span></span>

### <a name="related-topics"></a><span data-ttu-id="46a0c-151">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="46a0c-151">Related topics</span></span>
[<span data-ttu-id="46a0c-152">Planear el viaje</span><span class="sxs-lookup"><span data-stu-id="46a0c-152">Plan the journey</span></span>](upgrade-plan-journey.md)

[<span data-ttu-id="46a0c-153">Comprender el viaje de coexistencia y actualización de Skype Empresarial y Teams</span><span class="sxs-lookup"><span data-stu-id="46a0c-153">Understand the coexistence and upgrade journey for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[<span data-ttu-id="46a0c-154">Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="46a0c-154">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="46a0c-155">Retirar el entorno de Skype Empresarial local</span><span class="sxs-lookup"><span data-stu-id="46a0c-155">Decommission your on-premises Skype for Business environment</span></span>](/skypeforbusiness/hybrid/decommission-on-prem-overview)
