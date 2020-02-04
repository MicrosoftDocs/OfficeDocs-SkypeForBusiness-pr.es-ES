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
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: Puede Agregar una configuración de registro de dispositivo a la página de Editar configuración de registro, que determina el tamaño máximo de la caché de registro, el tamaño máximo de archivo de registro o la cantidad de tiempo que se guarda un archivo de registro antes de que se purgue. Puede cambiar esta configuración según los requisitos de la organización.
ms.openlocfilehash: 069548626972f8daf73f1863ec08f302bf20e082
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700315"
---
# <a name="device-log-configuration-edit"></a>Configuración de registro de dispositivo: Editar
 
Puede Agregar una configuración de registro de dispositivo a la página de **Editar configuración de registro** , que determina el tamaño máximo de la caché de registro, el tamaño máximo de archivo de registro o la cantidad de tiempo que se guarda un archivo de registro antes de que se purgue. Puede cambiar esta configuración según los requisitos de la organización.
  
> [!CAUTION]
> Al depurar los archivos, estos desaparecen para siempre del sistema de archivos. Tras depurar un archivo, no podrá recuperarlo. 
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Editar Registro** :
  
- Agregue una configuración de registro de dispositivo globalmente o para un sitio en particular.
    
- Modificar las opciones para una configuración de registro de dispositivo existente.
    
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.
  
- **Ámbito** Identifica el ámbito (global o de sitio) de la configuración del registro del dispositivo.
    
- **Nombre** Puede Agregar o modificar el nombre de la configuración del registro del dispositivo.
    
- **Tamaño máximo de archivo (bytes)** Puede especificar el tamaño máximo que puede tener un archivo de registro antes de purgarlo. El valor predeterminado es 1.024.000 bytes (1 MB).
    
- **Tamaño máximo de la caché (bytes)** Puede especificar la cantidad máxima de información (en bytes) que se puede mantener en la memoria caché de archivos de registro antes de que se pueda borrar la caché y los datos se escriban en un archivo de registro. El valor predeterminado es 512.000 bytes (0,5 MB).
    
- **Minutos para vaciar la caché (1-60)** Puede especificar la frecuencia con la que se almacena la información almacenada en la memoria caché del archivo de registro en el archivo de registro real. Una vez registrados los datos, la caché se borra. El valor predeterminado es de cinco minutos.
    
- **Días para conservar los archivos de registro (1-365)** Puede especificar el número de días que se conservan los archivos de registro antes de que se purguen. El valor predeterminado es de 10 días.
    
## <a name="see-also"></a>Vea también

[Configuración de registro de dispositivo](device-log-configuration.md)
