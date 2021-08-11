---
title: Configuración de registro de dispositivo
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
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: El servicio Device Update Web crea automáticamente archivos de registro que registran la actividad de actualización de dispositivos. Como parte de la estrategia de administración de datos de la organización, es posible que desee establecer umbrales en el tamaño de la memoria caché de datos de registro, el tamaño del archivo de registro o el tiempo que se conserva un archivo de registro antes de que se purgue. Puede cambiar esta configuración según los requisitos de su organización. Si no desea que el servicio Device Update Web purgue los archivos de registro de forma automática, puede purgarlos manualmente según sea necesario. La configuración de registros se puede cambiar de forma global o por sitio.
ms.openlocfilehash: 0233c48334bf40e36a36a9cf9247a1f01364ef6e05dfb5ee0875b04d746dca5c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307401"
---
# <a name="device-log-configuration"></a>Configuración de registro de dispositivo

El servicio Device Update Web crea automáticamente archivos de registro que registran la actividad de actualización de dispositivos. Como parte de la estrategia de administración de datos de la organización, es posible que desee establecer umbrales en el tamaño de la memoria caché de datos de registro, el tamaño del archivo de registro o el tiempo que se conserva un archivo de registro antes de que se purgue. Puede cambiar esta configuración según los requisitos de su organización. Si no desea que el servicio Device Update Web purgue los archivos de registro de forma automática, puede purgarlos manualmente según sea necesario. La configuración de registros se puede cambiar de forma global o por sitio.

> [!NOTE]
> También puede configurar una hora del día para que el servicio Device Update Web elimine automáticamente los archivos de registro más antiguos que el número de días configurados para que el servicio conserve los archivos de registro (de forma predeterminada, los archivos de registro de más de 10 días de antigüedad). Esta configuración no se puede modificar mediante Skype Empresarial Server Panel de control. En su lugar, debe usar Skype Empresarial Server Shell de administración. Para especificar la hora del día para eliminar los archivos de registro expirados, use el cmdlet **New-CsDeviceUpdateConfiguration** con el parámetro -LogCleanUpTimeOfDay. Para obtener más información, [vea New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).

> [!CAUTION]
> Al depurar los archivos, estos desaparecen para siempre del sistema de archivos. Tras depurar un archivo, no puede ser recuperado.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas en la página **Configuración de registro de dispositivo**:

- Agregar una configuración de registro de dispositivos de forma global o para un sitio o grupo concretos.

- Modifique las opciones para una configuración de registro de dispositivo existente.

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

Las siguientes listas describen los menús, comandos, campos y propiedades de la página.

- **Nuevo** Puedes agregar una nueva configuración de registro de dispositivos con el siguiente ámbito:

  - Global

  - Site

- **Editar** Puedes cambiar las opciones de una configuración de registro de dispositivos en la lista. Al usar esta opción, puede hacer lo siguiente:

  - **Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones de una configuración de registro de dispositivos.

  - **Seleccionar todo** Esta opción selecciona toda la configuración del registro de dispositivos en la lista.

  - **Eliminar** Esta opción elimina toda la configuración de registro de dispositivos seleccionada.

- **Actualizar** Puedes actualizar la lista de configuración del registro de dispositivos para comprobar el estado de las opciones de toda la configuración del registro de dispositivos.

## <a name="see-also"></a>Consulte también

[Modificar la configuración para los archivos de registro de la actividad de actualización de dispositivos](/previous-versions/office/lync-server-2013/lync-server-2013-modify-settings-for-device-update-log-files)