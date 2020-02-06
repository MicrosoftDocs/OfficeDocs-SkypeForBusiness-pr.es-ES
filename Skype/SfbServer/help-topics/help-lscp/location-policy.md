---
title: Directiva de ubicación
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: Las directivas de ubicación determinan si 9-1-1 mejorado (E9-1-1) está habilitado y el modo de usarlo, así como el modo en que la información de ubicación se usa para usuarios y contactos.
ms.openlocfilehash: 00c0635e6833c5cb4f356de2914abb50eb4ddafc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822703"
---
# <a name="location-policy"></a><span data-ttu-id="26505-103">Directiva de ubicación</span><span class="sxs-lookup"><span data-stu-id="26505-103">Location Policy</span></span>

<span data-ttu-id="26505-104">Las directivas de ubicación determinan si 9-1-1 mejorado (E9-1-1) está habilitado y el modo de usarlo, así como el modo en que la información de ubicación se usa para usuarios y contactos.</span><span class="sxs-lookup"><span data-stu-id="26505-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

<span data-ttu-id="26505-105">Las directivas de ubicación incluyen la directiva global y, de forma opcional, una o varias directivas de usuario y de sitio:</span><span class="sxs-lookup"><span data-stu-id="26505-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="26505-106">**Directiva global:** La directiva global se crea de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="26505-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="26505-107">Puede editar la directiva global, pero no puede eliminarla.</span><span class="sxs-lookup"><span data-stu-id="26505-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="26505-108">Si intenta quitar la directiva global, todos los valores de configuración se restablecen a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="26505-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="26505-109">**Directivas de sitio (opcional):** Puede crear una o más directivas de ubicación de sitios, cada una de las cuales se aplica a un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="26505-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="26505-110">Las directivas de sitio invalidan la directiva global.</span><span class="sxs-lookup"><span data-stu-id="26505-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="26505-111">**Directivas de usuario (opcional):** Puede crear una o varias directivas de ubicación de usuario, cada una de las cuales se aplica a un usuario específico o a un grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="26505-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="26505-112">Las directivas de usuario invalidan la directiva global y las directivas del sitio.</span><span class="sxs-lookup"><span data-stu-id="26505-112">User policies override the global policy and site policies.</span></span>

> [!NOTE]
> <span data-ttu-id="26505-113">También puede asignar directivas de ubicación a sitios de red, que son grupos de subredes.</span><span class="sxs-lookup"><span data-stu-id="26505-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="26505-114">Las directivas de ubicación asignadas a los sitios de red prevalecen sobre las demás directivas de usuario.</span><span class="sxs-lookup"><span data-stu-id="26505-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="26505-115">Para más información sobre cómo asignar directivas de ubicación a sitios de red con cmdlets, consulte [Agregar una directiva de ubicación a un sitio de red en Skype empresarial Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="26505-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="26505-116">Para obtener detalles sobre el uso del panel de control de Skype empresarial Server para asignar una directiva de ubicación a un sitio de red, consulte [configuración de sitios de red](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span><span class="sxs-lookup"><span data-stu-id="26505-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span>

<span data-ttu-id="26505-117">La página **Directiva de ubicación** muestra una lista de todas las directivas de ubicación definidas en la organización.</span><span class="sxs-lookup"><span data-stu-id="26505-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="26505-118">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="26505-118">Tasks you can perform</span></span>

<span data-ttu-id="26505-119">En la página **Directiva de ubicación** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="26505-119">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="26505-120">Crear una directiva de ubicación de sitio o de ubicación de usuario</span><span class="sxs-lookup"><span data-stu-id="26505-120">Create a new site location policy or user location policy</span></span>

- <span data-ttu-id="26505-121">Cambiar la directiva global o una directiva de sitio o de usuario existente</span><span class="sxs-lookup"><span data-stu-id="26505-121">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="26505-122">Eliminar una directiva de sitio o de usuario</span><span class="sxs-lookup"><span data-stu-id="26505-122">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="26505-123">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="26505-123">UI Reference</span></span>

<span data-ttu-id="26505-124">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="26505-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="26505-125">**Nuevo** Inicia una nueva Directiva de ubicación del sitio o una directiva de ubicación de usuario.</span><span class="sxs-lookup"><span data-stu-id="26505-125">**New** Starts a new site location policy or user location policy.</span></span>

- <span data-ttu-id="26505-126">**Editar** Abre la Directiva de ubicación seleccionada para editarla, selecciona todas las directivas de ubicación de la lista o elimina la Directiva de sitio o la Directiva de usuario seleccionada.</span><span class="sxs-lookup"><span data-stu-id="26505-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="26505-127">En el caso de la directiva global, con **Eliminar** se restablece la configuración a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="26505-127">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="26505-128">**Actualizar** Actualiza la lista de directivas de ubicación.</span><span class="sxs-lookup"><span data-stu-id="26505-128">**Refresh** Refreshes the list of location policies.</span></span>

<span data-ttu-id="26505-129">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="26505-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="26505-130">**Nombre** Identifica la Directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="26505-130">**Name** Identifies the location policy.</span></span>

- <span data-ttu-id="26505-131">**Ámbito** Identifica el ámbito de la Directiva de Ubicación: global, de sitio o de usuario.</span><span class="sxs-lookup"><span data-stu-id="26505-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>

- <span data-ttu-id="26505-132">**E9-1-1** Activado si los usuarios que tienen asignada esta directiva de ubicación están habilitados para E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="26505-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>

- <span data-ttu-id="26505-133">**Ubicación** Especifica si se pide a los usuarios que escriban información de ubicación cuando su cliente se registre con Skype empresarial Server en una nueva ubicación y si verán un aviso de declinación de responsabilidades si descartan la pregunta sin especificar la información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="26505-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>

- <span data-ttu-id="26505-134">**Uso de RTC** Especifica el uso de la red de telefonía pública conmutada (RTC) que se usa para determinar la ruta de voz usada para enrutar llamadas de emergencia de clientes que usan este perfil.</span><span class="sxs-lookup"><span data-stu-id="26505-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>

- <span data-ttu-id="26505-135">**E9-1-1 número** Especifica el número que se marca para alcanzar los servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="26505-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="26505-136">**Máscara E9-1-1** Especifica un número que un usuario marca y, a continuación, se convierte en el número de marcado de emergencia.</span><span class="sxs-lookup"><span data-stu-id="26505-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>

<span data-ttu-id="26505-137">Para obtener más información sobre las características y capacidades del servicio de emergencia de Enterprise Voice, consulte [información general sobre E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) en la documentación de planificación.</span><span class="sxs-lookup"><span data-stu-id="26505-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="26505-138">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span><span class="sxs-lookup"><span data-stu-id="26505-138">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


