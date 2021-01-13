---
title: Cola de grupos de respuesta Crear nuevos o editar existentes
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
description: Las colas de grupo de respuesta mantienen las llamadas a un grupo de respuesta hasta que un agente responde a la llamada.
ms.openlocfilehash: 097c28db7f2ae52d7ab0b362e828c8f05e132481
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808200"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>Cola de grupos de respuesta: Crear nuevos o editar los existentes

Las colas de grupo de respuesta mantienen las llamadas a un grupo de respuesta hasta que un agente responde a la llamada.

## <a name="ui-reference"></a>Referencia de la interfaz de usuario

En la siguiente lista se describen los campos de la página.

- **Nombre** Cada cola debe tener un nombre. Escriba un nombre descriptivo para la cola.

- **Descripción** Este campo es opcional. Úselo para proporcionar detalles sobre la cola.

- **Grupos** Seleccione los grupos de agentes que desea asignar a la cola. Haga clic en **Seleccionar** para agregar grupos de agentes a la lista. Haga clic en **Quitar** para eliminar el grupo de agentes seleccionado de la lista.

    Las flechas arriba y abajo mueven un grupo de agentes seleccionado hacia arriba y hacia abajo en la lista. El orden de los grupos de agentes afecta al orden en que Skype Empresarial Server busca un agente disponible. Es decir, el primer grupo de la lista se busca primero para un agente disponible, seguido del segundo grupo, etc.

- **Habilitar el tiempo de espera de cola** Active esta casilla para especificar un período máximo de tiempo para que el autor de la llamada espere en espera antes de que un agente responda a la llamada. Si selecciona esta opción, debe especificar también lo siguiente:

  - **Período de tiempo de espera (segundos)** Seleccione o escriba el número máximo de segundos que el autor de la llamada puede esperar antes de que un agente responda a la llamada.

  - **Acción de llamada** Seleccione la acción que se produce cuando se ha desa cabo el tiempo de espera de una llamada. Las opciones son:

  - **Desconectar**

  - **Reenviar al correo de voz** Si selecciona esta opción, en dirección **SIP,** escriba una dirección de correo de voz con el formato sip: <username> @ <domainname> (por ejemplo, sip:bob@contoso.com).

  - **Reenviar al número de teléfono** Si selecciona esta opción, en la dirección **SIP** escriba el número de teléfono con el formato sip: <number> @ <domainname> (por ejemplo, sip:+14255550121@contoso.com).

  - **Reenviar a dirección SIP** Seleccione esta opción para reenviar la llamada a otro usuario. En **la dirección SIP,** escriba el URI del usuario con el formato sip: <username> @ <domainname> .

  - **Reenviar a otra cola** Si selecciona esta opción, vaya a la cola que va a recibir las llamadas cuando se haya pasado el tiempo de espera de las llamadas.

- **Habilitar desbordamiento de cola** Active esta casilla para especificar el número máximo de llamadas que puede contener la cola. Si selecciona esta opción, debe especificar también lo siguiente:

  - **Número máximo de llamadas** Seleccione o escriba el número máximo de llamadas que puede contener la cola.

  - **Reenviar la llamada** Seleccione qué llamada debe realizar una acción cuando se alcance el umbral de desbordamiento de cola.

  - **Acción de llamada** Seleccione la acción que se produce cuando se alcanza el umbral de desbordamiento de cola. Sus opciones son:

  - **Desconectar**

  - **Reenviar al correo de voz** Si selecciona esta opción, en dirección **SIP,** escriba una dirección de correo de voz con el formato sip: <username> @ <domainname> (por ejemplo, sip:bob@contoso.com).

  - **Reenviar al número de teléfono** Si selecciona esta opción, en la dirección **SIP** escriba el número de teléfono con el formato sip: <number> @ <domainname> (por ejemplo, sip:+14255550121@contoso.com).

  - **Reenviar a dirección SIP** Seleccione esta opción para reenviar la llamada a otro usuario. En **la dirección SIP,** escriba el URI del usuario con el formato sip: <username> @ <domainname> .

  - **Reenviar a otra cola** Si selecciona esta opción, vaya a la cola que va a recibir llamadas cuando se alcance el umbral de desbordamiento de cola.

Para obtener más información sobre las características y capacidades de Grupo de respuesta, consulte [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) en la documentación sobre planeación. Para obtener detalles sobre cómo trabajar con colas, vea [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) en la documentación de operaciones.


