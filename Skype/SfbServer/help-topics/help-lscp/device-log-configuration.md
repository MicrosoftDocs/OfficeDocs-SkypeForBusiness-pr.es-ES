---
title: Configuración de registro de dispositivo
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
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: El servicio Device Update Web crea automáticamente archivos de registro que registran la actividad de actualización de dispositivos. Como parte de la estrategia de administración de datos de su organización, es posible que desee establecer umbrales en el tamaño de la memoria caché de datos de registro, el tamaño del archivo de registro o la cantidad de tiempo que se conserva un archivo de registro antes de que se purgue. Puede cambiar esta configuración según los requisitos de su organización. Si no desea que el servicio Device Update Web purgue los archivos de registro de forma automática, puede purgarlos manualmente según sea necesario. La configuración de registros se puede cambiar de forma global o por sitio.
ms.openlocfilehash: 27b4382c84d6aa12a642f191a6167e99ac10565c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829490"
---
# <a name="device-log-configuration"></a><span data-ttu-id="bb30c-107">Configuración de registro de dispositivo</span><span class="sxs-lookup"><span data-stu-id="bb30c-107">Device Log Configuration</span></span>

<span data-ttu-id="bb30c-108">El servicio Device Update Web crea automáticamente archivos de registro que registran la actividad de actualización de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bb30c-108">Device Update Web service automatically creates log files that record device update activity.</span></span> <span data-ttu-id="bb30c-109">Como parte de la estrategia de administración de datos de su organización, es posible que desee establecer umbrales en el tamaño de la memoria caché de datos de registro, el tamaño del archivo de registro o la cantidad de tiempo que se conserva un archivo de registro antes de que se purgue.</span><span class="sxs-lookup"><span data-stu-id="bb30c-109">As part of your organization's data management strategy, you may want to set thresholds on log data cache size, log file size, or the length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="bb30c-110">Puede cambiar esta configuración según los requisitos de su organización.</span><span class="sxs-lookup"><span data-stu-id="bb30c-110">You can change these settings according to your organization's requirements.</span></span> <span data-ttu-id="bb30c-111">Si no desea que el servicio Device Update Web purgue los archivos de registro de forma automática, puede purgarlos manualmente según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="bb30c-111">If you do not want Device Update Web service to purge log files automatically, you can purge them manually, as needed.</span></span> <span data-ttu-id="bb30c-112">La configuración de registros se puede cambiar de forma global o por sitio.</span><span class="sxs-lookup"><span data-stu-id="bb30c-112">Log settings can be changed globally or per site.</span></span>

> [!NOTE]
> <span data-ttu-id="bb30c-113">También puede configurar una hora del día para que el servicio Device Update Web elimine automáticamente los archivos de registro más antiguos que el número de días configurados para que el servicio conserve los archivos de registro (de forma predeterminada, los archivos de registro de más de 10 días de antigüedad).</span><span class="sxs-lookup"><span data-stu-id="bb30c-113">You can also configure a time of day when you want Device Update Web service to automatically delete log files that are older than the number of days you configured the service to keep log files (by default, that is log files that are more than 10 days old).</span></span> <span data-ttu-id="bb30c-114">Esta configuración no se puede modificar con el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bb30c-114">This setting cannot be modified using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="bb30c-115">En su lugar, debe usar el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="bb30c-115">Instead, you must use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="bb30c-116">Para especificar la hora del día para eliminar los archivos de registro expirados, use el cmdlet **New-CsDeviceUpdateConfiguration** con el parámetro -LogCleanUpTimeOfDay.</span><span class="sxs-lookup"><span data-stu-id="bb30c-116">To specify the time of day to delete expired log files, use the **New-CsDeviceUpdateConfiguration** cmdlet with the -LogCleanUpTimeOfDay parameter.</span></span> <span data-ttu-id="bb30c-117">Para obtener más información, [vea New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="bb30c-117">For details, see [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).</span></span>

> [!CAUTION]
> <span data-ttu-id="bb30c-p104">Al depurar los archivos, estos desaparecen para siempre del sistema de archivos. Tras depurar un archivo, no puede ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="bb30c-p104">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="bb30c-120">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="bb30c-120">Tasks you can perform</span></span>

<span data-ttu-id="bb30c-121">Puede realizar las siguientes tareas en la página **Configuración de registro de dispositivo**:</span><span class="sxs-lookup"><span data-stu-id="bb30c-121">You can perform the following tasks on the **Device Log Configuration** page:</span></span>

- <span data-ttu-id="bb30c-122">Agregar una configuración de registro de dispositivos de forma global o para un sitio o grupo concretos.</span><span class="sxs-lookup"><span data-stu-id="bb30c-122">Add a device log configuration globally or for a particular site or pool.</span></span>

- <span data-ttu-id="bb30c-123">Modifique las opciones para una configuración de registro de dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="bb30c-123">Modify the options for an existing device log configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="bb30c-124">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="bb30c-124">UI Reference</span></span>

<span data-ttu-id="bb30c-125">Las siguientes listas describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="bb30c-125">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="bb30c-126">**Nuevo** Puedes agregar una nueva configuración de registro de dispositivos con el ámbito siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb30c-126">**New** You can add a new device log configuration with the following scope:</span></span>

  - <span data-ttu-id="bb30c-127">Global</span><span class="sxs-lookup"><span data-stu-id="bb30c-127">Global</span></span>

  - <span data-ttu-id="bb30c-128">Site</span><span class="sxs-lookup"><span data-stu-id="bb30c-128">Site</span></span>

- <span data-ttu-id="bb30c-129">**Editar** Puedes cambiar las opciones de una configuración de registro de dispositivos en la lista.</span><span class="sxs-lookup"><span data-stu-id="bb30c-129">**Edit** You can change the options of a device log configuration in the list.</span></span> <span data-ttu-id="bb30c-130">Al usar esta opción, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb30c-130">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="bb30c-131">**Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones para una configuración de registro de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bb30c-131">**Show details** This option opens a dialog box in which you can change the options for a device log configuration.</span></span>

  - <span data-ttu-id="bb30c-132">**Seleccionar todo** Esta opción selecciona toda la configuración de registro de dispositivos de la lista.</span><span class="sxs-lookup"><span data-stu-id="bb30c-132">**Select All** This option selects all device log configuration in the list.</span></span>

  - <span data-ttu-id="bb30c-133">**Eliminar** Esta opción elimina toda la configuración de registro de dispositivos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bb30c-133">**Delete** This option deletes all selected device log configuration.</span></span>

- <span data-ttu-id="bb30c-134">**Actualizar** Puedes actualizar la lista de configuración del registro de dispositivos para comprobar el estado de las opciones de toda la configuración del registro de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bb30c-134">**Refresh** You can refresh the device log configuration list to verify the status of the options of all device log configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb30c-135">Ver también</span><span class="sxs-lookup"><span data-stu-id="bb30c-135">See also</span></span>

[<span data-ttu-id="bb30c-136">Modificar la configuración para los archivos de registro de la actividad de actualización de dispositivos</span><span class="sxs-lookup"><span data-stu-id="bb30c-136">Modify Settings for Log Files of Device Update Activity</span></span>](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
