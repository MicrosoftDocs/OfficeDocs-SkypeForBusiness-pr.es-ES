---
title: Directiva de conferencia
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
description: Directiva de conferencia define las características y capacidades que tienen disponibles los usuarios durante una conferencia (también conocida como una reunión).
ms.openlocfilehash: e1fea90ed978602c45abf7b71035506b0c039058
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="conferencing-policy"></a><span data-ttu-id="b6745-103">Directiva de conferencia</span><span class="sxs-lookup"><span data-stu-id="b6745-103">Conferencing Policy</span></span>
 
<span data-ttu-id="b6745-104">Directiva de conferencia define las características y capacidades que tienen disponibles los usuarios durante una conferencia (también conocida como una reunión).</span><span class="sxs-lookup"><span data-stu-id="b6745-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span>
  
<span data-ttu-id="b6745-105">Las directivas de la conferencia incluyen la directiva global y, opcionalmente, una o más directivas de sitios y usuarios:</span><span class="sxs-lookup"><span data-stu-id="b6745-105">Conferencing policies include the global policy and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="b6745-106">**Directiva global:** De forma predeterminada, se crea la directiva global.</span><span class="sxs-lookup"><span data-stu-id="b6745-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="b6745-107">Puede editar la directiva global, pero no puede eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="b6745-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="b6745-108">Si intenta quitar la directiva global, todos los valores se restablecen a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b6745-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>
    
- <span data-ttu-id="b6745-109">**Sitio de directivas (opcionales):** Puede crear una o varias conferencias directivas de sitios, cada uno de los cuales se aplica a un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="b6745-109">**Site policies (optional):** You can create one or more site conferencing policies, each of which applies to a specific site.</span></span> <span data-ttu-id="b6745-110">Directivas de sitio anulan la directiva global.</span><span class="sxs-lookup"><span data-stu-id="b6745-110">Site policies override the global policy.</span></span>
    
- <span data-ttu-id="b6745-111">**Las directivas de usuario (opcionales):** Puede crear una o varias conferencias directivas de usuario, cada uno de los cuales se aplica a un usuario o grupo específico de usuarios.</span><span class="sxs-lookup"><span data-stu-id="b6745-111">**User policies (optional):** You can create one or more user conferencing policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="b6745-112">Directivas de usuario anulan la directiva global y las políticas del sitio.</span><span class="sxs-lookup"><span data-stu-id="b6745-112">User policies override the global policy and site policies.</span></span>
    
<span data-ttu-id="b6745-113">La página **Directiva de conferencia** muestra una lista de todas las directivas de la conferencia que se definen para su organización.</span><span class="sxs-lookup"><span data-stu-id="b6745-113">The **Conferencing Policy** page displays a list of all the conferencing policies that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="b6745-114">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="b6745-114">Tasks you can perform</span></span>

<span data-ttu-id="b6745-115">En la página **Directiva de ubicación** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="b6745-115">You can perform the following tasks from the **Location Policy** page:</span></span>
  
- <span data-ttu-id="b6745-116">Crear una nueva directiva de conferencia de sitio o usuario conferencia</span><span class="sxs-lookup"><span data-stu-id="b6745-116">Create a new site conferencing policy or user conferencing policy</span></span>
    
- <span data-ttu-id="b6745-117">Cambiar la directiva global o una directiva de sitio o de usuario existente</span><span class="sxs-lookup"><span data-stu-id="b6745-117">Change the global policy or an existing site policy or user policy</span></span>
    
- <span data-ttu-id="b6745-118">Eliminar una directiva de sitio o de usuario</span><span class="sxs-lookup"><span data-stu-id="b6745-118">Delete a site policy or user policy</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="b6745-119">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="b6745-119">UI Reference</span></span>

<span data-ttu-id="b6745-120">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="b6745-120">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="b6745-121">**Nuevo** Inicia una nueva política de conferencia de sitio o usuario conferencias.</span><span class="sxs-lookup"><span data-stu-id="b6745-121">**New** Starts a new site conferencing policy or user conferencing policy.</span></span>
    
- <span data-ttu-id="b6745-122">**Editar** Abre la directiva de la conferencia seleccionada para modificarlo, selecciona todas las directivas de la conferencia de la lista o elimina la política de sitio seleccionado o usuario.</span><span class="sxs-lookup"><span data-stu-id="b6745-122">**Edit** Opens the selected conferencing policy to edit it, selects all conferencing policies in the list, or deletes the selected site policy or user policy.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b6745-123">En el caso de la directiva global, con **Eliminar** se restablece la configuración a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b6745-123">For the global policy, **Delete** resets the settings to the default values.</span></span>
  
- <span data-ttu-id="b6745-124">**Actualizar** Actualiza la lista de directivas de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="b6745-124">**Refresh** Refreshes the list of conferencing policies.</span></span>
    
<span data-ttu-id="b6745-125">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="b6745-125">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="b6745-126">**Nombre** Identifica la directiva de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="b6745-126">**Name** Identifies the conferencing policy.</span></span>
    
- <span data-ttu-id="b6745-127">**Ámbito de aplicación** Identifica el ámbito de la directiva de la conferencia: global, sitio o usuario.</span><span class="sxs-lookup"><span data-stu-id="b6745-127">**Scope** Identifies the scope of the conferencing policy: global, site, or user.</span></span>
    
- <span data-ttu-id="b6745-128">**Colaboración de datos** Comprueba si la directiva de conferencia especifica que se permite la colaboración de datos de conferencias.</span><span class="sxs-lookup"><span data-stu-id="b6745-128">**Data collaboration** Checked if the conferencing policy specifies that data collaboration is allowed in conferences.</span></span>
    
- <span data-ttu-id="b6745-129">**Uso compartido de aplicaciones** Comprueba si la directiva de conferencia especifica que está permitido el uso compartido de aplicaciones en conferencias.</span><span class="sxs-lookup"><span data-stu-id="b6745-129">**Application sharing** Checked if the conferencing policy specifies that application sharing is allowed in conferences.</span></span>
    
- <span data-ttu-id="b6745-130">**Audio** Comprueba si la directiva de conferencia especifica que el audio se permite en las conferencias.</span><span class="sxs-lookup"><span data-stu-id="b6745-130">**Audio** Checked if the conferencing policy specifies that audio is allowed in conferences.</span></span>
    
- <span data-ttu-id="b6745-131">**Vídeo** Comprueba si la directiva de conferencia especifica que el vídeo se permite en las conferencias.</span><span class="sxs-lookup"><span data-stu-id="b6745-131">**Video** Checked if the conferencing policy specifies that video is allowed in conferences.</span></span>
    
- <span data-ttu-id="b6745-132">**PSTN** Comprueba si la directiva de conferencia especifica que se permiten conferencias de acceso telefónico de PSTN.</span><span class="sxs-lookup"><span data-stu-id="b6745-132">**PSTN** Checked if the conferencing policy specifies that PSTN dial-in conferencing is allowed.</span></span>
    
- <span data-ttu-id="b6745-133">**Grabación** Comprueba si la directiva de conferencia especifica que se permite la grabación de conferencias.</span><span class="sxs-lookup"><span data-stu-id="b6745-133">**Recording** Checked if the conferencing policy specifies that recording is allowed in conferences.</span></span>
    
<span data-ttu-id="b6745-134">Para obtener más información acerca de las características de conferencia y capacidades, vea [Información general de la conferencia](http://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) en la documentación de planeamiento.</span><span class="sxs-lookup"><span data-stu-id="b6745-134">For details about conferencing features and capabilities, see [Overview of Conferencing](http://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation.</span></span> <span data-ttu-id="b6745-135">Para obtener más información acerca de cómo trabajar con directivas de conferencia, vea [Directivas de conferencias](http://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) en la documentación de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="b6745-135">For details about working with conferencing policies, see [Conferencing Policies](http://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>
  

