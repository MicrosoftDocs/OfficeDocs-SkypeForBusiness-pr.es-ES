---
title: Dispositivo de la prueba
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
description: Puede agregar un dispositivo de prueba a la página Dispositivo de prueba y luego usar este dispositivo para comprobar las funciones de las actualizaciones nuevas antes de implementar estas actualizaciones en los dispositivos de producción. Puedes probar un dispositivo globalmente (en todo el entorno) o dentro de un solo sitio. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Al agregar un dispositivo, aparece en la lista de la página Dispositivo de prueba del Panel de control de Skype Empresarial Server.
ms.openlocfilehash: e48c76237f8d9cafb1642e8ec1e598dcc24453c3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099356"
---
# <a name="test-device"></a><span data-ttu-id="c2e70-106">Dispositivo de la prueba</span><span class="sxs-lookup"><span data-stu-id="c2e70-106">Test Device</span></span>

<span data-ttu-id="c2e70-107">Puede agregar un dispositivo de prueba a la página **Dispositivo de prueba** y luego usar este dispositivo para comprobar las funciones de las actualizaciones nuevas antes de implementar estas actualizaciones en los dispositivos de producción.</span><span class="sxs-lookup"><span data-stu-id="c2e70-107">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="c2e70-108">Puedes probar un dispositivo globalmente (en todo el entorno) o dentro de un solo sitio.</span><span class="sxs-lookup"><span data-stu-id="c2e70-108">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="c2e70-109">Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie.</span><span class="sxs-lookup"><span data-stu-id="c2e70-109">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="c2e70-110">Al agregar un dispositivo, aparece en la lista de la página **Dispositivo** de prueba del Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c2e70-110">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="c2e70-111">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="c2e70-111">Tasks you can perform</span></span>

<span data-ttu-id="c2e70-112">Puede realizar las siguientes acciones en la página **Dispositivo de prueba**:</span><span class="sxs-lookup"><span data-stu-id="c2e70-112">You can perform the following tasks on the **Test Device** page:</span></span>

- <span data-ttu-id="c2e70-113">Agregar un dispositivo de prueba de forma global o para un sitio concreto.</span><span class="sxs-lookup"><span data-stu-id="c2e70-113">Add a test device globally or for a particular site.</span></span>

- <span data-ttu-id="c2e70-114">Modificar las opciones de un dispositivo de prueba existente.</span><span class="sxs-lookup"><span data-stu-id="c2e70-114">Modify the options for an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c2e70-115">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="c2e70-115">UI Reference</span></span>

<span data-ttu-id="c2e70-116">Las siguientes listas describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="c2e70-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="c2e70-117">**Nuevo** Puedes agregar un nuevo dispositivo de prueba con el siguiente ámbito:</span><span class="sxs-lookup"><span data-stu-id="c2e70-117">**New** You can add a new test device with the following scope:</span></span>

  - <span data-ttu-id="c2e70-118">Global</span><span class="sxs-lookup"><span data-stu-id="c2e70-118">Global</span></span>

  - <span data-ttu-id="c2e70-119">Site</span><span class="sxs-lookup"><span data-stu-id="c2e70-119">Site</span></span>

- <span data-ttu-id="c2e70-120">**Editar** Puedes cambiar las opciones de un dispositivo de prueba en la lista.</span><span class="sxs-lookup"><span data-stu-id="c2e70-120">**Edit** You can change the options of a test device in the list.</span></span> <span data-ttu-id="c2e70-121">Al usar esta opción, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c2e70-121">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="c2e70-122">**Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puedes cambiar las opciones de un dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="c2e70-122">**Show details** This option opens a dialog box in which you can change the options for a test device.</span></span>

  - <span data-ttu-id="c2e70-123">**Seleccionar todo** Esta opción selecciona todos los dispositivos de prueba de la lista.</span><span class="sxs-lookup"><span data-stu-id="c2e70-123">**Select All** This option selects all test devices in the list.</span></span>

  - <span data-ttu-id="c2e70-124">**Eliminar** Esta opción elimina todos los dispositivos de prueba seleccionados.</span><span class="sxs-lookup"><span data-stu-id="c2e70-124">**Delete** This option deletes all selected test devices.</span></span>

- <span data-ttu-id="c2e70-125">**Actualizar** Puedes actualizar la lista de dispositivos de prueba para comprobar el estado de las opciones de todos los dispositivos de prueba.</span><span class="sxs-lookup"><span data-stu-id="c2e70-125">**Refresh** You can refresh the test device list to verify the status of the options of all test devices.</span></span>

<span data-ttu-id="c2e70-126">Para obtener detalles sobre cómo probar dispositivos, vea [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="c2e70-126">For details about testing devices, see [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="c2e70-127">Ver también</span><span class="sxs-lookup"><span data-stu-id="c2e70-127">See also</span></span>

[<span data-ttu-id="c2e70-128">Dispositivo de prueba: Crear nuevo o editar existente</span><span class="sxs-lookup"><span data-stu-id="c2e70-128">Test Device: Create New or Edit Existing</span></span>](test-device-create-new-or-edit-existing.md)

[<span data-ttu-id="c2e70-129">New-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="c2e70-129">New-CsTestDevice</span></span>](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="c2e70-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="c2e70-130">Set-CsTestDevice</span></span>](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="c2e70-131">Ver actualizaciones de software para dispositivos de la organización</span><span class="sxs-lookup"><span data-stu-id="c2e70-131">View Software Updates for Devices in Your Organization</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)