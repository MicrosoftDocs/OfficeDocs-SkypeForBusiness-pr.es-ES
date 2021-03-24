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
description: Cuando se estaciona una llamada, se transfiere a un número temporal en el que se mantiene la llamada hasta que alguien la recupera o se abate el tiempo de espera. Debe configurar una tabla con los intervalos de números de extensión que va a reservar para las llamadas estacionadas. Las extensiones deben ser virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado). Cada grupo que ejecuta la aplicación estacionamiento de llamadas puede tener uno o más intervalos de extensiones. Estos intervalos deben ser únicos en el nivel global en toda la implementación.
ms.openlocfilehash: b7926c10424fd5902fdc43e6c0fccadb45e61f79
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097076"
---
# <a name="call-park"></a><span data-ttu-id="cbd9d-106">Estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="cbd9d-106">Call Park</span></span>

<span data-ttu-id="cbd9d-107">Cuando se estaciona una llamada, se transfiere a un número temporal en el que se mantiene la llamada hasta que alguien la recupera o se abate el tiempo de espera. Debe configurar una tabla con los intervalos de números de extensión que va a reservar para las llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="cbd9d-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="cbd9d-108">Las extensiones deben ser virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado).</span><span class="sxs-lookup"><span data-stu-id="cbd9d-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="cbd9d-109">Cada grupo que ejecuta la aplicación estacionamiento de llamadas puede tener uno o más intervalos de extensiones.</span><span class="sxs-lookup"><span data-stu-id="cbd9d-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="cbd9d-110">Estos intervalos deben ser únicos en el nivel global en toda la implementación.</span><span class="sxs-lookup"><span data-stu-id="cbd9d-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="cbd9d-111">La **página Estacionamiento de** llamadas muestra una lista de todos los intervalos de números de estacionamiento de llamadas definidos para su organización.</span><span class="sxs-lookup"><span data-stu-id="cbd9d-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="cbd9d-112">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="cbd9d-112">Tasks you can perform</span></span>

<span data-ttu-id="cbd9d-113">Puede realizar las siguientes tareas desde la página **Estacionamiento de llamadas**:</span><span class="sxs-lookup"><span data-stu-id="cbd9d-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="cbd9d-114">Crear un intervalo numérico nuevo</span><span class="sxs-lookup"><span data-stu-id="cbd9d-114">Create a new number range</span></span>

- <span data-ttu-id="cbd9d-115">Cambiar un intervalo numérico existente</span><span class="sxs-lookup"><span data-stu-id="cbd9d-115">Change an existing number range</span></span>

- <span data-ttu-id="cbd9d-116">Eliminar un intervalo numérico</span><span class="sxs-lookup"><span data-stu-id="cbd9d-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="cbd9d-117">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="cbd9d-117">UI Reference</span></span>

<span data-ttu-id="cbd9d-118">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="cbd9d-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="cbd9d-119">**Nuevo** Inicia un nuevo intervalo de números de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="cbd9d-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="cbd9d-120">**Editar** Abre el intervalo de números seleccionado para su edición, selecciona todos los intervalos de números de la lista o elimina el intervalo de números seleccionado.</span><span class="sxs-lookup"><span data-stu-id="cbd9d-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="cbd9d-121">**Actualizar** Actualiza la lista de intervalos de números.</span><span class="sxs-lookup"><span data-stu-id="cbd9d-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="cbd9d-122">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="cbd9d-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="cbd9d-123">**Nombre** Nombre único que identifica el intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="cbd9d-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="cbd9d-124">**Intervalo de inicio** El número inicial del intervalo.</span><span class="sxs-lookup"><span data-stu-id="cbd9d-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="cbd9d-125">**Intervalo final** El número final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="cbd9d-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="cbd9d-126">**Destino** Nombre de dominio completo (FQDN) o identificador de servicio del servicio de aplicación que hospeda la aplicación estacionamiento de llamadas para el intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="cbd9d-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="cbd9d-127">Para obtener más información sobre las características y capacidades del estacionamiento de llamadas, vea [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="cbd9d-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="cbd9d-128">Para obtener más información sobre cómo trabajar con intervalos de números de estacionamiento de llamadas, vea [Configure Phone Number Extensions for Parking Calls](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls).</span><span class="sxs-lookup"><span data-stu-id="cbd9d-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls).</span></span>