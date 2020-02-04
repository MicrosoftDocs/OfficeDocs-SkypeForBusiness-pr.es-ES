---
title: Configuración de reuniones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
ROBOTS: NOINDEX, NOFOLLOW
description: La configuración de la reunión define el tipo de conferencias (también calledmeetings) que los usuarios pueden crear y controlar cómo (o si) los usuarios anónimos y las conferencias de acceso telefónico local pueden unirse a estas conferencias. Estas opciones solo se aplican a las reuniones programadas. No se aplican a reuniones ad-hoc que se crean haciendo clic en la opción Reunirse ahora en el cliente.
ms.openlocfilehash: 15dfed475928fe56b42e7a47522c911256b0f033
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705015"
---
# <a name="meeting-configuration"></a><span data-ttu-id="91697-105">Configuración de reuniones</span><span class="sxs-lookup"><span data-stu-id="91697-105">Meeting Configuration</span></span>

<span data-ttu-id="91697-p102">Las opciones de configuración de reuniones ayudan a definir el tipo de conferencias (también denominadas "reuniones") que los usuarios pueden crear, además de controlar cómo (o si) pueden participar en las conferencias usuarios anónimos o de conferencias de acceso telefónico. Estas opciones solo se aplican a las reuniones programadas. No se aplican a reuniones ad-hoc que se crean haciendo clic en la opción Reunirse ahora en el cliente.</span><span class="sxs-lookup"><span data-stu-id="91697-p102">Meeting configuration settings define the type of conferences (also called "meetings") that users can create, and control how (or whether) anonymous users and dial-in conferencing users can join these conferences. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the Meet Now option in the client.</span></span>

<span data-ttu-id="91697-109">Las configuraciones de reuniones se aplican en el nivel global, de sitio o de grupo:</span><span class="sxs-lookup"><span data-stu-id="91697-109">Meeting configurations apply on the global, site, or pool level:</span></span>

- <span data-ttu-id="91697-110">**Configuración de la reunión global:** De forma predeterminada, se crea la configuración de la reunión global.</span><span class="sxs-lookup"><span data-stu-id="91697-110">**Global meeting configuration:** The global meeting configuration is created by default.</span></span> <span data-ttu-id="91697-111">Puede editar la configuración global de la reunión, pero no puede eliminarla.</span><span class="sxs-lookup"><span data-stu-id="91697-111">You can edit the global meeting configuration, but you cannot delete it.</span></span> <span data-ttu-id="91697-112">Si intenta quitar la configuración de la reunión global, todos los valores de configuración se restablecerán en los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="91697-112">If you try to remove the global meeting configuration, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="91697-113">**Configuración de la reunión de sitios (opcional):** Puede crear una o más configuraciones de reunión de sitio, cada una de las cuales se aplica a un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="91697-113">**Site meeting configuration (optional):** You can create one or more site meeting configurations, each of which applies to a specific site.</span></span> <span data-ttu-id="91697-114">Las configuraciones de sitio invalidan la configuración global.</span><span class="sxs-lookup"><span data-stu-id="91697-114">Site configurations override the global configuration.</span></span>

- <span data-ttu-id="91697-115">**Configuración de reunión de grupo (opcional):** Puede crear una o más configuraciones de reunión de grupo, cada una de las cuales se aplica a un grupo específico.</span><span class="sxs-lookup"><span data-stu-id="91697-115">**Pool meeting configuration (optional):** You can create one or more pool meeting configurations, each of which applies to a specific pool.</span></span> <span data-ttu-id="91697-116">Las configuraciones de grupo invalidan la configuración global y las configuraciones de sitios.</span><span class="sxs-lookup"><span data-stu-id="91697-116">Pool configurations override the global configuration and site configurations.</span></span>

<span data-ttu-id="91697-117">La página **Configuración de reunión** muestra una lista de todas las configuraciones de reuniones definidas en su organización.</span><span class="sxs-lookup"><span data-stu-id="91697-117">The **Meeting Configuration** page displays a list of all the meeting configurations that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="91697-118">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="91697-118">Tasks you can perform</span></span>

<span data-ttu-id="91697-119">En la página **Configuración de reunión** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="91697-119">You can perform the following tasks from the **Meeting Configuration** page:</span></span>

- <span data-ttu-id="91697-120">Crear una configuración de reunión de sitio o de reunión de grupo</span><span class="sxs-lookup"><span data-stu-id="91697-120">Create a new site meeting configuration or pool meeting configuration</span></span>

- <span data-ttu-id="91697-121">Cambiar la configuración global o una configuración de sitio o de grupo existente</span><span class="sxs-lookup"><span data-stu-id="91697-121">Change the global configuration or an existing site configuration or pool configuration</span></span>

- <span data-ttu-id="91697-122">Eliminar una configuración de sitio o de grupo</span><span class="sxs-lookup"><span data-stu-id="91697-122">Delete a site configuration or pool configuration</span></span>

## <a name="ui-reference"></a><span data-ttu-id="91697-123">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="91697-123">UI Reference</span></span>

<span data-ttu-id="91697-124">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="91697-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="91697-125">**Nuevo** Inicia una nueva configuración de reunión de sitio o configuración de reunión de grupo.</span><span class="sxs-lookup"><span data-stu-id="91697-125">**New** Starts a new site meeting configuration or pool meeting configuration.</span></span>

- <span data-ttu-id="91697-126">**Editar** Abre la configuración de la reunión seleccionada para modificarla, selecciona todas las configuraciones de la reunión de la lista o elimina la configuración del sitio o de la agrupación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="91697-126">**Edit** Opens the selected meeting configuration to edit it, selects all meeting configurations in the list, or deletes the selected site configuration or pool configuration.</span></span>

    > [!NOTE]
    > <span data-ttu-id="91697-127">En el caso de la configuración de reunión global, con **Eliminar** se restablece la configuración a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="91697-127">For the global meeting configuration, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="91697-128">**Actualizar** Actualiza la lista de configuraciones de reunión.</span><span class="sxs-lookup"><span data-stu-id="91697-128">**Refresh** Refreshes the list of meeting configurations.</span></span>

<span data-ttu-id="91697-129">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="91697-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="91697-130">**Nombre** Identifica la configuración de la reunión.</span><span class="sxs-lookup"><span data-stu-id="91697-130">**Name** Identifies the meeting configuration.</span></span>

- <span data-ttu-id="91697-131">**Ámbito** Identifica el ámbito de la configuración de la reunión: global, sitio o grupo.</span><span class="sxs-lookup"><span data-stu-id="91697-131">**Scope** Identifies the scope of the meeting configuration: global, site, or pool.</span></span>

<span data-ttu-id="91697-132">Para más detalles sobre cómo trabajar con configuraciones de reunión, mire [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="91697-132">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span>


