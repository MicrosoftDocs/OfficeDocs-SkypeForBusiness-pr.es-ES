---
title: Edición de configuración de registro de dispositivos
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: Puede agregar una configuración de registro del dispositivo a la página de Editar configuración de registro que determina el tamaño máximo del registro de la caché, tamaño de archivo máximo del registro o la longitud de tiempo que se mantiene un archivo de registro antes de purgarlo. Puede cambiar estos valores según los requisitos de su organización.
ms.openlocfilehash: 8003014f7b94824d0ef36a8d1328c6430e98d894
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="device-log-configuration-edit"></a>Configuración de registro del dispositivo: editar
 
Puede agregar una configuración de registro del dispositivo a la página de **Editar configuración de registro** que determina el tamaño máximo del registro de la caché, tamaño de archivo máximo del registro o la longitud de tiempo que se mantiene un archivo de registro antes de purgarlo. Puede cambiar estos valores según los requisitos de su organización.
  
> [!CAUTION]
> Al depurar los archivos, estos desaparecen para siempre del sistema de archivos. Tras depurar un archivo, no podrá recuperarlo. 
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Editar configuración de registro** :
  
- Agregar una configuración de registro de dispositivo globalmente o para un sitio determinado.
    
- Modificar las opciones para una configuración de registro de dispositivo existente.
    
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.
  
- **Ámbito de aplicación** Identifica el ámbito (Global o sitio) de la configuración de registro del dispositivo.
    
- **Nombre** Puede agregar o modificar el nombre de la configuración de registro del dispositivo.
    
- **Tamaño máximo de archivo (bytes)** Puede especificar el tamaño máximo que puede ser un archivo de registro antes de purgarlo. El valor predeterminado es 1.024.000 bytes (1 MB).
    
- **Tamaño máximo de caché (bytes)** Puede especificar la cantidad máxima de información (en bytes) que se puede almacenar en la caché de archivos de registro antes de que se debe borrar la caché y los datos se escriben en un archivo de registro. El valor predeterminado es 512.000 bytes (0,5 MB).
    
- **Minutos para vaciar la caché (1 de 60)** Puede especificar la frecuencia con la información almacenada en la caché de archivos de registro se escribe en el archivo de registro real. Después de que se registran los datos, la caché se borra. El valor predeterminado es cinco minutos.
    
- **Días para mantener los archivos de registro (1-365)** Puede especificar el número de días que se guardan los archivos de registro antes de ser eliminados. El valor predeterminado es de 10 días.
    
## <a name="see-also"></a>Vea también

#### 

[Configuración de dispositivos de registro](device-log-configuration.md)

