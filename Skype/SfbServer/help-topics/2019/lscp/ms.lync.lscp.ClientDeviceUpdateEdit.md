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
  
- **Ámbito** Identifica el ámbito (Global o Sitio) de la configuración del registro de dispositivos.
    
- **Nombre** Puedes agregar o modificar el nombre de la configuración del registro de dispositivos.
    
- **Tamaño máximo de archivo (bytes)** Puede especificar el tamaño máximo que puede tener un archivo de registro antes de que se purgue. El valor predeterminado es 1.024.000 (1 MB).
    
- **Tamaño máximo de caché (bytes)** Puede especificar la cantidad máxima de información (en bytes) que se puede almacenar en la memoria caché del archivo de registro antes de que se deba borrar esa memoria caché y los datos se escriban en un archivo de registro. El valor predeterminado es 512.000 (0,5 MB).
    
- **Minutos para vaciar la memoria caché (1-60)** Puede especificar la frecuencia con la que la información almacenada en la memoria caché del archivo de registro se escribe en el archivo de registro real. Una vez se ha registrado la información, la memoria caché se borra. El valor predeterminado es cinco minutos.
    
- **Días para conservar los archivos de registro (1-365)** Puede especificar el número de días que se conservarán los archivos de registro antes de que se purguen. El valor predeterminado es 10 días.
    
## <a name="see-also"></a>Vea también

[Configuración de registro de dispositivo](ms.lync.lscp.ClientDeviceCfgMain.md)
