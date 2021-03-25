---
title: Directiva de conferencia
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
description: La directiva de conferencias define las características y capacidades que los usuarios tendrán a su disposición durante una conferencia (también denominada "reunión")
ms.openlocfilehash: 6d69c463a9aa8a1e151b0787dfbfebf4e24fb693
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115370"
---
# <a name="conferencing-policy"></a><span data-ttu-id="a25bd-103">Directiva de conferencias</span><span class="sxs-lookup"><span data-stu-id="a25bd-103">Conferencing Policy</span></span>

<span data-ttu-id="a25bd-104">La directiva de conferencias define las características y capacidades que los usuarios tendrán a su disposición durante una conferencia (también denominada "reunión")</span><span class="sxs-lookup"><span data-stu-id="a25bd-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span>

<span data-ttu-id="a25bd-105">Las directivas de conferencia incluyen la directiva global y, de forma opcional, una o varias directivas de usuario y de sitio:</span><span class="sxs-lookup"><span data-stu-id="a25bd-105">Conferencing policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="a25bd-106">**Directiva global:** La directiva global se crea de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a25bd-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="a25bd-107">Puede editar la directiva global, pero no puede eliminarla.</span><span class="sxs-lookup"><span data-stu-id="a25bd-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="a25bd-108">Si intenta eliminarla, toda la configuración se restablecerá a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a25bd-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="a25bd-109">**Directivas de sitio (opcional):** Puede crear una o varias directivas de conferencia de sitio, cada una de las cuales se aplica a un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="a25bd-109">**Site policies (optional):** You can create one or more site conferencing policies, each of which applies to a specific site.</span></span> <span data-ttu-id="a25bd-110">Las directivas de sitio anulan la directiva global.</span><span class="sxs-lookup"><span data-stu-id="a25bd-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="a25bd-111">**Directivas de usuario (opcional):** Puede crear una o varias directivas de conferencia de usuario, cada una de las cuales se aplica a un usuario o grupo de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="a25bd-111">**User policies (optional):** You can create one or more user conferencing policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="a25bd-112">Las directivas de usuario anulan la directiva global y las directivas de sitio.</span><span class="sxs-lookup"><span data-stu-id="a25bd-112">User policies override the global policy and site policies.</span></span>

<span data-ttu-id="a25bd-113">La página **Directiva de conferencia** muestra una lista de todas las directivas de conferencia definidas para su organización.</span><span class="sxs-lookup"><span data-stu-id="a25bd-113">The **Conferencing Policy** page displays a list of all the conferencing policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="a25bd-114">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="a25bd-114">Tasks you can perform</span></span>

<span data-ttu-id="a25bd-115">Puede realizar las siguientes tareas desde la página **Directiva de ubicación**:</span><span class="sxs-lookup"><span data-stu-id="a25bd-115">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="a25bd-116">Crear una nueva directiva de conferencia de sitio o de conferencia de usuario</span><span class="sxs-lookup"><span data-stu-id="a25bd-116">Create a new site conferencing policy or user conferencing policy</span></span>

- <span data-ttu-id="a25bd-117">Cambiar la directiva global o una directiva de sitio o de usuario existente</span><span class="sxs-lookup"><span data-stu-id="a25bd-117">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="a25bd-118">Eliminar una directiva de sitio o de usuario</span><span class="sxs-lookup"><span data-stu-id="a25bd-118">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="a25bd-119">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="a25bd-119">UI Reference</span></span>

<span data-ttu-id="a25bd-120">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="a25bd-120">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="a25bd-121">**Nuevo** Inicia una nueva directiva de conferencia de sitio o una directiva de conferencia de usuario.</span><span class="sxs-lookup"><span data-stu-id="a25bd-121">**New** Starts a new site conferencing policy or user conferencing policy.</span></span>

- <span data-ttu-id="a25bd-122">**Editar** Abre la directiva de conferencia seleccionada para editarla, selecciona todas las directivas de conferencia de la lista o elimina la directiva de sitio o la directiva de usuario seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a25bd-122">**Edit** Opens the selected conferencing policy to edit it, selects all conferencing policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a25bd-123">Para la directiva global, **Eliminar** restablece la configuración a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a25bd-123">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="a25bd-124">**Actualizar** Actualiza la lista de directivas de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a25bd-124">**Refresh** Refreshes the list of conferencing policies.</span></span>

<span data-ttu-id="a25bd-125">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="a25bd-125">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="a25bd-126">**Nombre** Identifica la directiva de conferencia.</span><span class="sxs-lookup"><span data-stu-id="a25bd-126">**Name** Identifies the conferencing policy.</span></span>

- <span data-ttu-id="a25bd-127">**Ámbito** Identifica el ámbito de la directiva de conferencia: global, de sitio o de usuario.</span><span class="sxs-lookup"><span data-stu-id="a25bd-127">**Scope** Identifies the scope of the conferencing policy: global, site, or user.</span></span>

- <span data-ttu-id="a25bd-128">**Colaboración de datos** Se comprueba si la directiva de conferencia especifica que la colaboración de datos está permitida en las conferencias.</span><span class="sxs-lookup"><span data-stu-id="a25bd-128">**Data collaboration** Checked if the conferencing policy specifies that data collaboration is allowed in conferences.</span></span>

- <span data-ttu-id="a25bd-129">**Uso compartido de aplicaciones** Se comprueba si la directiva de conferencia especifica que se permite el uso compartido de aplicaciones en conferencias.</span><span class="sxs-lookup"><span data-stu-id="a25bd-129">**Application sharing** Checked if the conferencing policy specifies that application sharing is allowed in conferences.</span></span>

- <span data-ttu-id="a25bd-130">**Audio** Se comprueba si la directiva de conferencia especifica que el audio está permitido en las conferencias.</span><span class="sxs-lookup"><span data-stu-id="a25bd-130">**Audio** Checked if the conferencing policy specifies that audio is allowed in conferences.</span></span>

- <span data-ttu-id="a25bd-131">**Vídeo** Se comprueba si la directiva de conferencia especifica que el vídeo está permitido en conferencias.</span><span class="sxs-lookup"><span data-stu-id="a25bd-131">**Video** Checked if the conferencing policy specifies that video is allowed in conferences.</span></span>

- <span data-ttu-id="a25bd-132">**RTC** Se comprueba si la directiva de conferencia especifica que se permite la conferencia de acceso telefónico local RTC.</span><span class="sxs-lookup"><span data-stu-id="a25bd-132">**PSTN** Checked if the conferencing policy specifies that PSTN dial-in conferencing is allowed.</span></span>

- <span data-ttu-id="a25bd-133">**Grabación** Se comprueba si la directiva de conferencia especifica que se permite la grabación en conferencias.</span><span class="sxs-lookup"><span data-stu-id="a25bd-133">**Recording** Checked if the conferencing policy specifies that recording is allowed in conferences.</span></span>

<span data-ttu-id="a25bd-134">Para obtener detalles sobre las características y capacidades de la conferencia, vea [Overview of Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="a25bd-134">For details about conferencing features and capabilities, see [Overview of Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) in the Planning documentation.</span></span> <span data-ttu-id="a25bd-135">Para obtener detalles sobre cómo trabajar con directivas de conferencias, vea [Conferencing Policies](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="a25bd-135">For details about working with conferencing policies, see [Conferencing Policies](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) in the Operations documentation.</span></span>