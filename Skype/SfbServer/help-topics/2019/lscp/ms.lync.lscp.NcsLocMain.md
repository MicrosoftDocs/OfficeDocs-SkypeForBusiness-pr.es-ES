---
title: Directiva de ubicación
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: Las directivas de ubicación determinan si 9-1-1 (E9-1-1) mejorado está habilitado y cómo se usa, así como el modo en que la información de ubicación de usa para usuarios y contactos.
ms.openlocfilehash: 9f6d7468520b3398f186adeacffd5b393ce159b8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109576"
---
# <a name="location-policy"></a><span data-ttu-id="1eb9c-103">Directiva de ubicación</span><span class="sxs-lookup"><span data-stu-id="1eb9c-103">Location Policy</span></span>

<span data-ttu-id="1eb9c-104">Las directivas de ubicación determinan si 9-1-1 (E9-1-1) mejorado está habilitado y cómo se usa, así como el modo en que la información de ubicación de usa para usuarios y contactos.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

<span data-ttu-id="1eb9c-105">Las directivas de ubicación incluyen la directiva global y, de forma opcional, una o varias directivas de usuario y de sitio:</span><span class="sxs-lookup"><span data-stu-id="1eb9c-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="1eb9c-106">**Directiva global:** La directiva global se crea de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="1eb9c-107">Puede editar la directiva global, pero no puede eliminarla.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="1eb9c-108">Si intenta eliminarla, toda la configuración se restablecerá a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="1eb9c-109">**Directivas de sitio (opcional):** Puede crear una o varias directivas de ubicación de sitio, cada una de las cuales se aplica a un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="1eb9c-110">Las directivas de sitio anulan la directiva global.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="1eb9c-111">**Directivas de usuario (opcional):** Puede crear una o varias directivas de ubicación de usuario, cada una de las cuales se aplica a un usuario o grupo de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="1eb9c-112">Las directivas de usuario anulan la directiva global y las directivas de sitio.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-112">User policies override the global policy and site policies.</span></span>

> [!NOTE]
> <span data-ttu-id="1eb9c-113">También puede asignar directivas de ubicación a sitios de red, que son grupos de subredes.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="1eb9c-114">Las directivas de ubicación asignadas a los sitios de red prevalecen sobre las demás directivas de usuario.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="1eb9c-115">Para obtener más información sobre cómo asignar directivas de ubicación a sitios de red mediante cmdlets, vea Agregar una directiva de ubicación a un sitio de red [en Skype Empresarial Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="1eb9c-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="1eb9c-116">Para obtener más información sobre cómo usar el Panel de control de Skype Empresarial Server para asignar una directiva de ubicación a un sitio de red, vea [Configuring Network Sites](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-modifying-network-sites).</span><span class="sxs-lookup"><span data-stu-id="1eb9c-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-modifying-network-sites).</span></span>

<span data-ttu-id="1eb9c-117">La página **Directiva de ubicación** muestra una lista de todas las directivas de ubicación definidas para su organización.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="1eb9c-118">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="1eb9c-118">Tasks you can perform</span></span>

<span data-ttu-id="1eb9c-119">Puede realizar las siguientes tareas desde la página **Directiva de ubicación**:</span><span class="sxs-lookup"><span data-stu-id="1eb9c-119">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="1eb9c-120">Crear una nueva directiva de ubicación de sitio o de ubicación de usuario</span><span class="sxs-lookup"><span data-stu-id="1eb9c-120">Create a new site location policy or user location policy</span></span>

- <span data-ttu-id="1eb9c-121">Cambiar la directiva global o una directiva de sitio o de usuario existente</span><span class="sxs-lookup"><span data-stu-id="1eb9c-121">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="1eb9c-122">Eliminar una directiva de sitio o de usuario</span><span class="sxs-lookup"><span data-stu-id="1eb9c-122">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="1eb9c-123">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="1eb9c-123">UI Reference</span></span>

<span data-ttu-id="1eb9c-124">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="1eb9c-125">**Nuevo** Inicia una nueva directiva de ubicación del sitio o una directiva de ubicación de usuario.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-125">**New** Starts a new site location policy or user location policy.</span></span>

- <span data-ttu-id="1eb9c-126">**Editar** Abre la directiva de ubicación seleccionada para editarla, selecciona todas las directivas de ubicación de la lista o elimina la directiva de sitio o la directiva de usuario seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1eb9c-127">Para la directiva global, **Eliminar** restablece la configuración a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-127">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="1eb9c-128">**Actualizar** Actualiza la lista de directivas de ubicación.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-128">**Refresh** Refreshes the list of location policies.</span></span>

<span data-ttu-id="1eb9c-129">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="1eb9c-130">**Nombre** Identifica la directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-130">**Name** Identifies the location policy.</span></span>

- <span data-ttu-id="1eb9c-131">**Ámbito** Identifica el ámbito de la directiva de ubicación: global, de sitio o de usuario.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>

- <span data-ttu-id="1eb9c-132">**E9-1-1** Se comprueba si los usuarios asignados a esta directiva de ubicación están habilitados para E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>

- <span data-ttu-id="1eb9c-133">**Ubicación** Especifica si se pide a los usuarios que escriban información de ubicación cuando su cliente se registra con Skype Empresarial Server en una nueva ubicación y si ven una declinación de responsabilidades si descartan el mensaje sin especificar la información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>

- <span data-ttu-id="1eb9c-134">**Uso de RTC** Especifica el uso de la red telefónica conmutada (RTC) que se usa para determinar la ruta de voz usada para enrutar llamadas de emergencia de clientes que usan este perfil.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>

- <span data-ttu-id="1eb9c-135">**Número E9-1-1** Especifica el número que se marca para llegar a los servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="1eb9c-136">**Máscara E9-1-1** Especifica un número que marca un usuario que, a continuación, se convierte en el número de marcado de emergencia.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>

<span data-ttu-id="1eb9c-137">Para obtener más información Telefonía IP empresarial características y funcionalidades del servicio de emergencia, vea [Overview of E9-1-1](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) en la documentación sobre planeación.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) in the Planning documentation.</span></span> <span data-ttu-id="1eb9c-138">Para obtener detalles sobre cómo trabajar con directivas de ubicación, vea [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="1eb9c-138">For details about working with location policies, see [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information) in the Operations documentation.</span></span>