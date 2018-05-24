---
title: Dispositivo de prueba crear nuevos o editar los existentes
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
description: La característica Dispositivo de prueba funciona junto con la característica Actualización de dispositivos. Puede agregar un dispositivo de prueba a la página probar dispositivo y, a continuación, usar este dispositivo para comprobar la funcionalidad de nuevas actualizaciones antes de implementar las actualizaciones en los dispositivos de producción. Puede probar un dispositivo de forma global (en todo el entorno) o en un solo sitio. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Cuando se agrega un dispositivo, aparece en la lista en la página dispositivo de prueba de la Skype para el Panel de Control de servidor empresarial.
ms.openlocfilehash: 765bd7db9cbce369a92d3bb532076e480374ebb4
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="5436a-107">Dispositivo de prueba: Crear nuevo o editar existente</span><span class="sxs-lookup"><span data-stu-id="5436a-107">Test Device: Create New or Edit Existing</span></span>
 
<span data-ttu-id="5436a-108">La característica Dispositivo de prueba funciona junto con la característica Actualización de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5436a-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="5436a-109">Puede agregar un dispositivo de prueba a la página **Dispositivo de prueba** y, luego, usar este dispositivo para comprobar la funcionalidad de las actualizaciones nuevas antes de implementarlas en los dispositivos de producción.</span><span class="sxs-lookup"><span data-stu-id="5436a-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="5436a-110">Puede probar un dispositivo de forma global (en todo el entorno) o en un solo sitio.</span><span class="sxs-lookup"><span data-stu-id="5436a-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="5436a-111">Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie.</span><span class="sxs-lookup"><span data-stu-id="5436a-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="5436a-112">Cuando se agrega un dispositivo, aparece en la lista en la página **Dispositivo de prueba** de la Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="5436a-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="5436a-113">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="5436a-113">Tasks you can perform</span></span>

<span data-ttu-id="5436a-114">En las páginas **Nuevo dispositivo de prueba** o **Editar dispositivo de prueba** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="5436a-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>
  
- <span data-ttu-id="5436a-115">Agregar un nuevo dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="5436a-115">Add a new test device.</span></span>
    
- <span data-ttu-id="5436a-116">Modificar las propiedades de un dispositivo de prueba existente.</span><span class="sxs-lookup"><span data-stu-id="5436a-116">Modify the properties of an existing test device.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="5436a-117">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="5436a-117">UI Reference</span></span>

<span data-ttu-id="5436a-118">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="5436a-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="5436a-119">**Ámbito** Identifica el ámbito (Global o sitio) del dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="5436a-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>
    
- <span data-ttu-id="5436a-120">**Nombre** Puede agregar o modificar el nombre del dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="5436a-120">**Name** You can add or modify the name of the test device.</span></span>
    
- <span data-ttu-id="5436a-121">**Nombre de dispositivo** Puede agregar o modificar el nombre del dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="5436a-121">**Device name** You can add or modify the name of the test device.</span></span>
    
- <span data-ttu-id="5436a-122">**Tipo de identificador** Puede seleccionar el método que usar para identificar el dispositivo seleccionando una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="5436a-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>
    
  - <span data-ttu-id="5436a-123">**Dirección MAC**</span><span class="sxs-lookup"><span data-stu-id="5436a-123">**MAC address**</span></span>
    
  - <span data-ttu-id="5436a-124">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="5436a-124">**Serial number**</span></span>
    
- <span data-ttu-id="5436a-125">**Identificador único** Puede escribir la dirección MAC o número de serie del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5436a-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>
    
<span data-ttu-id="5436a-126">Para obtener información detallada acerca de cómo probar dispositivos, vea [Agregar un dispositivo para probar la funcionalidad de actualización](http://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="5436a-126">For details about testing devices, see [Add a Device to Test Update Functionality](http://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="5436a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="5436a-127">See also</span></span>

#### 

[<span data-ttu-id="5436a-128">Dispositivo de prueba</span><span class="sxs-lookup"><span data-stu-id="5436a-128">Test Device</span></span>](test-device.md)

[<span data-ttu-id="5436a-129">Nuevo-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="5436a-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)
  
[<span data-ttu-id="5436a-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="5436a-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)
  
[<span data-ttu-id="5436a-131">Ver actualizaciones de Software para dispositivos de la organización</span><span class="sxs-lookup"><span data-stu-id="5436a-131">View Software Updates for Devices in Your Organization</span></span>](http://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)

