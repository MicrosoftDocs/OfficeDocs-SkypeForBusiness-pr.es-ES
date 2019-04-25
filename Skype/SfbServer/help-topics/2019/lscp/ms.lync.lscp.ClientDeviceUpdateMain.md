---
title: Actualización de dispositivos
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft lanza periódicamente un nuevo conjunto de actualizaciones de firmware del dispositivo de Skype para Business Phone Edition, que puede importar a los servidores y distribuir a los usuarios. Puede obtener el conjunto de reglas de actualización de dispositivo más reciente, vaya a la página de ayuda y soporte técnico en el sitio Web de Microsoft y buscar forPhone Edition.Download el paquete de actualización más reciente y extraer los archivos a una carpeta en el equipo donde están las actualizaciones que se va a cargar. Una vez extraídos los archivos, puede usar el cmdlet Import-CsDeviceUpdate para importar las reglas de actualización del dispositivo que se encuentran en el archivo .CAB importado (que tendrán el nombre UCUpdates.cab). Para obtener información detallada, vea Import-CsDeviceUpdate.
ms.openlocfilehash: 67e398f992fa1cf4d76a75d91d9daf1d5c05b08c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32215839"
---
# <a name="device-update"></a><span data-ttu-id="4186b-106">Actualización de dispositivo</span><span class="sxs-lookup"><span data-stu-id="4186b-106">Device Update</span></span>

<span data-ttu-id="4186b-107">Microsoft lanza periódicamente un nuevo conjunto de actualizaciones de firmware del dispositivo de Skype para Business Phone Edition, que puede importar a los servidores y distribuir a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4186b-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="4186b-108">Puede obtener el último conjunto de reglas de actualización de dispositivos en la página Ayuda y soporte técnico del sitio web de Microsoft, buscando por "Phone Edition".</span><span class="sxs-lookup"><span data-stu-id="4186b-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="4186b-109">Descargue el último paquete de actualización y extraiga los archivos en una carpeta del PC donde se vayan a cargar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="4186b-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="4186b-110">Una vez extraídos los archivos, puede usar el cmdlet **Import-CsDeviceUpdate** para importar las reglas de actualización del dispositivo que se encuentran en el archivo .CAB importado (que tendrán el nombre UCUpdates.cab).</span><span class="sxs-lookup"><span data-stu-id="4186b-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="4186b-111">Para obtener información detallada, vea [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="4186b-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="4186b-112">Una vez importadas las reglas de actualización de dispositivo, puede usar la página **Actualización de dispositivos** para ver y administrar estas reglas para los dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="4186b-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="4186b-113">Puede probar las actualizaciones de firmware y, luego, y siempre y cuando las pruebas hayan sido satisfactorias, poner las actualizaciones a disposición de todos los dispositivos pertinentes usados en la organización.</span><span class="sxs-lookup"><span data-stu-id="4186b-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="4186b-114">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="4186b-114">Tasks you can perform</span></span>

<span data-ttu-id="4186b-115">En la página **Actualización de dispositivo** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="4186b-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="4186b-116">Aprobar actualizaciones de dispositivos en la lista.</span><span class="sxs-lookup"><span data-stu-id="4186b-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="4186b-117">Cancelar o restaurar las actualizaciones de dispositivos pendientes.</span><span class="sxs-lookup"><span data-stu-id="4186b-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="4186b-118">Eliminar las actualizaciones de dispositivos de la lista.</span><span class="sxs-lookup"><span data-stu-id="4186b-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="4186b-119">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="4186b-119">UI Reference</span></span>

<span data-ttu-id="4186b-120">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="4186b-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="4186b-121">**Editar** Puede usar esta opción para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4186b-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="4186b-122">**Seleccionar todo** Esta opción selecciona todas las actualizaciones de dispositivo de la lista.</span><span class="sxs-lookup"><span data-stu-id="4186b-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="4186b-123">**Eliminar** Esta opción elimina todas las actualizaciones de dispositivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4186b-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="4186b-124">**Acción** Puede seleccionar una o varias actualizaciones en la lista y realice las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="4186b-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="4186b-125">**Cancelar las actualizaciones pendientes** Esta opción impide que la actualización seleccionada se implemente en los dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="4186b-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="4186b-126">**Aprobar** Esta opción permite la actualización seleccionada se implemente en los dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="4186b-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="4186b-127">**Restaurar** Esta opción permite una actualización aprobada anteriormente se implemente en los dispositivos de su organización</span><span class="sxs-lookup"><span data-stu-id="4186b-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="4186b-128">**Actualizar** Puede actualizar la lista para comprobar el estado de todas las actualizaciones de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4186b-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="4186b-129">Para más detalles sobre el servicio Device Update Web, mire [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="4186b-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="4186b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="4186b-130">See also</span></span>

[<span data-ttu-id="4186b-131">Import-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="4186b-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
