---
title: Estacionamiento de llamadas
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: Cuando se estaciona una llamada, se transfiere a un número temporal en el que la llamada se mantiene hasta que alguien la recupera o se hace el tiempo de espera. Debe configurar una tabla con los intervalos de números de extensión que reserva para las llamadas estacionadas. Las extensiones deben ser virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado). Cada grupo de servidores que ejecuta la aplicación Estacionamiento de llamadas puede tener uno o varios intervalos de extensiones. Estos intervalos deben ser únicos en el nivel global en toda la implementación.
ms.openlocfilehash: 679e13cdeb6ef6cf614f5703f5711e86fa1c8c59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812170"
---
# <a name="call-park"></a><span data-ttu-id="6513a-106">Estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="6513a-106">Call Park</span></span>

<span data-ttu-id="6513a-107">Cuando se estaciona una llamada, se transfiere a un número temporal en el que la llamada se mantiene hasta que alguien la recupera o se hace el tiempo de espera. Debe configurar una tabla con los intervalos de números de extensión que reserva para las llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="6513a-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="6513a-108">Las extensiones deben ser virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado).</span><span class="sxs-lookup"><span data-stu-id="6513a-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="6513a-109">Cada grupo de servidores que ejecuta la aplicación Estacionamiento de llamadas puede tener uno o varios intervalos de extensiones.</span><span class="sxs-lookup"><span data-stu-id="6513a-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="6513a-110">Estos intervalos deben ser únicos en el nivel global en toda la implementación.</span><span class="sxs-lookup"><span data-stu-id="6513a-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="6513a-111">La **página Estacionamiento de** llamadas muestra una lista de todos los intervalos de números de estacionamiento de llamadas definidos para su organización.</span><span class="sxs-lookup"><span data-stu-id="6513a-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="6513a-112">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="6513a-112">Tasks you can perform</span></span>

<span data-ttu-id="6513a-113">Puede realizar las siguientes tareas desde la página **Estacionamiento de llamadas**:</span><span class="sxs-lookup"><span data-stu-id="6513a-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="6513a-114">Crear un intervalo numérico nuevo</span><span class="sxs-lookup"><span data-stu-id="6513a-114">Create a new number range</span></span>

- <span data-ttu-id="6513a-115">Cambiar un intervalo numérico existente</span><span class="sxs-lookup"><span data-stu-id="6513a-115">Change an existing number range</span></span>

- <span data-ttu-id="6513a-116">Eliminar un intervalo numérico</span><span class="sxs-lookup"><span data-stu-id="6513a-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="6513a-117">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="6513a-117">UI Reference</span></span>

<span data-ttu-id="6513a-118">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="6513a-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="6513a-119">**Nuevo** Inicia un nuevo intervalo de números de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6513a-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="6513a-120">**Editar** Abre el intervalo de números seleccionado para su edición, selecciona todos los intervalos de números de la lista o elimina el intervalo de números seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6513a-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="6513a-121">**Actualizar** Actualiza la lista de intervalos de números.</span><span class="sxs-lookup"><span data-stu-id="6513a-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="6513a-122">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="6513a-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="6513a-123">**Nombre** Nombre único que identifica el intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="6513a-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="6513a-124">**Intervalo de inicio** Número inicial del intervalo.</span><span class="sxs-lookup"><span data-stu-id="6513a-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="6513a-125">**Intervalo de finalización** Número final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="6513a-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="6513a-126">**Destino** Nombre de dominio completo (FQDN) o identificador de servicio del servicio de aplicación que hospeda la aplicación Estacionamiento de llamadas para el intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="6513a-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="6513a-127">Para obtener más información sobre las características y capacidades del estacionamiento de llamadas, consulte [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="6513a-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="6513a-128">Para obtener más información sobre cómo trabajar con intervalos de números de estacionamiento de llamadas, consulte [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="6513a-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


