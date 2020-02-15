---
title: Administrar etiquetas en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a administrar cómo se usan las etiquetas en su organización en Microsoft Teams.
ms.openlocfilehash: 3ade2f47474fe8aaf16c568e8c141dcd84526d86
ms.sourcegitcommit: 561b9bab7d6f5a621436bc85ea28ea14657e7868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034529"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="872ea-103">Administrar etiquetas en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="872ea-103">Manage tags in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="872ea-104">¿Aún no ve esta característica en el centro de administración de Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="872ea-104">Don't see this feature in the Microsoft Teams admin center yet?</span></span> <span data-ttu-id="872ea-105">Se está implementando en este momento y es posible que aún no esté disponible en su organización.</span><span class="sxs-lookup"><span data-stu-id="872ea-105">It's currently being rolled out and might not be available in your organization yet.</span></span> <span data-ttu-id="872ea-106">Para estar al día de las próximas características de Teams, consulte la [hoja de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span><span class="sxs-lookup"><span data-stu-id="872ea-106">To stay on top of upcoming Teams features, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span></span>

<span data-ttu-id="872ea-107">Las etiquetas de Microsoft Teams permiten a los usuarios comunicarse con un subconjunto de personas de un equipo.</span><span class="sxs-lookup"><span data-stu-id="872ea-107">Tags in Microsoft Teams let users communicate with a subset of people on a team.</span></span> <span data-ttu-id="872ea-108">Se pueden agregar etiquetas a uno o varios miembros del equipo para conectarse fácilmente con el subconjunto adecuado de personas.</span><span class="sxs-lookup"><span data-stu-id="872ea-108">Tags can be added to one or multiple team members to easily connect with the right subset of people.</span></span> <span data-ttu-id="872ea-109">Los miembros y propietarios del equipo (si la característica está habilitada) pueden agregar una o varias etiquetas a una persona.</span><span class="sxs-lookup"><span data-stu-id="872ea-109">Team owners and members (if the feature is enabled for them) can add one or more tags to a person.</span></span> <span data-ttu-id="872ea-110">Después, las etiquetas se pueden usar en @mentions por cualquier persona del equipo en una publicación de canal para comunicarse solo con las personas que tienen asignada esa etiqueta.</span><span class="sxs-lookup"><span data-stu-id="872ea-110">The tags can then be used in @mentions by anyone on the team in a channel post to communicate with only those people who are assigned that tag.</span></span>

> [!NOTE]
> <span data-ttu-id="872ea-111">Las etiquetas aún no son compatibles con los canales privados.</span><span class="sxs-lookup"><span data-stu-id="872ea-111">Tags are not yet supported in private channels.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="872ea-112">Cómo funcionan las etiquetas</span><span class="sxs-lookup"><span data-stu-id="872ea-112">How tags work</span></span>

<span data-ttu-id="872ea-113">Se puede Agregar una etiqueta a una persona en un equipo específico.</span><span class="sxs-lookup"><span data-stu-id="872ea-113">A tag can be added to a person on a specific team.</span></span> <span data-ttu-id="872ea-114">Una vez agregada una etiqueta, se puede usar en @mentions de cualquier canal estándar del equipo.</span><span class="sxs-lookup"><span data-stu-id="872ea-114">After a tag is added, it can be used in @mentions in any standard channel of the team.</span></span> <span data-ttu-id="872ea-115">Estos son algunos ejemplos de cómo se pueden usar etiquetas en Teams:</span><span class="sxs-lookup"><span data-stu-id="872ea-115">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="872ea-116">Un administrador de tienda desea enviar un anuncio a un canal y notificar a todos los cajeros.</span><span class="sxs-lookup"><span data-stu-id="872ea-116">A store manager wants to post an announcement to a channel and notify all cashiers.</span></span>
- <span data-ttu-id="872ea-117">Un director de producto de grupo quiere enviar un mensaje a todos los jefes de producto de un canal.</span><span class="sxs-lookup"><span data-stu-id="872ea-117">A group product manager wants to message all product managers in a channel.</span></span>
- <span data-ttu-id="872ea-118">Un administrador de un hospital quiere enviar un mensaje a todos los radiologists de un canal.</span><span class="sxs-lookup"><span data-stu-id="872ea-118">A hospital administrator wants to send a message to all radiologists in a channel.</span></span>

<span data-ttu-id="872ea-119">Para obtener más información, consulte [usar las etiquetas en Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span><span class="sxs-lookup"><span data-stu-id="872ea-119">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

## <a name="manage-tags-for-your-organization"></a><span data-ttu-id="872ea-120">Administrar etiquetas para la organización</span><span class="sxs-lookup"><span data-stu-id="872ea-120">Manage tags for your organization</span></span>

<span data-ttu-id="872ea-121">Como administrador, puede controlar quién puede agregar etiquetas y cómo se usan las etiquetas en la organización en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="872ea-121">As an admin, you can control who can add tags and how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Captura de pantalla de la configuración de etiquetado en el centro de administración de Microsoft Teams](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a><span data-ttu-id="872ea-123">Establecer quién puede agregar etiquetas</span><span class="sxs-lookup"><span data-stu-id="872ea-123">Set who can add tags</span></span>

<span data-ttu-id="872ea-124">De forma predeterminada, los propietarios del equipo pueden agregar etiquetas.</span><span class="sxs-lookup"><span data-stu-id="872ea-124">By default, team owners can add tags.</span></span> <span data-ttu-id="872ea-125">Puede cambiar esta configuración para permitir que los propietarios del equipo y los miembros del equipo agreguen etiquetas o desactive las etiquetas de su organización.</span><span class="sxs-lookup"><span data-stu-id="872ea-125">You can change this setting to allow team owners and team members to add tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="872ea-126">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en configuración de la **organización** > de**Teams**.</span><span class="sxs-lookup"><span data-stu-id="872ea-126">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="872ea-127">En **etiquetado**, junto a **etiquetado está habilitado para**, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="872ea-127">Under **Tagging**, next to **Tagging is enabled for**, select one of the following options:</span></span>

    - <span data-ttu-id="872ea-128">**Miembros y propietarios del equipo**: permita que los miembros y los propietarios del equipo agreguen etiquetas.</span><span class="sxs-lookup"><span data-stu-id="872ea-128">**Team owners and members**: Allow team owners and members to add tags.</span></span>
    - <span data-ttu-id="872ea-129">**Propietarios de equipo**: permita que los propietarios del equipo agreguen etiquetas.</span><span class="sxs-lookup"><span data-stu-id="872ea-129">**Team owners**: Allow team owners to add tags.</span></span>
    - <span data-ttu-id="872ea-130">**Desactivado**: desactivar etiquetas.</span><span class="sxs-lookup"><span data-stu-id="872ea-130">**Disabled**: Turn off tags.</span></span>

### <a name="configure-tags-settings"></a><span data-ttu-id="872ea-131">Configurar las opciones de etiquetas</span><span class="sxs-lookup"><span data-stu-id="872ea-131">Configure tags settings</span></span>

<span data-ttu-id="872ea-132">Puede configurar las siguientes opciones de etiquetas para controlar cómo se usan las etiquetas en la organización.</span><span class="sxs-lookup"><span data-stu-id="872ea-132">You can configure the following tags settings to control how tags are used across your organization.</span></span>

1. <span data-ttu-id="872ea-133">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en configuración de la **organización** > de**Teams**.</span><span class="sxs-lookup"><span data-stu-id="872ea-133">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="872ea-134">En **etiquetado**, defina lo siguiente según las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="872ea-134">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="872ea-135">El **propietario del equipo puede invalidar quién puede aplicar etiquetas**: cuando esta opción está activada, los propietarios del equipo pueden permitir o no miembros agregar etiquetas en la configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="872ea-135">**Team owner can override who can apply tags**: When this is turned on, team owners can allow or disallow members to add tags in team settings.</span></span>
    - <span data-ttu-id="872ea-136">**Los miembros pueden agregar etiquetas adicionales**: Si permite que los integrantes del grupo agreguen etiquetas, Active esta opción para permitir que los miembros del equipo agreguen etiquetas distintas de las sugeridas como predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="872ea-136">**Members can add additional tags**: If you allow team members to add tags, turn this on to let team members add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="872ea-137">Si esta opción está desactivada, los miembros del equipo solo pueden usar las etiquetas predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="872ea-137">If this is turned off, team members can only use the default tags.</span></span>
    - <span data-ttu-id="872ea-138">**Sugerencias de etiquetas predeterminadas**: Use esta opción para agregar un conjunto de etiquetas predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="872ea-138">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="872ea-139">Puede Agregar hasta 25 etiquetas y cada etiqueta puede contener un máximo de 25 caracteres.</span><span class="sxs-lookup"><span data-stu-id="872ea-139">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="872ea-140">Los miembros y propietarios del equipo (si la característica está habilitada) pueden usar estas sugerencias, agregarlas o crear un nuevo conjunto de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="872ea-140">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>

## <a name="manage-tags-settings-for-a-team"></a><span data-ttu-id="872ea-141">Administrar la configuración de etiquetas de un equipo</span><span class="sxs-lookup"><span data-stu-id="872ea-141">Manage tags settings for a team</span></span>

<span data-ttu-id="872ea-142">Si activó la opción el **propietario del equipo puede invalidar quién puede aplicar etiquetas** en el centro de administración de Microsoft Teams, los propietarios del equipo pueden establecer si los miembros pueden agregar etiquetas en el nivel de equipo.</span><span class="sxs-lookup"><span data-stu-id="872ea-142">If you turned on the **Team owner can override who can apply tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="872ea-143">Para ello, en la pestaña **configuración** de un equipo, vaya a **etiquetas**y, después, elija quién puede agregar etiquetas.</span><span class="sxs-lookup"><span data-stu-id="872ea-143">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![Captura de pantalla de la configuración de etiquetas en el nivel de equipo](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a><span data-ttu-id="872ea-145">Agregar etiquetas en Teams</span><span class="sxs-lookup"><span data-stu-id="872ea-145">Add tags in Teams</span></span>

<span data-ttu-id="872ea-146">En Teams, la pestaña **miembros** de la página Administrar equipo de un equipo incluye una columna **etiquetas** .</span><span class="sxs-lookup"><span data-stu-id="872ea-146">In Teams, the **Members** tab of the Manage team page for a team includes a **Tags** column.</span></span> <span data-ttu-id="872ea-147">Los miembros y propietarios del equipo (si la característica está habilitada) pueden hacer clic en **administrar etiquetas** junto a un miembro para ver la lista de etiquetas sugeridas para ese miembro y agregar etiquetas a la lista.</span><span class="sxs-lookup"><span data-stu-id="872ea-147">Team owners and members (if the feature is enabled for them) can click **Manage tags** next to a member to see the list of suggested tags for that member and add tags to the list.</span></span>

![<span data-ttu-id="872ea-148">Captura de pantalla de cómo aplicar etiquetas en el cliente de Teams</span><span class="sxs-lookup"><span data-stu-id="872ea-148">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png) 
