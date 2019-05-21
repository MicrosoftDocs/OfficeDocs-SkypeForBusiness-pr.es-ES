---
title: Directiva de conferencia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
ROBOTS: NOINDEX, NOFOLLOW
description: La Directiva de conferencia define las características y capacidades que los usuarios tienen disponibles durante una conferencia (también conocido como reunión).
ms.openlocfilehash: 1757af1665b3ee39bbc8a418c6372713e0af50ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300241"
---
# <a name="conferencing-policy"></a><span data-ttu-id="c35d4-103">Directiva de conferencia</span><span class="sxs-lookup"><span data-stu-id="c35d4-103">Conferencing Policy</span></span>

<span data-ttu-id="c35d4-104">La Directiva de conferencia define las características y capacidades que los usuarios tienen disponibles durante una conferencia (también conocido como reunión).</span><span class="sxs-lookup"><span data-stu-id="c35d4-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span>

<span data-ttu-id="c35d4-105">Las directivas de Conferencia incluyen la directiva global y, opcionalmente, una o varias directivas de sitio y usuario:</span><span class="sxs-lookup"><span data-stu-id="c35d4-105">Conferencing policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="c35d4-106">**Directiva global:** La directiva global se crea de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c35d4-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="c35d4-107">Puede editar la directiva global, pero no puede eliminarla.</span><span class="sxs-lookup"><span data-stu-id="c35d4-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="c35d4-108">Si intenta quitar la directiva global, todos los valores de configuración se restablecen a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="c35d4-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="c35d4-109">**Directivas de sitio (opcional):** Puede crear una o más directivas de conferencia de sitios, cada una de las cuales se aplica a un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="c35d4-109">**Site policies (optional):** You can create one or more site conferencing policies, each of which applies to a specific site.</span></span> <span data-ttu-id="c35d4-110">Las directivas de sitio invalidan la directiva global.</span><span class="sxs-lookup"><span data-stu-id="c35d4-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="c35d4-111">**Directivas de usuario (opcional):** Puede crear una o más directivas de conferencia de usuario, cada una de las cuales se aplica a un usuario específico o a un grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="c35d4-111">**User policies (optional):** You can create one or more user conferencing policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="c35d4-112">Las directivas de usuario invalidan la directiva global y las directivas del sitio.</span><span class="sxs-lookup"><span data-stu-id="c35d4-112">User policies override the global policy and site policies.</span></span>

<span data-ttu-id="c35d4-113">En la página **Directiva de conferencia** se muestra una lista de todas las directivas de conferencia definidas para su organización.</span><span class="sxs-lookup"><span data-stu-id="c35d4-113">The **Conferencing Policy** page displays a list of all the conferencing policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="c35d4-114">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="c35d4-114">Tasks you can perform</span></span>

<span data-ttu-id="c35d4-115">En la página **Directiva de ubicación** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="c35d4-115">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="c35d4-116">Crear una nueva Directiva de conferencia de sitio o una directiva de conferencia de usuario</span><span class="sxs-lookup"><span data-stu-id="c35d4-116">Create a new site conferencing policy or user conferencing policy</span></span>

- <span data-ttu-id="c35d4-117">Cambiar la directiva global o una directiva de sitio o de usuario existente</span><span class="sxs-lookup"><span data-stu-id="c35d4-117">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="c35d4-118">Eliminar una directiva de sitio o de usuario</span><span class="sxs-lookup"><span data-stu-id="c35d4-118">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c35d4-119">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="c35d4-119">UI Reference</span></span>

<span data-ttu-id="c35d4-120">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="c35d4-120">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="c35d4-121">**Nuevo** Inicia una nueva Directiva de conferencia de sitio o una directiva de conferencia de usuario.</span><span class="sxs-lookup"><span data-stu-id="c35d4-121">**New** Starts a new site conferencing policy or user conferencing policy.</span></span>

- <span data-ttu-id="c35d4-122">**Editar** Abre la Directiva de conferencia seleccionada para modificarla, selecciona todas las directivas de conferencia de la lista o elimina la Directiva del sitio o la Directiva de usuario seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c35d4-122">**Edit** Opens the selected conferencing policy to edit it, selects all conferencing policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c35d4-123">En el caso de la directiva global, con **Eliminar** se restablece la configuración a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="c35d4-123">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="c35d4-124">**Actualizar** Actualiza la lista de directivas de conferencia.</span><span class="sxs-lookup"><span data-stu-id="c35d4-124">**Refresh** Refreshes the list of conferencing policies.</span></span>

<span data-ttu-id="c35d4-125">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="c35d4-125">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="c35d4-126">**Nombre** Identifica la Directiva de conferencia.</span><span class="sxs-lookup"><span data-stu-id="c35d4-126">**Name** Identifies the conferencing policy.</span></span>

- <span data-ttu-id="c35d4-127">**Ámbito** Identifica el ámbito de la Directiva de Conferencia: global, de sitio o de usuario.</span><span class="sxs-lookup"><span data-stu-id="c35d4-127">**Scope** Identifies the scope of the conferencing policy: global, site, or user.</span></span>

- <span data-ttu-id="c35d4-128">**Colaboración de datos** Se activa si la Directiva de conferencia especifica que se permite la colaboración de datos en conferencias.</span><span class="sxs-lookup"><span data-stu-id="c35d4-128">**Data collaboration** Checked if the conferencing policy specifies that data collaboration is allowed in conferences.</span></span>

- <span data-ttu-id="c35d4-129">**Uso compartido de aplicaciones** Se activa si la Directiva de conferencia especifica que se permite el uso compartido de aplicaciones en conferencias.</span><span class="sxs-lookup"><span data-stu-id="c35d4-129">**Application sharing** Checked if the conferencing policy specifies that application sharing is allowed in conferences.</span></span>

- <span data-ttu-id="c35d4-130">**Audio** Se activa si la Directiva de conferencia especifica que se permite el audio en las conferencias.</span><span class="sxs-lookup"><span data-stu-id="c35d4-130">**Audio** Checked if the conferencing policy specifies that audio is allowed in conferences.</span></span>

- <span data-ttu-id="c35d4-131">**Vídeo** Se activa si la Directiva de conferencia especifica que se permite el vídeo en las conferencias.</span><span class="sxs-lookup"><span data-stu-id="c35d4-131">**Video** Checked if the conferencing policy specifies that video is allowed in conferences.</span></span>

- <span data-ttu-id="c35d4-132">**RTC** Se activa si la Directiva de conferencia especifica que se permiten las conferencias de acceso telefónico local RTC.</span><span class="sxs-lookup"><span data-stu-id="c35d4-132">**PSTN** Checked if the conferencing policy specifies that PSTN dial-in conferencing is allowed.</span></span>

- <span data-ttu-id="c35d4-133">**Grabación** Se activa si la Directiva de conferencia especifica que la grabación está permitida en las conferencias.</span><span class="sxs-lookup"><span data-stu-id="c35d4-133">**Recording** Checked if the conferencing policy specifies that recording is allowed in conferences.</span></span>

<span data-ttu-id="c35d4-p104">Para más detalles sobre las características y capacidades de la conferencia, mire [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) en la documentación de planeación. Para más detalles sobre cómo trabajar con directivas de conferencias, mire [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="c35d4-p104">For details about conferencing features and capabilities, see [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation. For details about working with conferencing policies, see [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>


