---
title: Edición de configuración del registro de dispositivo
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
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
ms.openlocfilehash: 09d0bc24ad61be98864fd1f37964c01f1fba84ba
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888269"
---
# <a name="device-log-configuration-edit"></a>Configuración de registro de dispositivo: Editar
 
Puede agregar una configuración de registro de dispositivo a la página **Editar configuración de registro** que determina el tamaño máximo del registro de la caché, el tamaño del archivo de registro máximo o período de tiempo que se mantiene un archivo de registro antes de que se elimina. Puede cambiar esta configuración según los requisitos de su organización.
  
> [!CAUTION]
> Al depurar los archivos, estos desaparecen para siempre del sistema de archivos. Tras depurar un archivo, no podrá recuperarlo. 
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Editar configuración de registro** :
  
- Agregar una configuración de registro de dispositivo de forma global o para un sitio concreto.
    
- Modificar las opciones para una configuración de registro de dispositivo existente.
    
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.
  
- **Ámbito** Identifica el ámbito (Global o sitio) de la configuración de registro de dispositivo.
    
- **Nombre** Puede agregar o modificar el nombre de la configuración de registro de dispositivo.
    
- **Tamaño máximo de archivo (bytes)** Puede especificar el tamaño máximo de un archivo de registro puede convertirse en antes que se elimine. El valor predeterminado es 1.024.000 bytes (1 MB).
    
- **Tamaño máximo de caché (bytes)** Puede especificar la cantidad máxima de información (en bytes) que se puede almacenar en la memoria caché de archivos de registro antes de que se debe borrar la memoria caché y los datos se escriben en un archivo de registro. El valor predeterminado es 512.000 bytes (0,5 MB).
    
- **Minutos para vaciar la memoria caché (1-60)** Puede especificar la frecuencia con la información almacenada en la memoria caché de archivos de registro se escribe en el archivo de registro real. Después de que se registran los datos, se borra la memoria caché. El valor predeterminado es de cinco minutos.
    
- **Días para mantener los archivos de registro (1-365)** Puede especificar el número de días que se conservan los archivos de registro antes de purgarse. El valor predeterminado es 10 días.
    
## <a name="see-also"></a>Consulte también

[Configuración de registro de dispositivo](device-log-configuration.md)
