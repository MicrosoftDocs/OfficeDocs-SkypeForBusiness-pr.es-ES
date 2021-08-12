---
title: Cola de grupos de respuesta Crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: Las colas de grupo de respuesta mantienen llamadas a un grupo de respuesta hasta que un agente responde a la llamada.
ms.openlocfilehash: 1754e2c3634bf2b37341e0b73608dd5aa23f5bc8b070bc9075fe1b583055ec67
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279258"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>Cola de grupos de respuesta: Crear nuevos o editar los existentes

Las colas de grupo de respuesta mantienen llamadas a un grupo de respuesta hasta que un agente responde a la llamada.

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Nombre** Cada cola debe tener un nombre. Escriba un nombre descriptivo para la cola.

- **Descripción** Este campo es opcional. Úselo para proporcionar detalles sobre la cola.

- **Grupos** Seleccione los grupos de agentes que desea asignar a la cola. Haga clic en **Seleccionar** para agregar grupos de agentes a la lista. Haga clic en **Quitar** para eliminar el grupo de agentes seleccionado de la lista.

    Las flechas arriba y abajo mueven un grupo de agentes seleccionado hacia arriba y hacia abajo en la lista. El orden de los grupos de agentes afecta al orden en que Skype Empresarial Server busca un agente disponible. Es decir, el primer grupo de la lista se busca primero para un agente disponible, seguido del segundo grupo, etc.

- **Habilitar el tiempo de espera de cola** Active esta casilla para especificar un período máximo de tiempo para que un autor de la llamada espere en espera antes de que un agente responda a la llamada. Si selecciona esta opción, debe especificar también lo siguiente:

  - **Período de tiempo de espera (segundos)** Seleccione o escriba el número máximo de segundos que un autor de la llamada puede esperar antes de que un agente responda a la llamada.

  - **Acción de llamada** Seleccione la acción que se produce cuando se produce un tiempo de espera de una llamada. Las opciones son:

  - **Desconectar**

  - **Reenviar al correo de voz** Si selecciona esta opción, en **dirección SIP,** escriba una dirección de correo de voz con el formato sip: <username> @ <domainname> (por ejemplo, sip:bob@contoso.com).

  - **Reenviar al número de teléfono** Si selecciona esta opción, en dirección **SIP** escriba el número de teléfono con el formato sip: <number> @ <domainname> (por ejemplo, sip:+14255550121@contoso.com).

  - **Reenviar a la dirección SIP** Seleccione esta opción para reenviar la llamada a otro usuario. En **dirección SIP,** escriba el URI del usuario con el formato sip: <username> @ <domainname> .

  - **Reenviar a otra cola** Si selecciona esta opción, vaya a la cola que va a recibir llamadas cuando las llamadas se alojen.

- **Habilitar desbordamiento de cola** Active esta casilla para especificar un número máximo de llamadas que la cola puede contener. Si selecciona esta opción, debe especificar también lo siguiente:

  - **Número máximo de llamadas** Seleccione o escriba el número máximo de llamadas que la cola puede contener.

  - **Reenviar la llamada** Seleccione qué llamada debe realizarse cuando se alcance el umbral de desbordamiento de cola.

  - **Acción de llamada** Seleccione la acción que se produce cuando se cumple el umbral de desbordamiento de cola. Sus opciones son:

  - **Desconectar**

  - **Reenviar al correo de voz** Si selecciona esta opción, en **dirección SIP,** escriba una dirección de correo de voz con el formato sip: <username> @ <domainname> (por ejemplo, sip:bob@contoso.com).

  - **Reenviar al número de teléfono** Si selecciona esta opción, en dirección **SIP** escriba el número de teléfono con el formato sip: <number> @ <domainname> (por ejemplo, sip:+14255550121@contoso.com).

  - **Reenviar a la dirección SIP** Seleccione esta opción para reenviar la llamada a otro usuario. En **dirección SIP,** escriba el URI del usuario con el formato sip: <username> @ <domainname> .

  - **Reenviar a otra cola** Si selecciona esta opción, vaya a la cola que va a recibir llamadas cuando se alcance el umbral de desbordamiento de cola.

Para obtener más información sobre las características y capacidades del grupo de respuesta, vea [Plan for the Response Group application in Skype Empresarial Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) en la documentación sobre planeación. Para obtener detalles sobre cómo trabajar con colas, vea [Managing Response Group Queues](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-queues) en la documentación de operaciones.