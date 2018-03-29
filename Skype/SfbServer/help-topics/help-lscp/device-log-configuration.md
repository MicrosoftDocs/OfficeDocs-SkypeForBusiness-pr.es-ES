---
title: Configuración de registro de dispositivo
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: El servicio Device Update Web crea automáticamente archivos de registro que registran la actividad de actualización de los dispositivos. Como parte de la estrategia de administración de datos de su organización, es aconsejable establecer umbrales basados en el tamaño de caché de datos de registro, el tamaño del archivo de registro o la longitud de tiempo que se mantiene un archivo de registro antes de purgarlo. Puede cambiar estos valores según los requisitos de su organización. Si no desea que el servicio Device Update Web purgue los archivos de registro de forma automática, puede purgarlos manualmente según sea necesario. La configuración de registros se puede cambiar de forma global o por sitio.
ms.openlocfilehash: e5a88c7437b654846fd464133b953465cd5d3e2a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="device-log-configuration"></a>Configuración de registro de dispositivo
 
El servicio Device Update Web crea automáticamente archivos de registro que registran la actividad de actualización de los dispositivos. Como parte de la estrategia de administración de datos de su organización, es aconsejable establecer umbrales basados en el tamaño de caché de datos de registro, el tamaño del archivo de registro o la longitud de tiempo que se mantiene un archivo de registro antes de purgarlo. Puede cambiar estos valores según los requisitos de su organización. Si no desea que el servicio Device Update Web purgue los archivos de registro de forma automática, puede purgarlos manualmente según sea necesario. La configuración de registros se puede cambiar de forma global o por sitio.
  
> [!NOTE]
> También puede configurar una hora del día al servicio Web de actualización de dispositivo para que elimine automáticamente los archivos de registro más antiguos que el número de días que configuró el servicio para mantener los archivos de registro (de forma predeterminada, los archivos de registro que tengan más de 10 días). No se puede modificar esta configuración mediante Skype para Panel de Control de servidor empresarial. En su lugar, debe utilizar Skype para el Shell de administración de servidor de empresa. Para especificar la hora del día para eliminar los archivos de registro caducado, utilice el cmdlet **New-CsDeviceUpdateConfiguration** con el parámetro - LogCleanUpTimeOfDay. Para obtener más información, consulte [CsDeviceUpdateConfiguration de nuevo](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps). 
  
> [!CAUTION]
> Al depurar los archivos, estos desaparecen para siempre del sistema de archivos. Tras depurar un archivo, no podrá recuperarlo. 
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En la página **Configuración de registro de dispositivo** puede realizar las siguientes tareas:
  
- Agregar una configuración de registro de dispositivos de forma global o para un sitio o grupo concretos.
    
- Modificar las opciones para una configuración de registro de dispositivo existente.
    
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.
  
- **Nuevo** Puede agregar una nueva configuración de registro del dispositivo con el siguiente ámbito:
    
  - Global
    
  - Sitio
    
- **Editar** Puede cambiar las opciones de una configuración de registro del dispositivo en la lista. Al usar esta opción, puede hacer lo siguiente:
    
  - **Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones de configuración de un registro de dispositivo.
    
  - **Seleccionar todo** Esta opción selecciona la configuración de registro de todos los dispositivos en la lista.
    
  - **Eliminar** Esta opción elimina todas las configuración de registro del dispositivo seleccionado.
    
- **Actualizar** Puede actualizar la lista de configuración de registro de dispositivos para comprobar el estado de las opciones de configuración de registro de todos los dispositivos.
    
## <a name="see-also"></a>Vea también

#### 

[Modificar la configuración de los archivos de registro de actividad de actualización de dispositivo](http://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)

