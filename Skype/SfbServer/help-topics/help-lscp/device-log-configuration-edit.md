---
title: Edición de configuración del registro de dispositivo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: Puede agregar una configuración de registro de dispositivo a la página Editar configuración de registro que determina el tamaño máximo del registro de la caché, el tamaño del archivo de registro máximo o período de tiempo que se mantiene un archivo de registro antes de que se elimina. Puede cambiar esta configuración según los requisitos de su organización.
ms.openlocfilehash: f3f1a39a304de49b169999f8bb12cd324f0e89a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913996"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="ba662-104">Configuración de registro de dispositivo: Editar</span><span class="sxs-lookup"><span data-stu-id="ba662-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="ba662-105">Puede agregar una configuración de registro de dispositivo a la página **Editar configuración de registro** que determina el tamaño máximo del registro de la caché, el tamaño del archivo de registro máximo o período de tiempo que se mantiene un archivo de registro antes de que se elimina.</span><span class="sxs-lookup"><span data-stu-id="ba662-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="ba662-106">Puede cambiar esta configuración según los requisitos de su organización.</span><span class="sxs-lookup"><span data-stu-id="ba662-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ba662-p103">Al depurar los archivos, estos desaparecen para siempre del sistema de archivos. Tras depurar un archivo, no podrá recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="ba662-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="ba662-109">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="ba662-109">Tasks you can perform</span></span>

<span data-ttu-id="ba662-110">Puede realizar las siguientes tareas en la página **Editar configuración de registro** :</span><span class="sxs-lookup"><span data-stu-id="ba662-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="ba662-111">Agregar una configuración de registro de dispositivo de forma global o para un sitio concreto.</span><span class="sxs-lookup"><span data-stu-id="ba662-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="ba662-112">Modificar las opciones para una configuración de registro de dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="ba662-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="ba662-113">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="ba662-113">UI Reference</span></span>

<span data-ttu-id="ba662-114">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="ba662-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="ba662-115">**Ámbito** Identifica el ámbito (Global o sitio) de la configuración de registro de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba662-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="ba662-116">**Nombre** Puede agregar o modificar el nombre de la configuración de registro de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba662-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="ba662-117">**Tamaño máximo de archivo (bytes)** Puede especificar el tamaño máximo de un archivo de registro puede convertirse en antes que se elimine.</span><span class="sxs-lookup"><span data-stu-id="ba662-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="ba662-118">El valor predeterminado es 1.024.000 bytes (1 MB).</span><span class="sxs-lookup"><span data-stu-id="ba662-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="ba662-119">**Tamaño máximo de caché (bytes)** Puede especificar la cantidad máxima de información (en bytes) que se puede almacenar en la memoria caché de archivos de registro antes de que se debe borrar la memoria caché y los datos se escriben en un archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="ba662-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="ba662-120">El valor predeterminado es 512.000 bytes (0,5 MB).</span><span class="sxs-lookup"><span data-stu-id="ba662-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="ba662-121">**Minutos para vaciar la memoria caché (1-60)** Puede especificar la frecuencia con la información almacenada en la memoria caché de archivos de registro se escribe en el archivo de registro real.</span><span class="sxs-lookup"><span data-stu-id="ba662-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="ba662-122">Después de que se registran los datos, se borra la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="ba662-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="ba662-123">El valor predeterminado es de cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="ba662-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="ba662-124">**Días para mantener los archivos de registro (1-365)** Puede especificar el número de días que se conservan los archivos de registro antes de purgarse.</span><span class="sxs-lookup"><span data-stu-id="ba662-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="ba662-125">El valor predeterminado es 10 días.</span><span class="sxs-lookup"><span data-stu-id="ba662-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ba662-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba662-126">See also</span></span>

[<span data-ttu-id="ba662-127">Configuración de registro de dispositivo</span><span class="sxs-lookup"><span data-stu-id="ba662-127">Device Log Configuration</span></span>](device-log-configuration.md)
