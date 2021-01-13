---
title: Estacionamiento de llamadas
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: Cuando se estaciona una llamada, se transfiere a un número temporal en el que la llamada se mantiene hasta que alguien la recupera o se le hace el tiempo de espera. Debe configurar una tabla con los intervalos de números de extensión que reserva para las llamadas estacionadas. Las extensiones deben ser virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado). Cada grupo de servidores que ejecuta la aplicación Estacionamiento de llamadas puede tener uno o varios intervalos de extensiones. Estos intervalos deben ser únicos en el nivel global en toda la implementación.
ms.openlocfilehash: 7723b3bb3145725834059c73c0acc273fc67ca61
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800310"
---
# <a name="call-park"></a>Estacionamiento de llamadas

Cuando se estaciona una llamada, se transfiere a un número temporal en el que la llamada se mantiene hasta que alguien la recupera o se le hace el tiempo de espera. Debe configurar una tabla con los intervalos de números de extensión que reserva para las llamadas estacionadas. Las extensiones deben ser virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado). Cada grupo de servidores que ejecuta la aplicación Estacionamiento de llamadas puede tener uno o varios intervalos de extensiones. Estos intervalos deben ser únicos en el nivel global en toda la implementación.

La **página Estacionamiento de** llamadas muestra una lista de todos los intervalos de números de estacionamiento de llamadas definidos para su organización.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

Puede realizar las siguientes tareas desde la página **Estacionamiento de llamadas**:

- Crear un intervalo numérico nuevo

- Cambiar un intervalo numérico existente

- Eliminar un intervalo numérico

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

En la siguiente lista se describen los comandos de la página.

- **Nuevo** Inicia un nuevo intervalo de números de estacionamiento de llamadas.

- **Editar** Abre el intervalo de números seleccionado para su edición, selecciona todos los intervalos de números de la lista o elimina el intervalo de números seleccionado.

- **Actualizar** Actualiza la lista de intervalos de números.

En la siguiente lista se describen los campos de la página.

- **Nombre** Nombre único que identifica el intervalo de números.

- **Intervalo de inicio** Número inicial del intervalo.

- **Intervalo de finalización** Número final del intervalo.

- **Destino** Nombre de dominio completo (FQDN) o identificador de servicio del servicio de aplicación que hospeda la aplicación estacionamiento de llamadas para el intervalo de números.

Para obtener más información sobre las características y capacidades del estacionamiento de llamadas, consulte [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md). Para obtener más información sobre cómo trabajar con intervalos de números de estacionamiento de llamadas, vea [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).


