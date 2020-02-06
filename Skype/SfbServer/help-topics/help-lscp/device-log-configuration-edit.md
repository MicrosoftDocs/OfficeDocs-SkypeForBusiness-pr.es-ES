---
title: Edición de configuración de registro de dispositivo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: Puede Agregar una configuración de registro de dispositivo a la página de Editar configuración de registro, que determina el tamaño máximo de la caché de registro, el tamaño máximo de archivo de registro o la cantidad de tiempo que se guarda un archivo de registro antes de que se purgue. Puede cambiar esta configuración según los requisitos de la organización.
ms.openlocfilehash: 3ea368c0f3bccd7655d1bca3cb93a98a86b99c47
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822913"
---
# <a name="device-log-configuration-edit"></a><span data-ttu-id="18dfe-104">Configuración de registro de dispositivo: Editar</span><span class="sxs-lookup"><span data-stu-id="18dfe-104">Device Log Configuration: Edit</span></span>
 
<span data-ttu-id="18dfe-105">Puede Agregar una configuración de registro de dispositivo a la página de **Editar configuración de registro** , que determina el tamaño máximo de la caché de registro, el tamaño máximo de archivo de registro o la cantidad de tiempo que se guarda un archivo de registro antes de que se purgue.</span><span class="sxs-lookup"><span data-stu-id="18dfe-105">You can add a device log configuration to the **Edit Log Setting** page that determines the maximum log cache size, maximum log file size, or length of time a log file is kept before it is purged.</span></span> <span data-ttu-id="18dfe-106">Puede cambiar esta configuración según los requisitos de la organización.</span><span class="sxs-lookup"><span data-stu-id="18dfe-106">You can change these settings according to your organization's requirements.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="18dfe-p103">Al depurar los archivos, estos desaparecen para siempre del sistema de archivos. Tras depurar un archivo, no podrá recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="18dfe-p103">Purging files permanently removes them from the file system. After you purge a file, it cannot be recovered.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="18dfe-109">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="18dfe-109">Tasks you can perform</span></span>

<span data-ttu-id="18dfe-110">Puede realizar las siguientes tareas en la página **Editar Registro** :</span><span class="sxs-lookup"><span data-stu-id="18dfe-110">You can perform the following tasks on the **Edit Log Setting** page:</span></span>
  
- <span data-ttu-id="18dfe-111">Agregue una configuración de registro de dispositivo globalmente o para un sitio en particular.</span><span class="sxs-lookup"><span data-stu-id="18dfe-111">Add a device log configuration globally or for a particular site.</span></span>
    
- <span data-ttu-id="18dfe-112">Modificar las opciones para una configuración de registro de dispositivo existente.</span><span class="sxs-lookup"><span data-stu-id="18dfe-112">Modify the options for an existing device log configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="18dfe-113">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="18dfe-113">UI Reference</span></span>

<span data-ttu-id="18dfe-114">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="18dfe-114">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="18dfe-115">**Ámbito** Identifica el ámbito (global o de sitio) de la configuración del registro del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="18dfe-115">**Scope** Identifies the scope (Global or Site) of the device log configuration.</span></span>
    
- <span data-ttu-id="18dfe-116">**Nombre** Puede Agregar o modificar el nombre de la configuración del registro del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="18dfe-116">**Name** You can add or modify the name of the device log configuration.</span></span>
    
- <span data-ttu-id="18dfe-117">**Tamaño máximo de archivo (bytes)** Puede especificar el tamaño máximo que puede tener un archivo de registro antes de purgarlo.</span><span class="sxs-lookup"><span data-stu-id="18dfe-117">**Maximum file size (bytes)** You can specify the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="18dfe-118">El valor predeterminado es 1.024.000 bytes (1 MB).</span><span class="sxs-lookup"><span data-stu-id="18dfe-118">The default is 1,024,000 bytes (1 MB).</span></span>
    
- <span data-ttu-id="18dfe-119">**Tamaño máximo de la caché (bytes)** Puede especificar la cantidad máxima de información (en bytes) que se puede mantener en la memoria caché de archivos de registro antes de que se pueda borrar la caché y los datos se escriban en un archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="18dfe-119">**Maximum cache size (bytes)** You can specify the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="18dfe-120">El valor predeterminado es 512.000 bytes (0,5 MB).</span><span class="sxs-lookup"><span data-stu-id="18dfe-120">The default is 512,000 bytes (0.5 MB).</span></span>
    
- <span data-ttu-id="18dfe-121">**Minutos para vaciar la caché (1-60)** Puede especificar la frecuencia con la que se almacena la información almacenada en la memoria caché del archivo de registro en el archivo de registro real.</span><span class="sxs-lookup"><span data-stu-id="18dfe-121">**Minutes to flush cache (1-60)** You can specify how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="18dfe-122">Una vez registrados los datos, la caché se borra.</span><span class="sxs-lookup"><span data-stu-id="18dfe-122">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="18dfe-123">El valor predeterminado es de cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="18dfe-123">The default is five minutes.</span></span>
    
- <span data-ttu-id="18dfe-124">**Días para conservar los archivos de registro (1-365)** Puede especificar el número de días que se conservan los archivos de registro antes de que se purguen.</span><span class="sxs-lookup"><span data-stu-id="18dfe-124">**Days to keep log files (1-365)** You can specify the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="18dfe-125">El valor predeterminado es de 10 días.</span><span class="sxs-lookup"><span data-stu-id="18dfe-125">The default is 10 days.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="18dfe-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="18dfe-126">See also</span></span>

[<span data-ttu-id="18dfe-127">Configuración de registro de dispositivo</span><span class="sxs-lookup"><span data-stu-id="18dfe-127">Device Log Configuration</span></span>](device-log-configuration.md)
