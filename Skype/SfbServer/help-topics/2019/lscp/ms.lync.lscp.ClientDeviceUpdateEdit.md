---
title: Edición de configuración del registro de dispositivos
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
ROBOTS: NOINDEX, NOFOLLOW
description: Puede agregar una configuración de registro de dispositivo a la página Editar configuración de registro, que determina el tamaño de caché de registro máximo o el tiempo de tiempo que se conserva un archivo de registro antes de que se purgue. Puede cambiar esta configuración según los requisitos de su organización.
ms.openlocfilehash: ac6c341460d0e196548a86620d89f67bc51d7b4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830300"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="add0c-104">Configuración de registro de dispositivo: Editar</span><span class="sxs-lookup"><span data-stu-id="add0c-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="add0c-105">Puede agregar una configuración de registro de dispositivo a la página **Editar configuración de registro**, que determina el tamaño de caché de registro máximo o el tiempo de tiempo que se conserva un archivo de registro antes de que se purgue.</span><span class="sxs-lookup"><span data-stu-id="add0c-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="add0c-106">Puede cambiar esta configuración según los requisitos de su organización.</span><span class="sxs-lookup"><span data-stu-id="add0c-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="add0c-p103">Al depurar los archivos, estos desaparecen para siempre del sistema de archivos. Tras depurar un archivo, no puede ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="add0c-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="add0c-109">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="add0c-109">Tasks you can perform</span></span>

<span data-ttu-id="add0c-110">Puede realizar las siguientes tareas en la página **Editar configuración de registro**:</span><span class="sxs-lookup"><span data-stu-id="add0c-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="add0c-111">Agregar una configuración de registro de dispositivo de forma global o para un sitio concreto.</span><span class="sxs-lookup"><span data-stu-id="add0c-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="add0c-112">Modificar las opciones para una configuración de registro de dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="add0c-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="add0c-113">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="add0c-113">UI Reference</span></span>

<span data-ttu-id="add0c-114">Las siguientes listas describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="add0c-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="add0c-115">**Ámbito** Identifica el ámbito (Global o Sitio) de la configuración del registro de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="add0c-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="add0c-116">**Nombre** Puedes agregar o modificar el nombre de la configuración del registro de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="add0c-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="add0c-117">**Tamaño máximo de archivo (bytes)** Puede especificar el tamaño máximo que puede tener un archivo de registro antes de que se purgue.</span><span class="sxs-lookup"><span data-stu-id="add0c-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="add0c-118">El valor predeterminado es 1.024.000 (1 MB).</span><span class="sxs-lookup"><span data-stu-id="add0c-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="add0c-119">**Tamaño máximo de caché (bytes)** Puede especificar la cantidad máxima de información (en bytes) que se puede almacenar en la memoria caché del archivo de registro antes de que se deba borrar esa memoria caché y los datos se escriban en un archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="add0c-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="add0c-120">El valor predeterminado es 512.000 (0,5 MB).</span><span class="sxs-lookup"><span data-stu-id="add0c-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="add0c-121">**Minutos para vaciar la memoria caché (1-60)** Puede especificar la frecuencia con la que la información almacenada en la memoria caché del archivo de registro se escribe en el archivo de registro real.</span><span class="sxs-lookup"><span data-stu-id="add0c-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="add0c-122">Una vez se ha registrado la información, la memoria caché se borra.</span><span class="sxs-lookup"><span data-stu-id="add0c-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="add0c-123">El valor predeterminado es cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="add0c-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="add0c-124">**Días para conservar los archivos de registro (1-365)** Puede especificar el número de días que se conservarán los archivos de registro antes de que se purguen.</span><span class="sxs-lookup"><span data-stu-id="add0c-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="add0c-125">El valor predeterminado es 10 días.</span><span class="sxs-lookup"><span data-stu-id="add0c-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="add0c-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="add0c-126">See also</span></span>

[<span data-ttu-id="add0c-127">Configuración de registro de dispositivo</span><span class="sxs-lookup"><span data-stu-id="add0c-127">Device Log Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)
