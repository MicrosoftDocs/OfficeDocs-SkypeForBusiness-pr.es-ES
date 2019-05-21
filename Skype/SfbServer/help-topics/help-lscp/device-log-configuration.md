---
title: Configuración de registro de dispositivo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: El servicio Device Update Web crea automáticamente archivos de registro que registran la actividad de actualización de los dispositivos. Como parte de la estrategia de administración de datos de su organización, es posible que desee establecer umbrales en el tamaño de la caché de datos de registro, tamaño de archivo de registro o la cantidad de tiempo que se guarda un archivo de registro antes de que se purgue. Puede cambiar esta configuración según los requisitos de la organización. Si no desea que el servicio Device Update Web purgue los archivos de registro de forma automática, puede purgarlos manualmente según sea necesario. La configuración de registros se puede cambiar de forma global o por sitio.
ms.openlocfilehash: e46811d40a7b93f5c59557c6744fb554b70aea2a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285942"
---
# <a name="device-log-configuration"></a>Configuración de registro de dispositivo

El servicio Device Update Web crea automáticamente archivos de registro que registran la actividad de actualización de los dispositivos. Como parte de la estrategia de administración de datos de su organización, es posible que desee establecer umbrales en el tamaño de la caché de datos de registro, tamaño de archivo de registro o la cantidad de tiempo que se guarda un archivo de registro antes de que se purgue. Puede cambiar esta configuración según los requisitos de la organización. Si no desea que el servicio Device Update Web purgue los archivos de registro de forma automática, puede purgarlos manualmente según sea necesario. La configuración de registros se puede cambiar de forma global o por sitio.

> [!NOTE]
> También puede configurar una hora del día en que desee que el servicio Web de actualización de dispositivos elimine automáticamente los archivos de registro anteriores al número de días que configuró el servicio para que conserve los archivos de registro (de forma predeterminada, es decir, los archivos de registro con más de 10 días de antigüedad). Esta configuración no se puede modificar con el panel de control de Skype empresarial Server. En su lugar, debe usar el shell de administración de Skype empresarial Server. Para especificar la hora del día a la que desea eliminar los archivos de registro expirados, use el cmdlet **New-CsDeviceUpdateConfiguration** con el parámetro-LogCleanUpTimeOfDay. Para obtener más información, vea [New-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps).

> [!CAUTION]
> Al depurar los archivos, estos desaparecen para siempre del sistema de archivos. Tras depurar un archivo, no podrá recuperarlo.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En la página **Configuración de registro de dispositivo** puede realizar las siguientes tareas:

- Agregar una configuración de registro de dispositivos de forma global o para un sitio o grupo concretos.

- Modificar las opciones para una configuración de registro de dispositivo existente.

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.

- **Nuevo** Puede Agregar una nueva configuración de registro de dispositivo con el siguiente ámbito:

  - Global

  - Sitio

- **Editar** Puede cambiar las opciones de la configuración de un registro de dispositivos en la lista. Al usar esta opción, puede hacer lo siguiente:

  - **Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones para la configuración de un registro de dispositivo.

  - **Seleccionar todo** Esta opción selecciona toda la configuración del registro de dispositivos de la lista.

  - **Eliminar** Esta opción elimina toda la configuración de registro de dispositivo seleccionada.

- **Actualizar** Puede actualizar la lista de configuración del registro de dispositivos para comprobar el estado de las opciones de toda la configuración del registro de dispositivos.

## <a name="see-also"></a>Vea también

[Modify Settings for Log Files of Device Update Activity](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
