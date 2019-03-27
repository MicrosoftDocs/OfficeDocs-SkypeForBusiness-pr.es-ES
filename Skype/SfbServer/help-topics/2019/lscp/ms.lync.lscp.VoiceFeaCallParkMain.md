---
title: Estacionamiento de llamadas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: Cuando una llamada está estacionada, se transfiere a un número temporal donde se mantiene la llamada hasta que alguien las recupera o se agota el tiempo. Debe configurar una tabla con los intervalos de números de extensión que desea reservar para llamadas estacionadas. Estas extensiones tienen que ser extensiones virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado). Cada grupo de servidores que se ejecuta la aplicación de estacionamiento de llamadas puede tener uno o más rangos de extensiones. Estos intervalos tienen que ser únicos en el nivel global en toda la implementación.
ms.openlocfilehash: f23ec10607c8cd1f6ec15dca3f9e3b99666abf1a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890265"
---
# <a name="call-park"></a>Estacionamiento de llamadas

Cuando una llamada está estacionada, se transfiere a un número temporal donde se mantiene la llamada hasta que alguien las recupera o se agota el tiempo. Debe configurar una tabla con los intervalos de números de extensión que desea reservar para llamadas estacionadas. Estas extensiones tienen que ser extensiones virtuales (es decir, extensiones que no tengan ningún usuario ni teléfono asignado). Cada grupo de servidores que se ejecuta la aplicación de estacionamiento de llamadas puede tener uno o más rangos de extensiones. Estos intervalos tienen que ser únicos en el nivel global en toda la implementación.

La página **Estacionamiento de llamadas** muestra una lista de todos los intervalos números estacionamiento de llamadas que se definen para su organización.

## <a name="tasks-you-can-perform"></a>Tareas que puede realizar

En la página **Estacionamiento de llamadas** puede realizar las siguientes tareas:

- Crear un intervalo de números

- Cambiar un intervalo de números existente

- Eliminar un intervalo de números

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los comandos de la página.

- **Nuevo** Inicia un nuevo intervalo numérico de estacionamiento de llamadas.

- **Editar** Se abre el intervalo numérico seleccionado para su edición, selecciona todos los intervalos numéricos de la lista o elimina el intervalo numérico seleccionado.

- **Actualizar** Actualiza la lista de intervalos de números.

En la siguiente lista se describen los campos de la página.

- **Nombre** El nombre único que identifica el intervalo de números.

- **Intervalo de inicio** El número inicial del rango.

- **Intervalo de finalización** El número final del rango.

- **Destino** El nombre de dominio completo (FQDN) el nombre o identificador de la aplicación que hospeda la aplicación de estacionamiento de llamadas para el intervalo de números de servicio.

Para obtener información detallada sobre las características de estacionamiento de llamadas y funciones, consulte [Plan de estacionamiento de llamadas en Skype para la empresa](../../../plan-your-deployment/enterprise-voice-solution/call-park.md). Para obtener información detallada sobre cómo trabajar con intervalos de números de estacionamiento de llamadas, vea [Configurar extensiones de número de teléfono para estacionar llamadas](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).


