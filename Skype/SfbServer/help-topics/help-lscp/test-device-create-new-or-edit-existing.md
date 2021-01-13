---
title: Probar la creación de dispositivos nuevos o editar los existentes
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
description: La característica Dispositivo de prueba funciona junto con la característica Actualización de dispositivos. Puede agregar un dispositivo de pruebas a la página Dispositivo de prueba y, a continuación, usar este dispositivo para comprobar la funcionalidad de las actualizaciones nuevas antes de implementar estas actualizaciones en los dispositivos de producción. Puede probar un dispositivo de forma global (en todo el entorno) o en un único sitio. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Cuando agrega un dispositivo, aparece en la lista de la página Dispositivo de prueba del Panel de control de Skype Empresarial Server.
ms.openlocfilehash: cf4895e84e486939515094042010383854587f46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819070"
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="5c787-107">Dispositivo de la prueba: Crear nuevos o editar los existentes</span><span class="sxs-lookup"><span data-stu-id="5c787-107">Test Device: Create New or Edit Existing</span></span>

<span data-ttu-id="5c787-108">La característica Dispositivo de prueba funciona junto con la característica Actualización de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5c787-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="5c787-109">Puede agregar un dispositivo de pruebas a la página **Dispositivo de prueba** y, a continuación, usar este dispositivo para comprobar la funcionalidad de las actualizaciones nuevas antes de implementar estas actualizaciones en los dispositivos de producción.</span><span class="sxs-lookup"><span data-stu-id="5c787-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="5c787-110">Puede probar un dispositivo de forma global (en todo el entorno) o en un único sitio.</span><span class="sxs-lookup"><span data-stu-id="5c787-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="5c787-111">Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie.</span><span class="sxs-lookup"><span data-stu-id="5c787-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="5c787-112">Cuando agrega un dispositivo, aparece en  la lista de la página Dispositivo de prueba del Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5c787-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="5c787-113">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="5c787-113">Tasks you can perform</span></span>

<span data-ttu-id="5c787-114">Puede realizar las siguientes tareas en la página **Nuevo dispositivo de prueba** o **Editar dispositivo de prueba**:</span><span class="sxs-lookup"><span data-stu-id="5c787-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>

- <span data-ttu-id="5c787-115">Agregar un nuevo dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="5c787-115">Add a new test device.</span></span>

- <span data-ttu-id="5c787-116">Modificar las propiedades de un dispositivo de prueba existente.</span><span class="sxs-lookup"><span data-stu-id="5c787-116">Modify the properties of an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="5c787-117">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="5c787-117">UI Reference</span></span>

<span data-ttu-id="5c787-118">Las siguientes listas describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="5c787-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="5c787-119">**Ámbito** Identifica el ámbito (Global o Sitio) del dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="5c787-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>

- <span data-ttu-id="5c787-120">**Nombre** Puedes agregar o modificar el nombre del dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="5c787-120">**Name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="5c787-121">**Nombre del dispositivo** Puedes agregar o modificar el nombre del dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="5c787-121">**Device name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="5c787-122">**Tipo de identificador** Puedes seleccionar el método que se va a usar para identificar el dispositivo seleccionando una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="5c787-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>

  - <span data-ttu-id="5c787-123">**Dirección MAC**</span><span class="sxs-lookup"><span data-stu-id="5c787-123">**MAC address**</span></span>

  - <span data-ttu-id="5c787-124">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="5c787-124">**Serial number**</span></span>

- <span data-ttu-id="5c787-125">**Identificador único** Puedes escribir la dirección MAC o el número de serie del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5c787-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>

<span data-ttu-id="5c787-126">Para obtener detalles sobre cómo probar dispositivos, vea [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="5c787-126">For details about testing devices, see [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="5c787-127">Ver también</span><span class="sxs-lookup"><span data-stu-id="5c787-127">See also</span></span>

[<span data-ttu-id="5c787-128">Dispositivo de la prueba</span><span class="sxs-lookup"><span data-stu-id="5c787-128">Test Device</span></span>](test-device.md)

[<span data-ttu-id="5c787-129">New-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="5c787-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="5c787-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="5c787-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="5c787-131">Ver actualizaciones de software para dispositivos de la organización</span><span class="sxs-lookup"><span data-stu-id="5c787-131">View Software Updates for Devices in Your Organization</span></span>](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
