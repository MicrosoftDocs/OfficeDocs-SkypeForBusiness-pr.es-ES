---
title: Configuración de registro de dispositivo
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: El servicio Device Update Web crea automáticamente archivos de registro que registran la actividad de actualización de los dispositivos. Como parte de la estrategia de administración de datos de la organización, es posible que desee establecer umbrales en tamaño de caché de datos de registro, el tamaño del archivo de registro o el período de tiempo que se mantiene un archivo de registro antes de que se elimina. Puede cambiar esta configuración según los requisitos de su organización. Si no desea que el servicio Device Update Web purgue los archivos de registro de forma automática, puede purgarlos manualmente según sea necesario. La configuración de registros se puede cambiar de forma global o por sitio.
ms.openlocfilehash: 69e75062038bdbc6072e48c18ed09193c7090659
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2018
ms.locfileid: "19988365"
---
# <a name="device-log-configuration"></a><span data-ttu-id="03415-107">Configuración de registro de dispositivo</span><span class="sxs-lookup"><span data-stu-id="03415-107">Device Log Configuration</span></span>
 
<span data-ttu-id="03415-108">El servicio Device Update Web crea automáticamente archivos de registro que registran la actividad de actualización de los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="03415-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="03415-109">Como parte de la estrategia de administración de datos de la organización, es posible que desee establecer umbrales en tamaño de caché de datos de registro, el tamaño del archivo de registro o el período de tiempo que se mantiene un archivo de registro antes de que se elimina.</span><span class="sxs-lookup"><span data-stu-id="03415-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="03415-110">Puede cambiar esta configuración según los requisitos de su organización.</span><span class="sxs-lookup"><span data-stu-id="03415-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="03415-111">Si no desea que el servicio Device Update Web purgue los archivos de registro de forma automática, puede purgarlos manualmente según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="03415-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="03415-112">La configuración de registros se puede cambiar de forma global o por sitio.</span><span class="sxs-lookup"><span data-stu-id="03415-112">Log settings can be changed globally or per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="03415-113">También puede configurar una hora del día cuando desee servicio Web Device Update para que elimine automáticamente los archivos de registro que sean más antiguos que el número de días configuró el servicio para mantener los archivos de registro (de forma predeterminada, que es archivos de registro que tengan más de 10 días).</span><span class="sxs-lookup"><span data-stu-id="03415-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="03415-114">Esta configuración no pueden modificarse mediante Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="03415-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="03415-115">En su lugar, debe usar Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="03415-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="03415-116">Para especificar la hora del día para eliminar los archivos de registro que han expirado, use el cmdlet **New-CsDeviceUpdateConfiguration** con el parámetro - LogCleanUpTimeOfDay.</span><span class="sxs-lookup"><span data-stu-id="03415-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="03415-117">Para obtener información detallada, vea [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="03415-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="03415-p104">Al depurar los archivos, estos desaparecen para siempre del sistema de archivos. Tras depurar un archivo, no podrá recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="03415-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="03415-120">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="03415-120">Tasks you can perform</span></span>

<span data-ttu-id="03415-121">En la página **Configuración de registro de dispositivo** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="03415-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>
  
- <span data-ttu-id="03415-122">Agregar una configuración de registro de dispositivos de forma global o para un sitio o grupo concretos.</span><span class="sxs-lookup"><span data-stu-id="03415-122">Add a device log configuration globally or for a particular site or pool.</span></span>
    
- <span data-ttu-id="03415-123">Modificar las opciones para una configuración de registro de dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="03415-123">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="03415-124">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="03415-124">UI Reference</span></span>

<span data-ttu-id="03415-125">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="03415-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="03415-126">**Nuevo** Puede agregar una nueva configuración de registro de dispositivo con el siguiente ámbito:</span><span class="sxs-lookup"><span data-stu-id="03415-126">**New** You can add a new device log configuration with the following scope:</span></span>
    
  - <span data-ttu-id="03415-127">Global</span><span class="sxs-lookup"><span data-stu-id="03415-127">Global</span></span>
    
  - <span data-ttu-id="03415-128">Sitio</span><span class="sxs-lookup"><span data-stu-id="03415-128">Site</span></span>
    
- <span data-ttu-id="03415-129">**Editar** Puede cambiar las opciones de configuración de registro de dispositivo en la lista.</span><span class="sxs-lookup"><span data-stu-id="03415-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="03415-130">Al usar esta opción, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="03415-130">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="03415-131">**Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones para una configuración de registro de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="03415-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>
    
  - <span data-ttu-id="03415-132">**Seleccionar todo** Esta opción selecciona todas las configuraciones de registro de dispositivos de la lista.</span><span class="sxs-lookup"><span data-stu-id="03415-132">**Select All** This option selects all device log configuration in the list.</span></span>
    
  - <span data-ttu-id="03415-133">**Eliminar** Esta opción elimina todas las configuraciones de registro de dispositivos seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="03415-133">**Delete** This option deletes all selected device log configuration.</span></span>
    
- <span data-ttu-id="03415-134">**Actualizar** Puede actualizar la lista de configuración de registro de dispositivo para comprobar el estado de las opciones de configuración de registro de todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="03415-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="03415-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="03415-135">See also</span></span>

[<span data-ttu-id="03415-136">Modificar la configuración de los archivos de registro de actividad de actualización de dispositivo</span><span class="sxs-lookup"><span data-stu-id="03415-136">Modify Settings for Log Files of Device Update Activity</span></span>](http://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)