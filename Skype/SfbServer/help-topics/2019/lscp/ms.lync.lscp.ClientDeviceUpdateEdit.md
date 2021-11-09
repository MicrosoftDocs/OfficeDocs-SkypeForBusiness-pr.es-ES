---
title: Edición de configuración del registro de dispositivos
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
ROBOTS: NOINDEX, NOFOLLOW
description: Puede agregar una configuración de registro de dispositivo a la página Editar configuración de registro, que determina el tamaño de caché de registro máximo o el tiempo de tiempo que se conserva un archivo de registro antes de que se purgue. Puede cambiar esta configuración según los requisitos de su organización.
ms.openlocfilehash: c9e058fc314a2dcc550d4d399fed0b34b8532029
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857837"
---
# <a name="device-log-configuration-edit"></a>Configuración de registro de dispositivo: Editar
 
Puede agregar una configuración de registro de dispositivo a la página **Editar configuración de registro**, que determina el tamaño de caché de registro máximo o el tiempo de tiempo que se conserva un archivo de registro antes de que se purgue. Puede cambiar esta configuración según los requisitos de su organización.
  
> [!CAUTION]
> Al depurar los archivos, estos desaparecen para siempre del sistema de archivos. Tras depurar un archivo, no puede ser recuperado. 
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Editar configuración de registro**:
  
- Agregar una configuración de registro de dispositivo de forma global o para un sitio concreto.
    
- Modificar las opciones para una configuración de registro de dispositivo existente.
    
## <a name="ui-reference"></a>Referencia de la interfaz de usuario

Las siguientes listas describen los menús, comandos, campos y propiedades de la página.
  
- **Ámbito** Identifica el ámbito (Global o Site) de la configuración del registro de dispositivos.
    
- **Nombre** Puedes agregar o modificar el nombre de la configuración del registro de dispositivos.
    
- **Tamaño máximo de archivo (bytes)** Puede especificar el tamaño máximo que puede tener un archivo de registro antes de purgarse. El valor predeterminado es 1.024.000 (1 MB).
    
- **Tamaño máximo de caché (bytes)** Puede especificar la cantidad máxima de información (en bytes) que se puede mantener en la memoria caché del archivo de registro antes de que esa memoria caché se debe borrar y los datos se escriben en un archivo de registro. El valor predeterminado es 512.000 (0,5 MB).
    
- **Minutos para vaciar la memoria caché (1-60)** Puede especificar la frecuencia con la que se escribe la información almacenada en la memoria caché del archivo de registro en el archivo de registro real. Una vez se ha registrado la información, la memoria caché se borra. El valor predeterminado es cinco minutos.
    
- **Días para mantener los archivos de registro (1-365)** Puede especificar el número de días que se mantienen los archivos de registro antes de que se purguen. El valor predeterminado es 10 días.
    
## <a name="see-also"></a>Consulte también

[Configuración de registro de dispositivo](ms.lync.lscp.ClientDeviceCfgMain.md)
