---
title: Actualización de dispositivos
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft lanza periódicamente un nuevo conjunto de actualizaciones de firmware del dispositivo de Skype para Business Phone Edition, que puede importar a los servidores y distribuir a los usuarios. Puede obtener el conjunto de reglas de actualización de dispositivo más reciente, vaya a la página de ayuda y soporte técnico en el sitio Web de Microsoft y buscar forPhone Edition.Download el paquete de actualización más reciente y extraer los archivos a una carpeta en el equipo donde están las actualizaciones que se va a cargar. Una vez extraídos los archivos, puede usar el cmdlet Import-CsDeviceUpdate para importar las reglas de actualización del dispositivo que se encuentran en el archivo .CAB importado (que tendrán el nombre UCUpdates.cab). Para obtener información detallada, vea Import-CsDeviceUpdate.
ms.openlocfilehash: e016dd80e809e98b58b3260e0d29e669773ddbd9
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255091"
---
# <a name="device-update"></a>Actualización de dispositivo

Microsoft lanza periódicamente un nuevo conjunto de actualizaciones de firmware del dispositivo de Skype para Business Phone Edition, que puede importar a los servidores y distribuir a los usuarios. Puede obtener el último conjunto de reglas de actualización de dispositivos en la página Ayuda y soporte técnico del sitio web de Microsoft, buscando por "Phone Edition". Descargue el último paquete de actualización y extraiga los archivos en una carpeta del PC donde se vayan a cargar las actualizaciones. Una vez extraídos los archivos, puede usar el cmdlet **Import-CsDeviceUpdate** para importar las reglas de actualización del dispositivo que se encuentran en el archivo .CAB importado (que tendrán el nombre UCUpdates.cab). Para obtener información detallada, vea [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).

Una vez importadas las reglas de actualización de dispositivo, puede usar la página **Actualización de dispositivos** para ver y administrar estas reglas para los dispositivos de su organización.

> [!TIP]
> Puede probar las actualizaciones de firmware y, luego, y siempre y cuando las pruebas hayan sido satisfactorias, poner las actualizaciones a disposición de todos los dispositivos pertinentes usados en la organización.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En la página **Actualización de dispositivo** puede realizar las siguientes tareas:

- Aprobar actualizaciones de dispositivos en la lista.

- Cancelar o restaurar las actualizaciones de dispositivos pendientes.

- Eliminar las actualizaciones de dispositivos de la lista.

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.

- **Editar** Puede usar esta opción para hacer lo siguiente:

  - **Seleccionar todo** Esta opción selecciona todas las actualizaciones de dispositivo de la lista.

  - **Eliminar** Esta opción elimina todas las actualizaciones de dispositivo seleccionado.

- **Acción** Puede seleccionar una o varias actualizaciones en la lista y realice las acciones siguientes:

  - **Cancelar las actualizaciones pendientes** Esta opción impide que la actualización seleccionada se implemente en los dispositivos de su organización.

  - **Aprobar** Esta opción permite la actualización seleccionada se implemente en los dispositivos de su organización.

  - **Restaurar** Esta opción permite una actualización aprobada anteriormente se implemente en los dispositivos de su organización

- **Actualizar** Puede actualizar la lista para comprobar el estado de todas las actualizaciones de dispositivo.

Para obtener información detallada sobre el servicio Web de actualización de dispositivos, consulte [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) en la documentación de planeación.
## <a name="see-also"></a>Vea también

[Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)