---
title: Estacionamiento de llamadas
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: Cuando se estaciona una llamada, se transfiere a un número temporal en el que se mantiene la llamada hasta que alguien la recupera o se abate el tiempo de espera. Debe configurar una tabla con los intervalos de números de extensión que va a reservar para las llamadas estacionadas. Las extensiones deben ser virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado). Cada grupo que ejecuta la aplicación estacionamiento de llamadas puede tener uno o más intervalos de extensiones. Estos intervalos deben ser únicos en el nivel global en toda la implementación.
ms.openlocfilehash: b7926c10424fd5902fdc43e6c0fccadb45e61f79
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097076"
---
# <a name="call-park"></a>Estacionamiento de llamadas

Cuando se estaciona una llamada, se transfiere a un número temporal en el que se mantiene la llamada hasta que alguien la recupera o se abate el tiempo de espera. Debe configurar una tabla con los intervalos de números de extensión que va a reservar para las llamadas estacionadas. Las extensiones deben ser virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado). Cada grupo que ejecuta la aplicación estacionamiento de llamadas puede tener uno o más intervalos de extensiones. Estos intervalos deben ser únicos en el nivel global en toda la implementación.

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

- **Intervalo de inicio** El número inicial del intervalo.

- **Intervalo final** El número final del intervalo.

- **Destino** Nombre de dominio completo (FQDN) o identificador de servicio del servicio de aplicación que hospeda la aplicación estacionamiento de llamadas para el intervalo de números.

Para obtener más información sobre las características y capacidades del estacionamiento de llamadas, vea [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md). Para obtener más información sobre cómo trabajar con intervalos de números de estacionamiento de llamadas, vea [Configure Phone Number Extensions for Parking Calls](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls).