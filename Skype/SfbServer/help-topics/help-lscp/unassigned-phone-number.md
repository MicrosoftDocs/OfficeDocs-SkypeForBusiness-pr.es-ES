---
title: Número de teléfono sin asignar
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
description: Los números sin asignar son números de teléfono válidos para su organización pero que no se han asignado a un usuario o teléfono. La tabla de números sin asignar identifica cómo desea que se traten las llamadas a números sin asignar.
ms.openlocfilehash: aeb81aef1b2dba23dc3daaa6ec8a788c0b232529
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122524"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="541dd-104">Número de teléfono sin asignar</span><span class="sxs-lookup"><span data-stu-id="541dd-104">Unassigned Phone Number</span></span>

<span data-ttu-id="541dd-p102">Los números sin asignar son números de teléfono válidos para su organización pero que no se han asignado a un usuario o teléfono. La tabla de números sin asignar identifica cómo desea que se traten las llamadas a números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="541dd-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="541dd-p103">La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Puede configurar la tabla con todas las extensiones válidas para la organización, con únicamente extensiones sin asignar o bien, con una combinación de ambos tipos de números. La tabla de números sin asignar puede incluir tanto números asignados como sin asignar, pero solamente se invoca cuando un autor de llamadas marca un número que no está asignado en esos momentos. Si incluye todas las extensiones válidas en la tabla de números sin asignar, puede especificar la acción que va a tener lugar siempre que alguien abandone la organización, sin necesidad de volver a configurar la tabla. Si incluye extensiones sin asignar en la tabla, puede personalizar la acción que va a tener lugar respecto a números específicos. Por ejemplo, si cambia la extensión del departamento de soporte interno, puede incluir el número antiguo de este departamento en la tabla y asignarlo a un anuncio que comunique el número nuevo.</span><span class="sxs-lookup"><span data-stu-id="541dd-p103">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="541dd-113">Antes de configurar la tabla de números sin asignar, debe haber definido uno o más anuncios o haber establecido un operador automático de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="541dd-113">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="541dd-114">La página **Número no asignado** muestra una lista de todos los intervalos de números sin asignar definidos para su organización.</span><span class="sxs-lookup"><span data-stu-id="541dd-114">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="541dd-115">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="541dd-115">Tasks you can perform</span></span>

<span data-ttu-id="541dd-116">Puede realizar las siguientes tareas desde la página **Número no asignado**:</span><span class="sxs-lookup"><span data-stu-id="541dd-116">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="541dd-117">Crear un intervalo numérico sin asignar nuevo</span><span class="sxs-lookup"><span data-stu-id="541dd-117">Create a new unassigned number range</span></span>

- <span data-ttu-id="541dd-118">Cambiar un intervalo numérico sin asignar existente</span><span class="sxs-lookup"><span data-stu-id="541dd-118">Change an existing unassigned number range</span></span>

- <span data-ttu-id="541dd-119">Eliminar un intervalo numérico sin asignar</span><span class="sxs-lookup"><span data-stu-id="541dd-119">Delete an unassigned number range</span></span>

- <span data-ttu-id="541dd-120">Cambiar el orden de intervalos numéricos sin asignar para determinar qué acción debe aplicarse primero a una llamada entrante que coincida con un número sin asignar.</span><span class="sxs-lookup"><span data-stu-id="541dd-120">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="541dd-121">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="541dd-121">UI Reference</span></span>

<span data-ttu-id="541dd-122">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="541dd-122">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="541dd-123">**Nuevo** Inicia un nuevo intervalo de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="541dd-123">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="541dd-124">**Editar** Abre el intervalo de números sin signo seleccionado para su edición, selecciona todos los intervalos de números sin signo de la lista o elimina el intervalo de números sin signo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="541dd-124">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="541dd-125">**Subir** Mueve el intervalo de números sinsignar seleccionado hacia arriba en la lista para que Skype Empresarial Server lo encuentre antes y aplique la acción especificada antes de aplicar las acciones especificadas para otros rangos de la lista.</span><span class="sxs-lookup"><span data-stu-id="541dd-125">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="541dd-126">Skype Empresarial Server busca en la tabla de números sinsignación de arriba a abajo y usa el primer intervalo que coincide con el número sin signo.</span><span class="sxs-lookup"><span data-stu-id="541dd-126">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="541dd-127">Por ejemplo, si tiene un intervalo que especifique una acción de último recurso, asegúrese de que ese intervalo se encuentra en último lugar en la lista.</span><span class="sxs-lookup"><span data-stu-id="541dd-127">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="541dd-128">**Bajar** Mueve el intervalo de números sin signo seleccionado hacia abajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="541dd-128">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="541dd-129">**Confirmar todo** Guarda todos los cambios realizados en intervalos de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="541dd-129">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="541dd-130">Este comando guarda todos los cambios realizados en la página **Nuevo número sin asignar** y en la página **Editar número sin asignar**.</span><span class="sxs-lookup"><span data-stu-id="541dd-130">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="541dd-131">**Actualizar** Actualiza la lista de intervalos de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="541dd-131">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="541dd-132">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="541dd-132">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="541dd-133">**Nombre** Nombre único que identifica el intervalo de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="541dd-133">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="541dd-134">**Estado** Muestra qué intervalos de números se han guardado en la base de datos y cuáles no.</span><span class="sxs-lookup"><span data-stu-id="541dd-134">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="541dd-135">**Intervalo de inicio** El número inicial del intervalo de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="541dd-135">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="541dd-136">**Intervalo final** El número final del intervalo de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="541dd-136">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="541dd-137">**Destino** El identificador de servicio del servicio de aplicación que hospeda la aplicación Anuncio que controlará las llamadas entrantes a este rango de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="541dd-137">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="541dd-138">**Anuncio** El anuncio que se reproducirá para este rango de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="541dd-138">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="541dd-139">Para obtener más información sobre las características y capacidades del anuncio, vea [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) en la documentación sobre planeación.</span><span class="sxs-lookup"><span data-stu-id="541dd-139">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="541dd-140">Para obtener más detalles sobre cómo trabajar con rangos de números sin asignar, vea [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="541dd-140">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) in the Operations documentation.</span></span>