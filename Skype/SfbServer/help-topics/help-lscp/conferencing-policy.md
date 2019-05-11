---
title: Directiva de conferencia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
description: Directiva de conferencia define las características y capacidades que los usuarios tendrán a su disposición durante una conferencia (también conocida como una reunión).
ms.openlocfilehash: 62aa6dbe2c237cd27a1dc8798da70a68685640ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929093"
---
# <a name="conferencing-policy"></a><span data-ttu-id="c7132-103">Directiva de conferencia</span><span class="sxs-lookup"><span data-stu-id="c7132-103">Conferencing Policy</span></span>

<span data-ttu-id="c7132-104">Directiva de conferencia define las características y capacidades que los usuarios tendrán a su disposición durante una conferencia (también conocida como una reunión).</span><span class="sxs-lookup"><span data-stu-id="c7132-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span>

<span data-ttu-id="c7132-105">Las directivas de conferencia incluyen la directiva global y, opcionalmente, una o varias directivas de usuario y de sitio:</span><span class="sxs-lookup"><span data-stu-id="c7132-105">Conferencing policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="c7132-106">**Directiva global:** De forma predeterminada, se crea la directiva global.</span><span class="sxs-lookup"><span data-stu-id="c7132-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="c7132-107">Puede editar la directiva global, pero no puede eliminar.</span><span class="sxs-lookup"><span data-stu-id="c7132-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="c7132-108">Si se intenta quitar la directiva global, se restablecen todas las opciones a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="c7132-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="c7132-109">**(Opcionales) de directivas de sitio:** Puede crear uno o varios sitios las directivas de conferencia, cada uno de los cuales se aplica a un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="c7132-109">**Site policies (optional):** You can create one or more site conferencing policies, each of which applies to a specific site.</span></span> <span data-ttu-id="c7132-110">Las directivas de sitio invalidar la directiva global.</span><span class="sxs-lookup"><span data-stu-id="c7132-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="c7132-111">**Las directivas de usuario (opcionales):** Puede crear uno o varios usuarios directivas de conferencia, cada uno de los cuales se aplica a un usuario específico o grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="c7132-111">**User policies (optional):** You can create one or more user conferencing policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="c7132-112">Las directivas de usuario reemplazan las directivas globales y las directivas de sitio.</span><span class="sxs-lookup"><span data-stu-id="c7132-112">User policies override the global policy and site policies.</span></span>

<span data-ttu-id="c7132-113">La página **Directiva de conferencia** muestra una lista de todas las directivas de conferencia que se definen para su organización.</span><span class="sxs-lookup"><span data-stu-id="c7132-113">The **Conferencing Policy** page displays a list of all the conferencing policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="c7132-114">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="c7132-114">Tasks you can perform</span></span>

<span data-ttu-id="c7132-115">En la página **Directiva de ubicación** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="c7132-115">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="c7132-116">Crear una nueva directiva de conferencia de sitio o directiva de conferencia de usuario</span><span class="sxs-lookup"><span data-stu-id="c7132-116">Create a new site conferencing policy or user conferencing policy</span></span>

- <span data-ttu-id="c7132-117">Cambiar la directiva global o una directiva de sitio o de usuario existente</span><span class="sxs-lookup"><span data-stu-id="c7132-117">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="c7132-118">Eliminar una directiva de sitio o de usuario</span><span class="sxs-lookup"><span data-stu-id="c7132-118">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c7132-119">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="c7132-119">UI Reference</span></span>

<span data-ttu-id="c7132-120">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="c7132-120">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="c7132-121">**Nuevo** Inicia una nueva directiva de conferencia de sitio o directiva de conferencia de usuario.</span><span class="sxs-lookup"><span data-stu-id="c7132-121">**New** Starts a new site conferencing policy or user conferencing policy.</span></span>

- <span data-ttu-id="c7132-122">**Editar** Se abre la directiva de conferencia seleccionada para editarla, selecciona todas las directivas de conferencia en la lista o elimina la directiva de sitio seleccionado o la directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="c7132-122">**Edit** Opens the selected conferencing policy to edit it, selects all conferencing policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c7132-123">En el caso de la directiva global, con **Eliminar** se restablece la configuración a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="c7132-123">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="c7132-124">**Actualizar** Actualiza la lista de directivas de conferencia.</span><span class="sxs-lookup"><span data-stu-id="c7132-124">**Refresh** Refreshes the list of conferencing policies.</span></span>

<span data-ttu-id="c7132-125">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="c7132-125">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="c7132-126">**Nombre** Identifica la directiva de conferencia.</span><span class="sxs-lookup"><span data-stu-id="c7132-126">**Name** Identifies the conferencing policy.</span></span>

- <span data-ttu-id="c7132-127">**Ámbito** Identifica el ámbito de la directiva de conferencia: global, sitio o usuario.</span><span class="sxs-lookup"><span data-stu-id="c7132-127">**Scope** Identifies the scope of the conferencing policy: global, site, or user.</span></span>

- <span data-ttu-id="c7132-128">**Colaboración de datos** Comprueba si la directiva de conferencia especifica que la colaboración de datos está permitida en las conferencias.</span><span class="sxs-lookup"><span data-stu-id="c7132-128">**Data collaboration** Checked if the conferencing policy specifies that data collaboration is allowed in conferences.</span></span>

- <span data-ttu-id="c7132-129">**Uso compartido de aplicaciones** Comprueba si la directiva de conferencia especifica que se permite el uso compartido de aplicaciones en las conferencias.</span><span class="sxs-lookup"><span data-stu-id="c7132-129">**Application sharing** Checked if the conferencing policy specifies that application sharing is allowed in conferences.</span></span>

- <span data-ttu-id="c7132-130">**Audio** Comprueba si la directiva de conferencia especifica que el audio está permitido en las conferencias.</span><span class="sxs-lookup"><span data-stu-id="c7132-130">**Audio** Checked if the conferencing policy specifies that audio is allowed in conferences.</span></span>

- <span data-ttu-id="c7132-131">**Vídeo** Comprueba si la directiva de conferencia especifica que el vídeo está permitido en las conferencias.</span><span class="sxs-lookup"><span data-stu-id="c7132-131">**Video** Checked if the conferencing policy specifies that video is allowed in conferences.</span></span>

- <span data-ttu-id="c7132-132">**RTC** Comprueba si la directiva de conferencia especifica que está permitida la conferencia de acceso telefónico RTC.</span><span class="sxs-lookup"><span data-stu-id="c7132-132">**PSTN** Checked if the conferencing policy specifies that PSTN dial-in conferencing is allowed.</span></span>

- <span data-ttu-id="c7132-133">**Grabación** Comprueba si la directiva de conferencia especifica que la grabación está permitida en las conferencias.</span><span class="sxs-lookup"><span data-stu-id="c7132-133">**Recording** Checked if the conferencing policy specifies that recording is allowed in conferences.</span></span>

<span data-ttu-id="c7132-p104">Para más detalles sobre las características y capacidades de la conferencia, mire [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) en la documentación de planeación. Para más detalles sobre cómo trabajar con directivas de conferencias, mire [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="c7132-p104">For details about conferencing features and capabilities, see [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation. For details about working with conferencing policies, see [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>


