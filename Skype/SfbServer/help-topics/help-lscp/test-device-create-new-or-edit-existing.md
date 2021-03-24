---
title: Probar dispositivo Crear nuevo o editar existente
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
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
description: La característica Dispositivo de prueba funciona junto con la característica Actualización de dispositivos. Puede agregar un dispositivo de pruebas a la página Dispositivo de prueba y, a continuación, usar este dispositivo para comprobar la funcionalidad de las actualizaciones nuevas antes de implementar estas actualizaciones en los dispositivos de producción. Puedes probar un dispositivo globalmente (en todo el entorno) o dentro de un solo sitio. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Al agregar un dispositivo, aparece en la lista de la página Dispositivo de prueba del Panel de control de Skype Empresarial Server.
ms.openlocfilehash: 6a472923040dbf1101044a28667cb1358399f808
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099376"
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="db239-107">Dispositivo de la prueba: Crear nuevos o editar los existentes</span><span class="sxs-lookup"><span data-stu-id="db239-107">Test Device: Create New or Edit Existing</span></span>

<span data-ttu-id="db239-108">La característica Dispositivo de prueba funciona junto con la característica Actualización de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="db239-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="db239-109">Puede agregar un dispositivo de pruebas a la página **Dispositivo de prueba** y, a continuación, usar este dispositivo para comprobar la funcionalidad de las actualizaciones nuevas antes de implementar estas actualizaciones en los dispositivos de producción.</span><span class="sxs-lookup"><span data-stu-id="db239-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="db239-110">Puedes probar un dispositivo globalmente (en todo el entorno) o dentro de un solo sitio.</span><span class="sxs-lookup"><span data-stu-id="db239-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="db239-111">Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie.</span><span class="sxs-lookup"><span data-stu-id="db239-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="db239-112">Al agregar un dispositivo, aparece en la lista de la página **Dispositivo** de prueba del Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="db239-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="db239-113">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="db239-113">Tasks you can perform</span></span>

<span data-ttu-id="db239-114">Puede realizar las siguientes tareas en la página **Nuevo dispositivo de prueba** o **Editar dispositivo de prueba**:</span><span class="sxs-lookup"><span data-stu-id="db239-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>

- <span data-ttu-id="db239-115">Agregar un nuevo dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="db239-115">Add a new test device.</span></span>

- <span data-ttu-id="db239-116">Modificar las propiedades de un dispositivo de prueba existente.</span><span class="sxs-lookup"><span data-stu-id="db239-116">Modify the properties of an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="db239-117">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="db239-117">UI Reference</span></span>

<span data-ttu-id="db239-118">Las siguientes listas describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="db239-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="db239-119">**Ámbito** Identifica el ámbito (Global o Site) del dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="db239-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>

- <span data-ttu-id="db239-120">**Nombre** Puedes agregar o modificar el nombre del dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="db239-120">**Name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="db239-121">**Nombre del dispositivo** Puedes agregar o modificar el nombre del dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="db239-121">**Device name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="db239-122">**Tipo de identificador** Puedes seleccionar el método que quieres usar para identificar el dispositivo seleccionando una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="db239-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>

  - <span data-ttu-id="db239-123">**Dirección MAC**</span><span class="sxs-lookup"><span data-stu-id="db239-123">**MAC address**</span></span>

  - <span data-ttu-id="db239-124">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="db239-124">**Serial number**</span></span>

- <span data-ttu-id="db239-125">**Identificador único** Puedes escribir la dirección MAC o el número de serie del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="db239-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>

<span data-ttu-id="db239-126">Para obtener detalles sobre cómo probar dispositivos, vea [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="db239-126">For details about testing devices, see [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="db239-127">Ver también</span><span class="sxs-lookup"><span data-stu-id="db239-127">See also</span></span>

[<span data-ttu-id="db239-128">Dispositivo de la prueba</span><span class="sxs-lookup"><span data-stu-id="db239-128">Test Device</span></span>](test-device.md)

[<span data-ttu-id="db239-129">New-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="db239-129">New-CsTestDevice</span></span>](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="db239-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="db239-130">Set-CsTestDevice</span></span>](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="db239-131">Ver actualizaciones de software para dispositivos de la organización</span><span class="sxs-lookup"><span data-stu-id="db239-131">View Software Updates for Devices in Your Organization</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)