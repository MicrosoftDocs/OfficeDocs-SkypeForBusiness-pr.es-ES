---
title: Actualización de dispositivos
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft lanza periódicamente un nuevo conjunto de actualizaciones de firmware de dispositivo para Business Phone Edition, que se puede importar a los servidores y distribuir a los usuarios de Skype. Puede obtener el último conjunto de reglas de actualización de dispositivo va a la página de ayuda y soporte técnico en el sitio Web de Microsoft y buscar forPhone Edition.Download el paquete de la actualización más reciente y extraer los archivos a una carpeta en el equipo donde están las actualizaciones para cargarse. Una vez extraídos los archivos, a continuación, puede utilizar el cmdlet Import-CsDeviceUpdate para importar las reglas de actualización de dispositivo se encuentra en los datos extraídos. Archivo CAB (que tendrá el nombre UCUpdates.cab). Para obtener más información, consulte CsDeviceUpdate de importación.
ms.openlocfilehash: 584c04e8169eec4621c91c469127b99388f4820a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="device-update"></a>Actualización de dispositivo
 
Microsoft lanza periódicamente un nuevo conjunto de actualizaciones de firmware de dispositivo para Business Phone Edition, que se puede importar a los servidores y distribuir a los usuarios de Skype. Puede obtener el último conjunto de reglas de actualización de dispositivos en la página Ayuda y soporte técnico del sitio web de Microsoft, buscando por "Phone Edition". Descargue el último paquete de actualización y extraiga los archivos en una carpeta del PC donde se vayan a cargar las actualizaciones. Una vez extraídos los archivos, puede usar el cmdlet **Import-CsDeviceUpdate** para importar las reglas de actualización del dispositivo que se encuentran en el archivo .CAB importado (que tendrán el nombre UCUpdates.cab). Para obtener más información, consulte [CsDeviceUpdate de importación](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).
  
Después de importar las reglas de actualización de dispositivo, puede utilizar la página de **Actualización de dispositivo** para ver y administrar estas reglas para los dispositivos de su organización.
  
> [!TIP]
> Puede probar las actualizaciones de firmware y, luego, y siempre y cuando las pruebas hayan sido satisfactorias, poner las actualizaciones a disposición de todos los dispositivos pertinentes usados en la organización. 
  
## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En la página **Actualización de dispositivo** puede realizar las siguientes tareas:
  
- Aprobar actualizaciones de dispositivos en la lista.
    
- Cancelar o restaurar las actualizaciones de dispositivos pendientes.
    
- Eliminar las actualizaciones de dispositivos de la lista.
    
## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.
  
- **Editar** Puede utilizar esta opción para hacer lo siguiente:
    
  - **Seleccionar todo** Esta opción selecciona todas las actualizaciones de dispositivo en la lista.
    
  - **Eliminar** Esta opción elimina todas las actualizaciones del dispositivo seleccionado.
    
- **Acción** Puede seleccionar una o más actualizaciones en la lista y realizar las acciones siguientes:
    
  - **Cancelar las actualizaciones pendientes** Esta opción evita la actualización seleccionada se implementen en los dispositivos de su organización.
    
  - **Aprobar** Esta opción permite la actualización seleccionada que se distribuirán a los dispositivos de su organización.
    
  - **Restaurar** Esta opción permite una actualización previamente aprobada que se distribuirán a los dispositivos de su organización
    
- **Actualizar** Puede actualizar la lista para comprobar el estado de todas las actualizaciones del dispositivo.
    
Para obtener más información acerca del servicio Web de actualización de dispositivo, vea [Ver actualizaciones de Software para los dispositivos de su organización](http://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) en la documentación de planeamiento.
## <a name="see-also"></a>Vea también

#### 

[CsDeviceUpdate de importación](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)

