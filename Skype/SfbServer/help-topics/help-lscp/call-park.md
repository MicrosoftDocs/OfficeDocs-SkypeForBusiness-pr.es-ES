---
title: Estacionamiento de llamadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: Cuando se aparca una llamada, se transfiere a un número temporal en el que se retiene la llamada hasta que alguien la recupere o agote el tiempo de espera. Debe configurar una tabla con los intervalos de números de extensión en los que está atendiendo las llamadas estacionadas. Estas extensiones tienen que ser extensiones virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado). Cada grupo que ejecuta la aplicación de estacionamiento de llamadas puede tener uno o más intervalos de extensiones. Estos intervalos tienen que ser únicos en el nivel global en toda la implementación.
ms.openlocfilehash: 69eca5a36ef0640f64fedb67d654cc6a835de72c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811578"
---
# <a name="call-park"></a><span data-ttu-id="3f4a9-106">Estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="3f4a9-106">Call Park</span></span>

<span data-ttu-id="3f4a9-107">Cuando se aparca una llamada, se transfiere a un número temporal en el que se retiene la llamada hasta que alguien la recupere o agote el tiempo de espera. Debe configurar una tabla con los intervalos de números de extensión en los que está atendiendo las llamadas estacionadas.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="3f4a9-108">Estas extensiones tienen que ser extensiones virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado).</span><span class="sxs-lookup"><span data-stu-id="3f4a9-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="3f4a9-109">Cada grupo que ejecuta la aplicación de estacionamiento de llamadas puede tener uno o más intervalos de extensiones.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="3f4a9-110">Estos intervalos tienen que ser únicos en el nivel global en toda la implementación.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="3f4a9-111">La página de **estacionamiento de llamadas** muestra una lista de todos los intervalos de números de estacionamiento de llamadas que se han definido para su organización.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="3f4a9-112">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="3f4a9-112">Tasks you can perform</span></span>

<span data-ttu-id="3f4a9-113">En la página **Estacionamiento de llamadas** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="3f4a9-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="3f4a9-114">Crear un intervalo de números</span><span class="sxs-lookup"><span data-stu-id="3f4a9-114">Create a new number range</span></span>

- <span data-ttu-id="3f4a9-115">Cambiar un intervalo de números existente</span><span class="sxs-lookup"><span data-stu-id="3f4a9-115">Change an existing number range</span></span>

- <span data-ttu-id="3f4a9-116">Eliminar un intervalo de números</span><span class="sxs-lookup"><span data-stu-id="3f4a9-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="3f4a9-117">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="3f4a9-117">UI Reference</span></span>

<span data-ttu-id="3f4a9-118">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="3f4a9-119">**Nuevo** Inicia un nuevo intervalo de números de aparcamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="3f4a9-120">**Editar** Abre el intervalo de números seleccionado para su edición, selecciona todos los intervalos de números de la lista o elimina el intervalo de números seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="3f4a9-121">**Actualizar** Actualiza la lista de intervalos numéricos.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="3f4a9-122">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="3f4a9-123">**Nombre** Nombre único que identifica el intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="3f4a9-124">**Intervalo de inicio** El número inicial del intervalo.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="3f4a9-125">**Finalizar rango** El número final del intervalo.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="3f4a9-126">**Destino** El nombre de dominio completo (FQDN) o el identificador de servicio del servicio de aplicación que hospeda la aplicación de estacionamiento de llamadas para el intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="3f4a9-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="3f4a9-127">Para obtener más información sobre las funciones y características de reactivación de llamadas, consulte [Plan for Call Park in Skype empresarial 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="3f4a9-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="3f4a9-128">Para obtener más información sobre cómo trabajar con intervalos numéricos de estacionamiento, consulte [configurar extensiones de números de teléfono para llamadas de aparcamiento](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="3f4a9-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


