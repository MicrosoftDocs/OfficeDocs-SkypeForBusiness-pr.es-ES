---
title: Número de teléfono sin asignar
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: Los números sin asignar son números de teléfono válidos en la organización, pero que no se han asignado a un usuario o teléfono. En la tabla de números sin asignar se identifica cómo desea que se traten las llamadas a números sin asignar.
ms.openlocfilehash: 910b83f18350bc2a26da281f2e0660e8aa8913b9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690395"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="96075-104">Número de teléfono sin asignar</span><span class="sxs-lookup"><span data-stu-id="96075-104">Unassigned Phone Number</span></span>

> [!NOTE]
> <span data-ttu-id="96075-105">La mensajería unificada de Exchange sigue disponible en Skype empresarial Server 2019 al integrar la 2019 de Skype empresarial con Exchange 2013 o Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="96075-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="96075-106">Debido a cambios en el soporte técnico de Exchange 2019, la integración de mensajería unificada de Exchange se subraya en favor del buzón de voz de nube y las características del operador automático de la nube.</span><span class="sxs-lookup"><span data-stu-id="96075-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="96075-p103">Los números sin asignar son números de teléfono válidos en la organización, pero que no se han asignado a un usuario o teléfono. En la tabla de números sin asignar se identifica cómo desea que se traten las llamadas a números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="96075-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="96075-p104">La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Puede configurar la tabla con todas las extensiones válidas para la organización, con únicamente extensiones sin asignar, o bien con una combinación de ambos tipos de números. La tabla de números sin asignar puede incluir tanto números asignados como sin asignar, pero solamente se invoca cuando un autor de llamadas marca un número que no está asignado en ese momento. Si incluye todas las extensiones válidas en la tabla de números sin asignar, puede especificar la acción que va a tener lugar siempre que alguien abandone la organización, sin necesidad de volver a configurar la tabla. Si incluye extensiones sin asignar en la tabla, puede personalizar la acción que va a tener lugar respecto a números específicos. Por ejemplo, si cambia la extensión del departamento de soporte interno, puede incluir el número antiguo de este departamento en la tabla y asignarlo a un anuncio que comunique el número nuevo.</span><span class="sxs-lookup"><span data-stu-id="96075-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96075-115">Antes de configurar la tabla de números sin asignar, tiene que haber definido uno o más anuncios o haber establecido un operador automático de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="96075-115">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="96075-116">La página **Número no asignado** muestra una lista de todos los intervalos de números sin asignar definidos en la organización.</span><span class="sxs-lookup"><span data-stu-id="96075-116">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="96075-117">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="96075-117">Tasks you can perform</span></span>

<span data-ttu-id="96075-118">En la página **Número no asignado** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="96075-118">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="96075-119">Crear un intervalo de números sin asignar</span><span class="sxs-lookup"><span data-stu-id="96075-119">Create a new unassigned number range</span></span>

- <span data-ttu-id="96075-120">Cambiar un intervalo de números sin asignar existente</span><span class="sxs-lookup"><span data-stu-id="96075-120">Change an existing unassigned number range</span></span>

- <span data-ttu-id="96075-121">Eliminar un intervalo de números sin asignar</span><span class="sxs-lookup"><span data-stu-id="96075-121">Delete an unassigned number range</span></span>

- <span data-ttu-id="96075-122">Cambiar el orden de los intervalos de números sin asignar para determinar qué acción necesita aplicarse primero a una llamada entrante que coincida con un número sin asignar.</span><span class="sxs-lookup"><span data-stu-id="96075-122">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="96075-123">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="96075-123">UI Reference</span></span>

<span data-ttu-id="96075-124">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="96075-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="96075-125">**Nuevo** Inicia un nuevo intervalo de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="96075-125">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="96075-126">**Editar** Abre el intervalo de números seleccionado sin asignar para editar, selecciona todos los intervalos de números sin asignar de la lista o elimina el intervalo de números sin asignar seleccionado.</span><span class="sxs-lookup"><span data-stu-id="96075-126">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="96075-127">**Subir** Mueve el intervalo de número no asignado seleccionado hacia arriba en la lista para que Skype empresarial Server lo encuentre antes de aplicar las acciones especificadas para otros rangos de la lista.</span><span class="sxs-lookup"><span data-stu-id="96075-127">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="96075-128">Skype empresarial Server busca la tabla de números sin asignar de arriba a abajo y usa el primer rango que coincida con el número sin asignar.</span><span class="sxs-lookup"><span data-stu-id="96075-128">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="96075-129">Por ejemplo, si tiene un intervalo que especifique una acción de último recurso, asegúrese de que ese intervalo se encuentra en último lugar en la lista.</span><span class="sxs-lookup"><span data-stu-id="96075-129">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="96075-130">**Bajar** Mueve el intervalo de número no asignado seleccionado hacia abajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="96075-130">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="96075-131">**Confirmar todo** Guarda todos los cambios realizados en intervalos de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="96075-131">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="96075-132">Este comando guarda todos los cambios realizados en las páginas **Nuevo número sin asignar** y **Editar número sin asignar**.</span><span class="sxs-lookup"><span data-stu-id="96075-132">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="96075-133">**Actualizar** Actualiza la lista de intervalos de números no asignados.</span><span class="sxs-lookup"><span data-stu-id="96075-133">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="96075-134">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="96075-134">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="96075-135">**Nombre** Nombre único que identifica el intervalo de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="96075-135">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="96075-136">**Estado** Muestra los intervalos de números que se han guardado en la base de datos y cuáles no.</span><span class="sxs-lookup"><span data-stu-id="96075-136">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="96075-137">**Intervalo de inicio** El número inicial del intervalo de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="96075-137">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="96075-138">**Finalizar rango** El número final del intervalo de números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="96075-138">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="96075-139">**Destino** El identificador de servicio del servicio de aplicación que hospeda la aplicación de anuncio que controlará las llamadas entrantes a este intervalo de números no asignados.</span><span class="sxs-lookup"><span data-stu-id="96075-139">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="96075-140">**Anuncio** El anuncio que se reproducirá para este rango de números no asignados.</span><span class="sxs-lookup"><span data-stu-id="96075-140">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="96075-141">Para obtener más información sobre las características y capacidades del anuncio, consulte [planear la aplicación de anuncios en Skype empresarial](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="96075-141">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="96075-142">Para más detalles sobre cómo trabajar con intervalos de números sin asignar, mire [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="96075-142">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


