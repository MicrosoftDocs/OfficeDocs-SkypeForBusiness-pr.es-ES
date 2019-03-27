---
title: Número de teléfono sin asignar
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
description: Los números sin asignar son números de teléfono válidos en la organización, pero que no se han asignado a un usuario o teléfono. En la tabla de números sin asignar se identifica cómo desea que se traten las llamadas a números sin asignar.
ms.openlocfilehash: fcb94ca101f2a2380c1d458ae740a492d6cd60c1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897723"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="c1434-104">Número de teléfono sin asignar</span><span class="sxs-lookup"><span data-stu-id="c1434-104">Unassigned Phone Number</span></span>

<span data-ttu-id="c1434-p102">Los números sin asignar son números de teléfono válidos en la organización, pero que no se han asignado a un usuario o teléfono. En la tabla de números sin asignar se identifica cómo desea que se traten las llamadas a números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="c1434-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="c1434-p103">La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Puede configurar la tabla con todas las extensiones válidas para la organización, con únicamente extensiones sin asignar, o bien con una combinación de ambos tipos de números. La tabla de números sin asignar puede incluir tanto números asignados como sin asignar, pero solamente se invoca cuando un autor de llamadas marca un número que no está asignado en ese momento. Si incluye todas las extensiones válidas en la tabla de números sin asignar, puede especificar la acción que va a tener lugar siempre que alguien abandone la organización, sin necesidad de volver a configurar la tabla. Si incluye extensiones sin asignar en la tabla, puede personalizar la acción que va a tener lugar respecto a números específicos. Por ejemplo, si cambia la extensión del departamento de soporte interno, puede incluir el número antiguo de este departamento en la tabla y asignarlo a un anuncio que comunique el número nuevo.</span><span class="sxs-lookup"><span data-stu-id="c1434-p103">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1434-113">Antes de configurar la tabla de números sin asignar, tiene que haber definido uno o más anuncios o haber establecido un operador automático de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="c1434-113">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="c1434-114">La página **Número no asignado** muestra una lista de todos los intervalos de números sin asignar definidos en la organización.</span><span class="sxs-lookup"><span data-stu-id="c1434-114">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="c1434-115">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="c1434-115">Tasks you can perform</span></span>

<span data-ttu-id="c1434-116">En la página **Número no asignado** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="c1434-116">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="c1434-117">Crear un intervalo de números sin asignar</span><span class="sxs-lookup"><span data-stu-id="c1434-117">Create a new unassigned number range</span></span>

- <span data-ttu-id="c1434-118">Cambiar un intervalo de números sin asignar existente</span><span class="sxs-lookup"><span data-stu-id="c1434-118">Change an existing unassigned number range</span></span>

- <span data-ttu-id="c1434-119">Eliminar un intervalo de números sin asignar</span><span class="sxs-lookup"><span data-stu-id="c1434-119">Delete an unassigned number range</span></span>

- <span data-ttu-id="c1434-120">Cambiar el orden de los intervalos de números sin asignar para determinar qué acción necesita aplicarse primero a una llamada entrante que coincida con un número sin asignar.</span><span class="sxs-lookup"><span data-stu-id="c1434-120">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c1434-121">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="c1434-121">UI Reference</span></span>

<span data-ttu-id="c1434-122">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="c1434-122">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="c1434-123">**Nuevo** Inicia un nuevo intervalo numérico sin asignar.</span><span class="sxs-lookup"><span data-stu-id="c1434-123">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="c1434-124">**Editar** Se abre el intervalo numérico sin asignar seleccionado para su edición, selecciona todos los intervalos numéricos sin asignar de la lista o elimina el intervalo numérico sin asignar seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c1434-124">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="c1434-125">**Mover hacia arriba** Mueve el intervalo numérico sin asignar seleccionado copia de seguridad en la lista de modo que Skype para Business Server encuentra antes y aplica la acción especificada antes de aplicar las acciones especificadas para otros rangos de la lista.</span><span class="sxs-lookup"><span data-stu-id="c1434-125">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c1434-126">Skype para Business Server busca en la tabla de números sin asignar de arriba a abajo y usa el primer rango que coincida con el número sin asignar.</span><span class="sxs-lookup"><span data-stu-id="c1434-126">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="c1434-127">Por ejemplo, si tiene un intervalo que especifique una acción de último recurso, asegúrese de que ese intervalo se encuentra en último lugar en la lista.</span><span class="sxs-lookup"><span data-stu-id="c1434-127">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="c1434-128">**Mover hacia abajo** Mueve el intervalo numérico sin asignar seleccionado hacia abajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="c1434-128">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="c1434-129">**Confirmar todos** Guarda todos los cambios realizados a intervalos numéricos sin asignar.</span><span class="sxs-lookup"><span data-stu-id="c1434-129">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c1434-130">Este comando guarda todos los cambios realizados en las páginas **Nuevo número sin asignar** y **Editar número sin asignar**.</span><span class="sxs-lookup"><span data-stu-id="c1434-130">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="c1434-131">**Actualizar** Actualiza la lista de intervalos numéricos sin asignar.</span><span class="sxs-lookup"><span data-stu-id="c1434-131">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="c1434-132">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="c1434-132">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="c1434-133">**Nombre** El nombre único que identifica el intervalo de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="c1434-133">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="c1434-134">**Estado** Muestra qué intervalos numéricos se han guardado en la base de datos y cuáles no.</span><span class="sxs-lookup"><span data-stu-id="c1434-134">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="c1434-135">**Intervalo de inicio** El número inicial del intervalo numérico sin asignar.</span><span class="sxs-lookup"><span data-stu-id="c1434-135">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="c1434-136">**Intervalo de finalización** El número final del intervalo numérico sin asignar.</span><span class="sxs-lookup"><span data-stu-id="c1434-136">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="c1434-137">**Destino** El identificador de servicio de la aplicación que hospeda la aplicación de anuncio que controlará las llamadas entrantes a este intervalo de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="c1434-137">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="c1434-138">**Anuncio** El anuncio que se reproducirá para este intervalo de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="c1434-138">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="c1434-139">Para obtener información detallada sobre las capacidades y características de anuncio, consulte [Plan para la aplicación de anuncio en Skype para 2015 empresarial](../../plan-your-deployment/enterprise-voice-solution/announcement.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="c1434-139">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="c1434-140">Para más detalles sobre cómo trabajar con intervalos de números sin asignar, mire [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="c1434-140">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


