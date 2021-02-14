---
title: Actualización de dispositivos
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft publica periódicamente un nuevo conjunto de actualizaciones de firmware de dispositivo para Skype Empresarial Phone Edition, que puede importar a los servidores y distribuir a los usuarios. Para obtener el conjunto más reciente de reglas de actualización de dispositivos, vaya a la página Ayuda y soporte técnico del sitio web de Microsoft y busquePhone Edition.Descargue el paquete de actualización más reciente y extraiga los archivos en una carpeta del equipo donde se cargarán las actualizaciones. Una vez extraídos los archivos, use el cmdlet Import-CsDeviceUpdate para importar las reglas de actualización de dispositivos que se encuentran en el archivo .CAB extraído (que tendrán el nombre UCUpdates.cab). Para obtener más información, consulte Import-CsDeviceUpdate.
ms.openlocfilehash: 375069d5812d5aa13ebd63dd02eaa3cdd6151cc3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811060"
---
# <a name="device-update"></a>Actualización de dispositivos

Microsoft publica periódicamente un nuevo conjunto de actualizaciones de firmware de dispositivo para Skype Empresarial Phone Edition, que puede importar a los servidores y distribuir a los usuarios. Puede obtener el último conjunto de reglas de actualización de dispositivos en la página Ayuda y soporte técnico, en el sitio web de Microsoft, buscando "Phone Edition". Descargue el último paquete de actualización y extraiga los archivos en una carpeta en el PC donde se cargarán las actualizaciones. Una vez extraídos los archivos, puede usar el cmdlet **Import-CsDeviceUpdate** para importar las reglas de actualización del dispositivo que se encuentran en el archivo .CAB importado (que tendrán el mismo nombre UCUpdates.cab). Para obtener más información, [vea Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).

Una vez importadas las reglas de  actualización de dispositivos, puedes usar la página Actualización de dispositivos para ver y administrar estas reglas para los dispositivos de la organización.

> [!TIP]
> Puede probar las actualizaciones de firmware y, a continuación, suponiendo que las pruebas hayan sido satisfactorias, poner las actualizaciones a disposición de todos los dispositivos pertinentes usados en la organización.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Actualización de dispositivo**:

- Aprobar actualizaciones de dispositivos en la lista.

- Cancelar o restaurar las actualizaciones de dispositivos pendientes.

- Eliminar las actualizaciones de dispositivos de la lista.

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

Las siguientes listas describen los menús, comandos, campos y propiedades de la página.

- **Editar** Puede usar esta opción para hacer lo siguiente:

  - **Seleccionar todo** Esta opción selecciona todas las actualizaciones de dispositivos de la lista.

  - **Eliminar** Esta opción elimina todas las actualizaciones de dispositivo seleccionadas.

- **Acción** Puede seleccionar una o más actualizaciones en la lista y realizar las siguientes acciones:

  - **Cancelar actualizaciones pendientes** Esta opción impide que la actualización seleccionada se implemente en los dispositivos de la organización.

  - **Aprobar** Esta opción permite que la actualización seleccionada se implemente en los dispositivos de la organización.

  - **Restaurar** Esta opción permite implementar una actualización aprobada anteriormente en los dispositivos de la organización

- **Actualizar** Puedes actualizar la lista para comprobar el estado de todas las actualizaciones de dispositivos.

Para obtener más información sobre el servicio web de actualización de dispositivos, vea [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) en la documentación de planeación.
## <a name="see-also"></a>Vea también

[Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
