---
title: Número de teléfono sin asignar
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: Los números sin asignar son números de teléfono válidos para su organización pero que no se han asignado a un usuario o teléfono. La tabla de números sin asignar identifica cómo desea que se traten las llamadas a números sin asignar.
ms.openlocfilehash: 2b2c8637e1fa44d8852465b21d2cf494442978b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830140"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="4cf91-104">Número de teléfono sin asignar</span><span class="sxs-lookup"><span data-stu-id="4cf91-104">Unassigned Phone Number</span></span>

> [!NOTE]
> <span data-ttu-id="4cf91-105">La mensajería unificada de Exchange permanece disponible en Skype Empresarial Server 2019 al integrar Skype Empresarial 2019 con Exchange 2013 o Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="4cf91-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="4cf91-106">Debido a los cambios en el soporte técnico en Exchange 2019, la integración de mensajería unificada de Exchange se está haciendo menos importante a favor del correo de voz en la nube y las características de Operador automático nube.</span><span class="sxs-lookup"><span data-stu-id="4cf91-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="4cf91-p103">Los números sin asignar son números de teléfono válidos para su organización pero que no se han asignado a un usuario o teléfono. La tabla de números sin asignar identifica cómo desea que se traten las llamadas a números sin asignar.</span><span class="sxs-lookup"><span data-stu-id="4cf91-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="4cf91-p104">La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Puede configurar la tabla con todas las extensiones válidas para la organización, con únicamente extensiones sin asignar o bien, con una combinación de ambos tipos de números. La tabla de números sin asignar puede incluir tanto números asignados como sin asignar, pero solamente se invoca cuando un autor de llamadas marca un número que no está asignado en esos momentos. Si incluye todas las extensiones válidas en la tabla de números sin asignar, puede especificar la acción que va a tener lugar siempre que alguien abandone la organización, sin necesidad de volver a configurar la tabla. Si incluye extensiones sin asignar en la tabla, puede personalizar la acción que va a tener lugar respecto a números específicos. Por ejemplo, si cambia la extensión del departamento de soporte interno, puede incluir el número antiguo de este departamento en la tabla y asignarlo a un anuncio que comunique el número nuevo.</span><span class="sxs-lookup"><span data-stu-id="4cf91-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4cf91-115">Antes de configurar la tabla de números sin asignar, debe haber definido uno o más anuncios o haber establecido un operador automático de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="4cf91-115">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="4cf91-116">La página **Número no asignado** muestra una lista de todos los intervalos de números sin asignar definidos para su organización.</span><span class="sxs-lookup"><span data-stu-id="4cf91-116">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="4cf91-117">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="4cf91-117">Tasks you can perform</span></span>

<span data-ttu-id="4cf91-118">Puede realizar las siguientes tareas desde la página **Número no asignado**:</span><span class="sxs-lookup"><span data-stu-id="4cf91-118">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="4cf91-119">Crear un intervalo numérico sin asignar nuevo</span><span class="sxs-lookup"><span data-stu-id="4cf91-119">Create a new unassigned number range</span></span>

- <span data-ttu-id="4cf91-120">Cambiar un intervalo numérico sin asignar existente</span><span class="sxs-lookup"><span data-stu-id="4cf91-120">Change an existing unassigned number range</span></span>

- <span data-ttu-id="4cf91-121">Eliminar un intervalo numérico sin asignar</span><span class="sxs-lookup"><span data-stu-id="4cf91-121">Delete an unassigned number range</span></span>

- <span data-ttu-id="4cf91-122">Cambiar el orden de intervalos numéricos sin asignar para determinar qué acción debe aplicarse primero a una llamada entrante que coincida con un número sin asignar.</span><span class="sxs-lookup"><span data-stu-id="4cf91-122">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="4cf91-123">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="4cf91-123">UI Reference</span></span>

<span data-ttu-id="4cf91-124">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="4cf91-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="4cf91-125">**Nuevo** Inicia un nuevo intervalo de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="4cf91-125">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="4cf91-126">**Editar** Abre el intervalo de números sin signo seleccionado para su edición, selecciona todos los intervalos de números sin signo de la lista o elimina el intervalo de números sin signo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4cf91-126">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="4cf91-127">**Subir** Mueve el intervalo de números sin signo seleccionado hacia arriba en la lista para que Skype Empresarial Server lo encuentre antes y aplique la acción especificada antes de aplicar las acciones especificadas para otros intervalos de la lista.</span><span class="sxs-lookup"><span data-stu-id="4cf91-127">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4cf91-128">Skype Empresarial Server busca en la tabla de números sin signo de arriba abajo y usa el primer intervalo que coincide con el número sin signo.</span><span class="sxs-lookup"><span data-stu-id="4cf91-128">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="4cf91-129">Por ejemplo, si tiene un intervalo que especifique una acción de último recurso, asegúrese de que ese intervalo se encuentra en último lugar en la lista.</span><span class="sxs-lookup"><span data-stu-id="4cf91-129">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="4cf91-130">**Bajar** Mueve el intervalo de números sin signo seleccionado hacia abajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="4cf91-130">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="4cf91-131">**Confirmar todo** Guarda todos los cambios realizados en intervalos de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="4cf91-131">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4cf91-132">Este comando guarda todos los cambios realizados en la página **Nuevo número sin asignar** y en la página **Editar número sin asignar**.</span><span class="sxs-lookup"><span data-stu-id="4cf91-132">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="4cf91-133">**Actualizar** Actualiza la lista de intervalos de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="4cf91-133">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="4cf91-134">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="4cf91-134">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="4cf91-135">**Nombre** Nombre único que identifica el intervalo de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="4cf91-135">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="4cf91-136">**Estado** Muestra qué intervalos de números se han guardado en la base de datos y cuáles no.</span><span class="sxs-lookup"><span data-stu-id="4cf91-136">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="4cf91-137">**Intervalo de inicio** Número inicial del intervalo de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="4cf91-137">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="4cf91-138">**Intervalo de finalización** Número final del intervalo de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="4cf91-138">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="4cf91-139">**Destino** El identificador de servicio del servicio de aplicación que hospeda la aplicación anuncio que controlará las llamadas entrantes a este intervalo de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="4cf91-139">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="4cf91-140">**Anuncio** Anuncio que se reproducirá para este intervalo de números sin signo.</span><span class="sxs-lookup"><span data-stu-id="4cf91-140">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="4cf91-141">Para obtener más información sobre las características y capacidades de anuncio, consulte [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) en la documentación sobre planeación.</span><span class="sxs-lookup"><span data-stu-id="4cf91-141">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="4cf91-142">Para obtener más detalles sobre cómo trabajar con rangos de números sin asignar, vea [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="4cf91-142">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


