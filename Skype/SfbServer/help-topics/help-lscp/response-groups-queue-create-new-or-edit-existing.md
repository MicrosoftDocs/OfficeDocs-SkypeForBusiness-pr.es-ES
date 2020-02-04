---
title: Cola de grupos de respuesta crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: Las colas de grupos de respuesta contienen llamadas a un grupo de respuesta hasta que un agente responde a la llamada.
ms.openlocfilehash: 4e290c47842ac58cec621629419281cbac63f206
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699795"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>Cola de grupos de respuesta: Crear nueva o editar existente

Las colas de grupos de respuesta contienen llamadas a un grupo de respuesta hasta que un agente responde a la llamada.

## <a name="ui-reference"></a>Referencia de interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Nombre** Cada cola debe tener un nombre. Escriba un nombre descriptivo para la cola.

- **Descripción** Este campo es opcional. Úselo para proporcionar detalles sobre la cola.

- **Grupos** Seleccione los grupos de agentes que desea asignar a la cola. Haga clic en **Seleccionar** para agregar grupos de agentes a la lista. Haga clic en **Quitar** para eliminar el grupo de agentes seleccionado de la lista.

    Las flechas arriba y abajo mueven un grupo de agentes seleccionado hacia arriba y hacia abajo en la lista. El orden de los grupos de agentes afecta al orden en el que Skype empresarial Server busca un agente disponible. Es decir, el primer grupo de la lista se busca primero en un agente disponible, seguido del segundo grupo y así sucesivamente.

- **Habilitar el tiempo de espera de la cola** Seleccione esta casilla para especificar un período máximo de tiempo para que la persona que llama espere en espera antes de que un agente responda a la llamada. Si selecciona esta opción, tendrá que especificar también lo siguiente:

  - **Período de tiempo de espera (segundos)** Selecciona o escribe el número máximo de segundos que una persona que llama puede esperar antes de que un agente responda a la llamada.

  - **Acción llamar** Seleccione la acción que se produce cuando se agota el tiempo de espera de una llamada. Las opciones son:

  - **Desconectar**

  - **Reenviar al correo de voz** Si selecciona esta opción, en **dirección SIP**, escriba una dirección de correo de voz en el formato SIP<username> @ <domainname> : (por ejemplo, SIP:Bob@contoso.com).

  - **Desviar al número de teléfono** Si selecciona esta opción, en **dirección SIP** , escriba el número de teléfono con el formato SIP<number> @ <domainname> : (por ejemplo, SIP:+14255550121@contoso.com).

  - **Desviar a dirección SIP** Seleccione esta opción para desviar la llamada a otro usuario. En **dirección SIP**, escriba el URI para el usuario con el formato SIP:<username>@<domainname>.

  - **Reenviar a otra cola** Si selecciona esta opción, vaya a la cola que recibirá las llamadas cuando se agote el tiempo de espera de las llamadas.

- **Habilitar desbordamiento de cola** Seleccione esta casilla para especificar un número máximo de llamadas que la cola puede contener. Si selecciona esta opción, tendrá que especificar también lo siguiente:

  - **Número máximo de llamadas** Seleccione o escriba el número máximo de llamadas que puede contener la cola.

  - **Desviar la llamada** Seleccione la llamada que debe tomarse cuando se cumpla el umbral de desbordamiento de la cola.

  - **Acción llamar** Seleccione la acción que se produce cuando se alcanza el umbral de desbordamiento de la cola. Las opciones son:

  - **Desconectar**

  - **Reenviar al correo de voz** Si selecciona esta opción, en **dirección SIP**, escriba una dirección de correo de voz en el formato SIP<username> @ <domainname> : (por ejemplo, SIP:Bob@contoso.com).

  - **Desviar al número de teléfono** Si selecciona esta opción, en **dirección SIP** , escriba el número de teléfono con el formato SIP<number> @ <domainname> : (por ejemplo, SIP:+14255550121@contoso.com).

  - **Desviar a dirección SIP** Seleccione esta opción para desviar la llamada a otro usuario. En **dirección SIP**, escriba el URI para el usuario con el formato SIP:<username>@<domainname>.

  - **Reenviar a otra cola** Si selecciona esta opción, vaya a la cola que va a recibir llamadas cuando se cumpla el umbral de desbordamiento de la cola.

Para obtener más información sobre las funciones y características de los grupos de respuesta, consulte [planear la aplicación de grupo de respuesta en Skype empresarial Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) en la documentación de planificación. Para más información sobre cómo trabajar con colas, mire [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) en la documentación de operaciones.


