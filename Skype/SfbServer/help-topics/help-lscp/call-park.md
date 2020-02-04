---
title: Estacionamiento de llamadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: Cuando se aparca una llamada, se transfiere a un número temporal en el que se retiene la llamada hasta que alguien la recupere o agote el tiempo de espera. Debe configurar una tabla con los intervalos de números de extensión en los que está atendiendo las llamadas estacionadas. Estas extensiones tienen que ser extensiones virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado). Cada grupo que ejecuta la aplicación de estacionamiento de llamadas puede tener uno o más intervalos de extensiones. Estos intervalos tienen que ser únicos en el nivel global en toda la implementación.
ms.openlocfilehash: 1a7417ab525f8471b730dc177a993c3458750a3f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700305"
---
# <a name="call-park"></a>Estacionamiento de llamadas

Cuando se aparca una llamada, se transfiere a un número temporal en el que se retiene la llamada hasta que alguien la recupere o agote el tiempo de espera. Debe configurar una tabla con los intervalos de números de extensión en los que está atendiendo las llamadas estacionadas. Estas extensiones tienen que ser extensiones virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado). Cada grupo que ejecuta la aplicación de estacionamiento de llamadas puede tener uno o más intervalos de extensiones. Estos intervalos tienen que ser únicos en el nivel global en toda la implementación.

La página de **estacionamiento de llamadas** muestra una lista de todos los intervalos de números de estacionamiento de llamadas que se han definido para su organización.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En la página **Estacionamiento de llamadas** puede realizar las siguientes tareas:

- Crear un intervalo de números

- Cambiar un intervalo de números existente

- Eliminar un intervalo de números

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los comandos de la página.

- **Nuevo** Inicia un nuevo intervalo de números de aparcamiento de llamadas.

- **Editar** Abre el intervalo de números seleccionado para su edición, selecciona todos los intervalos de números de la lista o elimina el intervalo de números seleccionado.

- **Actualizar** Actualiza la lista de intervalos numéricos.

En la siguiente lista se describen los campos de la página.

- **Nombre** Nombre único que identifica el intervalo de números.

- **Intervalo de inicio** El número inicial del intervalo.

- **Finalizar rango** El número final del intervalo.

- **Destino** El nombre de dominio completo (FQDN) o el identificador de servicio del servicio de aplicación que hospeda la aplicación de estacionamiento de llamadas para el intervalo de números.

Para obtener más información sobre las funciones y características de reactivación de llamadas, consulte [Plan for Call Park in Skype empresarial 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md). Para obtener más información sobre cómo trabajar con intervalos numéricos de estacionamiento, consulte [configurar extensiones de números de teléfono para llamadas de aparcamiento](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).


