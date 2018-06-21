---
title: Configuración de registro de dispositivo
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: El servicio Device Update Web crea automáticamente archivos de registro que registran la actividad de actualización de los dispositivos. Como parte de la estrategia de administración de datos de la organización, es posible que desee establecer umbrales en tamaño de caché de datos de registro, el tamaño del archivo de registro o el período de tiempo que se mantiene un archivo de registro antes de que se elimina. Puede cambiar esta configuración según los requisitos de su organización. Si no desea que el servicio Device Update Web purgue los archivos de registro de forma automática, puede purgarlos manualmente según sea necesario. La configuración de registros se puede cambiar de forma global o por sitio.
ms.openlocfilehash: 69e75062038bdbc6072e48c18ed09193c7090659
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2018
ms.locfileid: "19988365"
---
# <a name="device-log-configuration"></a>Configuración de registro de dispositivo
 
El servicio Device Update Web crea automáticamente archivos de registro que registran la actividad de actualización de los dispositivos. Como parte de la estrategia de administración de datos de la organización, es posible que desee establecer umbrales en tamaño de caché de datos de registro, el tamaño del archivo de registro o el período de tiempo que se mantiene un archivo de registro antes de que se elimina. Puede cambiar esta configuración según los requisitos de su organización. Si no desea que el servicio Device Update Web purgue los archivos de registro de forma automática, puede purgarlos manualmente según sea necesario. La configuración de registros se puede cambiar de forma global o por sitio.
  
> [!NOTE]
> También puede configurar una hora del día cuando desee servicio Web Device Update para que elimine automáticamente los archivos de registro que sean más antiguos que el número de días configuró el servicio para mantener los archivos de registro (de forma predeterminada, que es archivos de registro que tengan más de 10 días). Esta configuración no pueden modificarse mediante Skype para el Panel de Control de servidor empresarial. En su lugar, debe usar Skype para Shell de administración de servidor empresarial. Para especificar la hora del día para eliminar los archivos de registro que han expirado, use el cmdlet **New-CsDeviceUpdateConfiguration** con el parámetro - LogCleanUpTimeOfDay. Para obtener información detallada, vea [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps). 
  
> [!CAUTION]
> Al depurar los archivos, estos desaparecen para siempre del sistema de archivos. Tras depurar un archivo, no podrá recuperarlo. 
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En la página **Configuración de registro de dispositivo** puede realizar las siguientes tareas:
  
- Agregar una configuración de registro de dispositivos de forma global o para un sitio o grupo concretos.
    
- Modificar las opciones para una configuración de registro de dispositivo existente.
    
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.
  
- **Nuevo** Puede agregar una nueva configuración de registro de dispositivo con el siguiente ámbito:
    
  - Global
    
  - Sitio
    
- **Editar** Puede cambiar las opciones de configuración de registro de dispositivo en la lista. Al usar esta opción, puede hacer lo siguiente:
    
  - **Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones para una configuración de registro de dispositivo.
    
  - **Seleccionar todo** Esta opción selecciona todas las configuraciones de registro de dispositivos de la lista.
    
  - **Eliminar** Esta opción elimina todas las configuraciones de registro de dispositivos seleccionadas.
    
- **Actualizar** Puede actualizar la lista de configuración de registro de dispositivo para comprobar el estado de las opciones de configuración de registro de todos los dispositivos.
    
## <a name="see-also"></a>Vea también

[Modificar la configuración de los archivos de registro de actividad de actualización de dispositivo](http://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)