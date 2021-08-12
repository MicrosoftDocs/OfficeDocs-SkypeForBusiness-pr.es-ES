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
ms.openlocfilehash: e1dc3baec529640562b86372cbf3dbb4d797ec946fd1dcb0495613c40fe64b75
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280245"
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
