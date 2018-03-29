---
title: Estacionamiento de llamadas
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: Cuando una llamada está estacionada, se transfiere a un número temporal donde se mantiene la llamada hasta que alguien recupera o se agota el tiempo. Debe configurar una tabla con los rangos de números de extensión que desea reservar para las llamadas aparcadas. Estas extensiones tienen que ser extensiones virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado). Cada grupo que ejecuta la aplicación llamada Park puede tener uno o más rangos de extensiones. Estos intervalos tienen que ser únicos en el nivel global en toda la implementación.
ms.openlocfilehash: 710d923ae9c1e44320438334ad42a89d9d14062f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="call-park"></a><span data-ttu-id="e8cec-106">Estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="e8cec-106">Call Park</span></span>
 
<span data-ttu-id="e8cec-107">Cuando una llamada está estacionada, se transfiere a un número temporal donde se mantiene la llamada hasta que alguien recupera o se agota el tiempo. Debe configurar una tabla con los rangos de números de extensión que desea reservar para las llamadas aparcadas.</span><span class="sxs-lookup"><span data-stu-id="e8cec-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="e8cec-108">Estas extensiones tienen que ser extensiones virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado).</span><span class="sxs-lookup"><span data-stu-id="e8cec-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="e8cec-109">Cada grupo que ejecuta la aplicación llamada Park puede tener uno o más rangos de extensiones.</span><span class="sxs-lookup"><span data-stu-id="e8cec-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="e8cec-110">Estos intervalos tienen que ser únicos en el nivel global en toda la implementación.</span><span class="sxs-lookup"><span data-stu-id="e8cec-110">These ranges must be globally unique across your deployment.</span></span>
  
<span data-ttu-id="e8cec-111">El ** llamada Park ** página muestra una lista de todos los intervalos número parque de llamada que se definen para su organización.</span><span class="sxs-lookup"><span data-stu-id="e8cec-111">The ** Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="e8cec-112">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="e8cec-112">Tasks you can perform</span></span>

<span data-ttu-id="e8cec-113">En la página **Estacionamiento de llamadas** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="e8cec-113">You can perform the following tasks from the **Call Park** page:</span></span>
  
- <span data-ttu-id="e8cec-114">Crear un intervalo de números</span><span class="sxs-lookup"><span data-stu-id="e8cec-114">Create a new number range</span></span>
    
- <span data-ttu-id="e8cec-115">Cambiar un intervalo de números existente</span><span class="sxs-lookup"><span data-stu-id="e8cec-115">Change an existing number range</span></span>
    
- <span data-ttu-id="e8cec-116">Eliminar un intervalo de números</span><span class="sxs-lookup"><span data-stu-id="e8cec-116">Delete a number range</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="e8cec-117">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="e8cec-117">UI Reference</span></span>

<span data-ttu-id="e8cec-118">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="e8cec-118">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="e8cec-119">**Nuevo** Inicia un nuevo intervalo de número de llamada Park.</span><span class="sxs-lookup"><span data-stu-id="e8cec-119">**New** Starts a new Call Park number range.</span></span>
    
- <span data-ttu-id="e8cec-120">**Editar** Abre el intervalo seleccionado para su edición, selecciona todos los intervalos de números en la lista o elimina el intervalo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e8cec-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>
    
- <span data-ttu-id="e8cec-121">**Actualizar** Actualiza la lista de intervalos numéricos.</span><span class="sxs-lookup"><span data-stu-id="e8cec-121">**Refresh** Refreshes the list of number ranges.</span></span>
    
<span data-ttu-id="e8cec-122">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="e8cec-122">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="e8cec-123">**Nombre** El nombre único que identifica el intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="e8cec-123">**Name** The unique name that identifies the number range.</span></span>
    
- <span data-ttu-id="e8cec-124">**Inicio de intervalo** El número inicial del rango.</span><span class="sxs-lookup"><span data-stu-id="e8cec-124">**Start range** The beginning number of the range.</span></span>
    
- <span data-ttu-id="e8cec-125">**Intervalo final** El número final del rango.</span><span class="sxs-lookup"><span data-stu-id="e8cec-125">**End range** The ending number of the range.</span></span>
    
- <span data-ttu-id="e8cec-126">**Destino** El nombre de dominio completo (FQDN) de nombre o identificador del servicio de aplicación que hospeda la aplicación llamada Park para el intervalo de números de servicio.</span><span class="sxs-lookup"><span data-stu-id="e8cec-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>
    
<span data-ttu-id="e8cec-127">Para obtener detalles acerca de llamada Park características y capacidades, consulte [Plan para el parque de llamada en Skype para negocios 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span><span class="sxs-lookup"><span data-stu-id="e8cec-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="e8cec-128">Para obtener más información sobre cómo trabajar con intervalos numéricos llamada Park, vea [Configurar las extensiones de número de teléfono para llamadas de estacionamiento](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span><span class="sxs-lookup"><span data-stu-id="e8cec-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>
  

