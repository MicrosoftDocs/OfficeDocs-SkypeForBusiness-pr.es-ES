---
title: Dispositivo de prueba crear nuevo o editar existente
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
description: La característica Dispositivo de prueba funciona junto con la característica Actualización de dispositivos. Puede agregar un dispositivo de prueba a la página de prueba de dispositivos y, a continuación, utilizar este dispositivo para comprobar la funcionalidad de las nuevas actualizaciones antes de implementarlas en dispositivos de producción. Puede probar un dispositivo de forma global (en todo el entorno) o en un solo sitio. Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie. Cuando agrega un dispositivo, aparece en la lista en la página dispositivo de prueba de la Skype para Panel de Control de servidor empresarial.
ms.openlocfilehash: 022a56797952986f52772cb5fbed6d1f09bf7d75
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="3b14c-107">Dispositivo de prueba: Crear nuevo o editar existente</span><span class="sxs-lookup"><span data-stu-id="3b14c-107">Test Device: Create New or Edit Existing</span></span>
 
<span data-ttu-id="3b14c-108">La característica Dispositivo de prueba funciona junto con la característica Actualización de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3b14c-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="3b14c-109">Puede agregar un dispositivo de prueba a la página **Dispositivo de prueba** y, luego, usar este dispositivo para comprobar la funcionalidad de las actualizaciones nuevas antes de implementarlas en los dispositivos de producción.</span><span class="sxs-lookup"><span data-stu-id="3b14c-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="3b14c-110">Puede probar un dispositivo de forma global (en todo el entorno) o en un solo sitio.</span><span class="sxs-lookup"><span data-stu-id="3b14c-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="3b14c-111">Un dispositivo de prueba se identifica por su dirección Media Access Control (MAC) o número de serie.</span><span class="sxs-lookup"><span data-stu-id="3b14c-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="3b14c-112">Cuando agrega un dispositivo, aparece en la lista en la página de **Prueba de dispositivo** de la Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="3b14c-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="3b14c-113">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="3b14c-113">Tasks you can perform</span></span>

<span data-ttu-id="3b14c-114">En las páginas **Nuevo dispositivo de prueba** o **Editar dispositivo de prueba** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="3b14c-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>
  
- <span data-ttu-id="3b14c-115">Agregar un nuevo dispositivo de prueba.</span><span class="sxs-lookup"><span data-stu-id="3b14c-115">Add a new test device.</span></span>
    
- <span data-ttu-id="3b14c-116">Modificar las propiedades de un dispositivo de prueba existente.</span><span class="sxs-lookup"><span data-stu-id="3b14c-116">Modify the properties of an existing test device.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="3b14c-117">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="3b14c-117">UI Reference</span></span>

<span data-ttu-id="3b14c-118">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="3b14c-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="3b14c-119">**Ámbito de aplicación** Identifica el ámbito (Global o sitio) de dispositivo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="3b14c-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>
    
- <span data-ttu-id="3b14c-120">**Nombre** Puede agregar o modificar el nombre del dispositivo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="3b14c-120">**Name** You can add or modify the name of the test device.</span></span>
    
- <span data-ttu-id="3b14c-121">**Nombre de dispositivo** Puede agregar o modificar el nombre del dispositivo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="3b14c-121">**Device name** You can add or modify the name of the test device.</span></span>
    
- <span data-ttu-id="3b14c-122">**Tipo de identificador** Puede seleccionar el método que se utiliza para identificar el dispositivo, seleccionando una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="3b14c-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>
    
  - <span data-ttu-id="3b14c-123">**Dirección MAC**</span><span class="sxs-lookup"><span data-stu-id="3b14c-123">**MAC address**</span></span>
    
  - <span data-ttu-id="3b14c-124">**Número de serie**</span><span class="sxs-lookup"><span data-stu-id="3b14c-124">**Serial number**</span></span>
    
- <span data-ttu-id="3b14c-125">**Identificador único** Puede escribir la dirección MAC o número de serie del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b14c-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>
    
<span data-ttu-id="3b14c-126">Para obtener más información acerca de las pruebas de los dispositivos, vea [Agregar un dispositivo a prueba la funcionalidad de actualización](http://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) en la documentación de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="3b14c-126">For details about testing devices, see [Add a Device to Test Update Functionality](http://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="3b14c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b14c-127">See also</span></span>

#### 

[<span data-ttu-id="3b14c-128">Dispositivo de prueba</span><span class="sxs-lookup"><span data-stu-id="3b14c-128">Test Device</span></span>](test-device.md)
#### 

[<span data-ttu-id="3b14c-129">Nueva CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="3b14c-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)
  
[<span data-ttu-id="3b14c-130">Conjunto de CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="3b14c-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)
  
[<span data-ttu-id="3b14c-131">Ver actualizaciones de Software para los dispositivos de su organización</span><span class="sxs-lookup"><span data-stu-id="3b14c-131">View Software Updates for Devices in Your Organization</span></span>](http://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)

