---
title: Actualización de dispositivos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft lanza periódicamente un nuevo conjunto de actualizaciones de firmware de dispositivo para Skype empresarial Phone Edition, que puede importar a sus servidores y distribuir a los usuarios. Para obtener el último conjunto de reglas de actualización de dispositivos, vaya a la página de ayuda y soporte técnico en el sitio web de Microsoft y busque en la edición de forPhone. Descargue el paquete de actualización más reciente y extraiga los archivos en una carpeta del equipo en el que se van a cargar las actualizaciones. Una vez extraídos los archivos, puede usar el cmdlet Import-CsDeviceUpdate para importar las reglas de actualización del dispositivo que se encuentran en el archivo .CAB importado (que tendrán el nombre UCUpdates.cab). Para obtener más información, consulte Import-CsDeviceUpdate.
ms.openlocfilehash: ad296ebc3b8ade977884a925180dbb3639855f76
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822893"
---
# <a name="device-update"></a><span data-ttu-id="2c1d1-106">Actualización de dispositivo</span><span class="sxs-lookup"><span data-stu-id="2c1d1-106">Device Update</span></span>

<span data-ttu-id="2c1d1-107">Microsoft lanza periódicamente un nuevo conjunto de actualizaciones de firmware de dispositivo para Skype empresarial Phone Edition, que puede importar a sus servidores y distribuir a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2c1d1-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="2c1d1-108">Puede obtener el último conjunto de reglas de actualización de dispositivos en la página Ayuda y soporte técnico del sitio web de Microsoft, buscando por "Phone Edition".</span><span class="sxs-lookup"><span data-stu-id="2c1d1-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="2c1d1-109">Descargue el último paquete de actualización y extraiga los archivos en una carpeta del PC donde se vayan a cargar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="2c1d1-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="2c1d1-110">Una vez extraídos los archivos, puede usar el cmdlet **Import-CsDeviceUpdate** para importar las reglas de actualización del dispositivo que se encuentran en el archivo .CAB importado (que tendrán el nombre UCUpdates.cab).</span><span class="sxs-lookup"><span data-stu-id="2c1d1-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="2c1d1-111">Para obtener más información, consulte [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2c1d1-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="2c1d1-112">Una vez importadas las reglas de actualización de dispositivos, puede usar la página de **actualización de dispositivos** para ver y administrar estas reglas para los dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="2c1d1-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="2c1d1-113">Puede probar las actualizaciones de firmware y, luego, y siempre y cuando las pruebas hayan sido satisfactorias, poner las actualizaciones a disposición de todos los dispositivos pertinentes usados en la organización.</span><span class="sxs-lookup"><span data-stu-id="2c1d1-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="2c1d1-114">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="2c1d1-114">Tasks you can perform</span></span>

<span data-ttu-id="2c1d1-115">En la página **Actualización de dispositivo** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="2c1d1-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="2c1d1-116">Aprobar actualizaciones de dispositivos en la lista.</span><span class="sxs-lookup"><span data-stu-id="2c1d1-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="2c1d1-117">Cancelar o restaurar las actualizaciones de dispositivos pendientes.</span><span class="sxs-lookup"><span data-stu-id="2c1d1-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="2c1d1-118">Eliminar las actualizaciones de dispositivos de la lista.</span><span class="sxs-lookup"><span data-stu-id="2c1d1-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2c1d1-119">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="2c1d1-119">UI Reference</span></span>

<span data-ttu-id="2c1d1-120">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="2c1d1-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="2c1d1-121">**Editar** Puede usar esta opción para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c1d1-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="2c1d1-122">**Seleccionar todo** Esta opción selecciona todas las actualizaciones de dispositivos de la lista.</span><span class="sxs-lookup"><span data-stu-id="2c1d1-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="2c1d1-123">**Eliminar** Esta opción elimina todas las actualizaciones de dispositivos seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="2c1d1-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="2c1d1-124">**Acción** Puede seleccionar una o más actualizaciones de la lista y realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2c1d1-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="2c1d1-125">**Cancelar actualizaciones pendientes** Esta opción impide que la actualización seleccionada se implemente en los dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="2c1d1-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="2c1d1-126">**Aprobar** Esta opción permite implementar la actualización seleccionada en los dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="2c1d1-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="2c1d1-127">**Restaurar** Esta opción permite implementar una actualización aprobada previamente en los dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="2c1d1-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="2c1d1-128">**Actualizar** Puede actualizar la lista para comprobar el estado de todas las actualizaciones de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2c1d1-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="2c1d1-129">Para más detalles sobre el servicio Device Update Web, mire [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="2c1d1-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="2c1d1-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c1d1-130">See also</span></span>

[<span data-ttu-id="2c1d1-131">Importar-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="2c1d1-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
