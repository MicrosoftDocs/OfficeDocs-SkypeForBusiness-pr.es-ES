---
title: Actualización de dispositivos
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft publica periódicamente un nuevo conjunto de actualizaciones de firmware de dispositivo para Skype Empresarial Phone Edition, que puede importar a los servidores y distribuir a los usuarios. Para obtener el último conjunto de reglas de actualización de dispositivos, vaya a la página Ayuda y soporte técnico del sitio web de Microsoft y busquePhone Edition.Descargue el paquete de actualización más reciente y extraiga los archivos en una carpeta del equipo donde se van a cargar las actualizaciones. Una vez extraídos los archivos, use el cmdlet Import-CsDeviceUpdate para importar las reglas de actualización de dispositivos que se encuentran en el archivo .CAB extraído (que tendrán el nombre UCUpdates.cab). Para obtener más información, vea Import-CsDeviceUpdate.
ms.openlocfilehash: f62ece38e33bfdc02a6110bb7cc4e53210c9b500
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120259"
---
# <a name="device-update"></a><span data-ttu-id="5e48a-106">Actualización de dispositivos</span><span class="sxs-lookup"><span data-stu-id="5e48a-106">Device Update</span></span>

<span data-ttu-id="5e48a-107">Microsoft publica periódicamente un nuevo conjunto de actualizaciones de firmware de dispositivo para Skype Empresarial Phone Edition, que puede importar a los servidores y distribuir a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5e48a-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="5e48a-108">Puede obtener el último conjunto de reglas de actualización de dispositivos en la página Ayuda y soporte técnico, en el sitio web de Microsoft, buscando "Phone Edition".</span><span class="sxs-lookup"><span data-stu-id="5e48a-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="5e48a-109">Descargue el último paquete de actualización y extraiga los archivos en una carpeta en el PC donde se cargarán las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="5e48a-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="5e48a-110">Una vez extraídos los archivos, puede usar el cmdlet **Import-CsDeviceUpdate** para importar las reglas de actualización del dispositivo que se encuentran en el archivo .CAB importado (que tendrán el mismo nombre UCUpdates.cab).</span><span class="sxs-lookup"><span data-stu-id="5e48a-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="5e48a-111">Para obtener más información, [vea Import-CsDeviceUpdate](/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5e48a-111">For details, see [Import-CsDeviceUpdate](/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="5e48a-112">Después de importar las reglas de actualización de dispositivos, puedes usar la página **Actualización** de dispositivos para ver y administrar estas reglas para los dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="5e48a-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="5e48a-113">Puede probar las actualizaciones de firmware y, a continuación, suponiendo que las pruebas hayan sido satisfactorias, poner las actualizaciones a disposición de todos los dispositivos pertinentes usados en la organización.</span><span class="sxs-lookup"><span data-stu-id="5e48a-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="5e48a-114">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="5e48a-114">Tasks you can perform</span></span>

<span data-ttu-id="5e48a-115">Puede realizar las siguientes tareas en la página **Actualización de dispositivo**:</span><span class="sxs-lookup"><span data-stu-id="5e48a-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="5e48a-116">Aprobar actualizaciones de dispositivos en la lista.</span><span class="sxs-lookup"><span data-stu-id="5e48a-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="5e48a-117">Cancelar o restaurar las actualizaciones de dispositivos pendientes.</span><span class="sxs-lookup"><span data-stu-id="5e48a-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="5e48a-118">Eliminar las actualizaciones de dispositivos de la lista.</span><span class="sxs-lookup"><span data-stu-id="5e48a-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="5e48a-119">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="5e48a-119">UI Reference</span></span>

<span data-ttu-id="5e48a-120">Las siguientes listas describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="5e48a-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="5e48a-121">**Editar** Puede usar esta opción para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e48a-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="5e48a-122">**Seleccionar todo** Esta opción selecciona todas las actualizaciones de dispositivos de la lista.</span><span class="sxs-lookup"><span data-stu-id="5e48a-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="5e48a-123">**Eliminar** Esta opción elimina todas las actualizaciones de dispositivo seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="5e48a-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="5e48a-124">**Acción** Puede seleccionar una o más actualizaciones en la lista y realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="5e48a-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="5e48a-125">**Cancelar actualizaciones pendientes** Esta opción impide que la actualización seleccionada se implemente en los dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="5e48a-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="5e48a-126">**Aprobar** Esta opción permite implementar la actualización seleccionada en los dispositivos de la organización.</span><span class="sxs-lookup"><span data-stu-id="5e48a-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="5e48a-127">**Restaurar** Esta opción permite implementar una actualización aprobada previamente en los dispositivos de la organización</span><span class="sxs-lookup"><span data-stu-id="5e48a-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="5e48a-128">**Actualizar** Puedes actualizar la lista para comprobar el estado de todas las actualizaciones de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5e48a-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="5e48a-129">Para obtener más información sobre el servicio web de actualización de dispositivos, vea [View Software Updates for Devices in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="5e48a-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="5e48a-130">Ver también</span><span class="sxs-lookup"><span data-stu-id="5e48a-130">See also</span></span>

[<span data-ttu-id="5e48a-131">Import-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="5e48a-131">Import-CsDeviceUpdate</span></span>](/powershell/module/skype/import-csdeviceupdate?view=skype-ps)