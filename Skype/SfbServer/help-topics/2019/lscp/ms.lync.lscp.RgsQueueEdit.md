---
title: Cola de grupos de respuesta crear nuevos o editar los existentes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: Las colas de grupo de respuesta contienen las llamadas a un grupo de respuesta hasta que un agente atiende la llamada.
ms.openlocfilehash: 96d8bae5f4f3e818366872c4e81615a90fe24e86
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896976"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>Cola de grupos de respuesta: Crear nueva o editar existente

Las colas de grupo de respuesta contienen las llamadas a un grupo de respuesta hasta que un agente atiende la llamada.

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Nombre** Cada cola debe tener un nombre. Escriba un nombre descriptivo para la cola.

- **Descripción** Este campo es opcional. Úselo para proporcionar detalles sobre la cola.

- **Grupos** Seleccione los grupos de agentes que desea asignar a la cola. Haga clic en **Seleccionar** para agregar grupos de agentes a la lista. Haga clic en **Quitar** para eliminar el grupo de agentes seleccionado de la lista.

    Las flechas arriba y abajo mover un grupo de agentes seleccionado hacia arriba y hacia abajo en la lista. El orden de los grupos de agentes afecta al orden en el que Skype para Business Server busca un agente disponible. Es decir, el primer grupo de la lista se busca en primer lugar un agente disponible, seguido del segundo grupo y así sucesivamente.

- **Habilitar tiempo de espera de cola** Active esta casilla de verificación para especificar un período máximo de tiempo para un autor de la llamada que se debe esperar en espera antes de que un agente atiende la llamada. Si selecciona esta opción, tendrá que especificar también lo siguiente:

  - **Período de tiempo de espera (segundos)** Seleccione o escriba el número máximo de segundos que un autor de la llamada puede esperar antes de que un agente atiende la llamada.

  - **Acción de llamadas** Seleccione la acción que se produce cuando se agota el tiempo de espera de una llamada. Las opciones son:

  - **Desconectar**

  - **Desviar a correo de voz** Si selecciona esta opción, en la **dirección SIP**, escriba una dirección de correo de voz en el formato sip:<username> @ <domainname> (por ejemplo, sip:bob@contoso.com).

  - **Desviar a número de teléfono** Si selecciona esta opción, en la **dirección SIP** escriba el número de teléfono en el formato sip:<number> @ <domainname> (por ejemplo, sip:+14255550121@contoso.com).

  - **Desviar a dirección SIP** Seleccione esta opción para reenviar la llamada a otro usuario. En la **dirección SIP**, escriba el URI del usuario en el formato sip:<username>@<domainname>.

  - **Desviar a otra cola** Si selecciona esta opción, desplácese hasta la cola que va a recibir las llamadas cuando el tiempo de espera de las llamadas.

- **Habilitar desbordamiento de cola** Active esta casilla de verificación para especificar un número máximo de llamadas que puede contener la cola. Si selecciona esta opción, tendrá que especificar también lo siguiente:

  - **Número máximo de llamadas** Seleccione o escriba el número máximo de llamadas que puede contener la cola.

  - **Reenviar la llamada** Seleccione qué llamada se realizará la acción cuando se alcanza el umbral de desbordamiento de cola.

  - **Acción de llamadas** Seleccione la acción que se produce cuando se alcanza el umbral de desbordamiento de cola. Las opciones son:

  - **Desconectar**

  - **Desviar a correo de voz** Si selecciona esta opción, en la **dirección SIP**, escriba una dirección de correo de voz en el formato sip:<username> @ <domainname> (por ejemplo, sip:bob@contoso.com).

  - **Desviar a número de teléfono** Si selecciona esta opción, en la **dirección SIP** escriba el número de teléfono en el formato sip:<number> @ <domainname> (por ejemplo, sip:+14255550121@contoso.com).

  - **Desviar a dirección SIP** Seleccione esta opción para reenviar la llamada a otro usuario. En la **dirección SIP**, escriba el URI del usuario en el formato sip:<username>@<domainname>.

  - **Desviar a otra cola** Si selecciona esta opción, desplácese hasta la cola que va a recibir las llamadas cuando se alcanza el umbral de desbordamiento de cola.

Para obtener información detallada sobre las características de grupo de respuesta y funciones, consulte [Plan para la aplicación de grupo de respuesta en Skype para Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) en la documentación de planeación. Para más información sobre cómo trabajar con colas, mire [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) en la documentación de operaciones.


