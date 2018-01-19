---
title: "Configurar la administración para aplicaciones en Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Aprenda a permitir y habilitar aplicaciones en Microsoft Teams, incluida la carga lateral de aplicaciones externas.
ms.openlocfilehash: 4265866bb346da1aa773d337d02fc1c11149f579
ms.sourcegitcommit: ee1c79b6d6d73e5fc702fe55b9e5aee8a7aae793
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/10/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="b1b53-103">Configurar la administración para aplicaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1b53-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="b1b53-p101">Las aplicaciones son fichas, conectores, bots o cualquier combinación de estos tres elementos, que proporciona un servicio de terceros. Existen directivas de administración que se pueden configurar en el Centro de administración de Office 365 para controlar qué aplicaciones externas de terceros están permitidas. Estas directivas permiten especificar qué aplicaciones están permitidas y cuáles no, el comportamiento de las aplicaciones nuevas externas y si se permite la carga lateral de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b1b53-p101">In this section, we refer to tabs, connectors, and bots, or any combination of these capabilities, provided by a single third-party service as Apps. There are Admin policies that can be configured in the Office 365 Admin Portal to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external App behavior, as well as whether side-loading apps is allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="b1b53-107">Para ajustar la configuración de la administración de aplicaciones en Microsoft Teams, vaya al Centro de administración de Office 365, abra **Configuración** > **Servicios y complementos**, y seleccione **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="b1b53-107">To manage admin settings for apps in Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="b1b53-108">Si ha iniciado sesión como administrador de Office 365, puede acceder con este vínculo:</span><span class="sxs-lookup"><span data-stu-id="b1b53-108">If you're signed in as an Office 365 admin, this link should take you there:</span></span>
> 
> <span data-ttu-id="b1b53-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span><span class="sxs-lookup"><span data-stu-id="b1b53-109">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span></span> 

<span data-ttu-id="b1b53-110">**Permitir aplicaciones externas en Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="b1b53-110">**Allow external apps in Microsoft Teams**</span></span>

<span data-ttu-id="b1b53-p103">De manera predeterminada, en Microsoft Teams está habilitada la opción de permitir aplicaciones externas con todas las aplicaciones seleccionadas. Cuando se cambia esta directiva a **“Desactivado”**, se deshabilitan todas las aplicaciones externas de terceros. Puede profundizar aún más: puede permitir que se habiliten las aplicaciones externas y anular la selección de determinadas aplicaciones para que se deshabiliten, de manera individual.</span><span class="sxs-lookup"><span data-stu-id="b1b53-p103">By default, allow external apps in Microsoft Teams is enabled with all apps selected. When turning this policy to **“Off”**, then all external third-party apps are disabled. You can get more granular and allow external apps to be enabled and uncheck specific apps that you want to disable on an individual basis.</span></span>

<span data-ttu-id="b1b53-114">**Habilitar nuevas aplicaciones externas de manera predeterminada**</span><span class="sxs-lookup"><span data-stu-id="b1b53-114">**Enable new external apps by default**</span></span>

<span data-ttu-id="b1b53-p104">Cuando se envían nuevas aplicaciones al catálogo de aplicaciones de Microsoft Teams, este conmutador controla si están disponibles para los usuarios de este inquilino. De manera predeterminada, esta directiva está establecida en **“Activado”**. Esto permite a los usuarios acceder a las aplicaciones en cuanto estas se agregan al catálogo de aplicaciones del inquilino. Si prefiere validar las aplicaciones antes de permitir su uso en Teams, establezca esta directiva en **“Desactivado”**. Solo recuerde que si la establece en **“Desactivado”**, debe evaluar las nuevas aplicaciones que se agregan con cierta regularidad, para que los usuarios puedan beneficiarse de las últimas innovaciones y adiciones de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b1b53-p104">Whenever new apps are submitted to the Teams App Catalog, this switch controls whether they are available for users in this tenant. By default, this policy is set to **“On”** which allows users to have access to apps as soon as they are added to the Team’s app catalog. If you would prefer to validate apps before allowing them to be utilized in Teams, then set this policy to **Off.** Just remember, if you set this to **"Off",** you should evaluate newly added apps on a regular basis to make sure your users benefit from the latest innovations and additions of apps.</span></span>

<span data-ttu-id="b1b53-119">**Permitir la carga lateral de aplicaciones externas**</span><span class="sxs-lookup"><span data-stu-id="b1b53-119">**Allow side-loading of external apps**</span></span>

<span data-ttu-id="b1b53-p105">La carga lateral de aplicaciones en Microsoft Teams la pueden realizar únicamente los propietarios o los miembros del equipo. Estas son algunas de las ventajas de la carga lateral de aplicaciones en Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="b1b53-p105">Only Team owners or members who are granted permissions, can side-load apps into Microsoft Teams. Some benefits of side-loading apps into Microsoft Teams are:</span></span>

-   <span data-ttu-id="b1b53-122">Capacidad de probar aplicaciones antes de enviarlas a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1b53-122">Ability to test apps prior to submitting to Microsoft</span></span>

-   <span data-ttu-id="b1b53-123">Proporcionar aplicaciones directamente a los usuarios de la organización sin tener que enviarlas a la Tienda Office.</span><span class="sxs-lookup"><span data-stu-id="b1b53-123">Provide apps directly to users within your organization without having to submit to the Office Store.</span></span>

<span data-ttu-id="b1b53-124">Para saber más sobre la carga lateral de aplicaciones en Microsoft Teams, visite el tema sobre [carga lateral de aplicaciones en Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=854631) </span><span class="sxs-lookup"><span data-stu-id="b1b53-124">To learn more about side loading apps into Microsoft Teams, visit: [Side loading your app in a team](https://go.microsoft.com/fwlink/?linkid=854631).</span></span>

![Captura de pantalla de la sección Aplicaciones de la configuración de Microsoft Teams.](media/Admin_settings_for_apps_in_Microsoft_Teams_image1.png)
