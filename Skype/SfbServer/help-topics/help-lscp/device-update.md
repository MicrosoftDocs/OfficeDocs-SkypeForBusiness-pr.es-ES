---
title: Actualización de dispositivos
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft lanza periódicamente un nuevo conjunto de actualizaciones de firmware de dispositivo para Business Phone Edition, que se puede importar a los servidores y distribuir a los usuarios de Skype. Puede obtener el último conjunto de reglas de actualización de dispositivo va a la página de ayuda y soporte técnico en el sitio Web de Microsoft y buscar forPhone Edition.Download el paquete de la actualización más reciente y extraer los archivos a una carpeta en el equipo donde están las actualizaciones para cargarse. Una vez extraídos los archivos, a continuación, puede utilizar el cmdlet Import-CsDeviceUpdate para importar las reglas de actualización de dispositivo se encuentra en los datos extraídos. Archivo CAB (que tendrá el nombre UCUpdates.cab). Para obtener más información, consulte CsDeviceUpdate de importación.
ms.openlocfilehash: 584c04e8169eec4621c91c469127b99388f4820a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="device-update"></a><span data-ttu-id="e97d6-106">Actualización de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e97d6-106">Device Update</span></span>
 
<span data-ttu-id="e97d6-107">Microsoft lanza periódicamente un nuevo conjunto de actualizaciones de firmware de dispositivo para Business Phone Edition, que se puede importar a los servidores y distribuir a los usuarios de Skype.</span><span class="sxs-lookup"><span data-stu-id="e97d6-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="e97d6-108">Puede obtener el último conjunto de reglas de actualización de dispositivos en la página Ayuda y soporte técnico del sitio web de Microsoft, buscando por "Phone Edition".</span><span class="sxs-lookup"><span data-stu-id="e97d6-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="e97d6-109">Descargue el último paquete de actualización y extraiga los archivos en una carpeta del PC donde se vayan a cargar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="e97d6-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="e97d6-110">Una vez extraídos los archivos, puede usar el cmdlet **Import-CsDeviceUpdate** para importar las reglas de actualización del dispositivo que se encuentran en el archivo .CAB importado (que tendrán el nombre UCUpdates.cab).</span><span class="sxs-lookup"><span data-stu-id="e97d6-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="e97d6-111">Para obtener más información, consulte [CsDeviceUpdate de importación](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e97d6-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>
  
<span data-ttu-id="e97d6-112">Después de importar las reglas de actualización de dispositivo, puede utilizar la página de **Actualización de dispositivo** para ver y administrar estas reglas para los dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="e97d6-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>
  
> [!TIP]
> <span data-ttu-id="e97d6-113">Puede probar las actualizaciones de firmware y, luego, y siempre y cuando las pruebas hayan sido satisfactorias, poner las actualizaciones a disposición de todos los dispositivos pertinentes usados en la organización.</span><span class="sxs-lookup"><span data-stu-id="e97d6-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="e97d6-114">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="e97d6-114">Tasks you can perform</span></span>

<span data-ttu-id="e97d6-115">En la página **Actualización de dispositivo** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="e97d6-115">You can perform the following tasks on the **Device Update** page:</span></span>
  
- <span data-ttu-id="e97d6-116">Aprobar actualizaciones de dispositivos en la lista.</span><span class="sxs-lookup"><span data-stu-id="e97d6-116">Approve device updates in the list.</span></span>
    
- <span data-ttu-id="e97d6-117">Cancelar o restaurar las actualizaciones de dispositivos pendientes.</span><span class="sxs-lookup"><span data-stu-id="e97d6-117">Cancel or restore pending device updates.</span></span>
    
- <span data-ttu-id="e97d6-118">Eliminar las actualizaciones de dispositivos de la lista.</span><span class="sxs-lookup"><span data-stu-id="e97d6-118">Delete device updates from the list.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="e97d6-119">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="e97d6-119">UI Reference</span></span>

<span data-ttu-id="e97d6-120">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="e97d6-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="e97d6-121">**Editar** Puede utilizar esta opción para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e97d6-121">**Edit** You can use this option to do the following:</span></span>
    
  - <span data-ttu-id="e97d6-122">**Seleccionar todo** Esta opción selecciona todas las actualizaciones de dispositivo en la lista.</span><span class="sxs-lookup"><span data-stu-id="e97d6-122">**Select All** This option selects all device updates in the list.</span></span>
    
  - <span data-ttu-id="e97d6-123">**Eliminar** Esta opción elimina todas las actualizaciones del dispositivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e97d6-123">**Delete** This option deletes all selected device updates.</span></span>
    
- <span data-ttu-id="e97d6-124">**Acción** Puede seleccionar una o más actualizaciones en la lista y realizar las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e97d6-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>
    
  - <span data-ttu-id="e97d6-125">**Cancelar las actualizaciones pendientes** Esta opción evita la actualización seleccionada se implementen en los dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="e97d6-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>
    
  - <span data-ttu-id="e97d6-126">**Aprobar** Esta opción permite la actualización seleccionada que se distribuirán a los dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="e97d6-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>
    
  - <span data-ttu-id="e97d6-127">**Restaurar** Esta opción permite una actualización previamente aprobada que se distribuirán a los dispositivos de su organización</span><span class="sxs-lookup"><span data-stu-id="e97d6-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>
    
- <span data-ttu-id="e97d6-128">**Actualizar** Puede actualizar la lista para comprobar el estado de todas las actualizaciones del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e97d6-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>
    
<span data-ttu-id="e97d6-129">Para obtener más información acerca del servicio Web de actualización de dispositivo, vea [Ver actualizaciones de Software para los dispositivos de su organización](http://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) en la documentación de planeamiento.</span><span class="sxs-lookup"><span data-stu-id="e97d6-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](http://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="e97d6-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="e97d6-130">See also</span></span>

#### 

[<span data-ttu-id="e97d6-131">CsDeviceUpdate de importación</span><span class="sxs-lookup"><span data-stu-id="e97d6-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)

